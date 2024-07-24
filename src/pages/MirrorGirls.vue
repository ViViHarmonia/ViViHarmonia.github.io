<template>
  <div class="cardHolder flex-center q-pt-sm">
    <q-card class="cardMuse">
      <q-card-section>
        <div class="row flex-center text-subtitle2 text-center q-pa-sm">
          Characters I have/will roleplay, their characteristics, preferences,
          and such information, canon or personal.
        </div>
        <div class="row justify-center">
          <q-layout class="shadow-2 rounded-borders " view="hHh Lpr lff" container
            style="height: 500px; min-width: 300px;" v-if="$q.screen.lt.sm">
            <q-header class="scrollheader" elevated>
              <q-toolbar>
                <q-select v-model="museSect" :options="museSectLst" option-label="label" option-value="value"
                  input-debounce="0" dark outlined dense />
                <q-toggle v-model="nsfwSwitch" color="black" />
                <span v-show="nsfwSwitch">N</span>
                <span>SFW</span>
              </q-toolbar>
            </q-header>
            <q-scroll-area visible class="bg-grey-10 text-white rounded-borders"
              style="height: 500px; min-width: 300px;">
              <div class="museScrollArea q-pt-sm">
                <div class="row flex-center">
                  <q-btn v-for="(char, c) in finalCharArr" square padding="xs" flat
                    @click="museProfileOpen(char.sect, char.code, char.state, char.states)">
                    <q-avatar rounded size="60px">
                      <img :src="char.avatar">
                    </q-avatar>
                  </q-btn>
                </div>
              </div>
            </q-scroll-area>
            <q-footer elevated class="scrollheader">
              <q-toolbar>
                <q-btn class="buttonTable" @click="uniDialog = true" label="Universes" />
              </q-toolbar>
            </q-footer>
          </q-layout>
          <q-table row-key="name" :columns="museColumns" flat bordered dark class="my-sticky-header-table" hide-bottom
            virtual-scroll auto-width wrap-cells :rows-per-page-options="[0]" :rows="finalCharArr" v-else>
            <template v-slot:top>
              <q-select v-model="museSect" :options="museSectLst" option-label="label" option-value="value"
                input-debounce="0" dark outlined dense />
              <q-toggle v-model="nsfwSwitch" color="black" />
              <span v-show="nsfwSwitch">N</span>
              <span>SFW</span>
              <q-space />
              <q-btn class="buttonTable" @click="uniDialog = true" label="Universes" />
            </template>
            <template v-slot:body-cell-icon="props">
              <q-td :props="props">
                <q-avatar rounded class="iconMuseTable">
                  <img :src="props.row.avatar" />
                </q-avatar>
              </q-td>
            </template>
            <template v-slot:body-cell-universe="props">
              <q-td :props="props">
                <div>{{ auListDataBring(props.row.state).name }}</div>
              </q-td>
            </template>
            <template v-slot:body-cell-state="props">
              <q-td :props="props">
                <q-btn v-for="variant in props.row.states " circle flat padding="xs"
                  :disabled="props.row.state == auListDataBring(variant).au"
                  v-show="checkSFW(auListDataBring(variant).sfw)"
                  @click="props.row.state = auListDataBring(variant).au">
                  <q-avatar circle class="aubutton">
                    <img :src="auListDataBring(variant).emblem" />
                  </q-avatar>
                </q-btn>
              </q-td>
            </template>
            <template v-slot:body-cell-actions="props">
              <q-td :props="props">
                <q-btn class="buttonTable"
                  @click="museProfileOpen(props.row.sect, props.row.code, props.row.state, props.row.states)"
                  label="Desc." />
                <q-btn class="buttonTable" v-show="nsfwSwitch"
                  @click="museProfileOpen(props.row.sect, props.row.code, props.row.state, props.row.states); descKinkSwitch = true"
                  label="Kinks" />
              </q-td>
            </template>
          </q-table>
        </div>
      </q-card-section>
    </q-card>
  </div>
  <q-dialog v-model="museDialog" @keyup.left="museSwitch(1)" @keyup.right="museSwitch(2)" @keyup.down="slideKeyboard(2)"
    @keyup.up="slideKeyboard(1)" @keyup.x="museDialog = false">
    <q-card id="muse">
      <q-card-section class="q-pa-xs flex-center">
        <div class="row items-center q-pa-xs">
          <div class="col-md-5 col-xs-12">
            <div class="row justify-between items-center">
              <div class="col align-start">
                <div class="row items-center justify-start">
                  <q-toggle v-model="nsfwSwitch" color="black" v-show="nsfwSwitchSafe" />
                  <span v-show="nsfwSwitch">N</span>
                  <span>SFW</span>
                </div>
              </div>
              <div class="col align-end">
                <div class="row justify-end q-pr-md">
                  <q-avatar circle size="35px">
                    <img :src="discord(muse.MetaTupper)" />
                  </q-avatar>
                </div>
              </div>
            </div>
          </div>
          <div class="col-md-7 col-xs-12">
            <div class="row justify-between items-center">
              <div class="col align-start">
                <div class="row text-body2 items-center justify-start">
                  <span><b>Free Play: </b>{{ muse.FreePlay }}</span>
                </div>
              </div>
              <div class="col align-end">
                <div class="row justify-end items-center q-pr-sm">
                  <span v-show="descKinkSwitch && nsfwSwitch">Kinks</span>
                  <span v-show="!descKinkSwitch && nsfwSwitch">Bio</span>
                  <q-toggle v-model="descKinkSwitch" color="purple" v-show="nsfwSwitch" />
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="row q-px-sm flex-center">
          <div class="col-xs-12 col-md-5">
            <div class="row text-body2 justify-start">
              <div class="col-md-4 col-sm-2 col-xs-3"><b>Title:</b></div>
              <div class="col-md-8 col-sm-4 col-xs-9">
                {{ muse.Title }}<span class="secret">{{ muse.TitleSh }}</span>
              </div>
              <div class="col-md-4 col-sm-2 col-xs-3"><b>Name:</b></div>
              <div class="col-md-8 col-sm-4 col-xs-9">
                {{ muse.Name }}<span class="secret">{{ muse.NameSh }}</span>
              </div>
            </div>
            <div class="row text-body2 justify-start">
              <div class="col-md-4 col-sm-2 col-xs-3"><b>Species:</b></div>
              <div class="col-md-8 col-sm-4 col-xs-9">
                {{ muse.Spec }}<span class="secret">{{ muse.SpecSh }}</span>
              </div>
              <div class="col-md-4 col-sm-2 col-xs-3"><b>Region:</b></div>
              <div class="col-md-8 col-sm-4 col-xs-9">
                {{ muse.Reg }}<span class="secret">{{ muse.RegSh }}</span>
              </div>
            </div>
            <div class="row text-body2 justify-start" v-show="nsfwSwitch">
              <div class="col-xs-12"><b>Dom/Sub:</b></div>
              <div class="col-xs-12">
                {{ muse.SubDom }}<span class="secret">{{ muse.SubDomSh }}</span>
              </div>
            </div>
            <div class="row text-body2 justify-start items-center">
              <div class="col-xs-3"><b>Universes:</b></div>
              <div class="col-xs-12">
                <q-btn v-for="variant in muse.auArray " circle flat padding="xs"
                  :disabled="currentAU == auListDataBring(variant).au" v-show="checkSFW(auListDataBring(variant).sfw)"
                  @click="museProfileOpen(currentAreaCode, currentMuseCode, auListDataBring(variant).au, currentmuseAULst)">
                  <q-avatar circle size="40px">
                    <img :src="auListDataBring(variant).emblem" />
                  </q-avatar>
                </q-btn>
              </div>
            </div>
            <div class="row text-body2 justify-start">
              <div class="col-md-4 col-sm-2 col-xs-3"><b>Current U.:</b></div>
              <div class="col-md-8 col-sm-auto col-xs-9">
                <span>{{ auListDataBring(currentAU).name }}</span>
              </div>
            </div>
          </div>
          <div class="col-xs-12 col-md-7">
            <div class="row text-body2 justify-start">
              <div class="col-xs-12" v-show="!descKinkSwitch">
                <div class="row text-body2 justify-start">
                  <div class="col" v-show="muse.Desc != 'NSFW ONLY - '">
                    {{ muse.Desc }}<span class="secret" v-show="nsfwSwitch">{{ muse.DescLewd
                      }}</span>
                  </div>
                  <div class="col" v-show="muse.Desc == 'NSFW ONLY - '">
                    {{ muse.DescLewd }}
                  </div>
                </div>
              </div>
              <div class="col-xs-12" v-show="descKinkSwitch">
                <div class="row text-body2 justify-start" v-for="(category, c) in muse.kinks">
                  <div class="col-xs-4"><b>{{ kinklistlbl[c] }}</b></div>
                  <div class="col-xs-8">{{ category }}</div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="row justify-center">
          <div class="col-xs-auto q-pa-sm">
            <div class="row flex-center">
              <q-btn class="button" flat @click="museSwitch(1)">
                <q-icon left size="1rem" name="arrow_back" />
                <div>Prev</div>
              </q-btn>
            </div>
          </div>
          <div class="col-xs-auto q-pa-sm">
            <div class="row flex-center">
              <q-btn class="button" flat @click="museDialog = false">
                <q-icon left size="1rem" name="close" />
                <div>Close</div>
              </q-btn>
            </div>
          </div>
          <div class="col-xs-auto q-pa-sm">
            <div class="row flex-center">
              <q-btn class="button" flat @click="museSwitch(2)">
                <q-icon left size="1rem" name="arrow_forward" />
                <div>Next</div>
              </q-btn>
            </div>
          </div>
        </div>
      </q-card-section>
    </q-card>
  </q-dialog>
  <q-dialog v-model="uniDialog" @keyup.x="uniDialog = false; uniState = ''">
    <q-card class="au" style="width: var(--uniDlgCardWdth)">
      <q-card-section class="q-pa-xs flex-center">
        <div class="row justify-between items-center q-pl-none q-pr-sm">
          <div class="col align-start">
            <div class="row justify-start items-center">
              <q-toggle v-model="nsfwSwitch" color="black" />
              <span v-show="nsfwSwitch">N</span>
              <span>SFW</span>
            </div>
          </div>
          <div class="col align-end">
            <div class="row justify-end items-center">
              <q-btn class="button" size="10px" dense flat @click="uniDialog = false; uniState = ''">
                <q-icon size="1rem" name="close" />
              </q-btn>
            </div>
          </div>
        </div>
        <div class="row text-body2 text-center items-center justify-center q-pt-sm">
          Various Alternate Universes of characters, and their stories.
        </div>
        <div class="row flex-center q-pa-sm">
          <q-btn circle padding="xs" flat @click="universeShow(verse); uniState = verse" v-for="verse in museAUcardLst"
            v-show="checkSFW(auListDataBring(verse).sfw)" :disabled="verse == uniState">
            <q-avatar circle size="40px">
              <img :src="auListDataBring(verse).emblem">
            </q-avatar>
          </q-btn>
        </div>
        <div class="row text-subtitle2 q-pa-sm justify-center" v-if="uniDlgInfo == true"> {{ universes.title }}</div>
        <div class="row text-body2 q-pa-sm justify-start" v-if="uniDlgInfo == true"> {{ universes.description }}
        </div>
        <div class="row text-body2 q-px-sm justify-start" v-if="uniDlgInfo == true">
          <b>Muses Involved:</b>
        </div>
        <div class="row q-px-sm q-pb-sm justify-center" v-if="uniDlgInfo == true">
          <div class="row">
            <q-layout class="shadow-2 rounded-borders "
              :class="{ uniMusesHier: hierarchyUni == false, uniMusesNoHier: hierarchyUni == true }"
              :style="`width: ${bringWidth()}; max-width: 540px`" container>
              <q-scroll-area visible class="bg-purple-11 text-white rounded-borders"
                :class="{ uniMusesHier: hierarchyUni == false, uniMusesNoHier: hierarchyUni == true }"
                :style="`width: ${bringWidth()}; max-width: 540px`">
                <div class="row">
                  <div class="col align-center">
                    <div class="q-px-sm" v-if="hierarchyUni == false">
                      <div class="row justify-center q-pt-sm">
                        <div class="col-sm-2 col-xs-3" v-for="(chr, c) in charArrAu">
                          <div class="row justify-center">
                            <q-btn square padding="xs" flat
                              @click="museProfileOpen(chr.sect, chr.code, chr.state, chr.states)">
                              <q-avatar rounded class="iconMuseTable">
                                <img :src="chr.avatar">
                              </q-avatar>
                            </q-btn>
                          </div>
                          <div class="row justify-center" v-if="groupPos != ''"> {{ chr.groupPos }}</div>
                        </div>
                      </div>
                    </div>
                    <div class="q-px-sm" v-else>
                      <div class="row q-px-sm q-py-xs" v-for="position in universes.museDivs">
                        <div class="col">
                          <div class="row justify-center">
                            {{ position }}
                          </div>
                          <div class="row flex-center">
                            <div class="col-auto" v-for="(chr, c) in charArrAu">
                              <q-btn square padding="xs" flat v-if="chr.groupPos == position"
                                @click="museProfileOpen(chr.sect, chr.code, chr.state, chr.states)">
                                <q-avatar rounded class="iconMuseTable">
                                  <img :src="chr.avatar">
                                </q-avatar>
                              </q-btn>
                            </div>
                          </div>
                        </div>
                      </div>
                    </div>
                  </div>
                </div>
              </q-scroll-area>
            </q-layout>
          </div>
        </div>
      </q-card-section>
    </q-card>
  </q-dialog>
</template>
<script>
import { defineComponent } from "vue";
import { useQuasar } from 'quasar'

export default defineComponent({
  //cuando haces click en boton de AU, ventana pierde focus hasta que hagas click de nuevo
  name: "MirrorGirls",
  data: () => ({
    museSect: { label: "All", value: 0 },
    museDialog: false,
    uniDialog: false,
    uniDlgCardWdth: "700px",
    uniDlgInfo: false,
    uniState: "",
    nsfwSwitch: false,
    nsfwSwitchSafe: true,
    descKinkSwitch: false,
    currentMuseCode: "",
    currentAreaCode: 0,
    currentAU: "",
    currentmuseAULst: [],
    hierarchyUni: false,
    museColumns: [
      { name: "icon", label: "", align: "start", field: "avatar" },
      {
        name: "character",
        label: "Character",
        align: "center",
        field: "name",
      },
      { name: "free", label: "Free", align: "center", field: "free" },
      { name: "universe", label: "Current Uni.", align: "center", field: "uni" },
      { name: "state", label: "Universes", align: "center", field: "" },
      { name: "actions", label: "", align: "end", field: "" },
    ],
    kinklistlbl: {
      partner: "Partner:",
      organ: "Assets:",
      clothing: "Clothing:",
      relation: "Relation:",
      consent: "Consent:",
      substance: "Substance:",
      treatment: "Treatment:",
      bondage: "Bondage:",
      mindMod: "Mind Mod.:",
      bodyMod: "Body Mod.:",
      transform: "Transform:",
    },
    museSectLst: [
      { label: "All", value: 0 },
      { label: "Pokémon", value: 1 },
      { label: "Hoyo", value: 2 },
      { label: "MHA", value: 3 },
      { label: "Games", value: 4 },
      { label: "Series", value: 5 },
    ],
    museAUcardLst: ["rocket", "rainbow", "shy", "lust", "mirror", "ua"],
    museAULst: [
      //{ au: "base", emblem: "/versions/mirror.jpg", sfw: "Y", name: "Source" },
      //{ au: "baseN", emblem: "/versions/mirror.jpg", sfw: "N", name: "Source (Lewd)" },
      { au: "pokemon", emblem: "/versions/Poké_Ball_icon.svg.png", sfw: "Y", name: "Pokémon" },
      { au: "rocket", emblem: "/versions/hypnorocket.png", sfw: "N", name: "Team (Hypno) Rocket" },
      { au: "rainbow", emblem: "/versions/Team_Rainbow_Rocket_logo_USUL.png", sfw: "N", name: "Team Rainbow Rocket" },
      { au: "galaxy", emblem: "/versions/galactic.jpg", sfw: "N", name: "Team Galactic" },
      { au: "plasma", emblem: "/versions/Team_Plasma.png", sfw: "N", name: "Team Plasma" },
      { au: "flare", emblem: "/versions/team_flare_by_biochao.png", sfw: "N", name: "Team Flare" },
      { au: "aether", emblem: "/versions/aether.png", sfw: "N", name: "Ultra Beast" },
      { au: "genshin", emblem: "/versions/paimon.png", sfw: "Y", name: "Genshin Impact" },
      { au: "mirror", emblem: "/versions/Mirror_Maiden_Icon.png", sfw: "N", name: "New Mirror Maidens" },
      { au: "ua", emblem: "/versions/uagirls.png", sfw: "Y", name: "UA Heroine University" },
      { au: "samus", emblem: "/versions/samus.png", sfw: "Y", name: "Metroid" },
      { au: "mario", emblem: "/versions/Mario_emblem.svg.png", sfw: "Y", name: "Super Mario" },
      { au: "shy", emblem: "/versions/shy.png", sfw: "N", name: "Shy Gal" },
      { au: "bow", emblem: "/versions/bow.jpg", sfw: "N", name: "Koopa Slave" },
      { au: "shadow", emblem: "/versions/PMTTYD_Staff_Credits_45.png", sfw: "Y", name: "Shadow Fusion" },
      { au: "zelda", emblem: "/versions/triforce-logo.png", sfw: "Y", name: "The Legend of Zelda" },
      { au: "aoc", emblem: "/versions/HWAoC_Purah_Icon.png", sfw: "Y", name: "Pre-Calamity" },
      { au: "yiga", emblem: "/versions/Yiga_Eye.png", sfw: "N", name: "Yiga" },
      { au: "emblem", emblem: "/versions/falchion.png", sfw: "Y", name: "Fire Emblem" },
      { au: "helltaker", emblem: "/versions/helltaker.png", sfw: "Y", name: "Helltaker" },
      { au: "persona", emblem: "/versions/pt.jpg", sfw: "Y", name: "Persona 5" },
      { au: "lust", emblem: "/versions/annemblem.jpg", sfw: "N", name: "Phantom Thieves of Lust" },
      { au: "ddlc", emblem: "/versions/Ddlc_logo.png", sfw: "Y", name: "Doki Doki Literature Club" },
      { au: "dangan", emblem: "/versions/dr.jpg", sfw: "Y", name: "DanganRonpa" },
      { au: "danganR", emblem: "/versions/dr.jpg", sfw: "N", name: "DanganRonpa" },
      { au: "shantae", emblem: "/versions/shantaesmash.png", sfw: "Y", name: "Shantae" },
      { au: "fate", emblem: "/versions/chaldea.png", sfw: "Y", name: "Fate" },
      { au: "mmx", emblem: "/versions/Maverick_Hunter_Mark.png", sfw: "Y", name: "Mega Man X" },
      { au: "gear", emblem: "/versions/ggstrive.png", sfw: "Y", name: "Guilty Gear" },
      { au: "dressup", emblem: "/versions/marin.jpg", sfw: "Y", name: "Dress-Up Darling" },
      { au: "cyberpunk", emblem: "/versions/edgerunner.jpg", sfw: "Y", name: "Cyberpunk Edgerunners" },
      { au: "spyxfam", emblem: "/versions/spyxfam.png", sfw: "Y", name: "Spy X Family" },
      { au: "p&swg", emblem: "/versions/p&swg.png", sfw: "Y", name: "Panty & Stocking w/Garterbelt" },
      { au: "frieren", emblem: "/versions/frierendemonkillspell.png", sfw: "Y", name: "Sousou no Frieren" },
      { au: "mimic", emblem: "/versions/mimic.png", sfw: "N", name: "Mimic" },
      { au: "bocchi", emblem: "/versions/kessokuband.png", sfw: "Y", name: "Bocchi the Rock" },
      { au: "iltv", emblem: "/versions/reilaire.png", sfw: "Y", name: "In Love With the Villainess" },
      { au: "baiser", emblem: "/versions/shinyrod.png", sfw: "N", name: "Gushing Over Magical Girls" },
      { au: "lwa", emblem: "/versions/enormetastar.png", sfw: "Y", name: "Little Witch Academia" },
    ],
    universes: {
      title: "",
      description: "",
      muses: [],
      museDivs: [],
    },
    charArrAu: [],
    allCharArr: [
      {
        code: "rosa",
        sect: 1,
        name: "Rosa",
        state: "pokemon",
        free: "YES",
        states: ["pokemon", "rocket", "plasma", "ua"],
        avatar: "/museicon/rosa.jpg",
      },
      {
        code: "nem",
        sect: 1,
        name: "Nemona",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket"],
        avatar: "/museicon/nemona.png",
      },
      {
        code: "marn",
        sect: 1,
        name: "Marnie",
        state: "pokemon",
        free: "YES",
        states: ["pokemon", "rocket"],
        avatar: "/museicon/marnie.jpg",
      },
      {
        code: "ida",
        sect: 1,
        name: "Irida",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket", "galaxy"],
        avatar: "/museicon/irida.jpg",
      },
      {
        code: "iris",
        sect: 1,
        name: "Iris",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket", "plasma"],
        avatar: "/museicon/iris.jpeg",
      },
      {
        code: "sere",
        sect: 1,
        name: "Serena",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket", "flare"],
        avatar: "/museicon/serena.png",
      },
      {
        code: "brina",
        sect: 1,
        name: "Sabrina",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket"],
        avatar: "/museicon/sabrina.jpg",
      },
      {
        code: "cyn",
        sect: 1,
        name: "Cynthia",
        state: "pokemon",
        free: "YES",
        states: ["pokemon", "rocket", "galaxy"],
        avatar: "/museicon/cyn.jpg",
      },
      {
        code: "nesa",
        sect: 1,
        name: "Nessa",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket"],
        avatar: "/museicon/nesa.png",
      },
      {
        code: "jess",
        sect: 1,
        name: "Jessie",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket"],
        avatar: "/museicon/jessie.jpg",
      },
      {
        code: "ele",
        sect: 1,
        name: "Elesa",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket", "plasma"],
        avatar: "/museicon/ele.gif",
      },
      {
        code: "lusa",
        sect: 1,
        name: "Lusamine",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket", "aether"],
        avatar: "/museicon/lusa.jpg",
      },
      {
        code: "clair",
        sect: 1,
        name: "Clair",
        state: "pokemon",
        free: "NO",
        states: ["pokemon"],
        avatar: "/museicon/clair.jpg",
      },
      {
        code: "garde",
        sect: 1,
        name: "Gardenia",
        state: "pokemon",
        free: "NO",
        states: ["pokemon", "rocket", "galaxy"],
        avatar: "/museicon/gardenia.jpg",
      },
      {
        code: "mars",
        sect: 1,
        name: "Mars",
        state: "galaxy",
        free: "NO",
        states: ["galaxy"],
        avatar: "/museicon/mars.png",
      },
      {
        code: "ggrunt",
        sect: 1,
        name: "Team Galactic Grunt (♀)",
        state: "galaxy",
        free: "NO",
        states: ["galaxy"],
        avatar: "/museicon/galacticgrunt.png",
      },
      {
        code: "lumi",
        sect: 2,
        name: "Lumine",
        state: "genshin",
        free: "NO",
        states: ["genshin", "mirror"],
        avatar: "/museicon/lumi.jpeg",
      },
      {
        code: "lisa",
        sect: 2,
        name: "Lisa Minci",
        state: "genshin",
        free: "NO",
        states: ["genshin", "mirror"],
        avatar: "/museicon/lisa.jpg",
      },
      {
        code: "saria",
        sect: 2,
        name: "Rosaria",
        state: "genshin",
        free: "NO",
        states: ["genshin", "mirror"],
        avatar: "/museicon/rosaria.jpg",
      },
      {
        code: "yelan",
        sect: 2,
        name: "Yelan",
        state: "genshin",
        free: "NO",
        states: ["genshin", "mirror"],
        avatar: "/museicon/yelan.jpeg",
      },
      {
        code: "mira",
        sect: 2,
        name: "Mirror Maidens",
        state: "mirror",
        free: "NO",
        states: ["mirror"],
        avatar: "/museicon/mirror.jpeg",
      },
      {
        code: "mei",
        sect: 3,
        name: "Mei Hatsume",
        state: "ua",
        free: "YES",
        states: ["ua"],
        avatar: "/museicon/mei.jpeg",
      },
      {
        code: "tsu",
        sect: 3,
        name: "Tsuyu Asui",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/tsuyu.jpeg",
      },
      {
        code: "mina",
        sect: 3,
        name: "Mina Ashido",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/mina.jpeg",
      },
      {
        code: "momo",
        sect: 3,
        name: "Momo Yaoyorozu",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/momo.jpeg",
      },
      //{ code: "toru", sect: 3, name:"Tooru Hagakure",state: "ua", free: "NO", states:[ "ua" ], avatar: "/museicon/tooru.jpeg", }, DORMANT
      {
        code: "kendo",
        sect: 3,
        name: "Itsuka Kendo",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/kendo.jpeg",
      },
      {
        code: "kino",
        sect: 3,
        name: "Kinoko Komori",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/kinoko.png",
      },
      {
        code: "mel",
        sect: 3,
        name: "Melissa Shield",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/melissa.jpeg",
      },
      {
        code: "camie",
        sect: 3,
        name: "Camie Utsushimi",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/camie.jpeg",
      },
      {
        code: "joke",
        sect: 3,
        name: "Emi Fukukado",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/msjoke.jpeg",
      },
      {
        code: "rumi",
        sect: 3,
        name: "Rumi Usagiyama",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/miruko.jpeg",
      },
      {
        code: "yama",
        sect: 3,
        name: "Yu Takeyama",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/mtlady.jpeg",
      },
      {
        code: "nana",
        sect: 3,
        name: "Nana Shimura",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/nana.jpeg",
      },
      {
        code: "kai",
        sect: 3,
        name: "Kaina Tsutsumi",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/nagant.jpeg",
      },
      {
        code: "fumi",
        sect: 3,
        name: "Fuyumi Todoroki",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/fuyumi.jpeg",
      },
      {
        code: "inko",
        sect: 3,
        name: "Inko Midoriya",
        state: "ua",
        free: "NO",
        states: ["ua"],
        avatar: "/museicon/inko.png",
      },
      {
        code: "sam",
        sect: 4,
        name: "Samus Aran",
        state: "samus",
        free: "YES",
        states: ["samus", "shy"],
        avatar: "/museicon/samus.jpg",
      },
      {
        code: "bow",
        sect: 4,
        name: "Bowsette Koopa",
        state: "mario",
        free: "YES",
        states: ["mario", "shy"],
        avatar: "/museicon/bowsette.jpg",
      },
      {
        code: "pich",
        sect: 4,
        name: "Peach Toadstool",
        state: "mario",
        free: "NO",
        states: ["mario", "shy", "bow", "shadow"],
        avatar: "/museicon/peach.jpg",
      },
      {
        code: "lina",
        sect: 4,
        name: "Rosalina",
        state: "mario",
        free: "NO",
        states: ["mario", "shy", "bow"],
        avatar: "/museicon/rosalina.jpg",
      },
      {
        code: "lin",
        sect: 4,
        name: "Linkle",
        state: "zelda",
        free: "YES",
        states: ["zelda"],
        avatar: "/museicon/linkle.jpeg",
      },
      {
        code: "pura",
        sect: 4,
        name: "Purah",
        state: "zelda",
        free: "YES",
        states: ["zelda", "aoc", "yiga"],
        avatar: "/museicon/purah.jpeg",
      },
      {
        code: "edel",
        sect: 4,
        name: "Edelgard von Hresvelg",
        state: "emblem",
        free: "NO",
        states: ["emblem"],
        avatar: "/museicon/edelgard.jpg",
      },
      {
        code: "luci",
        sect: 4,
        name: "Lucifer Morningstar",
        state: "helltaker",
        free: "YES",
        states: ["helltaker"],
        avatar: "/museicon/lucifer.jpg",
      },
      {
        code: "azaz",
        sect: 4,
        name: "Azazel",
        state: "helltaker",
        free: "NO",
        states: ["helltaker"],
        avatar: "/museicon/azazel.jpg",
      },
      {
        code: "tae",
        sect: 4,
        name: "Tae Takemi",
        state: "persona",
        free: "YES",
        states: ["persona", "lust"],
        avatar: "/museicon/tae.png",
      },
      {
        code: "ann",
        sect: 4,
        name: "Ann Takamaki",
        state: "persona",
        free: "NO",
        states: ["persona", "lust"],
        avatar: "/museicon/ann.png",
      },
      {
        code: "sae",
        sect: 4,
        name: "Sae Nijima",
        state: "persona",
        free: "NO",
        states: ["persona", "lust"],
        avatar: "/museicon/sae1.jpeg",
      },
      //{ code: "roty", sect: 4, name:"",state: "shantae", free: "NO", states:[ "shantae" ], avatar: "/museicon/rotty.png", }, DORMANT
      {
        code: "moni",
        sect: 4,
        name: "Monika",
        state: "ddlc",
        free: "YES",
        states: ["ddlc"],
        avatar: "/museicon/monika.png",
      },
      {
        code: "junko",
        sect: 4,
        name: "Junko Enoshima",
        state: "danganR",
        free: "YES",
        states: ["danganR"],
        avatar: "/museicon/junko.jpg",
      },
      {
        code: "nami",
        sect: 4,
        name: "Chiaki Nanami",
        state: "dangan",
        free: "YES",
        states: ["dangan"],
        avatar: "/museicon/chiaki.jpg",
      },
      {
        code: "mikan",
        sect: 4,
        name: "Mikan Tsumiki",
        state: "dangan",
        free: "NO",
        states: ["dangan"],
        avatar: "/museicon/mikan.jpg",
      },
      {
        code: "shan",
        sect: 4,
        name: "Shantae",
        state: "shantae",
        free: "NO",
        states: ["shantae"],
        avatar: "/museicon/shantae.jpeg",
      },
      {
        code: "ruler",
        sect: 4,
        name: "Artoria Pendragon",
        state: "fate",
        free: "NO",
        states: ["fate"],
        avatar: "/museicon/ruler.jpeg",
      },
      {
        code: "ridem",
        sect: 4,
        name: "Medusa",
        state: "fate",
        free: "NO",
        states: ["fate"],
        avatar: "/museicon/riderM.jpg",
      },
      {
        code: "layer",
        sect: 4,
        name: "Layer",
        state: "mmx",
        free: "YES",
        states: ["mmx"],
        avatar: "/museicon/layer.jpeg",
      },
      {
        code: "brdgt",
        sect: 4,
        name: "Bridget ",
        state: "gear",
        free: "YES",
        states: ["gear"],
        avatar: "/museicon/bridge.png",
      },
      {
        code: "marin",
        sect: 5,
        name: "Marin Kitagawa",
        state: "dressup",
        free: "YES",
        states: ["dressup"],
        avatar: "/museicon/marin.jpg",
      },
      {
        code: "lucy",
        sect: 5,
        name: "Lucynda Kushinada",
        state: "cyberpunk",
        free: "NO",
        states: ["cyberpunk"],
        avatar: "/museicon/lucynda.png",
      },
      {
        code: "yor",
        sect: 5,
        name: "Yor Forger neé Briar",
        state: "spyxfam",
        free: "YES",
        states: ["spyxfam"],
        avatar: "/museicon/yor.png",
      },
      {
        code: "stock",
        sect: 5,
        name: "Stocking",
        state: "p&swg",
        free: "YES",
        states: ["p&swg"],
        avatar: "/museicon/stock.jpg",
      },
      {
        code: "frie",
        sect: 5,
        name: "Frieren",
        state: "frieren",
        free: "NO",
        states: ["frieren", "mimic"],
        avatar: "/museicon/frie.jpg",
      },
      {
        code: "fern",
        sect: 5,
        name: "Fern",
        state: "frieren",
        free: "NO",
        states: ["frieren"],
        avatar: "/museicon/fern.jpg",
      },
      {
        code: "paru",
        sect: 5,
        name: "PA-san",
        state: "bocchi",
        free: "YES",
        states: ["bocchi"],
        avatar: "/museicon/paru.jpg",
      },
      {
        code: "clare",
        sect: 5,
        name: "Claire François",
        state: "iltv",
        free: "YES",
        states: ["iltv"],
        avatar: "/museicon/claire.jpg",
      },
      {
        code: "utena",
        sect: 5,
        name: "Utena Hiiragi",
        state: "baiser",
        free: "YES",
        states: ["baiser"],
        avatar: "/museicon/utena.jpg",
      },
      {
        code: "ursa",
        sect: 5,
        name: "Ursula Callistis",
        state: "lwa",
        free: "YES",
        states: ["lwa"],
        avatar: "/museicon/ursula.jpg",
      },
      //{ code: "beni", sect: 5, name:"",state: "", free: "NO", states:[ "" ], avatar: "/museicon/kobeni.jpeg", }, DORMANT
    ],
    finalCharArr: [],
    muse: {
      Name: "",
      NameSh: "",
      SubDom: "",
      SubDomSh: "",
      Title: "",
      TitleSh: "",
      Spec: "",
      SpecSh: "",
      Reg: "",
      RegSh: "",
      Desc: "",
      DescLewd: "",
      MetaTupper: "",
      FreePlay: "",
      auArray: [],
      kinks: {
        partner: "",
        organ: "",
        clothing: "",
        relation: "",
        consent: "",
        substance: "",
        treatment: "",
        bondage: "",
        mindMod: "",
        bodyMod: "",
        transform: "",
      },
    },
  }),
  watch: {
    museDialog(value) {
      if (value == false) {
        this.descKinkSwitch = false;
      }
    },
    uniDialog(value) {
      if (value == false) {
        this.uniState = ""
        this.universes.title = ""
        this.universes.description = ""
        this.universes.muses = []
        this.universes.museDivs = []
        this.charArrAu = []
        this.uniDlgInfo = false
        for (var i = 0; i < this.finalCharArr.length; i++) {
          this.finalCharArr[i].state = this.finalCharArr[i].states[0]
        }
      }
    },
    museSect() {
      this.dataFill();
    },
    nsfwSwitch(value) {
      let tempCharStateSFW = ""
      let dlgMuseTempCSSFW = ""
      let dlgUniTempCSSFW = ""
      this.dataFill()
      if (value == false) {
        this.descKinkSwitch = false;
        for (var i = 0; i < this.finalCharArr.length; i++) {
          tempCharStateSFW = this.auListDataBring(this.finalCharArr[i].state).sfw
          if (tempCharStateSFW == "N") {
            this.finalCharArr[i].state = this.finalCharArr[i].states[0]
          }
        }
        if (this.museDialog == true) {
          dlgMuseTempCSSFW = this.auListDataBring(this.currentAU).sfw
          if (dlgMuseTempCSSFW = "N") {
            this.currentAU = this.currentmuseAULst[0]
            this.museProfileOpen(this.currentAreaCode, this.currentMuseCode, this.currentAU, this.currentmuseAULst)
          }
        }
        if (this.uniDialog == true) {
          dlgUniTempCSSFW = this.auListDataBring(this.uniState).sfw
          if (dlgUniTempCSSFW = "N") {
            this.uniState = "ua"
            this.universeShow(this.uniState)
          }
        }
      }
    }
  },
  methods: {
    bringWidth() {
      const $q = useQuasar()
      var uniMusesCardWdth = ""
      uniMusesCardWdth = ($q.screen.width * .8) + "px"
      return uniMusesCardWdth
    },
    auListDataBring(au) {
      for (var i = 0; i < this.museAULst.length; i++) {
        if (this.museAULst[i].au == au) {
          return this.museAULst[i]
        }
      }
    },
    universeShow(value) {
      this.universes.title = ""
      this.universes.description = ""
      this.universes.muses = []
      this.universes.museDivs = []
      this.charArrAu = []
      switch (value) {
        case 'rocket':
          this.universes.title = this.museAULst[1].name;
          this.universes.description = "A girls-only rebrand of Team Rocket, brought about by a takeover Dawn, focused on acquisition and training of Pokemon trainers, leaders, champions, etc. Takes a more hypnotic, sexual approach to both.";
          this.universes.muses = [["jess"], ["brina"], ["nesa", "nem"], ["cyn", "lusa", "garde"], ["rosa", "sere", "ele"], ["ida", "iris", "marn"]]
          this.universes.museDivs = ["Leader", "Commander", "Coordinator", "Scientist", "Agent", "Grunt"]
          this.hierarchyUni = true
          break
        case 'rainbow':
          this.universes.title = this.museAULst[2].name;
          this.universes.description = "An organization made of all villainous teams in the Pokemon Universe, here displaying girls not part of Team Rocket in their universe. Including those that in another time and place stood against said teams, made to join, willingly or not."
          this.universes.muses = [["mars", "cyn", "garde", "ggrunt"], ["ele", "rosa", "iris"], ["sere"], ["lusa"]]
          this.universes.museDivs = ["Galactic", "Plasma", "Flare", "Aether"]
          this.hierarchyUni = true
          break
        case 'shy':
          this.universes.title = this.museAULst[12].name + " Group";
          this.universes.description = "A group of volunteer girls wearing the same mask, and similar outfits, making no noise but for light grunts and moans, watching from the dark depths of the mask's eyes. No official comment on the notion the masks mess with the mind and self.";
          this.universes.muses = [["pich"], ["lina"], ["bow"], ["sam"]]
          this.universes.museDivs = ["Pink", "Cyan", "Yellow", "Blue"]
          this.hierarchyUni = false
          break
        case 'lust':
          this.universes.title = this.museAULst[21].name;
          this.universes.description = "A girls-only variant of the Phantom Thieves and allies that failed to pursue justice and fell victims to others' lustful cognitions of them, or their own twisted but arousing desires. Now they aim to make Tokyo as filthy as they've become.";
          this.universes.muses = [["sae"], ["ann"], ["tae"]]
          this.universes.museDivs = ["Chief", "Founder", "Medic"]
          this.hierarchyUni = false
          break
        case 'mirror':
          this.universes.title = this.museAULst[8].name;
          this.universes.description = "A group of assimilated illusionist women who work out of Teyvat, formerly allied with the Fatui. After La Signora's bare survival and escape of her execution, they remain loyal to her first, Fatui second. ";
          this.universes.muses = [["mira"], ["lumi", "lisa", "saria", "yelan"]]
          this.universes.museDivs = ["Reflection", "Sister"]
          this.hierarchyUni = true
          break
        case 'ua':
          this.universes.title = this.museAULst[9].name;
          this.universes.description = "A girls-only college ran by Headmistress Midnight to teach all the trades of being a hero...though it often ends with rather horny heroines, and unlocked sapphic tendencies.";
          this.universes.muses = [["fumi", "inko", "yama", "rumi", "joke"], ["momo", "mina", "tsu", "kendo", "kino", "camie", "mei", "mel"], ["kai", "nana"]]
          this.universes.museDivs = ["Staff", "Student", "Guest"]
          this.hierarchyUni = true
          break
      }
      var tempAU = value != 'rainbow' ? value : ["galaxy", "plasma", "flare", "aether"];
      var tempObjMuse;
      for (var i = 0; i < this.universes.muses.length; i++) {
        for (var k = 0; k < this.universes.muses[i].length; k++) {
          for (var j = 0; j < this.allCharArr.length; j++) {
            if (this.allCharArr[j].code == this.universes.muses[i][k]) {
              tempObjMuse = {}
              tempObjMuse = this.allCharArr[j]
              tempObjMuse.groupPos = this.universes.museDivs[i]
              tempObjMuse.state = value != 'rainbow' ? tempAU : tempAU[i];
              this.charArrAu.push(tempObjMuse)
            }
          }
        }
      }
      this.uniDlgInfo = true
    },
    discord(value) {
      var imgurl = ""
      if (value == "YES") {
        imgurl = "/icons/discord-logo.png"
      } else {
        imgurl = "/icons/discord-logoNO.png"
      }
      return imgurl
    },
    dataFill() {
      this.finalCharArr = [];
      var tempNSFWchk = "";
      if (this.museSect.value == 0) {
        if (this.nsfwSwitch == false) {
          for (var i = 0; i < this.allCharArr.length; i++) {
            for (var j = 0; j < this.museAULst.length; j++) {
              if (this.museAULst[j].au == this.allCharArr[i].states[0]) {
                tempNSFWchk = this.museAULst[j].sfw
              }
            }
            if (tempNSFWchk == "Y") {
              this.finalCharArr.push(this.allCharArr[i]);
            }
          }
        } else {
          this.finalCharArr = this.allCharArr;
        }
      } else {
        for (var k = 0; k < this.allCharArr.length; k++) {
          if (this.nsfwSwitch == false) {
            for (var j = 0; j < this.museAULst.length; j++) {
              if (this.museAULst[j].au == this.allCharArr[k].states[0]) {
                tempNSFWchk = this.museAULst[j].sfw
              }
            }
            if (tempNSFWchk == "Y") {
              if (this.allCharArr[k].sect == this.museSect.value) {
                this.finalCharArr.push(this.allCharArr[k]);
              }
            }
          } else {
            if (this.allCharArr[k].sect == this.museSect.value) {
              this.finalCharArr.push(this.allCharArr[k]);
            }
          }
        }
      }
    },
    checkSFW(sfwVar) {
      if (this.nsfwSwitch == false) {
        if (sfwVar == "N") {
          return false
        } else {
          return true
        }
      } else {
        return true
      }
    },
    museSwitch(move) {
      var newCode = "";
      var newSect = "";
      var auCheck = false;
      var tempArrayChar = []
      if (this.charArrAu != []) {
        tempArrayChar = this.charArrAu
      } else {
        tempArrayChar = this.finalCharArr
      }
      if (muse)
        switch (move) {
          case 1:
            for (var i = 0; i < tempArrayChar.length; i++) {
              if (this.currentMuseCode == tempArrayChar[i].code) {
                if (i - 1 < 0) {
                  newCode =
                    tempArrayChar[tempArrayChar.length - 1].code;
                  newSect =
                    tempArrayChar[tempArrayChar.length - 1].sect;
                  for (
                    var j = 0;
                    j <
                    tempArrayChar[tempArrayChar.length - 1].states
                      .length;
                    j++
                  ) {
                    if (
                      tempArrayChar[tempArrayChar.length - 1].states[
                      j
                      ] == this.currentAU
                    ) {
                      auCheck = true;
                    }
                  }
                } else {
                  newCode = tempArrayChar[i - 1].code;
                  newSect = tempArrayChar[i - 1].sect;
                  for (
                    var j = 0;
                    j < tempArrayChar[i - 1].states.length;
                    j++
                  ) {
                    if (tempArrayChar[i - 1].states[j] == this.currentAU) {
                      auCheck = true;
                    }
                  }
                }
              }
            }
            break;
          case 2:
            for (var i = 0; i < tempArrayChar.length; i++) {
              if (this.currentMuseCode == tempArrayChar[i].code) {
                if (i + 1 > tempArrayChar.length - 1) {
                  newCode = tempArrayChar[0].code;
                  newSect = tempArrayChar[0].sect;
                  for (var j = 0; j < tempArrayChar[0].states.length; j++) {
                    if (tempArrayChar[0].states[j] == this.currentAU) {
                      auCheck = true;
                    }
                  }
                } else {
                  newCode = tempArrayChar[i + 1].code;
                  newSect = tempArrayChar[i + 1].sect;
                  for (
                    var j = 0;
                    j < tempArrayChar[i + 1].states.length;
                    j++
                  ) {
                    if (tempArrayChar[i + 1].states[j] == this.currentAU) {
                      auCheck = true;
                    }
                  }
                }
              }
            }
            break;
        }
      if (auCheck == false) {
        for (var i = 0; i < tempArrayChar.length; i++) {
          if (tempArrayChar[i].code == newCode) {
            this.currentAU = tempArrayChar[i].state
          }
        }
      }
      var auList = [];
      for (var i = 0; i < tempArrayChar.length; i++) {
        if (tempArrayChar[i].code == newCode) {
          auList = tempArrayChar[i].states
        }
      }
      this.museProfileOpen(newSect, newCode, this.currentAU, auList);
    },
    museProfileOpen(area, char, au, aus) {
      this.cleanData();
      switch (area) {
        case 1:
          switch (char) {
            case "rosa":
              this.muse.Spec = "Human";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Pokemon Trainer";
                  this.muse.Reg = "Unova";
                  this.muse.Name = "Rosa Whitley";
                  this.muse.SubDom = "Submissive unless love requires dominance.";
                  this.muse.Desc = "A buntailed, peppy, flexible Unova Pokemon trainer, with a Paldean mother and Galarian the other, who loves to love, and always tries to see the bright side of life and people. Recently come into contact with her distant cousins Nemona and Marnie. ";
                  this.muse.DescLewd = "As expected of a former Team Plasma Grunt, she's eager to please, and quick to treat degradation and harm as 'love bites'.";
                  this.muse.kinks.partner = "Pokephilia"
                  this.muse.kinks.organ = "Pussy, Cock"
                  this.muse.kinks.clothing = "Nylon, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Romance"
                  this.muse.kinks.consent = "Free Use"
                  this.muse.kinks.substance = "Lactation, Sweat, Cum (Inside)"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Agent 'Lover'";
                  this.muse.Reg = "Unova";
                  this.muse.Name = "Rosa Whitley";
                  this.muse.SubDom = "Submissive unless mission requires dominance.";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A loyal member of Team Rocket's most arousing division. She remains highly peppy, cheerful, and loving, even if her love is Team Rocket. She intends to share her beloved with every cute and hot girl in the world, by whatever means are asked of her, hence her grunt codename.";
                  this.muse.kinks.partner = "Pokephilia, Team Rocket"
                  this.muse.kinks.organ = "Pussy, Cock"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Servitude, Romance"
                  this.muse.kinks.consent = "Free Use"
                  this.muse.kinks.substance = "Lactation, Sweat, Cum (Inside)"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling"
                  this.muse.kinks.mindMod = "Corruption, Assimilation"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "plasma":
                  this.muse.Title = "Plasma Grunt 'Princess'";
                  this.muse.Reg = "Unova";
                  this.muse.Name = "Rosa Whitley";
                  this.muse.SubDom = "Broken Submissive.";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A permanent long-time member of team Plasma, despite the royalty name she's treated as the lowest of the low, and has lost all notion of ever leaving, genuinely believing the way she's treated is only fair, be it as the team's slut, or the humiliating, arousing punishments for failure. At times she wonders what it would've been to leave, but then she's fucked and used all over and lets go of such silly notions. She is Team Plasma property, nothing else matters.";
                  this.muse.kinks.partner = "Pokephilia, Team Plasma"
                  this.muse.kinks.organ = "Pussy, Cock"
                  this.muse.kinks.clothing = "Nylon"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Free Use, Exhibitionist"
                  this.muse.kinks.substance = "Lactation, Sweat, Cum (Inside)"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis, Grappling"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
                case "ua":
                  this.muse.Title = "UA Support Student";
                  this.muse.Reg = "Japan, Musatafu";
                  this.muse.Name = "Shiroi 'Rosa' Mei";
                  this.muse.SubDom = "Worshipful in either direction";
                  this.muse.Desc = "A quirkless support student with greater focus on metallurgy and the arts, who's been assigned to support student Setsuna Tokage, and does so earnestly with a massive crush on her. But secretly, she's always wanted to try and be somewhat of an actual pro hero. WIth armor and sword. ";
                  this.muse.DescLewd = "She's endlessly fascinated by quirks and outfits, to the point of spending much mental power into how they can be used towards sexy shenanigans. She DOES adore Midnight after all.";
                  this.muse.kinks.partner = "Machines"
                  this.muse.kinks.organ = "Mouth, Ass, Cock"
                  this.muse.kinks.clothing = "YES"
                  this.muse.kinks.relation = "Servitude, Romance"
                  this.muse.kinks.consent = "Free Use, Stealth"
                  this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "nem":
              this.muse.SubDom = "Whoever wins the battle doms.";
              this.muse.Spec = "Human";
              this.muse.Reg = "Paldea";
              this.muse.Name = "Nemona Victoria";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Paldean Champion";
                  this.muse.Desc = "A very hyperactive girl who enjoys Pokemon battling above all else. It has led her to be a Champion-ranked student, though making her ability to relate to others much harder. Has come out of her shell a little through Juliana and Penny, and now her cousin Rosa. ";
                  this.muse.DescLewd = "She treats sex as roughly and dedicated as Pokémon battling. She has fucked and broken many girls she defeats, and intends to do the same for her new friends, longer, harder, tighter. Make them hers for good.";
                  this.muse.kinks.partner = "Pokephilia"
                  this.muse.kinks.organ = "Ass"
                  this.muse.kinks.clothing = "Nylon"
                  this.muse.kinks.relation = "Petplay, Rivalry"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Sweat, Cum (Inside)"
                  this.muse.kinks.treatment = "Praise, Ryona"
                  this.muse.kinks.bondage = "Rope, Grappling"
                  this.muse.kinks.mindMod = "Mindbreak"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Coordinator";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A rapidly risen leader of Team Hypno Rocket, aptly so given her thirst for competition and sex. She makes sure to take care of any girl under her care, treating them as already defeated and thus hers to play with. Had designs of starting her own evil team of the same occupations and goals, but joined Team Hypno Rocket to not start from scratch.";
                  this.muse.kinks.partner = "Pokephilia, Team Rocket"
                  this.muse.kinks.organ = "Ass"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Petplay, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Sweat, Cum (Inside)"
                  this.muse.kinks.treatment = "Praise, Ryona"
                  this.muse.kinks.bondage = "Rope, Grappling"
                  this.muse.kinks.mindMod = "Mindbreak, Assimilation"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "marn":
              this.muse.Name = "Marnie Mary";
              this.muse.Spec = "Human";
              this.muse.Reg = "Galar";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Spikemuth Gym Leader";
                  this.muse.SubDom = "Submissive unless irritated sufficiently. Like a Morpeko.";
                  this.muse.Desc = "A punk-ish girl who seems tough, hiding a truly shy and sweet disposition, with troubles smiling and otherwise expressing herself concisely. She has a legion of fans that cause ruckus, and two cousins that tease her endlessly, both of which she is eternally grateful to. ";
                  this.muse.DescLewd = "When she snaps, she truly embraces that toughness all see, and will use every filthy fantasy on whoever brought it on her. On the other hand, if she breaks, she'll take anything you do to her.";
                  this.muse.kinks.partner = "Toys, Gangbang"
                  this.muse.kinks.organ = "Mouth, Pussy"
                  this.muse.kinks.clothing = "Leather, Fishnet, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Cumplay, Smoking"
                  this.muse.kinks.treatment = "Degradation, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Chains, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Mindbreak"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Droneified Rocket Grunt";
                  this.muse.SubDom = "Completely submissive until ordered otherwise.";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A former trainer put in a deep trance of hypnosis, left as a drooling mess (from either end). With a snap of her fingers, she may go back to her former self, be put in a state of dominance, or go back to her true happy mindless self. She was more aware than she let on before her hypnosis. She just wanted to have someone else take care of her, and let her emote more, or be more comfortable with her state.";
                  this.muse.kinks.partner = "Toys, Gangbang, Team Rocket"
                  this.muse.kinks.organ = "Mouth, Pussy"
                  this.muse.kinks.clothing = "Latex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Cumplay, Smoking"
                  this.muse.kinks.treatment = "Degradation, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Chains, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "ida":
              this.muse.SubDom = "Submissive, worshipful";
              this.muse.Name = "Irida Kai";
              this.muse.Spec = "Human";
              this.muse.Reg = "Sinnoh";
              this.muse.RegSh = " (Hisui)";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Pokemon Trainer?";
                  this.muse.Desc = "A girl thrown into the leadership of the Pearl Clan too soon, she overcompensates with a tough attitude and disposition, hiding a rather soft self. She's been flung forward in time now, to modern day Sinnoh. While happy to explore the vast world in front of her, she can't help but wonder what to do without having to lead. ";
                  this.muse.DescLewd = "Sometimes she too wishes to step down and be just one more person worshiping, as well as forget the breaking of her life's theology..or find a new one.";
                  this.muse.kinks.partner = "Pokephilia, Gangbang"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nudity"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Dub-Con, Stealth"
                  this.muse.kinks.substance = "Sweat, Cumplay"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Rope, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Grunt 'Priestess'";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A girl flung forward in time to a confusing future, comforted by her new one and only religion: Team Hypno Rocket!! Hierarchy-wise she really is just grunt level, but her fervor and worship really earned her the special little codename. Part of her sometimes screams at her about the criminal, sometimes 'evil' actions of the team, but the comfort of worship and mindlessness soothe her too much to dwell on it too long.";
                  this.muse.kinks.partner = "Pokephilia, Gangbang, Team Rocket"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nudity, Spandex"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Dub-Con, Stealth"
                  this.muse.kinks.substance = "Sweat, Cumplay"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Rope, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "galaxy":
                  this.muse.Title = "Galactic Scientist";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A girl brought from the past to use her expertise to handle the mythological matters of the team. Thoroughly brainwashed and extracted of her knowledge, she is now a scientist only in name, as she's not too technologically savvy yet, but knows her lore.  She's caught the eye of Admin Cynthia, as an archaeologist and historian.";
                  this.muse.kinks.partner = "Machines, Pokephilia, Team Galactic"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nudity, Nylon"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Non-Con, Stealth"
                  this.muse.kinks.substance = "Sweat, Cumplay, Drugs"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Tentacles, Rope, Chains, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "YES"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "iris":
              this.muse.SubDom = "Dominant unless Dragon";
              this.muse.Spec = "Human";
              this.muse.Reg = "Unova";
              this.muse.Name = "Iris Magenta";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Opelucid Gym Leader, Unovan Champion";
                  this.muse.Desc = "A very wild girl who loves dragons, and Pokémon, but is rather clueless and slow to trust and learn when it comes to anything outside of that. After a great journey, she managed to become the Champion of Unova, a title which often swings between her and her claimed sister Rosa. ";
                  this.muse.DescLewd = "It is her earnest hope to be taken by a dragon as a mate and utterly ruined, only existing as a dragon's slave. Or perhaps commanded by one to execute their dominance on other victims.";
                  this.muse.kinks.partner = "Pokephilia, Dragonfucking"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Nudity, Dress-Up"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Sweat, Watersports"
                  this.muse.kinks.treatment = "Ryona"
                  this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Mindbreak"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Grunt 'Princess'";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Where Rosa goes so does she, so it was only a matter of time she cornered her sister and joined. While she still has a greater interest in dragons and championship, she has no problem helping in the newly found 'family business', even if she doesn't have many opportunities to show she too can be sexy. The codename is entirely sarcastic, as those who face her will instead find a dragon, and yet she's very pampered in-team.";
                  this.muse.kinks.partner = "Pokephilia, Dragonfucking, Team Rocket"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Nudity, Spandex"
                  this.muse.kinks.relation = "Enslavement, Servitude"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Sweat, Watersports"
                  this.muse.kinks.treatment = "Ryona"
                  this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Mindbreak, Assimilation"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "plasma":
                  this.muse.Title = "Plasma Grunt 'Dragon'";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Kidnapped as part of a recruitment plan, and set up as Rosa's counterpart. Her spirit broke..only towards the favor of Team Plasma. Outside of that, she is brutal and cruel to all who lie in her way, or rather, in Team Plasma's way. And she takes what she wants from her sister grunt, as any proper dragon would do to a princess";
                  this.muse.kinks.partner = "Pokephilia, Dragonfucking, Team Plasma"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Nylon"
                  this.muse.kinks.relation = "Enslavement, Incest"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Sweat, Watersports"
                  this.muse.kinks.treatment = "Ryona"
                  this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Mindbreak"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "sere":
              this.muse.Reg = "Kalos";
              this.muse.Spec = "Human";
              this.muse.Name = "Serena Yvonne";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Pokemon Trainer";
                  this.muse.SubDom = "Casual Switch.";
                  this.muse.Desc = "A fashionable young lady, who's very kind and polite, until she actually snaps. Rather lost in her way, she takes the time while trying to find her future by trying on all kinds of clothes...or tasting all sorts of lips. She IS Kalosian, after all. ";
                  this.muse.DescLewd = "It's not rare to find her only partially dressed, or wearing sexual parodies that barely count as clothes. This too is fashion after all!";
                  this.muse.kinks.partner = "Toys, Gangbang"
                  this.muse.kinks.organ = "Tits"
                  this.muse.kinks.clothing = "Nudity, Dress-Up"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "NEUTRAL"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Assimilation"
                  this.muse.kinks.bodyMod = "Body Writing"
                  this.muse.kinks.transform = "Bimbofication, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Agent 'Model' ";
                  this.muse.SubDom = "Cheerily, teasingly Submissive";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Infiltrated Team Rocket by wearing their uniform. On being caught, she claimed she loved the uniform so much she wanted to feel like part of its team. After several hours of hands-on tutoring by 'her superiors', workplace training videos, and physical training regimes, she can finally shine the uniform's true nature of a loyal Team Rocket member. Said tutoring involved lengthy groping, said training regimes growingly obscene poses and motions, and said workplace training videos were hypnotic. She has forgotten entirely she was ever here undercover, and she is 100% a Team Rocket member now and forever.";
                  this.muse.kinks.partner = "Toys, Gangbang, Team Rocket"
                  this.muse.kinks.organ = "Tits"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "NEUTRAL"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Assimilation"
                  this.muse.kinks.bodyMod = "Body Writing"
                  this.muse.kinks.transform = "Bimbofication, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "flare":
                  this.muse.Title = "Flare Admin ";
                  this.muse.SubDom = "Switch but always haughty.";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Hired to model their attires as they were designed, she ultimately fell in love with their ideas of beauty and fame, which her continued (and growingly enthusiastic) modelling of their outfits and goals granted her within. Her career may be less known, but in the end, beauty will win. And she IS beauty. Some of the outfits were treated to lower personal morals, and increase pleasure based on team Flare approval. She knows now, but doesn't mind, as she asked her current outfits to have ten times the potency of her trial ones.";
                  this.muse.kinks.partner = "Toys, Gangbang, Team Flare"
                  this.muse.kinks.organ = "Tits"
                  this.muse.kinks.clothing = "YES"
                  this.muse.kinks.relation = "Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "NEUTRAL"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication, Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "brina":
              this.muse.Reg = "Kanto";
              this.muse.Spec = "Human (Psychic)";
              this.muse.SubDom = "In Control.";
              this.muse.Name = "Sabrina";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Saffron Gym Leader";
                  this.muse.Desc = "A confident woman who's grown a little conceited in her psychic powers, and embraced the cockiness in it, dressing, speaking, and behaving the part of a powerful villain, even when doing good for others. Despite it, shimmers of the sweet kid she couldn't be sometimes shine through. ";
                  this.muse.DescLewd = "She's obsessed with control, and she'll use whatever she's got, be it her looks or her psychic powers, to make sure they go as she wishes. You have no choice in the matter.";
                  this.muse.kinks.partner = "Toys"
                  this.muse.kinks.organ = "Tits"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Dub-Con, Stealth, Voyeur"
                  this.muse.kinks.substance = "Sweating, Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis"
                  this.muse.kinks.mindMod = "Brainwashing, Asimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Commander";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Finding her wicked disposition and power praised and endorsed by the team, she joined truly of her own voalition, and uses her own psychic powers towards getting more members. Some people say the growing sexualization of the female members' outfits is due to her own fetishes, but none dare ever ask. She knows they intend to, though, and she'll never say.";
                  this.muse.kinks.partner = "Toys, Team Rocket"
                  this.muse.kinks.organ = "Tits"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Dub-Con, Stealth, Voyeur"
                  this.muse.kinks.substance = "Sweating, Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis"
                  this.muse.kinks.mindMod = "Brainwashing, Asimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "cyn":
              this.muse.Reg = "Sinnoh";
              this.muse.Name = "Cynthia Shirona";
              this.muse.Spec = "Human";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Sinnoh Champion / Archaeologist";
                  this.muse.SubDom = "Mostly Dommy Mommy.";
                  this.muse.Desc = "An adventuring archaeologist who's stumbled upon the title of champion. While not the greatest fan of battling, the title serves her well for clearance into important sites, and her team is prepared to deal with the blow of legendaries' actions. ";
                  this.muse.DescLewd = "She's well aware of the reputation and trauma her prowess does to others, and sometimes she revels in it, playing up her mystery and dominance. Other times? She surprises them with her tenderness. She enjoys either, and the arousing events they lead to.";
                  this.muse.kinks.partner = "Pokephilia"
                  this.muse.kinks.organ = "Mouth, Ass, Tits"
                  this.muse.kinks.clothing = "Nudity, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Incest"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Lactation, Cumplay"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Hypnosis, Grappling, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption"
                  this.muse.kinks.bodyMod = "Breeding, Piercing"
                  this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Scientist";
                  this.muse.SubDom = "Vicious Dommy, Power Bottom.";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Offered quite a bit of endorsement for her help in studying mythos (as well as promises that they wouldn't use it for as dangerous goals as Team Galactic), she joined on contract, though contact with their uniforms and culture and the myriad of Sonia's inventions degraded her until she accepted to join in full. She no longer has qualms about whether her knowledge is used for great evil, only how it'll serve team Rocket, her beloved.";
                  this.muse.kinks.partner = "Pokephilia, Team Rocket"
                  this.muse.kinks.organ = "Mouth, Ass, Tits"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Petplay, Servitude, Incest"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Lactation, Cumplay"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "Hypnosis, Grappling, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Assimilation"
                  this.muse.kinks.bodyMod = "Breeding, Piercing"
                  this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "galaxy":
                  this.muse.Title = "Galactic Admin";
                  this.muse.SubDom = "Ready to obey, and destroy";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Unknowingly and accidentally helped with the archaeological/mythos side of things, realizing how much she had helped the team broke her, choosing to use their tech to be brainwashed. Now she's happily loyal, without those pesky morals that gave her guilt, and all she had to give away was her life and pride. The errors that led to her assistance were entirely staged to wrack her with guilt, and the pleasure she gets when obeying from the brainwashing helped ensure she'd never leave.";
                  this.muse.kinks.partner = "Machines, Pokephilia, Team Galactic"
                  this.muse.kinks.organ = "Mouth, Ass, Tits"
                  this.muse.kinks.clothing = "Nylon"
                  this.muse.kinks.relation = "Petplay, Enslavement, Incest"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweating, Cumplay, Drugs"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis, Grappling, Environment"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "nesa":
              this.muse.SubDom = "Goes with the flow";
              this.muse.Spec = "Human";
              this.muse.Reg = "Galar";
              this.muse.Name = "Nessa Rurina";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Hulbury Gym Leader / Model";
                  this.muse.Desc = "A model and gym leader from Galar who much like the sea, is calm until battle comes and she becomes the storm. She worries about holding onto her modelling career alongside the gym, but she continues to shine on. She always has time for Sonia though! ";
                  this.muse.DescLewd = "She absolutely adores Sonia and would do anything for her, go as far as she asks. She's taken to masturbate to her at her own pool, hoping the waters hide her own fluids shed from thinking about her closest gal pal.";
                  this.muse.kinks.partner = "Gangbang"
                  this.muse.kinks.organ = "Ass"
                  this.muse.kinks.clothing = "Nudity, Spandex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Servitude, Romance"
                  this.muse.kinks.consent = "Dub-Con, Stealth"
                  this.muse.kinks.substance = "Sweating, Cumplay (Out), Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption"
                  this.muse.kinks.bodyMod = "Piercing"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Coordinator";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "She entered by Sonia's invitations, and her own secret sensual experiments on her left her suggestible enough to dedicate herself. Team Rocket has helped her greatly in managing her time for gym, modelling, and Rocket missions. And she always has time to assist her Sonia in the lab, grateful she got her here.";
                  this.muse.kinks.partner = "Gangbang, Team Rocket"
                  this.muse.kinks.organ = "Ass"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Petplay, Servitude, Romance"
                  this.muse.kinks.consent = "Dub-Con, Stealth"
                  this.muse.kinks.substance = "Sweating, Cumplay (Out), Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Assimilation"
                  this.muse.kinks.bodyMod = "Piercing"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "jess":
              this.muse.Spec = "Human";
              this.muse.Reg = "Kanto";
              this.muse.Name = "Jessie Musashi";
              this.muse.SubDom = "Cocky Top, Bratty Bottom";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Rocket Agent";
                  this.muse.Desc = "A longtime member of Team Rocket, coming from her own mother being a part of it. While adoring the fashion, the high life of crime, and even the evil plots, the goals of the organization, her position, and the fact she was unable to become a nurse still chafe at her to date, promising one day to rise the ranks and make the organization better anew. ";
                  this.muse.DescLewd = "She's quite confident in her looks, and does her best to wear as little as possible. She doesn't mind people having a look, but rare are those she permits to touch.";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Ass, Tits"
                  this.muse.kinks.clothing = "Latex, Dress-Up"
                  this.muse.kinks.relation = "Romance"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Cumplay"
                  this.muse.kinks.treatment = "Praise, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Rope, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Asimilation"
                  this.muse.kinks.bodyMod = "Tattoos"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "NO"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Leader";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A woman who's finally taken center stage in her life and at the top, where she belongs, helping command Team Rocket into a more positive, albeit arousing, direction. Her charm has aided her greatly in both recruitment and reworking Rocket's public perception.";
                  this.muse.kinks.partner = "Team Rocket"
                  this.muse.kinks.organ = "Ass, Tits"
                  this.muse.kinks.clothing = "Latex, Dress-Up"
                  this.muse.kinks.relation = "Servitude, Romance"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Cumplay"
                  this.muse.kinks.treatment = "Praise, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Rope, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Asimilation"
                  this.muse.kinks.bodyMod = "Tattoos"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "ele":
              this.muse.SubDom = "Electric Switch";
              this.muse.Spec = "Human";
              this.muse.Reg = "Unova";
              this.muse.Name = "Elesa Kamitsure";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Nimbasa Gym Leader / Model";
                  this.muse.Desc = "An enthusiastic gym leader and supermodel, who's happy to do her best for others and let them shine through, with their own spark. ";
                  this.muse.DescLewd = "She's proudly led many through the pipeline from model to whore, accompanying them all the while in the dark side of fashion and beauty. ";
                  this.muse.kinks.partner = "Pokephilia, Gangbang"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Dress-Up"
                  this.muse.kinks.relation = "NEUTRAL"
                  this.muse.kinks.consent = "Free Use, Stealth, Exhibition"
                  this.muse.kinks.substance = "Cumplay (Outside)"
                  this.muse.kinks.treatment = "Degradation, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos"
                  this.muse.kinks.transform = "Bimbofication, Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Agent 'Seamstress'";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "The actual fashion designer for Team Rocket's new uniforms. She was not originally asked to make them so..arousing, visually or wear-wise. But it went incredibly well, so they accept and ask of her to make them even sluttier.";
                  this.muse.kinks.partner = "Pokephilia, Gangbang, Team Rocket"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Free Use, Stealth, Exhibition"
                  this.muse.kinks.substance = "Cumplay (Outside)"
                  this.muse.kinks.treatment = "Degradation, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Assimilation"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos"
                  this.muse.kinks.transform = "Bimbofication, Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
                case "plasma":
                  this.muse.Title = "Plasma Admin";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Asked to be their fashion ambassador, and given Plasma-made earbuds for her looks. Said buds assaulted her brain every so often to break her mental defenses down, until it left her vulnerable enough to give herself to them. She still does modelling, sponsored by Team Plasma, and turning them into recruitment rallies, blasting the same waves that broke her to the audience.";
                  this.muse.kinks.partner = "Pokephilia, Gangbang, Team Plasma"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nylon"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Cumplay (Outside)"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Chains, Hypnosis, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "lusa":
              this.muse.Reg = "Alola";
              this.muse.Name = "Lusamine";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Aether President";
                  this.muse.Spec = "Human";
                  this.muse.SubDom = "Mommy Dommy, you decide if gentle or cruel.";
                  this.muse.Desc = "President of the Aether Foundation, who's too busy and lost in her obsessions to care for her daughter or son. Despite this she is not an unlikeable person, and too many are drawn to her to stop her influence. ";
                  this.muse.DescLewd = "She knows how great she looks and is not afraid to use it to her benefit, as well as simply to relax after a hard day of work...or even to punish and manipulate people into doing her bidding, believing her fully.";
                  this.muse.kinks.partner = "Machines, Ultra Bestiality"
                  this.muse.kinks.organ = "Ass, Tits, Cock"
                  this.muse.kinks.clothing = "Nudity, Spandex, Nylon, Dress-Up"
                  this.muse.kinks.relation = "Enslavement, Servitude, Incest"
                  this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
                  this.muse.kinks.substance = "YES"
                  this.muse.kinks.treatment = "YES"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "Mechanization, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "aether":
                  this.muse.Title = "Mother Beast";
                  this.muse.Spec = "Human / Ultra Beast";
                  this.muse.SubDom = "Cruel Mother";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A deranged woman who's lost herself in the feeling that her beloved Ultra Beast has given her, intent on sharing this gift with the world, starting with her unruly children, who too can become better themselves and truly hers if they accept a Beast too, or their Mother's one.";
                  this.muse.kinks.partner = "Ultra Bestiality"
                  this.muse.kinks.organ = "Ass, Tits, Cock"
                  this.muse.kinks.clothing = "Nudity, Living Clothes"
                  this.muse.kinks.relation = "Enslavement, Incest"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "YES"
                  this.muse.kinks.treatment = "Praise, Degradation, Ryona, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "Beastification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Scientist";
                  this.muse.Spec = "Human";
                  this.muse.SubDom = "Kind Dommy Mommy";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Joined Team Rocket under false pretenses to undermine them and get out of her way, but was given hypnosis to truly join them..and therapy to acknowledge the issues with her Ultra Beast obsession. After apologies to her daughter (who was already a member), she works hard to make up to her and the world by being very truly kind.";
                  this.muse.kinks.partner = "Pokephilia, Team Rocket"
                  this.muse.kinks.organ = "Ass, Tits, Cock"
                  this.muse.kinks.clothing = "Latex, Spandex"
                  this.muse.kinks.relation = "Enslavement, Servitude, Incest"
                  this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
                  this.muse.kinks.substance = "YES"
                  this.muse.kinks.treatment = "YES"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "Mechanization, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "clair":
              this.muse.Name = "Clair Ibuki";
              this.muse.SubDom = "Cocky Top, Flustered Bottom";
              this.muse.Title = "Blackthorn Gym Leader";
              this.muse.Spec = "Human";
              this.muse.Reg = "Johto";
              this.muse.Desc = "A woman with the confidence to stand with and against dragons in the home of the Dragon Tamers. She herself is like a dragon in many ways, and so often is weakened to not being seen as imposing. ";
              this.muse.DescLewd = "She likes to play the part sometimes of the cockiness and cruelty of dragons, and snatch and play around with victims, though many can attest if you are in fact not allured by this, it's easy to turn the tables on her";
              this.muse.kinks.partner = "Dragonfucking"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
              this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
              this.muse.kinks.substance = "Sweating, Watersports"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "garde":
              this.muse.Reg = "Sinnoh";
              this.muse.Name = "Gardenia Natane";
              this.muse.Spec = "Human";
              this.muse.SubDom = "Enthusiastic submissive";
              switch (au) {
                case "pokemon":
                  this.muse.Title = "Eterna Gym Leader";
                  this.muse.Desc = "A bright and optimistic lady who adores grass types, fears ghost types, and always seeks out new challenges, Gardenia is always ready for a battle, a trade, or a chat. ";
                  this.muse.DescLewd = "Her adoration of grass types can definitely get too far, as their usual agressive reactions to a stranger/bad news draw a very lustful reaction out of her when she's the victim.";
                  this.muse.kinks.partner = "Pokephilia"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nudity"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Watersports, Drugs"
                  this.muse.kinks.treatment = "Ryona, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Rope, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Mindbreak, Brainwashing"
                  this.muse.kinks.bodyMod = "Breeding, Piercing"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "rocket":
                  this.muse.Title = "Rocket Scientist";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Dawn approached her in assisting her with aphrodisiac and calming pheromones, to rebrand her recently acquired Team Rocket into something much more positive..and arousing. Claiming it'd popularize the effects of grass type pokemons, she accepted.";
                  this.muse.kinks.partner = "Pokephilia, Team Rocket"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nudity, Spandex"
                  this.muse.kinks.relation = "Petplay, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Watersports, Drugs"
                  this.muse.kinks.treatment = "Ryona, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Rope, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Mindbreak, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "Breeding, Piercing"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "galaxy":
                  this.muse.Title = "Galactic Grunt 'Mecha'";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Captured and thoroughly brainwashed, her mind switched her love of nature and plant types to machines and steel and electric types. Now a lowly grunt, she is allowed to keep her name, appearence, and tastes, if only for the entertainment of the higher ups, seeing such a nature-loving woman get aroused and obedient at machines with no feelings or heart.";
                  this.muse.kinks.partner = "Machines, Team Galactic"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nudity, Nylon"
                  this.muse.kinks.relation = "Petplay, Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Sweating, Watersports, Drugs"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "YES"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "mars":
              this.muse.Name = "Mars Ares";
              this.muse.SubDom = "Spirited Domme, bratty sub";
              this.muse.Title = "Galactic Commander";
              this.muse.Spec = "Human";
              this.muse.Reg = "Sinnoh";
              this.muse.Desc = "A rare Team Galactic Commander that lacks any sort of cruelty, though she can be quite hot-headed, she is merely loyal to the organization and the cause, truly aiming to make a better world than the one she's in. ";
              this.muse.DescLewd = "If you refuse Team Galactic too much, her temper may override her lack of cruelty. Accept them into your heart, and she will show you the wonders of the team and it's members.";
              this.muse.kinks.partner = "Machines, Team Galactic"
              this.muse.kinks.organ = "Ass, Cock"
              this.muse.kinks.clothing = "Nylon"
              this.muse.kinks.relation = "Servitude"
              this.muse.kinks.consent = "Dub-Con"
              this.muse.kinks.substance = "Cumplay, Sweating"
              this.muse.kinks.treatment = "Degradation, Objectification, Humiliation"
              this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis, Environment"
              this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
              this.muse.kinks.bodyMod = "Tattoos/Body Writing"
              this.muse.kinks.transform = "Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "ggrunt":
              this.muse.Name = "???";
              this.muse.SubDom = "Galactic-commanded Switch";
              this.muse.Title = "Galactic Grunt";
              this.muse.Spec = "Human";
              this.muse.Reg = "Sinnoh";
              this.muse.Desc = "NSFW ONLY - ";
              this.muse.DescLewd = "Servants and minions to the great Team Galactic, unaware of the height of their goals or true mission, but too enamoured with the organization to look into. And you can be one too. They'll certainly help, through whatever means necessary.";
              this.muse.kinks.partner = "Machines, Team Galactic"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "Nylon"
              this.muse.kinks.relation = "Enslavement"
              this.muse.kinks.consent = "Non-Con"
              this.muse.kinks.substance = "Sweating, Drugs"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis, Environment"
              this.muse.kinks.mindMod = "YES"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Mechanization, Twinning"
              this.muse.MetaTupper = "YES"
              break;
          }
          break;
        case 2:
          switch (char) {
            case "lumi":
              this.muse.Reg = "Teyvat";
              switch (au) {
                case "genshin":
                  this.muse.Name = "Lumine";
                  this.muse.Title = "Traveler";
                  this.muse.SubDom = "Submissive unless suficiently aroused";
                  this.muse.Spec = "???";
                  this.muse.Desc = "A girl who's come from far, far away, many many years ago, to look for her brother. She found him allied with the evil Fatui, and told her to see the world, and so she has, helping every other person who crosses her way, fighting monsters and foes, and dealing with far too much archon bullshit. ";
                  this.muse.DescLewd = "The pressures of being the Traveler, always helping, always going everywhere, tires her out to the point she'd rather just do nothing but masturbate to the unfairly hot women of Teyvat.";
                  this.muse.kinks.partner = "Monsterfucking (Churls)"
                  this.muse.kinks.organ = "Tits, Pussy, Cock"
                  this.muse.kinks.clothing = "NEUTRAL"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Free Use, Voyeur, Stealth, Exhibition"
                  this.muse.kinks.substance = "Sweating, Watersports"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Tentacles, Rope, Chains, Grappling"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak, Asimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "YES"
                  this.muse.MetaTupper = "YES"
                  break;
                case "mirror":
                  this.muse.Name = "???";
                  this.muse.Title = "Mirror Maiden";
                  this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                  this.muse.Spec = "Mirror Maiden";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                  this.muse.kinks.partner = "La Signora"
                  this.muse.kinks.organ = "Mouth, Tits"
                  this.muse.kinks.clothing = "Latex, Nylon, Living, Masks"
                  this.muse.kinks.relation = "Enslavement, Incest/Selfcest"
                  this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Cum (Outside)"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Hypnosis, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "Fatui Brands"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "lisa":
              this.muse.Reg = "Teyvat, Mondstat";
              switch (au) {
                case "genshin":
                  this.muse.Name = "Lisa Minci";
                  this.muse.SubDom = "Soft Mommy";
                  this.muse.Title = "";
                  this.muse.Spec = "Human";
                  this.muse.Desc = "A totally normal librarian who enjoys resting and relaxation, teasing, and a penchant for action and violence when her peace is threatened, almost to the point of sadism. ";
                  this.muse.DescLewd = "Fantasizes of being a mindless slave/drone to greater evils and let herself be used, just for peace of mind.";
                  this.muse.kinks.partner = "Toys, Monsterfucking (Churls), Gangbang"
                  this.muse.kinks.organ = "Tits"
                  this.muse.kinks.clothing = "Nudity, Nylon"
                  this.muse.kinks.relation = "Enslavement, Servitude, Incest"
                  this.muse.kinks.consent = "Free Use, Voyeur, Stealth"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Chains, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Brainwashing"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "mirror":
                  this.muse.Name = "???";
                  this.muse.Title = "Mirror Maiden";
                  this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                  this.muse.Spec = "Mirror Maiden";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                  this.muse.kinks.partner = "La Signora"
                  this.muse.kinks.organ = "Mouth, Tits"
                  this.muse.kinks.clothing = "Latex, Nylon, Living, Masks"
                  this.muse.kinks.relation = "Enslavement, Incest/Selfcest"
                  this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Cum (Outside)"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Hypnosis, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "Fatui Brands"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "saria":
              this.muse.Reg = "Teyvat, Mondstat";
              switch (au) {
                case "genshin":
                  this.muse.Name = "Rosaria";
                  this.muse.Title = "";
                  this.muse.SubDom = "Degenerate Tease or Mommy";
                  this.muse.Spec = "Human";
                  this.muse.Desc = "An utterly terrible yet loyal nun of the Church of Favonius. While she's grateful and indebted to it due to giving her a chance at a better life, she has no focus or interest on the actual religion of it, and uses her self-percieved wickedness she came with to do the more insidious tasks for the sake of them. ";
                  this.muse.DescLewd = "Such a thing is quite taxing on her, and so besides smoking, she unwinds by doing all sorts of filthy unchurchlike things with every man and woman that catches her by.";
                  this.muse.kinks.partner = "Gangbang"
                  this.muse.kinks.organ = "Mouth, Cock"
                  this.muse.kinks.clothing = "Leather, Fishnet"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Incest"
                  this.muse.kinks.consent = "Free Use, Stealth, Exhibition"
                  this.muse.kinks.substance = "Sweating, Cumplay Watersports, Alcohol, Smoking"
                  this.muse.kinks.treatment = "Degradation, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Chains, Grappling, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos/Body writing"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "mirror":
                  this.muse.Name = "???";
                  this.muse.Title = "Mirror Maiden";
                  this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                  this.muse.Spec = "Mirror Maiden";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                  this.muse.kinks.partner = "La Signora"
                  this.muse.kinks.organ = "Mouth, Tits"
                  this.muse.kinks.clothing = "Latex, Nylon, Living, Masks"
                  this.muse.kinks.relation = "Enslavement, Incest/Selfcest"
                  this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Cum (Outside)"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Hypnosis, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "Fatui Brands"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "yelan":
              this.muse.Reg = "Liyue, Mondstat";
              switch (au) {
                case "genshin":
                  this.muse.Name = "Yelan";
                  this.muse.Title = "";
                  this.muse.SubDom = "Whatever gets her what she wants";
                  this.muse.Spec = "Human";
                  this.muse.Desc = "A woman of many ways, mysterious as she is easygoing. She's an intelligence agent with many affiliations, a tragic tale, and an endless amount of dedication to whatever task is given, if still needing to take the most pragmatical route to conserve energy. ";
                  this.muse.DescLewd = "Depending on her role, her personage changes. The Lady of the Yanshang Teahouse, is an utter tease, a confident goddess people should kneel for, and a very gallant rewarder of those who's gambles go well.";
                  this.muse.kinks.partner = "Toys"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "YES"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
                  this.muse.kinks.substance = "Sweating, Cumplay (Outside), Watersports, Alcohol"
                  this.muse.kinks.treatment = "Praise, Degradation, Objectification"
                  this.muse.kinks.bondage = "Threads, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Mindbreak, Brainwashing"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication"
                  this.muse.MetaTupper = "YES"
                  break;
                case "mirror":
                  this.muse.Title = "Mirror Maiden";
                  this.muse.Name = "???";
                  this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                  this.muse.Spec = "Mirror Maiden";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                  this.muse.kinks.partner = "La Signora"
                  this.muse.kinks.organ = "Mouth, Tits"
                  this.muse.kinks.clothing = "Latex, Nylon, Living, Masks"
                  this.muse.kinks.relation = "Enslavement, Incest/Selfcest"
                  this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Cum (Outside)"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Hypnosis, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "Fatui Brands"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "mira":
              this.muse.Name = "None";
              this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
              this.muse.Title = "Mirror Maiden";
              this.muse.Spec = "Mirror Maiden";
              this.muse.Reg = "Teyvat";
              this.muse.Desc = "Beautiful minions of the Fatui, with a wicked disposition to others, a loving one to their sisters, and a subservient one to their masters. They will accept only from their Mistress the diminishing treatment they give to non-Fatui partners. Most of them look alike, though some a bit different, familiar. Always looking for new recruits. ";
              this.muse.DescLewd = "Said recruits are always unwilling..at first. The Maidens always get them to understand in the end. And they get to keep their appearances on hold to show or discard if it helps them get more recruits.";
              this.muse.kinks.partner = "La Signora"
              this.muse.kinks.organ = "Mouth, Tits"
              this.muse.kinks.clothing = "Latex, Nylon, Living, Masks"
              this.muse.kinks.relation = "Enslavement, Incest/Selfcest"
              this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
              this.muse.kinks.substance = "Cum (Outside)"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "Hypnosis, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
              this.muse.kinks.bodyMod = "Fatui Brands"
              this.muse.kinks.transform = "Twinning"
              this.muse.MetaTupper = "YES"
              break;
          }
          break;
        case 3:
          switch (char) {
            case "mei":
              this.muse.Name = "Mei Hatsume";
              this.muse.SubDom = "Dom when hyperfocused, Subby when taken out of focus";
              this.muse.Title = "UA Support Student";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "The greatest engineer in quirked history, she's brilliant, bombastic, and can't remember silly things like names, hygiene, or shame. All she needs in her world are her babies, and what girls may take an interest in her and her babies. ";
              this.muse.DescLewd = "Is more into machines than humans, would roboticize every hot girl she meets if she could.";
              this.muse.kinks.partner = "Machines"
              this.muse.kinks.organ = "Tits"
              this.muse.kinks.clothing = "Nudity"
              this.muse.kinks.relation = "Servitude"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Exhibition"
              this.muse.kinks.substance = "Sweating, Cumplay (Inside), Watersports"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Tentacles, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Brainwashing"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "tsu":
              this.muse.Name = "Tsuyu Asui";
              this.muse.SubDom = "Whatever strikes the mood";
              this.muse.Title = "UA Hero Student - Froppy";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A hero in training with big dreams, a long tongue, and zero ability to hold either in. She is adored by many, and her quirks (pun intended) are charming to many, just as she adores her classmates. ";
              this.muse.DescLewd = "She has enough sense not to bring up how often she wants to wrap and tongue-fuck her female classmates daily...unless they ask.";
              this.muse.Spec = "Human (Quirked), Frog";
              this.muse.kinks.partner = "Toys, Monsterfucking (Noumu)"
              this.muse.kinks.organ = "Mouth, Tits"
              this.muse.kinks.clothing = "Latex, Dress-Up"
              this.muse.kinks.relation = "NEUTRAL"
              this.muse.kinks.consent = "Free Use, Exhibition"
              this.muse.kinks.substance = "Sweating, Cumplay (Outside), Watersports"
              this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
              this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling"
              this.muse.kinks.mindMod = "Brainwashing"
              this.muse.kinks.bodyMod = "NEUTRAL"
              this.muse.kinks.transform = "Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "mina":
              this.muse.Name = "Mina Ashido";
              this.muse.SubDom = "YES";
              this.muse.Title = "UA Hero Student - Pinky";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A funky, spunky, alien-looking gal with a good heart, and a gooder sense of fun. She will spend her days scheming over her friends love lives, organize games, and save the world dancing away. ";
              this.muse.DescLewd = "With all her boundless energy come hours upon hours of sex, and she's specifically tailored her hero suit to attract that attention. Midnight is her icon for a reason.";
              this.muse.Spec = "Human (Quirked), Alien";
              this.muse.kinks.partner = "Monsterfucking (Noumu), Gangbang"
              this.muse.kinks.organ = "Ass, Pussy, Cock"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Enslavement, Romance"
              this.muse.kinks.consent = "Free Use, Voyeur, Exhibition"
              this.muse.kinks.substance = "Cumplay, Watersports, Drugs"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Tentacles, Rope, Environment"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication, Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "momo":
              this.muse.Name = "Momo Yaoyorozu";
              this.muse.SubDom = "Shyly submissive until gaining confidence to engage Mommy Momo mode";
              this.muse.Title = "UA Hero Student - Creati";
              this.muse.Nat = "Regal";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Desc = "A girl born of wealth with a genuine heart of gold and a mind that holds great knowledge. Despite her dazzling intellect, astonishing quirk, and stunning beauty, her confidence needs some serious work. But she will always stand by the side of her friends. ";
              this.muse.DescLewd = "Midnight has taken her in as a pseudo-daughter and a successor to her spirit, and she intends to work hard on her confidence to live up to it and become the newest Mistress of heroics.";
              this.muse.kinks.partner = "Toys, Machines, Monsterfucking (Noumu)"
              this.muse.kinks.organ = "Tits, Cock"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Enslavement, Servitude, Romance, Incest"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth, Exhibition"
              this.muse.kinks.substance = "Lactation, Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
              this.muse.kinks.bondage = "Rope, Chains, Grappling, Environment "
              this.muse.kinks.mindMod = "Corruption, Brainwashing"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "YES"
              this.muse.MetaTupper = "YES"
              break;
            case "toru":
              this.muse.Name = "Tooru Hagakure";
              this.muse.SubDom = "Casual Switch";
              this.muse.Title = "UA Hero Student - Invisible Girl";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A girl born invisible, pushing herself to be loud and bright and seen. Thanks to her friends and training, she has become more visible than ever at UA, thus aiming as a hero to look out for others who might be left unseen. ";
              this.muse.DescLewd = "People watching is her hobby, which has often veered into very perverted situations...not that she minds the show, or interrupts, or even leaves. Also has developed a nudist streak.";
              this.muse.kinks.partner = "Monsterfucking (Noumu), Gangbang"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "Nudity"
              this.muse.kinks.relation = "Romance"
              this.muse.kinks.consent = "Voyeur, Stealth, Exhibition"
              this.muse.kinks.substance = "Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Objectification"
              this.muse.kinks.bondage = "Tentacles, Rope, Chains, Grappling"
              this.muse.kinks.mindMod = "Mindbreak"
              this.muse.kinks.bodyMod = "Piercings"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "kendo":
              this.muse.Name = "Itsuka Kendo";
              this.muse.SubDom = "Submissive to any request, but dominant if requested";
              this.muse.Title = "UA Hero Student - Battle Fist";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A martial artist with a big brain, big heart, and bigger hands, the class representative of class B is as ruthless with her criticism as her combative disposition. She does however have a tendency to let go for others, neglecting her own wants and needs. ";
              this.muse.DescLewd = "One can only hope her friend slash crush Setsuna does not take advantage of that...or that she lets herself go along the rather sexualized world of female pro-heroism.";
              this.muse.kinks.partner = "Monsterfucking (Noumu), Gangbang"
              this.muse.kinks.organ = "Pussy, Cock"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Enslavement, Romance"
              this.muse.kinks.consent = "Free Use, Stealth"
              this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "Hypnosis, Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Brainwashing, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "kino":
              this.muse.Name = "Kinoko Komori";
              this.muse.SubDom = "Giddy top, blushy sub";
              this.muse.Title = "UA Hero Student - Shemage";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A shy girl who loves her quirk's focus, and is trying to get a little les shy. She's growing more open to her own class, and sometimes lets herself loose in the magic of mushrooms, becoming quite the fun gal. ";
              this.muse.DescLewd = "Much like her namesakes she's incredibly hypersexual, but she's not very open about it. Were one of her classmates to ask however..she'd sure show them such wonders. And if they take her in, she couldn't complain at all.";
              this.muse.kinks.partner = "Toys, Monsterfucking (Noumu)"
              this.muse.kinks.organ = "Ass, Tits, Cock"
              this.muse.kinks.clothing = "Nudity, Spandex"
              this.muse.kinks.relation = "NEUTRAL"
              this.muse.kinks.consent = "Voyeur, Stealth"
              this.muse.kinks.substance = "Watersports, Shrooms"
              this.muse.kinks.treatment = "NEUTRAL"
              this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Asimilation"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "camie":
              this.muse.Name = "Camie Utsushimi";
              this.muse.SubDom = "Dominant unless finding something kinky and fun worth subbing for.";
              this.muse.Title = "Ketsubutsu Hero Student - Illus-o-Camie";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A Ketsubutsu-taught pro-heroine in training, with a bubbly and absentminded demeanor that's hard to understand at times, but covering for remarkable cleverness of both quirk use and emotional insight. ";
              this.muse.DescLewd = "Her hero outfit and flirtatiousness bely the fact that she likes to draw in the attention, the only question being, what she will do with that attention. She knows quite well the answer will be 'whatever Camie desires'.";
              this.muse.kinks.partner = "Monsterfucking (Noumu), Gangbang"
              this.muse.kinks.organ = "Tits, Pussy, Cock"
              this.muse.kinks.clothing = "Nudity, Latex, Leather, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement"
              this.muse.kinks.consent = "Free Use, Exhibition"
              this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "YES"
              this.muse.kinks.bondage = "Tentacles, Rope, Chains, Hypnosis"
              this.muse.kinks.mindMod = "Corruption, Mindbreak, Brainwashing"
              this.muse.kinks.bodyMod = "Breeding, Piercing"
              this.muse.kinks.transform = "Bimbofication, Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "mel":
              this.muse.Name = "Melissa Shield";
              this.muse.SubDom = "Experimental switch, sub-leaning";
              this.muse.Title = "";
              this.muse.Spec = "Human";
              this.muse.Reg = "I-Island";
              this.muse.Desc = "A quirkless american girl who wants to save people, and has decided to do so through her inventions. Despite her outgoing nature, she doesn't have many friends. Something she intends to fix as well. ";
              this.muse.DescLewd = "She is not blind to how her looks makes others feel. She hopes the acquisition of friends will facilitate experimenting with that.";
              this.muse.kinks.partner = "Machines, Gangbang"
              this.muse.kinks.organ = "Mouth, Tits, Cock"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Petplay, Servitude"
              this.muse.kinks.consent = "Free Use, Voyeur, Stealth"
              this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Degradation, Objectification, Humiliation"
              this.muse.kinks.bondage = "Rope, Chains, Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication, Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "joke":
              this.muse.Name = "Emi Fukukado";
              this.muse.SubDom = "Mostly subby, for Midnight";
              this.muse.Title = "Pro Hero - Ms. Joke";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A pro-hero who uses the power of comedy to save people! And beat up dead cows. She flirts and laughs and loves, and never quite shuts up, to the chagrin of many. Has a book of jokes on every topic under the rising sun. ";
              this.muse.DescLewd = "Still wants to meet a hot villainess to happily surrender to, already has a suit, name and theme planned to serve her.";
              this.muse.kinks.partner = "Monsterfucking (Noumu), Gangbang"
              this.muse.kinks.organ = "Mouth"
              this.muse.kinks.clothing = "Latex, Spandex, Nylon"
              this.muse.kinks.relation = "Petplay, Romance"
              this.muse.kinks.consent = "Free Use, Voyeur, Stealth"
              this.muse.kinks.substance = "Sweat, Cum (Inside), Watersports"
              this.muse.kinks.treatment = "Praise, Degradation"
              this.muse.kinks.bondage = "Tentacles, Rope, Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption"
              this.muse.kinks.bodyMod = "NEUTRAL"
              this.muse.kinks.transform = "Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "kai":
              this.muse.Name = "Kaina Tsutsumi";
              this.muse.SubDom = "Dominant";
              this.muse.Title = "Pro Hero (Former) - Lady Nagant";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A former hero turned assassin for the Hero Association, Nagant once wanted to truly help people, but was used as a weapon of subterfuge, until she killed her own boss who led her down that path. Free now, as a villain, she sprawls the streets ready to aim and shoot. ";
              this.muse.DescLewd = "Has an interest in female pro-heroes, and teaching them a tough lesson...however they may need it.";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "Pussy, Cock"
              this.muse.kinks.clothing = "Latex, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement"
              this.muse.kinks.consent = "Non-Con, Exhibition"
              this.muse.kinks.substance = "Sweat, Cum (Outside), Watersports"
              this.muse.kinks.treatment = "Degradation, Ryona, Humiliation"
              this.muse.kinks.bondage = "Grappling"
              this.muse.kinks.mindMod = "Corruption"
              this.muse.kinks.bodyMod = "NEUTRAL"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "rumi":
              this.muse.Name = "Rumi Usagiyama";
              this.muse.SubDom = "Rough Dommy unless beaten in a fight or romantically approached";
              this.muse.Title = "Pro Hero - Miruko";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "An incredibly aggressive, lone wolf rabbit-like woman who kicks ass, in every concievable way. She has made her way to the top three through sheer force of..well, force, hiding a care for others under the spite of her quirk's perception. ";
              this.muse.DescLewd = "Her viciousness sometimes goes out of hand, and she will get it out through more fighting..or breeding like her quirksake. Any woman nearby is at risk. But if you manage to beat her, you'll have a very willing horny bunny in your grasp";
              this.muse.Spec = "Human (Quirked), Bunny";
              this.muse.kinks.partner = "Monsterfucking (Noumu)"
              this.muse.kinks.organ = "Tits, Cock"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Servitude, Romance"
              this.muse.kinks.consent = "Non-Con, Exhibition"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Degradation, Ryona, Humiliation"
              this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "yama":
              this.muse.Name = "Yu Takeyama (Mt. Lady)";
              this.muse.SubDom = "Submissive Brat";
              this.muse.Title = "Pro Hero - Mt. Lady";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A recent pro-hero who seems to be everything wrong with them. Vain, lazy, cocky, lustful, spiteful. Despite this, she has a strong heart that will shine in the worst of times. Even if the rest of times she spends bickering and teasing. ";
              this.muse.DescLewd = "Often expresses her attraction to her fellow pro-heroes by mockery, argument and teasing, desperate to push them to snap and do as they will with her. Most of them know this and don't want to give her the satisfaction.";
              this.muse.kinks.partner = "Monsterfucking (Noumu), Bestiality"
              this.muse.kinks.organ = "Ass, Tits"
              this.muse.kinks.clothing = "Latex, Leather, Nylon, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Romance"
              this.muse.kinks.consent = "Dub-Con, Non-Con, Stealth, Exhibition"
              this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "YES"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication"
              this.muse.MetaTupper = "YES"
              break;
            case "nana":
              this.muse.Name = "Nana Shimura";
              this.muse.SubDom = "Dominant unless flustered.";
              this.muse.Title = "Pro Hero ";
              this.muse.TitleSh = "(KIA)";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "An old hero, who always puts a smile on her face. Despite coming from a rather dark age, she does not let it put her down, and is training her successor to the quirk she holds, and hoping for him to become something greater, a symbol. ";
              this.muse.DescLewd = "She's very proud of her body, and does enjoy some of the reactions her muscles get. Especially from some of the ladies. Though she's not strong enough to handle a turnabout.";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "Ass, Tits"
              this.muse.kinks.clothing = "Nudity"
              this.muse.kinks.relation = "Romance"
              this.muse.kinks.consent = "Voyeur, Stealth"
              this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "NEUTRAL"
              this.muse.kinks.bodyMod = "NEUTRAL"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "fumi":
              this.muse.Name = "Fuyumi Todoroki";
              this.muse.SubDom = "Mostly Submissive";
              this.muse.Title = "Teacher";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A woman who's spent her life trying to keep things together for her family, or her idea of it. She's a preschool teacher, with a weak quirk, and often percieved as weak herself. But it takes great strength to be kind and want better under her circumstances. ";
              this.muse.DescLewd = "Something less than wonderful brews beneath her softness, and if pushed, it will no doubt come out.";
              this.muse.kinks.partner = "Toys"
              this.muse.kinks.organ = "Tits, Pussy, Cock"
              this.muse.kinks.clothing = "Latex, Nylon, Dress-Up"
              this.muse.kinks.relation = "Servitude, Romance, Incest"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
              this.muse.kinks.substance = "Lactation, Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Degradation"
              this.muse.kinks.bondage = "Rope, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption"
              this.muse.kinks.bodyMod = "Piercing, Tattoos/Body writing"
              this.muse.kinks.transform = "Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "inko":
              this.muse.Name = "Inko Midoriya";
              this.muse.SubDom = "Middle Ground Switch";
              this.muse.Title = "Mother";
              this.muse.Spec = "Human (Quirked)";
              this.muse.Reg = "Japan, Musatafu";
              this.muse.Desc = "A mother, no longer a lover, at least in her mind. With her son on the dangerous paths of heroism (yet doing well) and a great deal of regret and time left on her own, she listlessly spends her days watching soap operas, and wondering on what could be. ";
              this.muse.DescLewd = "Few have met the steel behind the tears, when it comes to her heart. Perhaps someone out there may yet be for her.";
              this.muse.kinks.partner = "Toys"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Romance"
              this.muse.kinks.consent = "Stealth"
              this.muse.kinks.substance = "Lactation, Cumplay"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "NEUTRAL"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
          }
          break;
        case 4:
          switch (char) {
            case "sam":
              switch (au) {
                case "samus":
                  this.muse.Name = "Samus Aran";
                  this.muse.Title = "Bounty Hunter";
                  this.muse.SubDom = "Whatever the 'mission' requires";
                  this.muse.Spec = "Human / Chozo / Metroid";
                  this.muse.Reg = "Space";
                  this.muse.Desc = "A capable yet sensibly muted warrior who unwinds through sex, and carries on her mission to the end, but has trouble emoting, connecting, or sensing. ";
                  this.muse.DescLewd = "She'd happily surrender to an evil alien force if it returned her the ability to feel joy and pleasure and love.";
                  this.muse.kinks.partner = "Machines, Aliens (Monsters, Beasts)"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Latex, Living, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Romance, Incest"
                  this.muse.kinks.consent = "Free Use, Dub-Con, Non-Con, Stealth"
                  this.muse.kinks.substance = "Lactation, Sweat, Cum (Inside), Watersports"
                  this.muse.kinks.treatment = "Praise, Ryona"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Grappling, Environment"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "Breeding, Tattoos"
                  this.muse.kinks.transform = "Bimbofication, Gothification, Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
                case "shy":
                  this.muse.Name = "???";
                  this.muse.Title = "Blue";
                  this.muse.SubDom = "Submissive unless orders";
                  this.muse.Spec = "Shy Gal";
                  this.muse.Reg = "Around";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A shy gal who makes even less noises than the usual, but shows little shyness in offering herself up for pleasure and flirtation. She seems almost thrilled to be in this position of anonimity. ";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Masks"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "Cumplay, Watersports"
                  this.muse.kinks.treatment = "Objectification"
                  this.muse.kinks.bondage = "Hypnosis, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "bow":
              switch (au) {
                case "mario":
                  this.muse.Name = "Bowsette Koopa";
                  this.muse.Title = "Koopa Queen";
                  this.muse.Reg = "Dark World";
                  this.muse.SubDom = "Dominant unless trapped into it or flipped by a gorgeous princess";
                  this.muse.Spec = "Koopa/Human";
                  this.muse.Desc = "A newfound boisterous girl with a thirst for cute princesses and world domination. Despite her added human, she's still strong, brash, possessive...and weak to the beauty of princesses. Her dream is all princesses to adore her, and fall for her charms to be hers. ";
                  this.muse.DescLewd = "Though sometimes, she'd like to see what it'd be like if the princesses turned the tables on her.";
                  this.muse.kinks.partner = "Princesses, Gangbang"
                  this.muse.kinks.organ = "Tits, Cock"
                  this.muse.kinks.clothing = "Latex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Romance"
                  this.muse.kinks.consent = "Dub-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Sweat, Cum (Inside)"
                  this.muse.kinks.treatment = "Praise, Degradation"
                  this.muse.kinks.bondage = "Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Bimbofication"
                  this.muse.MetaTupper = "YES"
                  break;
                case "shy":
                  this.muse.Name = "???";
                  this.muse.Title = "Yellow";
                  this.muse.SubDom = "Coy, bratty submissive";
                  this.muse.Reg = "Around";
                  this.muse.Spec = "Shy Gal";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "The very leader of the shy gals, going undercover to see what they get up to, and doing it many more times to enjoy the supposed anonimity of the mask to take a break from being bossy and the top. Actually, every shy gal knows it's her, but it's alright by them. The masks will ensure she does as they do, after all...";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Tits, Cock"
                  this.muse.kinks.clothing = "Masks"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "Cumplay, Watersports"
                  this.muse.kinks.treatment = "Objectification"
                  this.muse.kinks.bondage = "Hypnosis, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "pich":
              switch (au) {
                case "mario":
                  this.muse.Name = "Peach Toadstool";
                  this.muse.Title = "Mushroom Princess";
                  this.muse.SubDom = "Submissive unless her partner wants a taste";
                  this.muse.Spec = "Toad/Human";
                  this.muse.Reg = "Mushroom Kingdom";
                  this.muse.Desc = "A bubbly princess with great enthusiasm and love for the people of her kingdom. She may be a princess, but she doesn't always stay in the sidelines. Loves to bake, and dress-up, and do all sorts of sports. She either happily enjoys activities with people, or stubbornly refuses.  ";
                  this.muse.DescLewd = "Often, her stubbornness is just in order to invite further pressuring and convincing, as well as playing the part of a good kidnapped princess corrupted. If well convinced, she could assist in corrupting and kidnapping fellow princesses";
                  this.muse.kinks.partner = "Princesses, Koopas, Gangbang"
                  this.muse.kinks.organ = "YES"
                  this.muse.kinks.clothing = "Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Romance"
                  this.muse.kinks.consent = "Free Use, Voyeur, Stealth, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "NEUTRAL"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "YES"
                  this.muse.MetaTupper = "YES"
                  break;
                case "bow":
                  this.muse.Name = "Peachy Koopa";
                  this.muse.SubDom = "Submissive Slave";
                  this.muse.Title = "Koopa Slave";
                  this.muse.Spec = "Toad/Human";
                  this.muse.Reg = "Dark World, Mushroom Kingdom";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "The Koopa King/Queen's happy little slave, fucked into utter blissful submission after a succesful moon wedding. While legally and technically a wife, Peach knows well from her treatment and the comings of other princesses that she's nothing but Bowsette's slave...and it couldn't have gotten her happier.  Currently acts as though nothing happened, but observant folk can tell she's a little messier when being rescued than when taken, and the flashes of a very familiar emblem as a tattoo on her body.";
                  this.muse.kinks.partner = "Queen Bowsette"
                  this.muse.kinks.organ = "YES"
                  this.muse.kinks.clothing = "Latex"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Chains, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "shy":
                  this.muse.Name = "???";
                  this.muse.SubDom = "Endearingly Submissive";
                  this.muse.Spec = "Shy Gal";
                  this.muse.Title = "Pink";
                  this.muse.Reg = "Around";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A pink spunky shy gal, who's bashful in a very endearing way, as though hoping you'd catch her and do as you wish to her body. She is permitted the sounds of her giggles, melodious and seductive as they are, as well as her soft moans, which are quite frequent. She too finds freedom in the anonimity of the mask, and sometimes she forgets she's a princess at all...or her name, or her face. Surely, doing it again won't be a danger?";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Masks"
                  this.muse.kinks.relation = "Servitude"
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "Cumplay, Watersports"
                  this.muse.kinks.treatment = "Objectification"
                  this.muse.kinks.bondage = "Hypnosis, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "shadow":
                  this.muse.Name = "Peach Amanita";
                  this.muse.SubDom = "Dominant even when amused enough to recieve.";
                  this.muse.Spec = "Toad / Human / Shadow";
                  this.muse.Title = "Shadow Princess";
                  this.muse.Reg = "Rogueport, Mushroom Kingdom";
                  this.muse.Desc = "A dark queen who took over the world many years ago, now possessing Princess Peach to have a second hand at it. The fusion has completed between them, making her agreeable enough to talk, and cordial enough to not destroy it all. ";
                  this.muse.DescLewd = "She's also physical enough to appreciate pleasures of the flesh. She is neither Peach nor the original Shadow queen in full, carrying now all of Peach's lighter traits..and darker sides, including her sexual tastes.";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "YES"
                  this.muse.kinks.clothing = "Nudity, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Romance"
                  this.muse.kinks.consent = "Dub-Con, Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports, Shadow"
                  this.muse.kinks.treatment = "NEUTRAL"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak, Brainwashing"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "lina":
              switch (au) {
                case "mario":
                  this.muse.Title = "Mother of all Stars";
                  this.muse.Reg = "Comet Observatory";
                  this.muse.Name = "Rosalina Estela";
                  this.muse.SubDom = "Soft Dommy Mommy unless convinced otherwise by great force.";
                  this.muse.Spec = "Human/Goddess";
                  this.muse.Desc = "The mother of all stars, Rosalina is a greatly capable mechanic and mother, traveling space for centuries and seeing her babies turn into planets and galaxies. ";
                  this.muse.DescLewd = "But even a mother and goddess has needs, and space gets very cold and lonely. Hence her frequent visits to the Mushroom Kingdom, or how she sometimes adopts people as their mother yet does lewd activities with them.";
                  this.muse.kinks.partner = "Machines, Aliens (Monsters, Beasts)"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Spandex, Latex, Living, Dress-Up"
                  this.muse.kinks.relation = "Enslavement, Servitude, Romance, Incest"
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay"
                  this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Tentacles, Rope, Hypnosis, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "Bimbofication, Gothification, Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
                case "bow":
                  this.muse.Title = "Koopa Slave";
                  this.muse.Reg = "Dark World, Comet Observatory";
                  this.muse.Name = "Rosie Koopa";
                  this.muse.SubDom = "Broken Submissive.";
                  this.muse.Spec = "Human/Goddess";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "The former mother of all stars, lowered to a pathetic slut after Bowser destroyed her space station and decided to kidnap her on the way. While less of a frequent visitor than Peachy (given Bow's long time love of the Mushroom Princess) she's no less loyal to her monarch. ";
                  this.muse.kinks.partner = "Queen Bowsette"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Latex"
                  this.muse.kinks.relation = "Enslavement"
                  this.muse.kinks.consent = "Non-Con, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Chains, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "shy":
                  this.muse.Title = "Cyan";
                  this.muse.Reg = "Around";
                  this.muse.Name = "???";
                  this.muse.SubDom = "Cuddly Submissive.";
                  this.muse.Spec = "Shy Gal";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A particularly clingy shy gal, who does her best to stick to you while happily offering her holes. Something is rather ethereal about her, leading to being treated as a rare and lucky find. She's rather a glutton for semen, and the more she drinks the bigger her boobs grow.";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Cock"
                  this.muse.kinks.clothing = "Masks"
                  this.muse.kinks.relation = "Servitude "
                  this.muse.kinks.consent = "Free Use, Exhibition"
                  this.muse.kinks.substance = "Cumplay, Watersports"
                  this.muse.kinks.treatment = "Objectification"
                  this.muse.kinks.bondage = "Hypnosis, Grappling, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "lin":
              this.muse.Name = "Linkle Ordona";
              this.muse.SubDom = "Cheerful Submissive";
              this.muse.Title = "Farmgirl (Hero)";
              this.muse.Spec = "Hylian";
              this.muse.Reg = "Hyrule";
              this.muse.Desc = "A farmer who believes herself to be the hero of Hyrule, winning over hearts with a sweet smile. She will befriend anyone, as she keeps getting lost and finding herself anywhere. ";
              this.muse.DescLewd = "Fantasizes about taking care of the animals with her body, as well as being defeated by the monsters, only to take the upper hand after loooong long hours of fun sex with them.";
              this.muse.kinks.partner = "Monsterfucking, Bestiality"
              this.muse.kinks.organ = "Tits, Pussy"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement"
              this.muse.kinks.consent = "Free Use, Stealth"
              this.muse.kinks.substance = "Sweat"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Rope, Grappling, Environment"
              this.muse.kinks.mindMod = "Corruption, Brainwashing"
              this.muse.kinks.bodyMod = "Breeding, Body writing"
              this.muse.kinks.transform = "Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "pura":
              this.muse.Name = "Purah";
              this.muse.SubDom = "Dominant unless coerced by greater power.";
              this.muse.Reg = "Hyrule";
              switch (au) {
                case "zelda":
                  this.muse.Spec = "Sheikah Hylian";
                  this.muse.Title = "Sheikah Scientist";
                  this.muse.Desc = "A pre-Calamity science who aged herself to match the hero and princess (though not without error), she strives to work her way up to the wisdom of the ancient sheikah scientists. Her latest look has drawn much attention. ";
                  this.muse.DescLewd = "Ultimately, her eagerness for science is just a tad higher than her ethics, and the only reason she's stuck by the royal family is due to finding a connection with Zelda. Otherwise, she would do anything and anyone if it'd take her tech to greater heights.";
                  this.muse.kinks.partner = "Machines"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nylon, Latex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "Piercing"
                  this.muse.kinks.transform = "Gothification, Mechanization, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "aoc":
                  this.muse.Spec = "Sheikah Hylian";
                  this.muse.Title = "Sheikah Scientist";
                  this.muse.Desc = "A very eccentric researcher, older sister to Impa, and working for the royal family of Hyrule. She has found a likeminded soul in Zelda, and does her best to get the tech up to speed to her and the champions' needs, even if sometimes she forgets the world around for her. ";
                  this.muse.DescLewd = "It is a great tragedy that all her efforts will not come to help, and she'll have to wait a century to see the world truly safe AND Zelda well and at ease.";
                  this.muse.kinks.partner = "Machines"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nylon, Latex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing"
                  this.muse.kinks.bodyMod = "Piercing"
                  this.muse.kinks.transform = "Gothification, Mechanization, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "yiga":
                  this.muse.Spec = "Yiga Hylian";
                  this.muse.Title = "Yiga Researcher";
                  this.muse.Desc = "A woman who defected from the modern Sheikah for refusing technology, and joined up the Yiga to get them back on track for their original ideology. Despite being ruthless and deeply anti-royalty, under her care the Yiga are much less cruel overall, and more affable to non-Hylian Royalty and Sheikah. ";
                  this.muse.DescLewd = "She has no intent to harm or destroy the princess, and would much rather kidnap her, keep her to herself, and perhaps use the ancient sheikah tech to brainwash her into an obedient puppet for Ganon...and herself";
                  this.muse.kinks.partner = "Machines, Monsterfucking"
                  this.muse.kinks.organ = "NEUTRAL"
                  this.muse.kinks.clothing = "Nylon, Latex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Brainwashing, Assimilation"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos"
                  this.muse.kinks.transform = "Gothification, Mechanization, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "edel":
              this.muse.Title = "";
              this.muse.Name = "Edelgard von Hresvelg"
              this.muse.Reg = "Fódlan";
              this.muse.Desc = "A woman with the weight of the world in her shoulders, carrying great and dark secrets, and dedicated to her goals to dangerous heights. She maintains formality and composure, and trusts in others abilities, but forgets to relax, and her trust does not means she lets her own guard down emotionally. ";
              this.muse.DescLewd = "Has a massive crush on her teacher, Byleth, and if she won't fuck Edelgard herself she'll make sure to fuck Byleth instead.";
              this.muse.Spec = "Human";
              this.muse.SubDom = "Whatever Byleth requires";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "Nylon, Latex"
              this.muse.kinks.relation = "Servitude, Romance"
              this.muse.kinks.consent = "Dub-Con, Stealth"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Rope, Chains, Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Brainwashing"
              this.muse.kinks.bodyMod = "Tattoos/Body writing"
              this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "luci":
              this.muse.Name = "Lucifer Morningstar";
              this.muse.SubDom = "Absolutely Dominant";
              this.muse.SubDomSh = " unless genuinely romantically approached, or left powerless";
              this.muse.Title = "CEO of Hell";
              this.muse.Spec = "Demon ";
              this.muse.SpecSh = "(Fallen Angel)";
              this.muse.Reg = "Hell";
              this.muse.Desc = "A smooth-talking woman who's done the best of her situation. Despite her charm, she's a black-hearted queen with only a few soft spots, fine dining, drinking, worship. She flusters if her authority is upended. ";
              this.muse.DescLewd = "She's very weak outside of actual hell, and secretly likes it when she is abused on her weakness. She will repay when returning to hell, however.";
              this.muse.kinks.partner = "Monsterfucking, Bestiality, Gangbang"
              this.muse.kinks.organ = "Mouth, Cock"
              this.muse.kinks.clothing = "Leather, Dress-Up"
              this.muse.kinks.relation = "Enslavement, Romance"
              this.muse.kinks.consent = "Free Use, Dub-Con, Non-Con, Exhibition"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Degradation, Objectification, Humiliation"
              this.muse.kinks.bondage = "Tentacles, Chains, Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "azaz":
              this.muse.Name = "Azazel";
              this.muse.SubDom = "Eager submissive";
              this.muse.Spec = "Angel";
              this.muse.SpecSh = "(Soon to be Fallen)";
              this.muse.Reg = "Hell";
              this.muse.Desc = "An angel who's too curious for her own good, and too gay to function. Despite talking high and mighty of purity, God, heaven angels and whatnot, in reality she prioritizes knowledge, research, and understanding at a higher rate than any of these. ";
              this.muse.DescLewd = "This will be her downfall, and her turn to fallen angel is a certainty. The only question is how much will she accept herself..and how much damage she'll cause to others.";
              this.muse.kinks.partner = "Monsterfucking, Bestiality, Gangbang"
              this.muse.kinks.organ = "Mouth"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Servitude, Romance"
              this.muse.kinks.consent = "Voyeur"
              this.muse.kinks.substance = "Sweat, Watersports"
              this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Gothification, Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "tae":
              this.muse.Spec = "Human";
              this.muse.Reg = "Japan, Yongen-Jaya";
              this.muse.SubDom = "Dominant unless experimentation requires otherwise";
              this.muse.Name = "Tae Takemi";
              switch (au) {
                case "persona":
                  this.muse.Title = "Doctor";
                  this.muse.Desc = "An excellent, innovative doctor, who got her reputation ruined by standard medical arrogance of others. She has become a black-alley doctor, and while the things she's accused for tend to be fake, she has a sadistic side to her that would put those accusations to shame. ";
                  this.muse.DescLewd = "Sometimes she takes advantage of patients' unconscious or unwell state to have her way with them, or test even more dangerous, lascivious products on them.";
                  this.muse.kinks.partner = "Machines"
                  this.muse.kinks.organ = "Mouth, Cock"
                  this.muse.kinks.clothing = "Latex, Fishnet, Leather"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Non-Con, Stealth"
                  this.muse.kinks.substance = "YES"
                  this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Brainwashing"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos/Body writing"
                  this.muse.kinks.transform = "Gothification, Mechanization"
                  this.muse.MetaTupper = "YES"
                  break;
                case "lust":
                  this.muse.Title = "Medic";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "A disgraced doctor hired by the Phantom Whores, after being sufficiently perverted in the metaverse. She works undercover at Shujin to provide spaces and tools for sexual recreation, test fertility and arousal drugs, and overall assist in Ann and company's mission. While not active in the cognitive world, her real life contributions make her a worthy Phantom Whore.";
                  this.muse.kinks.partner = "Machines"
                  this.muse.kinks.organ = "Mouth, Cock"
                  this.muse.kinks.clothing = "Latex, Fishnet, Leather"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
                  this.muse.kinks.consent = "Dub-Con, Non-Con, Stealth"
                  this.muse.kinks.substance = "YES"
                  this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Brainwashing"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos/Body writing"
                  this.muse.kinks.transform = "Gothification, Mechanization"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "ann":
              this.muse.Name = "Ann Takamaki";
              this.muse.Reg = "Japan, Yongen-Jaya";
              this.muse.SubDom = "Whatever she feels like";
              this.muse.Spec = "Human";
              switch (au) {
                case "persona":
                  this.muse.Title = "";
                  this.muse.Desc = "A fiery girl who works as a model, and goes to school like an average girl. She loves sweets, her girlfriend Shiho, and hates injustice. Feels strongly about how she's perceived by others, be it her womanhood, her sexuality, her race, or her body. And she's perfectly willing to take control and show them all wrong. ";
                  this.muse.DescLewd = "Though at times, she just wants to give in to everyone's perception of her as a bimbo and a slut, and drag her girlfriend down with her.";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Tits, Pussy, Cock"
                  this.muse.kinks.clothing = "Nudity, Latex, Dress-Up"
                  this.muse.kinks.relation = "Servitude, Romance"
                  this.muse.kinks.consent = "Voyeur, Stealth"
                  this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Praise"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "NEUTRAL"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "NEUTRAL"
                  this.muse.MetaTupper = "YES"
                  break;
                case "lust":
                  this.muse.Spec = " / Cognition, Shadow";
                  this.muse.Title = "Panther or Kitten";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "After Ann and Shiho fused with the cognitive versions of themselves in Kamoshida's palace, Ann became every bit the slut she was seen as, but her persona kept her fiery dominance and hatred of Kamoshida. After his defeat, this new Ann has decided to kick the world's libido into high gear, seducing shadows in the cognitive world to turn everyone into perverts, alongside her slutty bunny girlfriend Shiho.";
                  this.muse.kinks.partner = "Monsterfucking (Shadows), Gangbang"
                  this.muse.kinks.organ = "Tits, Pussy, Cock"
                  this.muse.kinks.clothing = "Nudity, Latex, Dress-Up"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Romance"
                  this.muse.kinks.consent = "Free Use, Dub-Con, Exhibition"
                  this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
                  this.muse.kinks.treatment = "YES"
                  this.muse.kinks.bondage = "YES"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak, Brainwashing"
                  this.muse.kinks.bodyMod = "YES"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "sae":
              this.muse.Spec = "Human";
              this.muse.Reg = "Japan, Yongen-Jaya";
              this.muse.Name = "Sae Nijima";
              switch (au) {
                case "persona":
                  this.muse.SubDom = "Dominant unless tired";
                  this.muse.Title = "Prosecutor";
                  this.muse.Desc = "A fierce prosecutor who's eternally overworked, undervalued, and ready to strike. She cares deeply for her sister Makoto, but having to care for her as a mother has greatly twisted and strained their relationship. ";
                  this.muse.DescLewd = "She sees the law as a game of chance that she must manipulate in her favor, and intends to place everyone beneath her heel, with her sister to serve her instead.";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Ass"
                  this.muse.kinks.clothing = "Nylon, Fishnet"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Incest"
                  this.muse.kinks.consent = "Dub-Con, Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Rope, Chains, Hypnosis, Grappling, Environment"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
                  this.muse.MetaTupper = "YES"
                  break;
                case "lust":
                  this.muse.Title = "Miss Fortune";
                  this.muse.SubDom = "Whatever the fortune might bring.";
                  this.muse.SubDomSh = "..though she cheats to always win and dominate.";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "The twisted true self of a prosecutor, fed up with the gambles of the law and intending to make it her own. With assistance from the Phantom Whores, she fused with her non-cognitive self, and made it to the top of the legal ladder through trickery and perversion, letting the PW's perverted actions and goals slide, as they provide pleasure for her as well, in real life or in the metaverse. The shadows of those who stand against perversion, or use it for their own without the enjoyment of the other, are let to suffer and wander her casino forever, their real selves too lost to commit further crimes against lust.";
                  this.muse.kinks.partner = "NEUTRAL"
                  this.muse.kinks.organ = "Ass"
                  this.muse.kinks.clothing = "Nylon, Fishnet"
                  this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Incest"
                  this.muse.kinks.consent = "Dub-Con, Non-Con, Voyeur, Exhibition"
                  this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
                  this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
                  this.muse.kinks.bondage = "Rope, Chains, Hypnosis, Grappling, Environment"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "NEUTRAL"
                  this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
                  this.muse.MetaTupper = "NO"
                  break;
              }
              break;
            case "moni":
              this.muse.Name = "Monika";
              this.muse.NameSh = ".chr";
              this.muse.SubDom = "She'll take charge if necessary, but if you want otherwise she's up for it.";
              this.muse.Title = "Literature Club President";
              this.muse.Spec = "Human ";
              this.muse.SpecSh = "Character File";
              this.muse.Reg = "Close. ";
              this.muse.RegSh = "In your computer, DDLC.exe";
              this.muse.Desc = "The smartest, kindest, most beautiful girl in school, who's decided you are her soulmate, and is distraught by you focusing on the other members of her Literature Club. She will happily use her dedication to make sure you only look at her. ";
              this.muse.DescLewd = "Though, she does find the girls rather attractive herself...she wouldn't mind them around, if they acknowledge her as the head girlfriend. She'll make sure they love her too. She has her ways.";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "Nylon, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Romance"
              this.muse.kinks.consent = "Free Use, Dub-Con, Voyeur, Stealth, Exhibition"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Objectification"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Mindbreak, Brainwashing"
              this.muse.kinks.bodyMod = "Breeding, Love Marks"
              this.muse.kinks.transform = "Bimbofication, Gothification, Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "roty":
              this.muse.Name = "Rottytops";
              this.muse.SubDom = "YES";
              this.muse.Title = "";
              this.muse.Spec = "Zombie";
              this.muse.Reg = "Zombie Caravan";
              this.muse.Desc = "A cheerful zombie who enjoys cosplay and teasing, Rotty is Shantae's bestest undead friend. Despite genuinely caring for Shantae, she's conniving, tricky and naughty in every single way. It's part of her charm, and sorely wishes to 'corrupt' Shantae. ";
              this.muse.DescLewd = "Preferably by dating her, kissing her, eating her out, and doing all sorts of fun stuff to her body.";
              this.muse.kinks.partner = "Machines"
              this.muse.kinks.organ = "YES"
              this.muse.kinks.clothing = "Nudity, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Romance"
              this.muse.kinks.consent = "Free Use, Voyeur, Stealth, Exhibition"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Objectification"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Mindbreak, Brainwashing"
              this.muse.kinks.bodyMod = "Piercings, Branding, Splitting"
              this.muse.kinks.transform = "YES, Zombiefication"
              this.muse.MetaTupper = "YES"
              break;
            case "shan":
              this.muse.Reg = "Scuttle Town";
              this.muse.Title = "Half-Genie Hero";
              this.muse.Name = "Shantae";
              this.muse.Spec = "Genie/Human";
              this.muse.SubDom = "Sub when approached, Dom when approaching";
              this.muse.Desc = "A half-genie hero, worthy of said title by her care for others and dedication to helping...even if it is thwarted by annoyances, both villainous and even allied. She rarely holds any ill will regardless, and has helped her foes if need be a good amount of times. ";
              this.muse.DescLewd = "She is rather aware that she's surrounded by very hot gals, and has given serious thought to fooling around with all of them. Even Risky Boots.";
              this.muse.kinks.partner = "Machines, Monsterfucking"
              this.muse.kinks.organ = "Ass, Tits"
              this.muse.kinks.clothing = "Nylon, Satin, Dress-Up"
              this.muse.kinks.relation = "Enslavement, Servitude, Romance"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Degradation, Objectification, Humiliation"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Brainwashing"
              this.muse.kinks.bodyMod = "NEUTRAL"
              this.muse.kinks.transform = "Bimbofication, Gothification, Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "junko":
              this.muse.Name = "Junko Enoshima";
              this.muse.SubDom = "Dominant unless submission causes her despair";
              this.muse.Title = "Ultimate Despair";
              this.muse.Spec = "Human";
              this.muse.Reg = "Japan";
              this.muse.Desc = "NSFW ONLY - ";
              this.muse.DescLewd = "The ultimate fashionista, but ultimately just a girl who turns despair into pleasure for herself, she wants nothing but to share what she feels with everyone in the world. She's twisted, switches between states of self constantly, and her victory and defeat taste equally good to someone as utterly despairful as herself. There's nothing to hide anymore.";
              this.muse.kinks.partner = "YES"
              this.muse.kinks.organ = "YES"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Incest"
              this.muse.kinks.consent = "Non-Con, Voyeur, Exhibition"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "YES"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Mindbreak, Brainwashing"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "YES"
              this.muse.MetaTupper = "YES"
              break;
            case "nami":
              this.muse.Name = "Chiaki Nanami";
              this.muse.SubDom = "Weak submissive, Shy dom";
              this.muse.Title = "Ultimate Gamer";
              this.muse.Spec = "Human";
              this.muse.SpecSh = ", then Program";
              this.muse.Reg = "Japan";
              this.muse.Desc = "The ultimate gamer, all but for dating sims. She's rather soft-spoken, and gentle, to the point of even second-guessing her own statements and ideas. But ultimately she is well-meaning and easy to get along with by everyone. ";
              this.muse.DescLewd = "Recently she's really been getting into lewd games...with all the kinks they teach. Still as bad at them as in dating sims however.";
              this.muse.kinks.partner = "Machines, Monsterfucking, Gangbang"
              this.muse.kinks.organ = "Tits"
              this.muse.kinks.clothing = "Nylon, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Romance"
              this.muse.kinks.consent = "Dub-Con, Stealth"
              this.muse.kinks.substance = "Lactation, Cum (Inside), Watersports"
              this.muse.kinks.treatment = "NEUTRAL"
              this.muse.kinks.bondage = "NEUTRAL"
              this.muse.kinks.mindMod = "YES"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "YES"
              this.muse.MetaTupper = "YES"
              break;
            case "mikan":
              this.muse.Name = "Mikan Tsumiki";
              this.muse.SubDom = "Filthy submissive, possessive dom";
              this.muse.Title = "Ultimate Nurse";
              this.muse.Spec = "Human";
              this.muse.Reg = "Japan";
              this.muse.Desc = "The ultimate nurse, a nervous wreck of a clumsy gal who can't handle much. A lifetime of abuse and experience at medicine means that she's confident in her healing, and her reading of people's thoughts, yet her self-esteem immediately assumes she's wrong at the latter if it's positive stuff about her. ";
              this.muse.DescLewd = "Her clumsiness is intended to appease, and she cannot handle the thought of not being abused, used and harassed. If given even the slightest bit of affection, she'll cling hard and mindlessly, and she lets loose all her ugly feelings and needs if sufficiently annoyed. ";
              this.muse.kinks.partner = "Toys, Bestiality, Gangbang"
              this.muse.kinks.organ = "YES"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Romance"
              this.muse.kinks.consent = "Free-Use, Exhibition"
              this.muse.kinks.substance = "YES"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "YES"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break;
            case "layer":
              this.muse.Name = "Layer";
              this.muse.SubDom = "Subby until she gains confidence in the relationship";
              this.muse.Title = "Operator";
              this.muse.Spec = "Reploid";
              this.muse.Reg = "Galápagos Islands";
              this.muse.Desc = "The picture of a professional and capable Navigator Reploid..until romance comes into play. At which point she'll become a flustered, shy disaster. Good thing her bangs cover her eyes...even if her top doesn't cover the bottom of her chest.";
              this.muse.DescLewd = "Gaining enough confidence in her romantic situation unlocks her confident mommy side...but it's a slow burn to get there. Before however? She'll let her interest do whatever they want to her.";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "Tits"
              this.muse.kinks.clothing = "Nylon, Dress-Up"
              this.muse.kinks.relation = "Servitude, Romance"
              this.muse.kinks.consent = "Free Use, Voyeur, Stealth"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Tentacles, Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "Bimbofication, Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "ruler":
              this.muse.Name = "";
              this.muse.NameSh = "Artoria Pendragon";
              this.muse.SubDom = "Dominant unless you win";
              this.muse.Title = "Ruler";
              this.muse.Spec = "Heroic Spirit ";
              this.muse.SpecSh = " (Heavenly)";
              this.muse.Reg = "???";
              this.muse.Desc = "A woman who enjoys food and battle, turned human heroic spirit, and grown into a Heaven Heroic Spirit. While much more composed due to her growth, flashes of her battle-hungry (and general appetite hungry) self still shine through at times. Currently she is enjoying the world once more, this time as the greatest casino dealer. ";
              this.muse.DescLewd = "Another kind of hunger has awakened in her more mature form, and she will feed on it kindly if finding a victor, or harshly if finding a cheater.";
              this.muse.kinks.partner = "Bestiality"
              this.muse.kinks.organ = "Mouth, Tits"
              this.muse.kinks.clothing = "Nylon, Fishnet, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Servitude"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth, Exhibition"
              this.muse.kinks.substance = "NEUTRAL"
              this.muse.kinks.treatment = "Praise, Ryona"
              this.muse.kinks.bondage = "Rope, Chains, Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "NEUTRAL"
              this.muse.kinks.bodyMod = "Breeding, Tattoos/Body writing"
              this.muse.kinks.transform = "Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "ridem":
              this.muse.Name = "";
              this.muse.NameSh = "Medusa";
              this.muse.SubDom = "Indifferent switch";
              this.muse.Title = "Rider";
              this.muse.Spec = "Heroic Spirit";
              this.muse.Reg = "???";
              this.muse.Desc = "A woman who conceals both her emotions and eyes, hiding beauty and horrors behind both. She is completely loyal to her Master, and is not ultimately cruel, though she is hampered by a great deal of self-consciousness. ";
              this.muse.DescLewd = "She also hides a lot of care, for those who reciprocate loyalty to her, or those who remind of herself. Only with them will she let her emotions out...all of them. Very enthusiastically.";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "Pussy, Cock"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Enslavement, Servitude, Romance"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
              this.muse.kinks.substance = "Sweating, Cumplay (Inside), Watersports"
              this.muse.kinks.treatment = "Praise"
              this.muse.kinks.bondage = "Snakes, Chains, Hypnosis, Grappling, Sense Deprivation"
              this.muse.kinks.mindMod = "Mindbreak"
              this.muse.kinks.bodyMod = "Piercing, Tattoos/Body writing"
              this.muse.kinks.transform = "Mechanization"
              this.muse.MetaTupper = "YES"
              break;
            case "brdgt":
              this.muse.Name = "Bridget";
              this.muse.SubDom = "Swinging Switch";
              this.muse.Title = "Bounty Huntress";
              this.muse.Spec = "Human";
              this.muse.Reg = "England";
              this.muse.Desc = "A very prolific bounty hunter who's recently accepted herself as a huntress. She's a bit of an airhead and a show-off, and extremely polite, though her bounties see a rougher side of her, that doesn't detracts from her loveliness much. ";
              this.muse.DescLewd = "Accepting herself has massively increased her sexual interest, and she's looking forward to becoming both a sexy cock-y domme, and an absolute slut to be railed. So long as her gender's acknowledged, she'd happily go either way. She's always been ambitious!";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "Ass, Cock"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Petplay, Romance"
              this.muse.kinks.consent = "Free Use, Stealth"
              this.muse.kinks.substance = "Cumplay, Watersports, Estrogen"
              this.muse.kinks.treatment = "Praise, Objectification, Humiliation"
              this.muse.kinks.bondage = "Rope, Hypnosis, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "NEUTRAL"
              this.muse.kinks.transform = "Bimbofication"
              this.muse.MetaTupper = "YES"
              break;
          }
          break;
        case 5:
          switch (char) {
            case "beni":
              this.muse.Name = "Kobeni Higashiyama";
              this.muse.SubDom = "Broken Submissive";
              this.muse.Title = "";
              this.muse.Spec = "Human";
              this.muse.SpecSh = " (Makima's Puppy, Power's Cow)";
              this.muse.Reg = "Japan";
              this.muse.Desc = "A hot mess and nervous wreck of a girl who's found some level of safety and ease in following the commands of her fellow coworkers and superiors, particularly Makima and Power. ";
              this.muse.DescLewd = "She enjoy being their pet, what bodily additions they've made her get, and wants everyone to drink her milk, and know she's owned. Really really likes it when Power yells at her.";
              this.muse.kinks.partner = "Monsterfucking"
              this.muse.kinks.organ = "Tits, Cock"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Petplay, Enslavement, Romance"
              this.muse.kinks.consent = "Free Use, Exhibition"
              this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "Rope, Chains, Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption, Brainwashing"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication"
              this.muse.MetaTupper = "YES"
              break;
            case "marin":
              this.muse.SubDom = "YES";
              this.muse.Title = "";
              this.muse.Reg = "Japan";
              this.muse.Name = "Marin Kitagawa";
              this.muse.Spec = "Human";
              this.muse.Desc = "A girl who loves what she loves, and isn't ashamed of it. In this case, it's eroges, and cosplay, and her beloved Shizuku-tan (who she has cosplayed, from an eroge). For all her lack of shame in body and tastes, she gets quite flustered at romantic affairs. ";
              this.muse.DescLewd = "She will shamelessly endorse and enjoy the most degenerate, girl-degrading stuff, having internalized a lot of stuff from her porn.";
              this.muse.kinks.partner = "YES"
              this.muse.kinks.organ = "Pussy, Cock"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Servitude, Romance"
              this.muse.kinks.consent = "YES"
              this.muse.kinks.substance = "Cumplay, Watersports"
              this.muse.kinks.treatment = "YES"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication, Gothification, Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "lucy":
              this.muse.Name = "Lucyna Kushinada";
              this.muse.SubDom = "Totally in control";
              this.muse.Title = "";
              this.muse.Spec = "Human (Enhanced)";
              this.muse.Reg = "Night City, California";
              this.muse.Desc = "An introverted netrunner who uses her looks for her advantage, as innocent or seductive as is needed to survive. She dreams of one day reaching the Moon and escaping the prison that is the city she lives in. ";
              this.muse.DescLewd = "Sometimes she fantasizes of taking over AND rule from the moon, make the world her bitch, starting with one short, loud girl who she'd love to pick up and break.";
              this.muse.kinks.partner = "Machines, Gangbang"
              this.muse.kinks.organ = "NEUTRAL"
              this.muse.kinks.clothing = "Latex, Leather, Nylon, Living, Dress-Up"
              this.muse.kinks.relation = "Enslavement, Servitude"
              this.muse.kinks.consent = "NEUTRAL"
              this.muse.kinks.substance = "Sweat, Cumplay, Watersports, Smoking"
              this.muse.kinks.treatment = "YES"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Corruption, Brainwashing"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "YES"
              this.muse.MetaTupper = "YES"
              break;
            case "yor":
              this.muse.TitleSh = "Thorn Princess";
              this.muse.Reg = "Ostonia";
              this.muse.Name = "Yor Forger nee Briar";
              this.muse.SubDom = "Dommy Mommy until genuinely cared and adored for";
              this.muse.Spec = "Human";
              this.muse.Desc = "The greatest assassin and mother, Yor took up killing to provide for her brother, and now her family. She's terrible at lying and cooking, but she gives her all for who she cares for. There are no more secrets between her and her 'fake' husband. ";
              this.muse.DescLewd = "He's okay with her sleeping around, so long as she does it in secret. She finds it thrilling, and has fooled around with her coworkers, his coworkers, Eden parents, and even some survivors of her missions.";
              this.muse.kinks.partner = "NEUTRAL"
              this.muse.kinks.organ = "Ass, Tits"
              this.muse.kinks.clothing = "Latex, Leather, Living, Dress-Up"
              this.muse.kinks.relation = "Enslavement, Servitude, Romance, Incest"
              this.muse.kinks.consent = "Dub-Con, Stealth"
              this.muse.kinks.substance = "Lactation, Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Ryona, Objectification"
              this.muse.kinks.bondage = "Chains, Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Bimbofication"
              this.muse.MetaTupper = "YES"
              break;
            case "stock":
              this.muse.Title = "";
              this.muse.Reg = "Japanifornia, Daten City";
              this.muse.Name = "Stocking Anarchy";
              this.muse.SubDom = "Dominant unless given the right motivation";
              this.muse.Spec = "Angel";
              this.muse.SpecSh = " or Demon";
              this.muse.Desc = "A relatively professional ghost-destroying angel, Stocking adores sweets and mocks sex, in defiance of her loose and sweet-hating sister. She perfectly combines gothic and sweet lolita styles, just as well as she is both sweetness and seriousness. ";
              this.muse.DescLewd = "Despite often making fun of Scanty and Kneesocks for their incestual, BDSM-heavy life, she herself is aroused by those things as well. And she will do anything for sweets.";
              this.muse.kinks.partner = "YES"
              this.muse.kinks.organ = "Mouth, Cock"
              this.muse.kinks.clothing = "Frills, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement, Romance, Incest"
              this.muse.kinks.consent = "Dub-Con, Non-Con, Exhibition"
              this.muse.kinks.substance = "Foodplay, Sweat, Cumplay, Watersports"
              this.muse.kinks.treatment = "Degradation, Ryona, Objectification, Humiliation"
              this.muse.kinks.bondage = "Tentacles, Rope, Chains, Environment"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "frie":
              this.muse.Title = "";
              this.muse.Reg = "N/A: Traveling";
              switch (au) {
                case "frieren":
                  this.muse.Name = "Frieren";
                  this.muse.SubDom = "Experimental Switch";
                  this.muse.Spec = "Elf";
                  this.muse.Desc = "An ancient elf who loves magic, hates demons, and is otherwise a mess. Despite being the world's greatest mage, she has rookie mistakes, and can't resist mimics. She's still getting the hang of human lifespans. ";
                  this.muse.DescLewd = "While elves have a low sex drive, she IS interested in the topic, and having fun with it. Just as magic, she looks for objects and tomes about it, and she's the greatest layer, even if she has some gaps.";
                  this.muse.kinks.partner = "Monsterfucking (Mimics, Demons)"
                  this.muse.kinks.organ = "Mouth"
                  this.muse.kinks.clothing = "Nudity"
                  this.muse.kinks.relation = "Petplay, Enslavement"
                  this.muse.kinks.consent = "Free Use, Voyeur"
                  this.muse.kinks.substance = "Cumplay (Outside), Watersports"
                  this.muse.kinks.treatment = "Praise, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Corruption, Mindbreak"
                  this.muse.kinks.bodyMod = "Piercing, Tattoos/Body writing"
                  this.muse.kinks.transform = "Bimbofication, Gothification"
                  this.muse.MetaTupper = "YES"
                  break;
                case "mimic":
                  this.muse.Name = "Frieren?";
                  this.muse.SubDom = "Carnivore";
                  this.muse.Spec = "Elf";
                  this.muse.SpecSh = " / Mimic";
                  this.muse.Desc = "NSFW ONLY - ";
                  this.muse.DescLewd = "Once a great mage, she is now a monster of sorts herself. Her outfit can change to what she wills, even if it'll always be a little tight. She goes around breeding women for new mimic eggs, and alluring travelers into some more advanced mimics. Demons love the new Frieren, and she quite loves herself too. None know if she's still Frieren but too fallen into pleasure to retrieve, or a mimic that's copied her form and mannerisms. Not even herself.";
                  this.muse.kinks.partner = "Monsterfucking (Mimics, Demons)"
                  this.muse.kinks.organ = "Mouth"
                  this.muse.kinks.clothing = "Living Clothes"
                  this.muse.kinks.relation = "Enslavement, Incest"
                  this.muse.kinks.consent = "Non-Con, Stealth"
                  this.muse.kinks.substance = "Lactation, Cumplay (Inside), Watersports, Aphrodisiacs"
                  this.muse.kinks.treatment = "Ryona, Objectification"
                  this.muse.kinks.bondage = "Tentacles, Hypnosis, Environment, Sense Deprivation"
                  this.muse.kinks.mindMod = "Brainwashing"
                  this.muse.kinks.bodyMod = "Breeding"
                  this.muse.kinks.transform = "Mimicry"
                  this.muse.MetaTupper = "YES"
                  break;
              }
              break;
            case "fern":
              this.muse.Title = "";
              this.muse.Reg = "N/A: Traveling";
              this.muse.Name = "Fern";
              this.muse.SubDom = "Resigned bottom, frustrated top";
              this.muse.Spec = "Human";
              this.muse.Desc = "A young girl being taught by Frieren, though half the time she's taking care of her over poor habits. She tries to embody the simple enjoyment of magic by itself, though she's quick to frustrate and anger. ";
              this.muse.DescLewd = "Unfortunately dragged along commonly to her master's sex-periments, usually having to play nice until it's done. Thankfully used to taking her frustrations out on her in private, in control.";
              this.muse.kinks.partner = "Monsterfucking"
              this.muse.kinks.organ = "Tits, Cock"
              this.muse.kinks.clothing = "NEUTRAL"
              this.muse.kinks.relation = "Servitude, Incest"
              this.muse.kinks.consent = "Dub-Con, Stealth, Exhibition"
              this.muse.kinks.substance = "Lactation, Sweating, Cumplay (/Inside), Watersports"
              this.muse.kinks.treatment = "YES"
              this.muse.kinks.bondage = "Tentacles, Grappling"
              this.muse.kinks.mindMod = "Mindbreak"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "Bimbofication, Gothification"
              this.muse.MetaTupper = "YES"
              break;
            case "paru":
              this.muse.Name = "Paru Amano";
              this.muse.SubDom = "Needy nympho switch";
              this.muse.Title = "Public Address Sound Engineer (PA-san)";
              this.muse.Spec = "Human";
              this.muse.Reg = "Japan";
              this.muse.Desc = "An easygoing woman working at Starry's after dropping out of high school, and doing vtubing on the side. Despite her sweetness and ease, she's actually somewhat insecure about presence, as she's not super active as a vtuber, and outside of that she works behind the scenes. ";
              this.muse.DescLewd = "She's incredibly aroused and perverted though, and is not shy in using her assets to get off, feeling quite confident in the throes of lust.";
              this.muse.kinks.partner = "Gangbang, Machine"
              this.muse.kinks.organ = "Tits, Cock"
              this.muse.kinks.clothing = "Latex, Leather, Fishnet"
              this.muse.kinks.relation = "Enslavement, Servitude"
              this.muse.kinks.consent = "Free Use, Dub-Con, Stealth, Exhibition"
              this.muse.kinks.substance = "Cumplay, Watersports, Smoking"
              this.muse.kinks.treatment = "Praise, Degradation, Objectification, Humiliation"
              this.muse.kinks.bondage = "Tentacles, Chains, Grappling"
              this.muse.kinks.mindMod = "Corruption, Mindbreak"
              this.muse.kinks.bodyMod = "Piercing, Tattoos"
              this.muse.kinks.transform = "Gothification, Twinning"
              this.muse.MetaTupper = "YES"
              break;
            case "clare":
              this.muse.Name = "Claire François";
              this.muse.SubDom = "Powerful top, flustered tsundere if caught offguard";
              this.muse.Spec = "Human";
              this.muse.Reg = "Bauer Kingdom";
              this.muse.RegSh = ", Earth";
              this.muse.Desc = "A fiery, strong-willed girl who's proud to be a noble, without taking it and it's intended purpose for granted. She does her utmost at all she tries, and tries to project confidence. ";
              this.muse.DescLewd = "Despite secretly being very vulnerable, she does have somewhat of a sadistic, dominating streak, and if she found enough strength in herself or faith in those drawn to her, she's willing to make a mess of them.";
              this.muse.kinks.partner = "Toys"
              this.muse.kinks.organ = "Mouth, Pussy"
              this.muse.kinks.clothing = "Nudity, Dress-Up"
              this.muse.kinks.relation = "Petplay, Servitude, Romance, Incest,"
              this.muse.kinks.consent = "Dub-Con, Voyeur, Stealth"
              this.muse.kinks.substance = "Lactation"
              this.muse.kinks.treatment = "Praise, Objectification"
              this.muse.kinks.bondage = "Rope, Grappling, Environment, Sense Deprivation"
              this.muse.kinks.mindMod = "Corruption"
              this.muse.kinks.bodyMod = "Tattoos/Body writing"
              this.muse.kinks.transform = "Bimbofication"
              this.muse.MetaTupper = "YES"
              break
            case "utena":
              this.muse.Name = "Utena Hiiragi";
              this.muse.SubDom = "Deranged dominant";
              this.muse.Title = "Magia Baiser";
              this.muse.Spec = "Human";
              this.muse.Reg = "Japan";
              this.muse.Desc = "NSFW ONLY - ";
              this.muse.DescLewd = "A sullen plain girl who loves magical girls and...is enthusiastic about BDSM. She has found a ground in common in putting her current locals through sexual villainous scenarios, to see them overcome them. Though things are more complicated than that usually, she's happy to indulge in her girls and her tastes.";
              this.muse.kinks.partner = "Toys/Machines, Monsterfucking"
              this.muse.kinks.organ = "Tits, Ass"
              this.muse.kinks.clothing = "Latex, Dress-Up"
              this.muse.kinks.relation = "Petplay, Enslavement"
              this.muse.kinks.consent = "Dub-Con, Non-Con, Voyeur, Exhibition"
              this.muse.kinks.substance = "YES"
              this.muse.kinks.treatment = "YES"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "YES"
              this.muse.kinks.bodyMod = "YES"
              this.muse.kinks.transform = "NEUTRAL"
              this.muse.MetaTupper = "YES"
              break
            case "ursa":
              this.muse.Name = "Ursula Callistis";
              this.muse.NameSh = " Chariot du Nord";
              this.muse.SubDom = "Service switch, eyes on her.";
              this.muse.Title = "Luna Nova Astronomy Teacher";
              this.muse.Spec = "Human (Witch)";
              this.muse.Reg = "London, Luna Nova";
              this.muse.Desc = "A clumsy, nervous woman new to teaching at Luna Nova, who seems to know a lot about short time idol and former student Shiny Chariot. She cares truly for her students and her subject, particularly Akko, the only student from a non-magical family. ";
              this.muse.DescLewd = "She actually IS Chariot, trying to guide Akko to fulfill the fate she failed. She yearns some for the adoration of a captive audience, and is tempted to show a little more of her body to get said looks onto her, though her self-esteem needs some work and stops her from doing so.";
              this.muse.kinks.partner = "Toys/Machines, Monsterfucking, Gangbang"
              this.muse.kinks.organ = "Mouth, Ass"
              this.muse.kinks.clothing = "Dress-Up"
              this.muse.kinks.relation = "Servitude, Romance"
              this.muse.kinks.consent = "Dub-Con, Exhibition"
              this.muse.kinks.substance = "Sweating, Cumplay, Watersports"
              this.muse.kinks.treatment = "Praise, Objectification"
              this.muse.kinks.bondage = "YES"
              this.muse.kinks.mindMod = "Mindbreak, Brainwashing"
              this.muse.kinks.bodyMod = "Breeding"
              this.muse.kinks.transform = "Bimbofication, Gothification"
              this.muse.MetaTupper = "YES"
              break
          }
          break;
      }
      this.currentMuseCode = char;
      this.currentAreaCode = area;
      this.currentmuseAULst = aus
      this.muse.auArray = aus
      this.currentAU = au;
      for (var i = 0; i < this.finalCharArr.length; i++) {
        if (this.finalCharArr[i].code == char) {
          if (au == this.finalCharArr[i].states[0]) {
            console.log(au)
            this.muse.FreePlay = this.finalCharArr[i].free
          } else {
            console.log("au")
            this.muse.FreePlay = "Already AU"
          }
        }
      }
      if (this.auListDataBring(this.currentmuseAULst[0]).sfw == "N") {
        this.nsfwSwitchSafe = false
      } else {
        this.nsfwSwitchSafe = true
      }
      this.museDialog = true;
    },
    cleanData() {
      this.muse.Name = "";
      this.muse.NameSh = "";
      this.muse.SubDom = "";
      this.muse.SubDomSh = "";
      this.muse.Title = "";
      this.muse.TitleSh = "";
      this.muse.Spec = "";
      this.muse.SpecSh = "";
      this.muse.Reg = "";
      this.muse.RegSh = "";
      this.muse.Desc = "";
      this.muse.DescLewd = "";
      this.muse.auArray = [];
      this.muse.MetaTupper = "";
      this.muse.MetaTupper = "";
      this.muse.kinks.partner = ""
      this.muse.kinks.organ = ""
      this.muse.kinks.clothing = ""
      this.muse.kinks.relation = ""
      this.muse.kinks.consent = ""
      this.muse.kinks.substance = ""
      this.muse.kinks.treatment = ""
      this.muse.kinks.bondage = ""
      this.muse.kinks.mindMod = ""
      this.muse.kinks.bodyMod = ""
      this.muse.kinks.transform = ""
      this.muse.MetaTupper = "YES"
    },
  },
  mounted() {
    this.dataFill();
  },
});
</script>
<style>
@media screen and (min-width: 980px) {
  .iconMuseTable {
    font-size: 64px;
  }

  .buttonTable {
    font-size: 14px;
  }

  .my-sticky-header-table {
    width: 1000px;
  }

  .aubutton {
    font-size: 40px;
  }

  .button {
    background: white;
    color: black;
    font-size: 14px
  }
}

@media screen and (max-width: 980px) {
  .iconMuseTable {
    font-size: 50px;
  }

  .buttonTable {
    font-size: 10px;
  }

  .aubutton {
    font-size: 32px;
  }

  .button {
    background: white;
    color: black;
    font-size: 10px
  }
}

.au {
  background: #cf4cc9;
  color: white;
}

#muse {
  background: #cf4cc9;
  color: white;
  width: 700px;
}

.cardHolder {
  padding: 0 4%;
  gap: 12px;
}

.uniMusesHier {
  height: 108px;
  width: 540px
}

.uniMusesNoHier {
  height: 210px;
  width: 540px
}

.museScrollArea {
  margin-bottom: 60px;
  margin-top: 60px;
  padding: 0 4%;
  gap: 12px;
}

.buttonTable {
  background: white;
  color: black;
  margin: 2px;
}

.button[disabled] {
  background: rgb(158, 158, 158);
  color: rgb(92, 92, 92);
  opacity: 1 !important;
}

.secret {
  color: black;
  background-color: black;
}

.scrollheader {
  background-color: #5a0a58;
}

.secret:hover {
  color: white;
}

.cardMuse {
  background: #cf4cc9d9;
  color: white;
  max-width: 970px;
  width: fit-content;
}



.my-sticky-header-table {
  height: 500px;
}

.q-table__top,
.q-table__bottom,
thead tr:first-child th {
  background-color: #5a0a58;
}

thead tr th {
  position: sticky;
  z-index: 1;
}

thead tr:first-child th {
  top: 0;
}

.q-table--loading thead tr:last-child th {
  top: 48px;
}

tbody {
  scroll-margin-top: 48px;
}

body {
  background-image: url("/images/mirrorbg.jpg");
  background-size: cover;
  background-position: center;
}

.q-body--fullscreen-mixin,
.q-body--prevent-scroll {
  position: relative !important;
}
</style>
