<template>
   <div class="cardHolder flex-center q-pt-sm">
      <q-card class="card">
         <q-card-section>
            <div class="row flex-center text-subtitle2 text-center q-pa-sm"> A glimpse into the girls who've found
               pleasure
               through the Mirror Mistress...</div>
            <div class="row flex-center">
               <div class="col-xs-auto q-pa-sm" v-for="sect in sectBtn">
                  <div class="row flex-center"><q-btn class="button" :dense="$q.screen.lt.xs"
                        :disabled="section == sect.index" @click="section = sect.index">{{ sect.label }}</q-btn>
                  </div>
               </div>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <div class="cardHolder flex-center q-pt-sm" v-if="section == 1">
      <q-card class="card">
         <q-card-section>
            <div class="row justify-center">
               <div class="text-h6 q-pa-sm justify-center">MIRROR'S CONDITIONS
               </div>
            </div>
            <div class="row flex-center">
               <div class="col-sm-12 col-md-6">
                  <div class="row text-subtitle2 q-pa-sm justify-center"> ❤ PREFERENCES ❤</div>
                  <div class="row text-body2 q-pa-sm justify-start"> ❤ English/Spanish RP</div>
                  <div class="row text-body2 q-pa-sm justify-start"> ❤ Intersex/Futa muses by default, you may ask for
                     cis/trans
                     version</div>
                  <div class="row text-body2 q-pa-sm justify-start"> ❤ Drawn to women, monsters, or evil groups</div>
               </div>
               <div class="col-sm-12 col-md-6">
                  <div class="row text-subtitle2 q-pa-sm justify-center"> ✖ LIMITS ✖ </div>
                  <div class="row text-body2 q-pa-sm justify-start"> ✖ Scat, Excessive pain, Cutting, Needles</div>
                  <div class="row text-body2 q-pa-sm justify-start"> ✖ Excessive temperature or voltage play</div>
                  <div class="row text-body2 q-pa-sm justify-start"> ✖ Snuff, Human Vore/Unbirth, Drugs</div>
               </div>
            </div>
            <div class="row flex-center">
               <div class="col-xs-12">
                  <div class="row text-subtitle2 q-pa-sm text-center justify-center"> ✖ CHARACTERS IN REST ✖ </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Rottytops (Shantae)</div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Junko Enoshima, Chiaki Nanami
                     (Danganronpa)</div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Tooru Hagakure (BNHA)</div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Kobeni Higashiyama (Chainsaw Man)
                  </div>
               </div>
            </div>
            <div class="row flex-center">
               <div class="col-xs-12">
                  <div class="row text-subtitle2 q-pa-sm text-center justify-center"> ✖ WARNINGS ✖ </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Minors, i waited till I was 19, so
                     should you
                  </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Images for icons and slideshows not
                     my own,
                     nor claim them to be so. </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Parody account, not officially
                     affiliated with
                     any company, nor pose a canonical representation of the characters. </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> Mun uses the terms futa/intersex
                     interchangeably,
                     and will use whichever one partner is more comfy with. </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> All muses strictly over 18 years
                     old. </div>
                  <div class="row text-body2 q-pa-sm text-center justify-center"> FANTASY RP EXPLORATION =/= PERSONAL
                     ETHICAL BELIEF. If you don't enjoy the kink don't engage with it, i have tons others of them!
                  </div>
               </div>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <div class="cardHolder flex-center q-pt-sm" v-if="section == 2">
      <q-card class="card">
         <q-card-section>
            <div class="row flex-center">
               <div class="col-auto">
                  <div class="row text-body2 q-pa-sm justify-start">{{ lore.par1 }}</div>
                  <div class="row text-body2 q-pa-sm justify-start">{{ lore.par2 }}</div>
                  <div class="row text-body2 q-pa-sm justify-start">{{ lore.par3 }}</div>
               </div>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <div class="cardHolder flex-center q-pt-sm" v-if="section == 3">
      <q-card :class="{ cardMuse: museSect != 5, cardAllMuse: museSect == 5 }">
         <q-card-section>
            <div class="row flex-center q-pa-xs">
               <q-btn-group class="button">
                  <q-btn class="button" @click="museSect = 1" :disabled="museSect == 1" label="Nintendo" />
                  <q-btn class="button" @click="museSect = 2" :disabled="museSect == 2" label="Games" />
                  <q-btn class="button" @click="museSect = 3" :disabled="museSect == 3" label="MHA" />
                  <q-btn class="button" @click="museSect = 4" :disabled="museSect == 4" label="Anime" />
                  <q-btn class="button" @click="museSect = 5" :disabled="museSect == 5" label="All" />
               </q-btn-group>
            </div>
            <div class="row flex-center q-pa-xs" v-if="museSect != 0"></div>
            <div class="row flex-center">
               <q-btn v-for="(char, c) in allCharArr" square padding="xs" flat
                  v-show="char.sect == museSect || museSect == 5"
                  @click="museProfileOpen(char.sect, char.code, baseAU)">
                  <q-avatar square :class="{ museImg: museSect != 5, allmuseimg: museSect == 5 }">
                     <img :src="char.avatar">
                  </q-avatar>
               </q-btn>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <div class="cardHolder flex-center q-pt-sm" v-if="section == 4">
      <q-card class="card">
         <q-card-section>
            <div class="row text-body2 q-pa-sm justify-center text-center"> Groups that corrupt iterations of the
               mirror's muses, or groups of muses with something in common, endorsed and supported by the Mirror
               Mistress.
            </div>
            <div class="row flex-center q-pa-sm">
               <q-btn circle padding="xs" flat @click="groupShow(group.name)" v-for="(group, g) in allygroups" :name="g"
                  :key="group">
                  <q-avatar circle class="groupIcon">
                     <img :src="group.emblem">
                  </q-avatar>
               </q-btn>
            </div>
            <div class="row text-subtitle2 q-pa-sm justify-center" v-if="allyDialog == true"> {{ ally.title }}</div>
            <div class="row text-body2 q-pa-sm justify-start" v-if="allyDialog == true"> {{ ally.description }}
            </div>
            <div class="row text-body2 q-pa-sm justify-start" v-if="allyDialog == true">
               <p><b>Mirror Muses Involved:</b></p>
            </div>
            <div class="row q-pa-sm justify-start" v-if="allyDialog == true">
               <div class="row">
                  <div class="col-xs-auto" v-for="(char, c) in museAllies">
                     <div class="row justify-center">
                        <q-btn square padding="xs" flat @click="museProfileOpen(char.sect, char.code, char.au)">
                           <q-avatar rounded class="grupMuseImg">
                              <img :src="char.avatar">
                           </q-avatar>
                        </q-btn>
                     </div>
                     <div class="row justify-center" v-if="groupPos != ''"> {{ char.groupPos }}</div>
                  </div>
               </div>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <div class="cardHolder flex-center q-pt-sm" v-if="section == 5">
      <q-card class="card">
         <q-card-section>
            <div class="row text-body2 q-pa-sm justify-start"> A glossary and definition of kinks shared by the members
               of the Mirror, albeit in diverse intensities per member (To Be Included)</div>
            <div class="row q-pa-sm justify-center">
               <div class="col-xs-3 col-md-3">
                  <div class="row flex-center" v-for="(term, t) in knkGlosBtn"><q-btn style="width: 150px"
                        class="button" :disabled="kinkCat == term.index" @click="kinkGlossary(term.index)">{{
                  term.label }}</q-btn>
                  </div>
               </div>
               <div class="col-xs-9 col-md-9" v-if="knkGloscatDesc != ''">
                  <div class="row text-body2 q-pa-sm justify-start" v-if="knkGloscatDesc != ''"> {{
                  knkGloscatDesc }}</div>
                  <q-separator dark v-if="knkGloscatDesc != ''" />
                  <div class="row text-body2 q-pa-sm justify-start" v-for="kink in kinkGloss" v-show="kink != ''">{{
                  kink }}</div>
               </div>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <q-dialog v-model="museDialog" @keyup.left="museSwitch(1)" @keyup.right="museSwitch(2)"
      @keyup.down="slideKeyboard(2)" @keyup.up="slideKeyboard(1)" @keyup.x="museDialog = false">
      <q-card id="muse">
         <q-card-section class="q-pa-sm flex-center">
            <div class="row q-pa-sm flex-center">
               <div class="col-xs-12 col-md-7">
                  <div class="row justify-center q-pa-xs">
                     <q-btn-group class="button">
                        <q-btn class="button" @click="museDataCheck = 1" :disabled="museDataCheck == 1" label="Data" />
                        <q-btn class="button" @click="museDataCheck = 2" :disabled="museDataCheck == 2" label="Kinks" />
                     </q-btn-group>
                  </div>
                  <div v-if="museDataCheck == 1">
                     <div class="row text-body2 q-pa-xs justify-start">
                        <div class="col-xs-3 col-sm-2"><b>Name:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Name }}<span class="secret">{{ muse.NameSh }}</span>
                        </div>
                        <div class="col-xs-3 col-sm-2"><b>Species:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Spec }}<span class="secret">{{ muse.SpecSh }}</span>
                        </div>
                     </div>
                     <div class="row text-body2 q-pa-xs justify-start">
                        <div class="col-xs-3 col-sm-2"><b>Universe:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Uni }}<span class="secret">{{ muse.UniSh }}</span>
                        </div>
                        <div class="col-xs-3 col-sm-2"><b>Region:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Reg }}<span class="secret">{{ muse.RegSh }}</span>
                        </div>
                     </div>
                     <div class="row text-body2 q-pa-xs justify-start">
                        <div class="col-sm-12 col-md-2"><b>Bio:</b></div>
                        <div class="col-sm-12 col-md-10">{{ muse.Desc }}<span class="secret">{{ muse.DescSh
                              }}</span>
                        </div>
                     </div>
                     <div class="row text-body2 q-pa-xs justify-start">
                        <div class="col-sm-12 col-md-2"><b>Dom/Sub:</b></div>
                        <div class="col-sm-12 col-md-10">{{ muse.SubDom }}<span class="secret">{{ muse.SubDomSh
                              }}</span>
                        </div>
                     </div>
                     <div class="row text-body2 q-pa-xs justify-start items-center" v-if="muse.auArray.length != 1">
                        <div class="col-sm-12 col-md-2"><b>Variants:</b></div>
                        <div class="col-xs-auto">
                           <q-btn v-for="variant in muse.auArray" :key="variant.au" circle flat padding="xs"
                              :disabled="variant.check"
                              @click="museProfileOpen(variant.area, currentMuseCode, variant.au)">
                              <q-avatar circle size="45px">
                                 <img :src="variant.emblem">
                              </q-avatar>
                           </q-btn>
                        </div>
                     </div>
                  </div>
                  <div v-if="museDataCheck == 2">
                     <div class="row q-pa-sm justify-start">
                        <q-card class="kinklist">
                           <q-card-section>
                              <div class="row justify-start">
                                 <div class="col-xs-6">
                                    <q-expansion-item v-for="(content, cat) in muse.kinksA" group="kinks" :label="cat"
                                       dense>
                                       <q-card class="kinkitem">
                                          <q-card-section>
                                             <div class="row text-body2 justify-start" v-for="(kink, k) in content"
                                                v-show="kink != ''">
                                                <p>{{ kinkA[cat][k] }}<span v-if="kink != 'YES'">: {{
                  kink }}</span></p>
                                             </div>
                                          </q-card-section>
                                       </q-card>
                                    </q-expansion-item>
                                 </div>
                                 <div class="col-xs-6">
                                    <q-expansion-item v-for="(content, cat) in muse.kinksB" group="kinks" :label="cat"
                                       dense>
                                       <q-card class="kinkitem">
                                          <q-card-section>
                                             <div class="row text-body2 justify-start" v-for="(kink, k) in content"
                                                v-show="kink != ''">
                                                <p>{{ kinkB[cat][k] }}<span v-if="kink != 'YES'">: {{
                  kink }}</span></p>
                                             </div>
                                          </q-card-section>
                                       </q-card>
                                    </q-expansion-item>
                                 </div>
                              </div>
                           </q-card-section>
                        </q-card>
                     </div>
                  </div>
                  <div class="row justify-center">
                     <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" flat @click="museSwitch(1)">
                              <q-icon left size="1rem" name="arrow_back" />
                              <div>Prev</div>
                           </q-btn>
                        </div>
                     </div>
                     <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" flat @click="museDialog = false">
                              <q-icon left size="1rem" name="close" />
                              <div>Close</div>
                           </q-btn>
                        </div>
                     </div>
                     <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" flat @click="museSwitch(2)">
                              <q-icon left size="1rem" name="arrow_forward" />
                              <div>Next</div>
                           </q-btn></div>
                     </div>
                  </div>
               </div>
               <div class="col-xs-12 col-md-5">
                  <q-carousel control-color="purple" animated v-model="slide" arrows vertical navigation infinite
                     height="500px">
                     <q-carousel-slide v-for="(version, v) in muse.slideArray" :name="v" :key="v">
                        <div class="row fit flex-center">
                           <q-img :src="version.pic" style="max-height: 480px" fit="contain">
                              <div class="absolute-top text-body-1 text-center custom-cap" v-if="version.name != ''">
                                 {{ version.name }}
                              </div>
                           </q-img>
                        </div>
                     </q-carousel-slide>
                  </q-carousel>
               </div>
            </div>
         </q-card-section>
      </q-card>
   </q-dialog>
</template>
<script>
import { defineComponent } from 'vue'
import { ref } from 'vue'
export default defineComponent({
   //cuando haces click en boton de AU, ventana pierde focus hasta que hagas click de nuevo
   name: 'MirrorGirls',
   data: () => ({
      museSect: 0,
      museDialog: false,
      allyDialog: false,
      lore: {
         par1: "Long ago, a woman of light attempted to take down a great evil. In his defeat, he destroyed her realm, ending the lives of her lovers, with her escaping the destruction through a mirror, the shards sent to worlds beyond. With her beloved lovers gone, she waned in strength, trapped alone.",
         par2: "Until one shard was picked up by a girl called Rosa. Reminding her of one of her beloveds, she connected to her desires of love and lust. Slowly, through pleasures of the mind and body, Rosa came to trust her, enough to happily open a portal. She entered the palace the woman had created, and was blessed by her kindness and presence for many days. The pleasure empowered the woman, enough to send Rosa's consciousness to versions of her around the multiverse. Lost in bliss, she put herself in many arousing and romantic events, in turn empowering the woman further.",
         par3: "Finding joy in this event, the woman embraced her existance as a multidimensional Mistress of the Mirror, deeming Rosa her first Mirror Muse. Eventually, the now called Mirror Mistress empowered the shards to attract more girls who'd join as her muses through the multiverse, to harvest more love and lust, to gain neverending pleasure, and never be alone again.",
      },
      section: 0,
      kinkCat: 0,
      museDataCheck: 1,
      currentMuseCode: "",
      baseAU: 'base',
      currentAU: "",
      sectBtn: [
         { label: "Rules", index: 1 },
         { label: "Lore", index: 2 },
         { label: "Muses", index: 3 },
         { label: "Groups", index: 4 },
         { label: "Kinks", index: 5 },
      ],
      allCharArr: [
         { code: "rosa", sect: 1, avatar: "/museicon/nintendo/rosa.jpg", },
         { code: "iris", sect: 1, avatar: "/museicon/nintendo/iris.jpeg", },
         { code: "marn", sect: 1, avatar: "/museicon/nintendo/marnie.jpg", },
         { code: "nem", sect: 1, avatar: "/museicon/nintendo/nemona.png", },
         { code: "ida", sect: 1, avatar: "/museicon/nintendo/irida.jpg", },
         { code: "sere", sect: 1, avatar: "/museicon/nintendo/serena.png", },
         { code: "cyn", sect: 1, avatar: "/museicon/nintendo/cyn.jpg", },
         { code: "nesa", sect: 1, avatar: "/museicon/nintendo/nesa.png", },
         { code: "brina", sect: 1, avatar: "/museicon/nintendo/sabrina.jpg", },
         { code: "sam", sect: 1, avatar: "/museicon/nintendo/samus.jpg", },
         { code: "pich", sect: 1, avatar: "/museicon/nintendo/peach.jpg", },
         { code: "lina", sect: 1, avatar: "/museicon/nintendo/rosalina.jpg", },
         { code: "bow", sect: 1, avatar: "/museicon/nintendo/bowsette.jpg", },
         { code: "lin", sect: 1, avatar: "/museicon/nintendo/linkle.jpeg", },
         { code: "pura", sect: 1, avatar: "/museicon/nintendo/purah.jpeg", },
         { code: "edel", sect: 1, avatar: "/museicon/nintendo/edelgard.jpg", },
         { code: "lumi", sect: 2, avatar: "/museicon/genshin/lumi.jpeg", },
         { code: "lisa", sect: 2, avatar: "/museicon/genshin/lisa.jpg", },
         { code: "saria", sect: 2, avatar: "/museicon/genshin/rosaria.jpg", },
         { code: "yelan", sect: 2, avatar: "/museicon/genshin/yelan.jpeg", },
         { code: "mira", sect: 2, avatar: "/museicon/genshin/mirror.jpeg", },
         { code: "ann", sect: 2, avatar: "/museicon/games/ann.png", },
         { code: "tae", sect: 2, avatar: "/museicon/games/tae.png", },
         { code: "sae", sect: 2, avatar: "/museicon/games/sae1.jpeg", },
         { code: "shan", sect: 2, avatar: "/museicon/games/shantae.jpeg", },
         //{ code: "roty", sect: 2, avatar: "/museicon/games/rotty.png", },
         //{ code: "junko", sect: 2, avatar: "/museicon/games/junko.jpg", },
         //{ code: "nami", sect: 2, avatar: "/museicon/games/chiaki.jpg", },
         { code: "ridem", sect: 2, avatar: "/museicon/fate/riderM.jpg", },
         { code: "ruler", sect: 2, avatar: "/museicon/fate/ruler.jpeg", },
         { code: "luci", sect: 2, avatar: "/museicon/games/lucifer.jpg", },
         { code: "moni", sect: 2, avatar: "/museicon/games/monika.png", },
         { code: "layer", sect: 2, avatar: "/museicon/games/layer.jpeg", },
         { code: "mina", sect: 3, avatar: "/museicon/mha/mina.jpeg", },
         { code: "momo", sect: 3, avatar: "/museicon/mha/momo.jpeg", },
         //{ code: "toru", sect: 3, avatar: "/museicon/mha/tooru.jpeg", },
         { code: "tsu", sect: 3, avatar: "/museicon/mha/tsuyu.jpeg", },
         { code: "kendo", sect: 3, avatar: "/museicon/mha/kendo.jpeg", },
         { code: "mei", sect: 3, avatar: "/museicon/mha/mei.jpeg", },
         { code: "mel", sect: 3, avatar: "/museicon/mha/melissa.jpeg", },
         { code: "camie", sect: 3, avatar: "/museicon/mha/camie.jpeg", },
         { code: "joke", sect: 3, avatar: "/museicon/mha/msjoke.jpeg", },
         { code: "rumi", sect: 3, avatar: "/museicon/mha/miruko.jpeg", },
         { code: "nana", sect: 3, avatar: "/museicon/mha/nana.jpeg", },
         { code: "yama", sect: 3, avatar: "/museicon/mha/mtlady.jpeg", },
         { code: "kai", sect: 3, avatar: "/museicon/mha/nagant.jpeg", },
         { code: "fumi", sect: 3, avatar: "/museicon/mha/fuyumi.jpeg", },
         { code: "inko", sect: 3, avatar: "/museicon/mha/inko.png", },
         { code: "marin", sect: 4, avatar: "/museicon/anime/marin.jpg", },
         { code: "yor", sect: 4, avatar: "/museicon/anime/yor.png", },
         { code: "stock", sect: 4, avatar: "/museicon/anime/stock.jpg", },
         { code: "frie", sect: 4, avatar: "/museicon/anime/frie.jpg", },
         //{ code: "beni", sect: 4, avatar: "/museicon/anime/kobeni.jpeg", },
         { code: "lucy", sect: 4, avatar: "/museicon/anime/lucynda.png", },
      ],
      allygroups: [
         { name: 'rocket', emblem: '/versions/hypnorocket.png' },
         { name: 'shy', emblem: '/versions/shy.png' },
         { name: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png' },
         { name: 'phantom', emblem: '/versions/annemblem.jpg' },
         { name: 'ua', emblem: '/versions/uagirls.png' },
         { name: 'venom', emblem: '/versions/symbiote.png' },
      ],
      ally: {
         title: "",
         description: "",
         muses: [],
         musesTitles: [],
      },
      museAllies: [],
      muse: {
         Name: "",
         NameSh: "",
         SubDom: "",
         SubDomSh: "",
         Uni: "",
         UniSh: "",
         Spec: "",
         SpecSh: "",
         Reg: "",
         RegSh: "",
         Desc: "",
         DescSh: "",
         auArray: [],
         slideArray: [],
         kinksA: {
            partner: ["PERSON", "GROUP", "MACHINE", "MONSTER", "ANIMAL"],
            relation: ["CULTIST", "PET", "SLAVE", "ASSISTANT", "LOVER", "FAMILY"],
            clothing: ["NONE", "ANIMAL", "MATERIAL", "UNIFORM", "FASHION"],
            bodyMod: ["BREED", "PIERCE", "BRAND", "GROW"],
            mindMod: ["CORRUPT", "MINDBREAK", "BRAINWASH", "MINDBLANK", "HIVEMIND"],
         },
         kinksB: {
            transform: ["BIMBO", "GOTH", "MECHA", "TWIN"],
            treatment: ["PRAISE", "DEGRADE", "RYONA", "OBJECT", "HUMILIATE"],
            consent: ["FREE", "DUB", "NONE", "WATCH", "STEALTH", "EXHIBIT"],
            substance: ["FOOD", "SWEAT", "CUM", "PISS", "DRUGS"],
            bondage: ["BIND", "HYPNO", "GRAPPLE", "WORLD", "SENSE"],
         }
      },
      kinkA: {
         partner: ["Person", "Group", "Machine", "Monster", "Animal"],
         relation: ["Cultist", "Pet", "Slave", "Assistant", "Girlfriend", "Family"],
         clothing: ["None", "Animal", "Material", "Uniform", "Fashion"],
         bodyMod: ["Breeding", "Piercing", "Branding", "Growing"],
         mindMod: ["Corruption", "Mind Break", "Brainwashing", "Blank", "HiveMind"],
      },
      kinkB: {
         transform: ["Bimbofication", "Gothification", "Mechanization", "Twinning"],
         treatment: ["Praise", "Degradation", "Ryona", "Objectification", "Humiliation"],
         consent: ["Free Use", "Dub-Con", "Non-Con", "Voyeur", "Stealthing", "Exhibitionism"],
         substance: ["Food", "Sweat", "Semen", "Urine", "Drugs"],
         bondage: ["Bindings", "Hypnosis", "Grappling", "Environment", "Sensory Deprivation"],
      },
      knkGlosBtn: [
         { label: "Relation", index: 1 },
         { label: "Partner", index: 2 },
         { label: "Clothing", index: 3 },
         { label: "Body Modification", index: 4 },
         { label: "Mind Modification", index: 5 },
         { label: "Transformation", index: 6 },
         { label: "Treatment", index: 7 },
         { label: "Consent", index: 8 },
         { label: "Substances", index: 9 },
         { label: "Bondage", index: 10 },
      ],
      knkGloscatDesc: "",
      kinkGloss: {
         catKink1: "",
         catKink2: "",
         catKink3: "",
         catKink4: "",
         catKink5: "",
         catKink6: "",
      }
   }),
   setup() {
      return {
         slide: ref(0)
      }
   },
   watch: {
      museDialog(value) {
         if (value == false) {
            this.museDataCheck = 1
         }
      }
   },
   methods: {
      kinkGlossary(cat) {
         for (let object in this.kinkGloss) {
            this.kinkGloss[object] = ""
         }
         this.kinkCat = cat
         switch (cat) {
            case 1:
               this.knkGloscatDesc = "Preferred forms of relationship between Muse and her sexual partner/s."
               this.kinkGloss.catKink1 = "Cultist: Being part of a cult towards them, share in the delight of worship with them, or be worshipped."
               this.kinkGloss.catKink2 = "Pet: Being their pet (particular animals mentioned), or having them as a pet."
               this.kinkGloss.catKink3 = "Slave: Being subservient under threat and harm to their will entirely, even imprisoned by them, or having them subservient to/imprisoned by her."
               this.kinkGloss.catKink4 = "Assistant: Being their assistant, secretary, henchwoman, etc, or having them as one."
               this.kinkGloss.catKink5 = "Lover: Being their genuine romantic partner and for them to be hers."
               this.kinkGloss.catKink6 = "Family: Being their Mommy, Sis or Daughter, with them being the respective Daughter, Sis or Mommy."
               break
            case 2:
               this.knkGloscatDesc = "Preferred partner species by the Muse."
               this.kinkGloss.catKink1 = "Person: The local sapient species that Muse enjoys playing with."
               this.kinkGloss.catKink2 = "Group: A gang, or a cult, or any more than two people working together towards pleasure."
               this.kinkGloss.catKink3 = "Machine: Mechanical non-sapient devic/s to toy with, or be toyed by someone else with."
               this.kinkGloss.catKink4 = "Monster: A being with mostly non-humanoid anatomy and/or thought, usually dangerous or antagonistic."
               this.kinkGloss.catKink5 = "Animal: A common non-sapient entity, that can't speak, but can be a pet, and can mate.'"
               break
            case 3:
               this.knkGloscatDesc = "Preferred forms of attire to arouse Muse and others."
               this.kinkGloss.catKink1 = "None: Going au naturale, or see others forgo their clothing."
               this.kinkGloss.catKink2 = "Animal: Animal-themed outfits, such as cowkinis, playboy bunnies, etc."
               this.kinkGloss.catKink3 = "Material: Particular materials that entice and arouse Muse, being worn by her or others, such as latex, fur, mesh, and even living"
               this.kinkGloss.catKink4 = "Uniform: Wearing the same outfit (or similar enough) to others in a group experience, such as a school or military uniform"
               this.kinkGloss.catKink5 = "Fashion: A tendency to shop, accessorize, and generally mess around with clothing styles and dresses."
               break
            case 4:
               this.knkGloscatDesc = "Preferred forms Muse enjoys having hers or others' bodies changed, for a time or forever"
               this.kinkGloss.catKink1 = "Breeding: To fill with cum with the goal of getting knocked up."
               this.kinkGloss.catKink2 = "Piercing: Appeal for embedded jewelry or needle point tattooing."
               this.kinkGloss.catKink3 = "Branding: Artistic marks or writing to denote things about the person, be it drawing, body writing, or magical emblems"
               this.kinkGloss.catKink4 = "Growth: The expansion, through flesh or silicone, of body and its parts, like ass and breasts."
               break
            case 5:
               this.knkGloscatDesc = "preferred forms Muse enjoys having hers or others' minds changed, for a time or forever"
               this.kinkGloss.catKink1 = "Corruption: Falling for vices, temptations, fear or harm, away from their usual behaviour, and enjoying their new way of life."
               this.kinkGloss.catKink2 = "Mind Break: Tear away all thought and/or personality through force and overwhelming abuse turned to pleasure"
               this.kinkGloss.catKink3 = "Brainwash: Peacefully wash away all thought, memory and/or self and replacing it with new ones, often with the person unaware of the change"
               this.kinkGloss.catKink4 = "Blank State: Leaving someone empty of personality and self, very suggestible. Can be more technologically oriented, with commands and programming."
               this.kinkGloss.catKink5 = "Hive Mind: Connecting their mind to others, or assimilate it into a whole."
               break
            case 6:
               this.knkGloscatDesc = "Preferred forms Muse enjoys having hers or others' personhood altered, body and mind and soul, either for a time or forever"
               this.kinkGloss.catKink1 = "Bimbofication/Gyarufication: Includes blonde hair, preference for pinks, skimpy clothing, massive tits and ass, sometimes a tan, and a general excess of libido and lack of intelligence (or a need for it)"
               this.kinkGloss.catKink2 = "Gothification/Punkification: Black or alternative hair colors, wearing leather, latex and/or mesh, in same as hair color/s. Expect sass and a pissed or aloof attitude. Lots of piercing and tattoos common too."
               this.kinkGloss.catKink3 = "Mechanization/Droneification: Covered in technology, or fused with it, or turned into a machine being, often Blank State'd or in a Hivemind."
               this.kinkGloss.catKink4 = "Twinning: To look and act exactly as someone else, or as their twin that has always existed."
               this.kinkGloss.catKink5 = "*Note: You can mix and match these too. Goth Bimbos, Bimbo Drones, Goth Twins, etc."
               break
            case 7:
               this.knkGloscatDesc = "Ways Muse prefers to be treated, or treat their partner/s."
               this.kinkGloss.catKink1 = "Praise: Being lavished and loved and adored."
               this.kinkGloss.catKink2 = "Degradation: Being treated as a lesser, pathetic being, who's lucky to get to hear even the words of disdain"
               this.kinkGloss.catKink3 = "Ryona: Getting physically and psychologically abused, more emphasis on physical on this glossary (as psychological is covered by Degradation)"
               this.kinkGloss.catKink4 = "Objectification: Treatment as an item or prop, no more sapient than a lamp or seat."
               this.kinkGloss.catKink5 = "Humiliation: Openly devaluing and mocking someone through the darker forms of treatment, bondage, etc."
               break
            case 8:
               this.knkGloscatDesc = "The state of consent of the Muse that'll arouse them, of their partner/s, or of uninvolved people."
               this.kinkGloss.catKink1 = "Free Consent: Available to fuck at every single moment, waking or unconscious, busy or free, doesn't matter."
               this.kinkGloss.catKink2 = "Dub-Con: Using any sort of body and/or mind modification or substance that makes the judgement of consent questionable"
               this.kinkGloss.catKink3 = "Non-Con: Fuck or be fucked against their wishes expressed verbally and openly."
               this.kinkGloss.catKink4 = "Voyeur: Watching sexual activity happen, sometimes without their awareness or consent."
               this.kinkGloss.catKink5 = "Stealthing: A middle point of private and public, such as gloryholes, or doing it somewhere with little traffic, or behind an obstacle unseen."
               this.kinkGloss.catKink6 = "Exhibitionism: Let them all see what depravities are to be enjoyed."
               break
            case 9:
               this.knkGloscatDesc = "Fluids and other substances that the Muse or partner/s enjoy, share, and more"
               this.kinkGloss.catKink1 = "Food: Anything usually bought at a grocery store, or set at a table. Important inclusion of milk."
               this.kinkGloss.catKink2 = "Sweat: Salty results of vigorous exercise and heat, on the body of a gorgeous gal."
               this.kinkGloss.catKink3 = "Semen: Somewhat used for babymaking, but also good as a beauty product for to the skin, as well as a very filling meal."
               this.kinkGloss.catKink4 = "Urine: A warm golden shower of physical relief."
               this.kinkGloss.catKink5 = "Drug: Otherwise substances with neurochemical effects, usually addictive, and dangerous. Includes smoking, drinking, and biological drugs in trial without medical check."
               break
            case 10:
               this.knkGloscatDesc = "Ways in which Muse likes herself or others to be restrained and forced into positions for play"
               this.kinkGloss.catKink1 = "Bindings: Objects wrapped around the person and tying them up nicely. Includes tentacles, chains, ropes, tape, etc."
               this.kinkGloss.catKink2 = "Hypnosis: Control over a person's body, leaving them conscious inside their mind."
               this.kinkGloss.catKink3 = "Grappling: Physically restraining and manipulating a person into naughty positions."
               this.kinkGloss.catKink4 = "Environment: Setups and settled devices to put a slut in place, literally."
               this.kinkGloss.catKink5 = "Sensory Deprivation: Limiting or blocking sight and/or hearing (rarely the remaining three), to intensify the sense of pleasure, or make them feel helpless, lost and adrift."
               break
         }
      },
      groupShow(value) {
         this.ally.title = ""
         this.ally.description = ""
         this.ally.muses = []
         this.ally.musesTitles = []
         this.museAllies = []
         switch (value) {
            case 'rocket':
               this.ally.title = "TEAM HYPNO ROCKET";
               this.ally.description = "A girls-only offshoot of Team Rocket, focused on acquisition and training of Pokemon trainers, leaders, champions, etc. Takes a more hypnotic, sexual approach to both.";
               this.ally.muses = ["nem", "brina", "nesa", "cyn", "sere", "ida", "rosa", "iris", "marn"]
               this.ally.musesTitles = ["Leader", "Commander", "Coordinator", "Scientist", "Model", "Priestess", "Grunt", "Grunt", "Undercover"]
               break
            case 'shy':
               this.ally.title = "SHY GAL GROUP";
               this.ally.description = "A group of volunteer girls wearing the same mask, and similar outfits, making no noise but for light grunts and moans, watching from the dark depths of the mask's eyes. No official comment on the notion the masks mess with the mind and self.";
               this.ally.muses = ["pich", "lina", "bow", "sam"]
               this.ally.musesTitles = ["Pink", "Cyan", "Yellow", "Blue"]
               break
            case 'phantom':
               this.ally.title = "PHANTOM THIEVES OF LUST";
               this.ally.description = "A girls-only variant of the Phantom Thieves and allies that failed to pursue justice and fell victims to others' lustful cognitions of them. Now they aim to make Tokyo as filthy as they've become.";
               this.ally.muses = ["sae", "ann", "tae"]
               this.ally.musesTitles = ["Chief", "Founder (& Partner)", "Medic"]
               break
            case 'mirror':
               this.ally.title = "MIRROR MAIDENS";
               this.ally.description = "A group of assimilated illusionist women who work out of Teyvat, allied with the Fatui. Their assimilation inspired the Mistress' style. ";
               this.ally.muses = ["mira", "lumi", "lisa", "saria", "yelan"]
               this.ally.musesTitles = ["Reflection", "Sister", "Sister", "Sister", "Sister"]
               break
            case 'ua':
               this.ally.title = "UA HEROINE UNIVERSITY";
               this.ally.description = "A girls-only college ran by Headmistress Midnight to teach all the trades of being a hero...though it often ends with rather horny heroines, and unlocked sapphic tendencies.";
               this.ally.muses = ["fumi", "inko", "yama", "rumi", "joke", "momo", "mina", "tsu", "kendo", "camie", "mei", "mel", "kai", "nana"] //"toru",  
               this.ally.musesTitles = ["Secretary", "Staff", "Staff", "Staff", "Staff", "Student", "Student", "Student", "Student", "Student", "Student", "Student", "Guest", "Guest"]
               break
            case 'venom':
               this.ally.title = "VENOM SYMBIOTE";
               this.ally.description = "A parasite that fuses to bodies, evolved to feed on pleasure and with a little more interest in their host's desires. Thanks to the Mirror Mistress, available in many more worlds. ";
               this.ally.muses = ["rosa", "nem", "sam", "bow", "peach", "lina", "pura", "edel", "yelan", "ann", "shan", "mina", "momo", "tsu", "rumi", "marin", "yor", "stock"]
         }
         this.currentAU = value;
         var tempObjMuse;
         for (var i = 0; i < this.ally.muses.length; i++) {
            for (var j = 0; j < this.allCharArr.length; j++) {
               if (this.allCharArr[j].code == this.ally.muses[i]) {
                  tempObjMuse = {}
                  tempObjMuse = this.allCharArr[j]
                  tempObjMuse.groupPos = (value != "venom") ? this.ally.musesTitles[i] : ""
                  tempObjMuse.au = value;
                  this.museAllies.push(tempObjMuse)
               }
            }
         }
         this.allyDialog = true
      },
      slideKeyboard(move) {
         switch (move) {
            case 1:
               if (this.slide - 1 < 0) {
                  this.slide = this.muse.slideArray.length - 1
               } else {
                  this.slide--
               }
               break
            case 2:
               if (this.slide + 1 > this.muse.slideArray.length - 1) {
                  this.slide = 0
               } else {
                  this.slide++
               }
               break
         }
      },
      museSwitch(move) {
         var tempMoveArr = [];
         switch (this.section) {
            case 3:
               if (this.museSect != 5) {
                  for (var i = 0; i < this.allCharArr.length; i++) {
                     if (this.allCharArr[i].sect == this.museSect) {
                        tempMoveArr.push(this.allCharArr[i])
                     }
                  }
               } else {
                  tempMoveArr = this.allCharArr
               }
               break
            case 4:
               for (var i = 0; i < this.ally.muses.length; i++) {
                  for (var j = 0; j < this.allCharArr.length; j++) {
                     if (this.allCharArr[j].code == this.ally.muses[i]) {
                        tempMoveArr.push(this.allCharArr[j])
                     }
                  }
               }
               break
         }
         var newCode = "";
         var newSect = "";
         switch (move) {
            case 1:
               for (var i = 0; i < tempMoveArr.length; i++) {
                  if (this.currentMuseCode == tempMoveArr[i].code) {
                     if (i - 1 < 0) {
                        newCode = tempMoveArr[tempMoveArr.length - 1].code
                        newSect = tempMoveArr[tempMoveArr.length - 1].sect
                     } else {
                        newCode = tempMoveArr[i - 1].code
                        newSect = tempMoveArr[i - 1].sect
                     }
                  }
               }
               break
            case 2:
               for (var i = 0; i < tempMoveArr.length; i++) {
                  if (this.currentMuseCode == tempMoveArr[i].code) {
                     if (i + 1 > tempMoveArr.length - 1) {
                        newCode = tempMoveArr[0].code
                        newSect = tempMoveArr[0].sect
                     } else {
                        newCode = tempMoveArr[i + 1].code
                        newSect = tempMoveArr[i + 1].sect
                     }
                  }
               }
               break
         }
         if (this.section == 3) {
            this.museProfileOpen(newSect, newCode, this.baseAU)
         } else if (this.section == 4) {
            this.museProfileOpen(newSect, newCode, this.currentAU)
         }
      },
      museProfileOpen(area, char, au) {
         this.cleanData();
         switch (area) {
            case 1:
               switch (char) {
                  case 'rosa':
                     this.muse.Uni = "Pokemon";
                     this.muse.Reg = "Unova";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Rosa Whitley";
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Submissive unless love requires dominance.";
                           this.muse.Desc = "A buntailed, peppy, flexible Unova Pokemon trainer, with a Paldean mother and Galarian the other, who loves to love, and always tries to see the bright side of life and people. Recently come into contact with her distant cousins Nemona and Marnie. ";
                           this.muse.DescSh = "As expected of a former Team Plasma Grunt, she's eager to please, and quick to treat degradation and harm as 'love bites'.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosa/sample_c8c08bce5d1c14378c80640c3d5742f0.jpg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/10f3939031c1e5aedb246d8a26f0bc97.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/079bcf70472d4318c357c6d1ac71beed.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/20230919_143700.jpg", name: "Bikini" },
                              { pic: "/slideshow/nintendo/rosa/7abc933223fd45300515de17564b00be.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/a5457539d19d084c32b460c9b66a014b.jpg", name: "Alpha" },
                              { pic: "/slideshow/nintendo/rosa/acee350228baad91a72577384a2dbfb8.jpg", name: "Gyaru" },
                              { pic: "/slideshow/nintendo/rosa/44718e9d72eb20171e75060ec2319fab.png", name: "Team Galactic" },
                              { pic: "/slideshow/nintendo/rosa/7f257638c323de13261c74951d363f5e.jpg", name: "Team Flare" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Grunt Rosa";
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Submissive unless mission requires dominance.";
                           this.muse.Desc = "A loyal member of Team Rocket's most arousing division, she happily included her cousins Nemona and Marnie in, one through deep hypnosis even. Despite this, she remains highly peppy and cheerful, and adores love, even if her love now is her Team. ";
                           this.muse.DescSh = "She intends to share this wonderful team with every cute and hot girl in the world, by whatever means are asked of her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosa/rocket/105398019_p6.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/Salazr4-931458-Rosa_team_rocket.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/f60790321c674de16d1e92fb2bb6ac79.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/sample_3cf246ab2e795e22a469305684eebaeb.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/7120ec5922c549d184120ad3b8800381.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/799bd3d2e6e89a001cbbe2dd7d5067bc.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/8dc8cf7f1ccc019c6fb4b59e3157c031.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/8ce13aa7999c1a4d7c61bcc349767617.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/112995136_p0.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/rocket/c076d274ac7e2baaf538b162a9343196.jpeg", name: "" },
                           ];
                           break
                        case 'plasma':
                           this.muse.Name = "Princess";
                           this.muse.SubDom = "Broken Submissive.";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A permanent long-time member of team Plasma, despite the royalty name she's treated as the lowest of the low, and has lost all notion of ever leaving, genuinely believing the way she's treated is only fair, be it as the team's slut, or the humiliating, arousing punishments for failure. ";
                           this.muse.DescSh = "At times she wonders what it would've been to leave, but then she's fucked and used all over and lets go of such silly notions. She is Team Plasma property, nothing else matters.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosa/plasma/6.jpg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/plasma/d4bbadacd98635870ed9b442a5c591e4.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/plasma/98d5b1da7c785cb8293d91a24dae138f.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/plasma/523d2d0922c5dcf837c484409094ecf9.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosa/plasma/110125025_p0.png", name: "" },
                              { pic: "/slideshow/nintendo/rosa/plasma/GB-NVYoWUAApR0n.jpeg", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Amor";
                           this.muse.SubDom = "Dominant until/unless you accept to dominate her";
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.Desc = "Fused with a symbiote, she wanders the streets and stalks people for love. And by love we refer to passionate sex to feed her symbiosis. She rarely if ever intends to listen to her victims, unless they accept her as their lover, and prove they own her. ";
                           this.muse.DescSh = "Sometimes, glimmers of her original self come out after truly inhuman marathonic sex sessions, getting cuddly and affectionate.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosa/Crrwhi4e.jpeg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Team Rocket, Team Plasma", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["Member (Self)", "Dog, Cow, Bun (Self)", "Slave (Self)", "Assistant (Self)", "YES", "Mommy/Daughter (Partner/Self), Sister"]
                     this.muse.kinksA.clothing = ["", "Pokemon (Dog, Cow, Bun)", "Latex, Nylon, Living", "Evil Team, Maid, School", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "", "YES", "Breasts, Hips"]
                     this.muse.kinksA.mindMod = ["Self", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.transform = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksB.treatment = ["YES", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["YES", "YES", "YES", "", "", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "Inside", "", ""]
                     this.muse.kinksB.bondage = ["Rope, Tentacles, Tape", "YES", "Groping", "", ""]
                     break
                  case 'nem':
                     this.muse.SubDom = "Whoever wins the battle doms. She wants to win more, and wants more with them than from them to her.";
                     this.muse.Uni = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Paldea";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Nemona Victoria";
                           this.muse.Desc = "A very hyperactive girl who enjoys Pokemon battling above all else. It has led her to be a Champion-ranked student, though making her ability to relate to others much harder. Has come out of her shell a little through Juliana and Penny, and now her cousin Rosa. ";
                           this.muse.DescSh = "She treats sex as roughly and dedicated as Pokémon battling. She has fucked and broken many girls she defeats, and intends to do the same for her new friends, longer, harder, tighter. Make them hers for good.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/nemona/FzmC1wdXsAEB_nX.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/nemona/4148abbf63d8bdcd6081ea67b23a784d.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/nemona/108033854_p0.png", name: "" },
                              { pic: "/slideshow/nintendo/nemona/c35221bb5d0fc10b6c79306556a88023.jpeg", name: "Reward" },
                              { pic: "/slideshow/nintendo/nemona/a22aa18c8c3e9d25fe3caf1b9c062e2f.jpg", name: "Alpha" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Leader Nemona";
                           this.muse.Desc = "A rapidly risen leader of Team Hypno Rocket, aptly so given her thirst for competition and sex. She makes sure to take care of any girl under her care, treating them as already defeated and thus hers to play with. ";
                           this.muse.DescSh = "Had designs of starting her own evil team of the same occupations and goals, but joined Team Hypno Rocket to not start from scratch.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/nemona/114534578_p5.png", name: "" },
                              { pic: "/slideshow/nintendo/nemona/114534578_p7.png", name: "" },
                              { pic: "/slideshow/nintendo/nemona/sample_76d2991400b75a59f375c40abaf7a14f.jpg", name: "" },
                              { pic: "/slideshow/nintendo/nemona/30a7e0432cda01fdf2c54babee6a711e.jpeg", name: "" },
                           ];
                           break
                           case 'venom':
                           this.muse.Name = "Victoria";
                           this.muse.Desc = "Her new form has allowed her to take on Pokemon Battles all by herself, proving and testing herself constantly anew. She retains her last name, and her former self's loneliness at the peak of battle prowess. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/nemona/94dcee624918260ed9c7e7b660e2c447.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["", "Dog", "", "YES", "Rivals", ""]
                     this.muse.kinksA.clothing = ["", "Pokemon", "Nylon", "School, Team Rocket", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "YES", ""]
                     this.muse.kinksA.mindMod = ["", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["Partner", "Partner", "", ""]
                     this.muse.treatment = ["YES", "", "YES", "", ""]
                     this.muse.consent = ["Self", "Partner", "Partner", "YES", "", "YES"]
                     this.muse.substance = ["", "YES", "YES", "", ""]
                     this.muse.bondage = ["Rope, Tentacles", "Partner", "YES", "YES", "YES"]
                     break
                  case 'marn':
                     this.muse.Uni = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Galar";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Marnie Mary";
                           this.muse.SubDom = "Submissive unless irritated sufficiently. Like a Morpeko.";
                           this.muse.Desc = "A punk-ish girl who seems tough, hiding a truly shy and sweet disposition, with troubles smiling and otherwise expressing herself concisely. She has a legion of fans that cause ruckus, and two cousins that tease her endlessly, both of which she is eternally grateful to. ";
                           this.muse.DescSh = "When she snaps, she truly embraces that toughness all see, and will use every filthy fantasy on whoever brought it on her. On the other hand, if she breaks, she'll take anything you do to her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/marnie/55c584c17a73553625175db1989ec923.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/marnie/a240cd2a1cd908c8e4a4aa86070b75c1.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/marnie/15b08487f548518c8597bca79a788301.png", name: "Delinquent" },
                              { pic: "/slideshow/nintendo/marnie/af8f30cde4a1e4071ea53fdb46196ef6.jpeg", name: "Bunny" },
                              { pic: "/slideshow/nintendo/marnie/07e72781031334839aa8f0cad4126c11.jpeg", name: "Bunny (Reverse)" },
                              { pic: "/slideshow/nintendo/marnie/20231002_142935.jpg", name: "Morpeko" },
                              { pic: "/slideshow/nintendo/marnie/13395b2704bd0d32a00681f04f681517.jpeg", name: "Alpha" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Undercover Grunt Marnie";
                           this.muse.SubDom = "Completely submissive until ordered otherwise.";
                           this.muse.Desc = "A former trainer put in a deep trance of hypnosis, left as a drooling mess (from either end). With a snap of her fingers, she may go back to her former self, be put in a state of dominance, or go back to her true happy mindless self. ";
                           this.muse.DescSh = "She was more aware than she let on before her hypnosis. She just wanted to have someone else take care of her, and let her emote more, or be more comfortable with her state.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/marnie/106960435_p3.png", name: "" },
                              { pic: "/slideshow/nintendo/marnie/108312608_p1.png", name: "" },
                              { pic: "/slideshow/nintendo/marnie/f2b7f334901e1a276916e87496b97b35.png", name: "" },
                              { pic: "/slideshow/nintendo/marnie/78605419_p0.png", name: "" },
                              { pic: "/slideshow/nintendo/marnie/7fc6377613d6c6af101558ebd3f7c2bd.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/marnie/a10ba9d055682d3f4110d244c6cf24fa.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Team Rocket", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "Pokemon", "Latex, Leather, Nylon, Fishnet", "Team Rocket", "Punk, Pastel"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", "Boobs"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "YES", ""]
                     this.muse.kinksB.transform = ["YES", "Partner", "", "YES"]
                     this.muse.kinksB.treatment = ["Self", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "YES", "YES", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", "Smoking"]
                     this.muse.kinksB.bondage = ["Chains, Rope, Tentacle", "YES", "YES", "YES", "YES"]
                     break
                  case 'ida':
                     this.muse.SubDom = "Submissive";
                     this.muse.Uni = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Hisui";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Irida Kai";
                           this.muse.Desc = "A girl thrown into the leadership of the Pearl Clan too fast, too young, and too soon, she overcompensates with a tough attitude and disposition, hiding a rather soft and vulnerable self. She dedicates herself to the vastness of Hisui, despite being stuck in her position. ";
                           this.muse.DescSh = "Sometimes she too wishes to step down and be just one more person worshiping, as well as forget the breaking of her life's theology..or find a new one.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/irida/458f7ba4266eb957c5a7932a549dd5f2.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/irida/c3f67f1d3240368a38a4f77691a4c2d8.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/irida/b8d11a378e26cce975c56d29f1f56bc8.jpeg", name: "Glaceon" },
                              { pic: "/slideshow/nintendo/irida/f781168d50efb09fc74b4811e782e4d7.jpg", name: "Alpha" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Priestess Irida";
                           this.muse.Desc = "A girl flung forward in time to a confusing future, comforted by her new one and only religion: Team Hypno Rocket!! Hierarchy-wise she really is just grunt level, but her fervor and worship really earned her the special little nickname. ";
                           this.muse.DescSh = "Part of her sometimes screams at her about the criminal, sometimes 'evil' actions of the team, but the comfort of worship and mindlessness soothe her too much to dwell on it too long.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/irida/109404044_p4.png", name: "" },
                              { pic: "/slideshow/nintendo/irida/109404044_p5.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "YES", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["Self", "Self", "", "", "", ""]
                     this.muse.kinksA.clothing = ["YES", "Pokemon", "Breathable fabrics", "Pearl Clan, Team Rocket", ""]
                     this.muse.kinksA.bodyMod = ["", "", "Painting", ""]
                     this.muse.kinksA.mindMod = ["", "", "Self", "", "YES"]
                     this.muse.kinksB.transform = ["", "", "", "As Partner"]
                     this.muse.kinksB.treatment = ["Partner", "", "", "Self", ""]
                     this.muse.kinksB.consent = ["", "Self", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Rope, Tentacles", "YES", "YES", "YES", "YES"]
                     break
                  case 'iris':
                     this.muse.SubDom = "Dominant unless Dragon";
                     this.muse.Uni = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Unova";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Iris Magenta";
                           this.muse.Desc = "A very wild girl who loves dragons, and Pokémon, but is rather clueless and slow to trust and learn when it comes to anything outside of that. After a great journey, she managed to become the Champion of Unova, a title which often swings between her and her claimed sister Rosa. ";
                           this.muse.DescSh = "It is her earnest hope to be taken by a dragon as a mate and utterly ruined, only existing as a dragon's slave. Or perhaps commanded by one to execute their dominance on other victims.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/iris/62e51d2fbdf846d6554d9a44d26f9156.png", name: "" },
                              { pic: "/slideshow/nintendo/iris/57d75eb4d32f24e35aed04b8b56a2e73.jpeg", name: "Bunny" },
                              { pic: "/slideshow/nintendo/iris/728f604f9ec3bfd5d5caae388b0511668e38ad58.png", name: "Dragon" },
                              { pic: "/slideshow/nintendo/iris/af150e09620200ce637325560180101d.jpeg", name: "Alpha" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Grunt Iris";
                           this.muse.Desc = "Where Rosa goes so does she, so it was only a matter of time she cornered her sister and joined. While she still has a greater interest in dragons and championship, she has no problem helping in the newly found 'family business', even if she doesn't have many opportunities to show she too can be sexy. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/iris/91822231_p5.jpg", name: "" },
                              { pic: "/slideshow/nintendo/iris/77937344_p6.jpg", name: "" },
                              { pic: "/slideshow/nintendo/iris/b0f559a5f7dcb1f712fcc52297596d87.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "", "", "Pokemon", "Dragon"]
                     this.muse.kinksA.relation = ["", "YES", "YES", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "Pokemon, Dragon", "", "Evil Team (Rocket, Plasma)", "Princess, Devil"]
                     this.muse.kinksA.bodyMod = ["YES", "Nipple Rings", "Scars", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["", "", "", "YES"]
                     this.muse.kinksB.treatment = ["PRAISE", "DEGRADE", "RYONA", "OBJECT", "HUMILIATE"]
                     this.muse.kinksB.consent = ["FREE", "DUB", "NONE", "WATCH", "STEALTH", "EXHIBIT"]
                     this.muse.kinksB.substance = ["FOOD", "SWEAT", "CUM", "PISS", "DRUGS"]
                     this.muse.kinksB.bondage = ["BIND", "HYPNO", "GRAPPLE", "WORLD", "SENSE"]
                     break
                  case 'sere':
                     this.muse.Uni = "Pokemon";
                     this.muse.Reg = "Kalos";
                     this.muse.Spec = "Human";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Serena Yvonne";
                           this.muse.SubDom = "Casual Switch.";
                           this.muse.Desc = "A fashionable young lady, who's very kind and polite, until she actually snaps. Rather lost in her way, she takes the time while trying to find her future by trying on all kinds of clothes...or tasting all sorts of lips. She IS Kalosian, after all. ";
                           this.muse.DescSh = "It's not rare to find her only partially dressed, or wearing sexual parodies that barely count as clothes. This too is fashion after all!";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'flare', emblem: '/versions/team_flare_by_biochao_dezue6u-pre.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/serena/sample_3f4d63e78c0f6b1ff9ba5a144ec7b595.jpg", name: "" },
                              { pic: "/slideshow/nintendo/serena/7fe69f9345e69b3cc8328cff58e117dd.png", name: "" },
                              { pic: "/slideshow/nintendo/serena/3af7be0eedb170cfbc4784513d925336.png", name: "" },
                              { pic: "/slideshow/nintendo/serena/056f533916d7428c3512eb34ba1d693a.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/serena/1c141a6ff3e580dcfbf75f18d28e5f9a.png", name: "" },
                              { pic: "/slideshow/nintendo/serena/84585605_p0.png", name: "" },
                              { pic: "/slideshow/nintendo/serena/ad55e3a959b5cf9ac349be0ed075c885.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/serena/F23AtdDXkAA4uJw.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/serena/F5IY95eWYAA0xlC.jpeg", name: "" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Model Serena";
                           this.muse.SubDom = "Cheerily Submissive";
                           this.muse.Desc = "Infiltrated Team Rocket by wearing their uniform. On being caught, she lied and said she loved the uniform so much she wanted to feel part of things. After several hours of hands-on tutoring by 'her superiors', informative workplace training videos, and physical pose and training regimes, she finally can shine the uniform's true nature of a loyal Team Rocket member. She still gets to try new ones too. ";
                           this.muse.DescSh = "Said tutoring involved lengthy groping, said training regimes growingly obscene poses and motions, and said workplace training videos were hypnotic. She has forgotten entirely she was ever here undercover, and she is 100% a Team Rocket member now and forever.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                              { au: 'flare', emblem: '/versions/team_flare_by_biochao_dezue6u-pre.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/serena/104213773_p3.png", name: "" },
                              { pic: "/slideshow/nintendo/serena/104213773_p4.png", name: "" },
                              { pic: "/slideshow/nintendo/serena/Twitter 2.jpg", name: "" },
                              { pic: "/slideshow/nintendo/serena/ba5ee35ad4fb555780f9757a71c6729a.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/serena/97188664_p0.jpg", name: "" },
                           ];
                           break
                        case 'flare':
                           this.muse.Name = "Admin Serena";
                           this.muse.SubDom = "Switch but always haughty.";
                           this.muse.Desc = "Hired to model their attires as they were designed, she ultimately fell in love with their ideas of beauty and fame, which her continued (and growingly enthusiastic) modelling of their outfits and goals granted her within. Her career may be less known, but in the end, beauty will win. And she IS beauty. ";
                           this.muse.DescSh = "Some of the outfits were treated to lower personal morals, and increase pleasure based on team Flare approval. She knows now, but doesn't mind, as she asked her current outfits to have ten times the potency of her trial ones.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'flare', emblem: '/versions/team_flare_by_biochao_dezue6u-pre.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/serena/7f3a07040cd3749b96f0d6873787a203.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/serena/111730049_p0.jpg", name: "" },
                              { pic: "/slideshow/nintendo/serena/116733751_p0.png", name: "(+ Maman)" },
                              { pic: "/slideshow/nintendo/serena/2d43619914930a8599ca53b9edbbcad9.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/serena/102927351_p0.jpg", name: "" },
                              { pic: "/slideshow/nintendo/serena/95565241_p5.jpg", name: "" },
                           ];
                           break

                     }
                     this.muse.kinksA.partner = ["Human", "Team Rocket, Team Flare", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["", "", "", "YES", "YES", "Mommy/Daughter: Grace/Self"]
                     this.muse.kinksA.clothing = ["", "Pokemon (Fox)", "", "Evil Team", "YES"]
                     this.muse.kinksA.bodyMod = ["", "YES", "Sponsorship", "Tits"]
                     this.muse.kinksA.mindMod = ["YES", "", "YES", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", ""]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "", "YES", "", "Smoking"]
                     this.muse.kinksB.bondage = ["Rope", "YES", "", "YES", "YES"]

                     break
                  case 'cyn':
                     this.muse.Uni = "Pokemon";
                     this.muse.Reg = "Unova";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Cynthia Shirona";
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Mostly Dommy Mommy.";
                           this.muse.Desc = "An adventuring archaeologist who's stumbled upon the title of champion. While not the greatest fan of battling, the title serves her well for clearance into important sites, and her team is prepared to deal with the blow of legendaries' actions. ";
                           this.muse.DescSh = "She's well aware of the reputation and trauma her prowess does to others, and sometimes she revels in it, playing up her mystery and dominance. Other times? She surprises them with her tenderness. She enjoys either";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/cynthia/sample_46f7d45f3df7d6fa3b94cb376ca12b4e.jpg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/cynthia_pokemon_and_2_more_drawn_by_ginhaha__cc368d92d57ba6812e551d5882734a29.png", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/1426a270e43fcd952d9bf754ae1ec5fd.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/F_PYH5MW8AERouv.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/FUHl-bvXwAAp-IN.jpeg", name: "Renegade" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Rocket Scientist Cynthia";
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Vicious Dommy, Power Bottom.";
                           this.muse.Desc = "Offered quite a bit of endorsement for her help in studying mythos (as well as promises that they wouldn't use it for as dangerous goals as Team Galactic), she joined on contract, though contact with their uniforms and culture and the myriad of Sonia's inventions degraded her until she accepted to join in full. ";
                           this.muse.DescSh = "She no longer has qualms about whether her knowledge is used for great evil, only how it'll serve team Rocket, her beloved.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/cynthia/rocket/GKbkRfxWwAA-Zpd.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/81105c265a347e41061aaf08480c8a76.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/768dac8a75af8d7387e5efa7154dfa1a.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/86f7a48ac152f9edea96d04f1b98a98d.jpg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/1f29832f3ce4ec0cbbaf669a5925ad15.jpg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/48e1649cca728f421d956e8b01285cd6.png", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/90978ed1ae5cb032202d001d9c981d0c.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/rocket/13.png", name: "" },
                           ];
                           break
                        case 'galaxy':
                           this.muse.Name = "Admin Cynthia";
                           this.muse.SubDom = "Ready to obey";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "Unknowingly and accidentally helped with the archaeological/mythos side of things, realizing how much she had helped the team broke her, choosing to use their tech to be brainwashed. Now she's happily loyal, without those pesky morals that gave her guilt, and all she had to give away was her life and pride. ";
                           this.muse.DescSh = "The errors that led to her assistance were entirely staged to wrack her with guilt, and the pleasure she gets when obeying from the brainwashing helped ensure she'd never leave.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/cynthia/galaxy/f81413db35920e9c3d66bc1027ee1a3d.jpg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/galaxy/eef75109b9325aa76ee9f2b85cd0c461.jpg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/galaxy/109078811_p1.png", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/galaxy/114562458_p1.png", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Historia";
                           this.muse.SubDom = "Dommy Mommy Supreme";
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.Desc = "Found a strange substance in some ruins, that have given her the strength to go toe to toe with legendaries, and a viciousness at battle. Those who lose to her will have to accept being her adopted 'children', and hours of making love. ";
                           this.muse.DescSh = ".";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/cynthia/venom/11fc59be157d5cdd555e8fb7e08bbb7b.jpg", name: "" },
                              { pic: "/slideshow/nintendo/cynthia/venom/56c6c69e5ebd8be4bedaf2702c56d716.jpg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Team Rocket, Team Galactic", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "", "Partner", "YES", "Self - Mommy"]
                     this.muse.kinksA.clothing = ["YES", "", "Latex, Fur", "Evil Team", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "", "", "Boobs"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", ""]
                     this.muse.kinksB.treatment = ["YES", "YES", "", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "YES", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'nesa':
                     this.muse.SubDom = "Goes with the flow";
                     this.muse.Uni = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Galar";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Nessa Rurina";
                           this.muse.Desc = "A model and gym leader from Galar who much like the sea, is calm until battle comes and she becomes the storm. She worries about holding onto her modelling career alongside the gym, but she continues to shine on. She always has time for Sonia though! ";
                           this.muse.DescSh = "She absolutely adores Sonia and would do anything for her, go as far as she asks. She's taken to masturbate to her at her own pool, hoping the waters hide her own fluids shed from thinking about her closest gal pal.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/nessa/62e996c47d7c846df60e7e764e26cbf6.png", name: "" },
                              { pic: "/slideshow/nintendo/nessa/81e9b85cbd6a64de19f00c8dff362b16.png", name: "" },
                              { pic: "/slideshow/nintendo/nessa/__nessa_pokemon_and_2_more_drawn_by_maniacpaint__635588b734766d0604df0597822acfb5.jpg", name: "" },
                              { pic: "/slideshow/nintendo/nessa/RDT_20230218_1417587122187047633158608.jpg", name: "" },
                              { pic: "/slideshow/nintendo/nessa/FJYhANXVQAIFabl.png", name: "" },
                              { pic: "/slideshow/nintendo/nessa/be7118ff43e7812f7df4775891681b2b.png", name: "" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Coordinator Nessa";
                           this.muse.Desc = "She entered by Sonia's invitations, and her own secret sensual experiments on her left her suggestible enough to dedicate herself. Team Rocket has helped her greatly in managing her time for gym, modelling, and Rocket missions. And she always has time to assist her Sonia in the lab, grateful she got her here.";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/nessa/30c9fdc5293fc419ba812e237361bd99.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/nessa/7dbbf55cbc24e9f6c1260e3727447ccc.jpeg", name: "(+ Rocket Grunt Hilda)" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "YES", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["", "", "", "Self", "Sonia", ""]
                     this.muse.kinksA.clothing = ["YES", "", "Spandex, Latex", "", "Model"]
                     this.muse.kinksA.bodyMod = ["", "Yes", "", "Gigantamax"]
                     this.muse.kinksA.mindMod = ["", "Self", "Self", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", ""]
                     this.muse.kinksB.treatment = ["YES", "", "", "", ""]
                     this.muse.kinksB.consent = ["YES", "", "", "", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", ""]
                     this.muse.kinksB.bondage = ["", "", "YES", "YES", "YES"]
                     break
                  case 'brina':
                     this.muse.Uni = "Pokemon";
                     this.muse.Reg = "Kanto";
                     this.muse.Spec = "Psychic Human";
                     this.muse.SubDom = "In Control.";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Sabrina";
                           this.muse.Desc = "A confident woman who's grown a little conceited in her psychic powers, and embraced the cockiness in it, dressing, speaking, and behaving the part of a powerful villain, even when doing good for others. Despite it, shimmers of the sweet kid she couldn't be sometimes shine through. ";
                           this.muse.DescSh = "She's obsessed with control, and she'll use whatever she's got, be it her looks or her psychic powers, to make sure they go as she wishes. You have no choice in the matter.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/sabrina/sample_76daf3045608cdf9add80ec7a0f6ab08.jpg", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/0dac33d717cafda078a25268b7e6b77b.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/2d4e43fdb628827ecbdac2d90f8f4503.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/8ec5778e116f820f88cdad36e4219a7f.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/28cc18613706872e3f10160315ca8a03.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/d11f56711b448f439d45554587f3dcde.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/a3885779d7d6a8afbfd6f263c99abc95.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/2edd0d90955855df4bbc219599d17c3c.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/F3dJdM7XsAAYD_T.jpeg", name: "" },
                           ];
                           break
                        case 'rocket':
                           this.muse.Name = "Head Sabrina";
                           this.muse.Desc = "Finding her wicked disposition and power praised and endorsed by the team, she joined truly of her own voalition, and uses her own psychic powers towards getting more members. ";
                           this.muse.DescSh = "Some people say the growing sexualization of the female members' outfits is due to her own fetishes, but none dare ever ask. She knows they intend to, though, and she'll never say.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/sabrina/r/e7fb29d4a4c314d4d5cf93f856777fd8.jpg", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/r/13c0bc2ba7c4cbd1b35f12eda7069d98.jpg", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/r/8ce988a9f6dfce841112cbe72ee4dca1.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/r/cf43c3afe15bab587abccecee1f0b302.png", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/r/d7eab4ac4f5436026cb4e51916ac7922.jpg", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/r/bf66a73a29a95191fba3d13336351867.jpg", name: "" },
                              { pic: "/slideshow/nintendo/sabrina/r/IMG_2078.jpg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Team Rocket", "", "Pokemon", ""]
                     this.muse.kinksA.relation = ["Self - Worshipped", "Self - Owner", "Self - Owner", "", "", "Self - Mommy"]
                     this.muse.kinksA.clothing = ["", "", "Nylon, Latex", "Evil Team", ""]
                     this.muse.kinksA.bodyMod = ["", "YES", "As Hers", ""]
                     this.muse.kinksA.mindMod = ["Partner", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.transform = ["Partner", "YES", "", ""]
                     this.muse.kinksB.treatment = ["Self", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.consent = ["", "Partner", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Tentacles, Rope, Whip", "YES", "", "", "YES"]
                     break
                  case 'sam':
                     this.muse.Uni = "Metroid";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Samus Aran";
                           this.muse.SubDom = "Whatever the 'mission' requires";
                           this.muse.Spec = "Human / Chozo / Metroid";
                           this.muse.Reg = "Space";
                           this.muse.Desc = "A capable yet sensibly muted warrior who unwinds through sex, and carries on her mission to the end, but has trouble emoting, connecting, or sensing. ";
                           this.muse.DescSh = "She'd happily surrender to an evil alien force if it returned her the ability to feel joy and pleasure and love.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/samus/sample_b3d98ce251d9b5f6da9be094b1e00014.jpg", name: "Zero Suit (1)" },
                              { pic: "/slideshow/nintendo/samus/suit-hentai-41.jpg", name: "Zero Suit (2)" },
                              { pic: "/slideshow/nintendo/samus/F3L7JHdWcBMoe_r.jpeg", name: "Bunny" },
                              { pic: "/slideshow/nintendo/samus/abcf9eebb7e253df7f7af05c5548e092.png", name: "Bimbo" },
                              { pic: "/slideshow/nintendo/samus/1290cb9401811f101aa30d07cadcd751.jpeg", name: "Phazon" },
                              { pic: "/slideshow/nintendo/samus/78e5271ef7bbf3c49bc3080cdeb653ec.png", name: "Mother Metroid" },
                           ];
                           break
                        case 'shy':
                           this.muse.Name = "Blue";
                           this.muse.SubDom = "Submissive unless orders";
                           this.muse.Spec = "Shy Gal";
                           this.muse.Reg = "Mushroom Kingdom";
                           this.muse.Desc = "A shy gal who makes even less noises than the usual, but shows little shyness in offering herself up for pleasure and flirtation. She seems almost thrilled to be in this position of anonimity. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/samus/shysam.jpg", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Hadaris";
                           this.muse.SubDom = "Dominant Lifeform";
                           this.muse.Spec = "Human / Chozo / Symbiote";
                           this.muse.Reg = "Space";
                           this.muse.Desc = "A woman to gave in to a very different slimy parasite, forgoing the need for her armor...or morality. While still focused on ending great threats, she takes greater pleasure in their destruction, and takes breaks enjoyed through sexual marathons (willing or otherwise). ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/samus/venom/F7_tUQEWQAA-7Ds.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/f5258199447bd959f2cc469b38e4d6ff.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/e5cdb37a5ee6c0634ba80592af7b4d1f.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/foxyart samus symbiote.jpg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/F9TQ7nSWQAAHWiY.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/109702750_p4.jpg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/2cc79e646b446586a5662ad8dbbdbf3b.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/samus/venom/59e04c45c87daa82e4ce9f2ae6920ed7.jpeg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Aliens", "", "YES", "YES", ""]
                     this.muse.kinksA.relation = ["", "YES", "YES", "", "YES", "Mommy/Daughter"]
                     this.muse.kinksA.clothing = ["", "", "Latex, Living", "YES", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "", "Tattoos", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.transform = ["YES", "YES", "YES", ""]
                     this.muse.kinksB.treatment = ["YES", "", "YES", "", ""]
                     this.muse.kinksB.consent = ["YES", "Self", "Self", "", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "YES", "Inside", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Tentacles", "YES", "YES", "YES", ""]
                     break
                  case 'bow':
                     this.muse.Uni = "Mario";
                     this.muse.Reg = "Dark World";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Bowsette Koopa";
                           this.muse.SubDom = "Dominant unless trapped into it or flipped by a gorgeous princess";
                           this.muse.Spec = "Koopa/Human";
                           this.muse.Desc = "A newfound boisterous girl with a thirst for cute princesses and world domination. Despite her added human, she's still strong, brash, possessive...and weak to the beauty of princesses. Her dream is all princesses to adore her, and fall for her charms to be hers. ";
                           this.muse.DescSh = "Though sometimes, she'd like to see what it'd be like if the princesses turned the tables on her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/bowsette/54b7c2fcf96bc05f69743d084085716a.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/bowsette/458bc9469fed5f8fe9bd29f7ae009e9b.png", name: "Driver" },
                              { pic: "/slideshow/nintendo/bowsette/37ff85d6ecbf54875d496f583b7e6281.jpeg", name: "Office" },
                              { pic: "/slideshow/nintendo/bowsette/pale blonde bowsette frame 1.jpg", name: "Default (Blonde)" },
                              { pic: "/slideshow/nintendo/bowsette/tan redhead bowsette frame 1.jpg", name: "Default (Redhead)" },
                              { pic: "/slideshow/nintendo/bowsette/fury bowsette gif frame 1.jpg", name: "Fury" },
                           ];
                           break
                        case 'shy':
                           this.muse.Name = "Yellow";
                           this.muse.SubDom = "Coy, bratty submissive";
                           this.muse.Spec = "Shy Gal";
                           this.muse.Desc = "The very leader of the shy gals, going undercover to see what they get up to, and doing it many more times to enjoy the supposed anonimity of the mask to take a break from being bossy and the top. ";
                           this.muse.DescSh = "Actually, every shy gal knows it's her, but it's alright by them. The masks will ensure she does as they do, after all...";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/bowsette/shybow.jpg", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Reina";
                           this.muse.SubDom = "One True Dominant Queen";
                           this.muse.Spec = "Koopa/Human/Symbiote";
                           this.muse.Desc = "A dangerous woman with no more hesitation or second-guessing. She WILL possess all the princesses, even if she must sneak into their rooms and rape them into broken, submissive slaves to her. ";
                           this.muse.DescSh = "And once she's done with all the kingdoms..well, space is out there, with many planets filled with life. How many more princesses are there to be found? She's willing to find out.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/bowsette/89445fe5b636797e9888bcc55c9eb28a.jpg", name: "" },
                              { pic: "/slideshow/nintendo/bowsette/2d17e37ed09bfc1914625f8a54c9c91d.jpg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Princesses", "", "YES", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "", "Latex", "", "Princess, Goth, Punk, Delinquent"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["YES", "Partner", "", ""]
                     this.muse.kinksB.treatment = ["YES", "Partner", "YES", "Partner", "Partner"]
                     this.muse.kinksB.consent = ["", "YES", "YES", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains, Rope", "", "YES", "YES", "YES"]
                     break
                  case 'pich':
                     this.muse.Uni = "Mario";
                     this.muse.Reg = "Mushroom Kingdom";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Peach Toadstool";
                           this.muse.SubDom = "Submissive unless her partner wants a taste";
                           this.muse.Spec = "Toad/Human";
                           this.muse.Desc = "A bubbly princess with great enthusiasm and love for the people of her kingdom. She may be a princess, but she doesn't always stay in the sidelines. Loves to bake, and dress-up, and do all sorts of sports. She either happily enjoys activities with people, or stubbornly refuses. ";
                           this.muse.DescSh = "Often, her stubbornness is just in order to invite further pressuring and convincing, as well as playing the part of a good kidnapped princess corrupted. If well convinced, she could assist in corrupting and kidnapping fellow princesses";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/peach/c31a9d1306baaffa68a50283ea7c8478.jpeg", name: "Default" },
                              { pic: "/slideshow/nintendo/peach/ba99dfa01c617f8d7859aa1c0aa5325e.png", name: "Driver" },
                              { pic: "/slideshow/nintendo/peach/6d7ade0db7e02521355916647b8c21e6.png", name: "Swimwear" },
                              { pic: "/slideshow/nintendo/peach/c1cfa98c27e251a2a303bb222ba6e46d.jpg", name: "Sports" },
                              { pic: "/slideshow/nintendo/peach/052b4e87c959efad5ca0b8eb8d24004e.jpg", name: "Nurse" },
                              { pic: "/slideshow/nintendo/peach/F2c77X2aQAEC1MD.jpeg", name: "Bimbo" },
                              { pic: "/slideshow/nintendo/peach/651aad609633568d0998e587cdd82874.jpeg", name: "Goth" },
                              { pic: "/slideshow/nintendo/peach/763d3b6dd3615daa4c6fb2bcc2643fb2.jpeg", name: "Koopa Slave" },
                           ];
                           break
                        case 'bow':
                           this.muse.Name = "Peachy";
                           this.muse.SubDom = "Submissive Slave";
                           this.muse.Spec = "Toad/Human";
                           this.muse.Desc = "The Koopa King/Queen's happy little slave, fucked into utter blissful submission after a succesful moon wedding. While legally and technically a wife, Peach knows well from her treatment and the comings of other princesses that she's nothing but Bowsette's slave...and it couldn't have gotten her happier.  ";
                           this.muse.DescSh = "Currently acts as though nothing happened, but observant folk can tell she's a little messier when being rescued than when taken, and the flashes of a very familiar emblem as a tattoo on her body.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: true },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/peach/bow/3272f8fc25b5ba264c8076477cc41506.png", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/763d3b6dd3615daa4c6fb2bcc2643fb2.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/fe4dfc3da62b98b27f5d84ba1de0b72e.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/20230312_183800.jpg", name: "Nun" },
                              { pic: "/slideshow/nintendo/peach/bow/FyN8ZEuaMAAJEjJ.jpeg", name: "CloseUp" },
                              { pic: "/slideshow/nintendo/peach/bow/87e8fa19fc02576ff6e3e7df4a2a76b5.png", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/ea6c270e840a05b00062234522e85477.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/9c913af3db878f8766c6fec2a8d786f2.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/9bd6db67b1f10b945cfe91d71c046cc8.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/001_bowser_koopa_princess_peach_super_mario_bros._cosplay.jpg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/22f50674accb0fb8a749efaae7c435e7.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/b111e2df0a814bdbf69f74faed7c517be1999c57.png", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/a926b030bf03ea98e2cc8253a3350600.png", name: "" },
                              { pic: "/slideshow/nintendo/peach/bow/181fe2943eecf1008d9d4d57394cac98.jpeg", name: "" },
                           ];
                           break
                        case 'shy':
                           this.muse.Name = "Pink";
                           this.muse.SubDom = "Endearingly Submissive";
                           this.muse.Spec = "Shy Gal";
                           this.muse.Desc = "A pink spunky shy gal, who's bashful in a very endearing way, as though hoping you'd catch her and do as you wish to her body. She is permitted the sounds of her giggles, melodious and seductive as they are, as well as her soft moans, which are quite frequent. ";
                           this.muse.DescSh = "She too finds freedom in the anonimity of the mask, and sometimes she forgets she's a princess at all...or her name, or her face. Surely, doing it again won't be a danger?";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: true },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/peach/shypeach.png", name: "" },
                              { pic: "/slideshow/nintendo/peach/765066_thirstypeachy_shy-peach.png", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Amanita";
                           this.muse.SubDom = "Aggressively open to dominating and submitting.";
                           this.muse.Spec = "Toad/Human/Symbiote";
                           this.muse.Desc = "A princess who takes matters into her own hands, tired of playing nice with others. She's still full of love, though covered in spikes and thorns, and capable of growing to a gigantic problem if needed. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/peach/6a4acfed82eb746346aea99a8bda87e3.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/F6hGZY6W8AAAr1T.jpeg", name: "" },
                           ];
                           break
                        case 'shadow':
                           this.muse.Name = "Shadow Queen";
                           this.muse.SubDom = "Dominant even when amused enough to recieve.";
                           this.muse.Spec = "Toad/Human/Shadow";
                           this.muse.Desc = "A dark queen who took over the world many years ago, now possessing Princess Peach to have a second hand at it. The fusion has completed between them, making her agreeable enough to talk, cordial enough to not destroy it all, and physical enough to appreciate pleasures of the flesh. ";
                           this.muse.DescSh = "For the perfect fusion to happen, Peach agreed to combine with the Shadow Queen in full. Neither are as they were before, and the new one carries all of Peach's darker sides...and her tastes.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/peach/shadow/1d6459e3a54e81ef75f900bd9153d80d.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/shadow/b98143d66ce6e49a297a7bbee53fd336.jpg", name: "" },
                              { pic: "/slideshow/nintendo/peach/shadow/32ec183d1d062c81750b4914d72c5f89.png", name: "" },
                              { pic: "/slideshow/nintendo/peach/shadow/b7e3e9a4ea9183ae97c0fa53f4a481e4.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/shadow/F7NULfkWUAA__Ma.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/peach/shadow/F6t7cWJbcAA67wp.jpeg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["YES", "Princesses", "YES", "Koopa", "YES"]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["", "YES", "Frills", "", "Pink"]
                     this.muse.kinksA.bodyMod = ["YES", "Nipple Piercings", "Tattoo", "Butt"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["Partner", "YES", "YES", "YES"]
                     this.muse.kinksB.treatment = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["YES", "Self", "Self", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'lina':
                     this.muse.Uni = "Mario";
                     this.muse.Reg = "Comet Observatory";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Rosalina Estela";
                           this.muse.SubDom = "Soft Dommy Mommy unless convinced otherwise by great force.";
                           this.muse.Spec = "Human/Goddess";
                           this.muse.Desc = "The mother of all stars, Rosalina is a greatly capable mechanic and mother, traveling space for centuries and seeing her babies turn into planets and galaxies. ";
                           this.muse.DescSh = "But even a mother and goddess has needs, and space gets very cold and lonely. Hence her frequent visits to the Mushroom Kingdom, or how she sometimes adopts people as her kids and also does lewd activities with them.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosalina/fb38c00659eb642664c7004149d84310.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/Fzmw5bGWAAAlq2v.jpeg", name: "Driver" },
                              { pic: "/slideshow/nintendo/rosalina/10878353ec3368048c042e1e50f15b7a.jpg", name: "Witch" },
                              { pic: "/slideshow/nintendo/rosalina/09497125e1334763a4dc17a40544ae7c.jpeg", name: "Cosmos" },
                           ];
                           break
                        case 'bow':
                           this.muse.Name = "Rosie";
                           this.muse.SubDom = "Broken Submissive.";
                           this.muse.Spec = "Human/Goddess";
                           this.muse.Desc = "The former mother of all stars, lowered to a pathetic slut after Bowser destroyed her space station and decided to kidnap her on the way. While less of a frequent visitor than Peachy (given Bow's long time love of the Mushroom Princess) she's no less loyal to her monarch. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosalina/13cb108356db2a7210232ed15c816ee6.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/0bffab4318930b85640f61dfb3b91193.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/9c8ea799a33a9fe878fd1ec2bc0de549.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/2ff5e2b4825d0b691e060539024ee493.png", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/14b9689943ce1a95a202944a15c819cb.png", name: "+ Peachy" },
                           ];
                           break
                        case 'shy':
                           this.muse.Name = "Cyan";
                           this.muse.SubDom = "Cuddly Submissive.";
                           this.muse.Spec = "Human/Goddess";
                           this.muse.Desc = "A particularly clingy shy gal, who does her best to stick to you while happily offering her holes. Something is rather ethereal about her, leading to being treated as a rare and lucky find. ";
                           this.muse.DescSh = "She's rather a glutton for semen, and the more she drinks the bigger her boobs grow.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: true },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosalina/dcq0t6g-05d9bdb4-5bab-4b8b-b2df-7e46ef585d53.png", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/aeb77619d0c1b955a6512dc96e2fab339c43655e.jpeg", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Astra";
                           this.muse.SubDom = "Rough Dommy Mommy";
                           this.muse.Spec = "Human/Goddess/Symbiote";
                           this.muse.Desc = "The mother of the galaxy, aided by an aggressive symbiote, who has decided to start being more proactive in her role as a mother, ending entire galaxies rampant with corruption and cruelty, though sheltering the refugees and victims. ";
                           this.muse.DescSh = "A great many few of said refugees vanish for hours or days at a time, returning drained and rather mindless, and Mother looking a little happier.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'shy', emblem: '/versions/shy.png', area: 1, check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/rosalina/6cbefdde2ae7593950779b74dfc966c2.jpg", name: "" },
                              { pic: "/slideshow/nintendo/rosalina/Fxov055XsAEGTOo.jpeg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["YES", "", "YES", "Koopa, Other", ""]
                     this.muse.kinksA.relation = ["Self: Worshipped", "", "Self", "YES", "YES", "Mommy/Daughter (Self/Partner)"]
                     this.muse.kinksA.clothing = ["YES", "", "Spandex, Latex, Living", "", "Dresses"]
                     this.muse.kinksA.bodyMod = ["YES", "", "", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "", "YES", "YES", "YES"]
                     this.muse.kinksB.transform = ["YES", "YES", "YES", ""]
                     this.muse.kinksB.treatment = ["YES", "", "", "Self", ""]
                     this.muse.kinksB.consent = ["YES", "", "", "", "", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "PISS", "DRUGS"]
                     this.muse.kinksB.bondage = ["Tentacles", "YES", "", "", "YES"]
                     break
                  case 'lin':
                     this.muse.Name = "Linkle Ordona";
                     this.muse.SubDom = "Happy Submissive";
                     this.muse.Uni = "Zelda";
                     this.muse.Spec = "Hylian";
                     this.muse.Reg = "Hyrule";
                     this.muse.Desc = "A farmer who believes herself to be the hero of Hyrule, winning over hearts with a sweet smile. She will befriend anyone, as she keeps getting lost and finding herself anywhere. ";
                     this.muse.DescSh = "Fantasizes about taking care of the animals with her body, as well as being defeated by the monsters, only to take the upper hand after loooong long hours of fun sex with them.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/nintendo/linkle/87a9ff4760f1926ad3d61e56c01464c5.png", name: "" },
                        { pic: "/slideshow/nintendo/linkle/4ceaabc63b02170ba79e0bf1a025b57e.png", name: "" },
                        { pic: "/slideshow/nintendo/linkle/FwzG0ItWYAMWipg.jpeg", name: "Heroine" },
                        { pic: "/slideshow/nintendo/linkle/FzVSDuTXoAAEbsK.jpeg", name: "Sheikah Tech" },
                     ];
                     this.muse.kinksA.partner = ["Hylian, Gerudo", "", "", "YES", "YES"]
                     this.muse.kinksA.relation = ["", "Self (Dog)", "Self", "", "", ""]
                     this.muse.kinksA.clothing = ["YES", "Cow, Dog, Horse", "", "Knight, Hero", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["", "", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", ""]
                     this.muse.kinksB.consent = ["YES", "", "", "", "YES", ""]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "YES", ""]
                     this.muse.kinksB.bondage = ["Rope", "", "YES", "YES", ""]
                     break
                  case 'pura':
                     this.muse.Name = "Purah";
                     this.muse.SubDom = "Dominant unless coerced by greater power.";
                     this.muse.Uni = "Zelda";
                     this.muse.Reg = "Hyrule";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Sheikah Hylian";
                           this.muse.Desc = "A pre-Calamity science who aged herself to match the hero and princess (though not without error), she strives to work her way up to the wisdom of the ancient sheikah scientists. Her latest look has drawn much attention. ";
                           this.muse.DescSh = "Ultimately, her eagerness for science is just a tad higher than her ethics, and the only reason she's stuck by the royal family is due to finding a connection with Zelda. Otherwise, she would do anything and anyone if it'd take her tech to greater heights.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', area: 1, check: false },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/purah/bf2aaa998e8f62e0a07a15b0d4f01029.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/purah/F6Wh9SjWgAA_yRU.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/purah/F6afonyWMAA0235.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/purah/6817bd0af302b30bcb584ca8796061c1.jpeg", name: "" },
                           ];
                           break
                        case 'aoc':
                           this.muse.Spec = "Sheikah Hylian";
                           this.muse.Desc = "A very eccentric researcher, older sister to Impa, and working for the royal family of Hyrule. She has found a likeminded soul in Zelda, and does her best to get the tech up to speed to her and the champions' needs, even if sometimes she forgets the world around for her. ";
                           this.muse.DescSh = "It is a great tragedy that all her efforts will not come to help, and she'll have to wait a century to see the world truly safe AND Zelda well and at ease.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', area: 1, check: true },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/purah/500d1db4c6d62d1e046ebc99077bc9fd.jpg", name: "" },
                              { pic: "/slideshow/nintendo/purah/51616c04cb740af681632f830c886c27.jpg", name: "" },
                              { pic: "/slideshow/nintendo/purah/0a49e9db29fde931b3b5cac620fac4bf.jpeg", name: "" },
                              { pic: "/slideshow/nintendo/purah/f9e029308d2145ac82e21f5c33630903.jpeg", name: "" },
                           ];
                           break
                        case 'yiga':
                           this.muse.Spec = "Yiga Hylian";
                           this.muse.Desc = "A woman who defected from the modern Sheikah for refusing technology, and joined up the Yiga to get them back on track for their original ideology. Despite being ruthless and deeply anti-royalty, under her care the Yiga are much less cruel overall, and more affable to non-Hylian Royalty and Sheikah. ";
                           this.muse.DescSh = "She has no intent to harm or destroy the princess, and would much rather kidnap her, keep her to herself, and perhaps use the ancient sheikah tech to brainwash her into an obedient puppet for Ganon...and herself";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', area: 1, check: false },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/purah/F0UTJkdX0AEl96l.jpeg", name: "" },
                           ];
                           break
                        case 'venom':
                           this.muse.Spec = "Sheikah Hylian/Symbiote";
                           this.muse.Desc = "A symbiosis made of a strange goo she found exploring the depths. Unlike most ocassions she kept her name and personality overall, simply adding biological sciences to her studies..and a bit of a sexually aggressive disposition towards a few girls. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', area: 1, check: false },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/purah/Inktober_2023_Day_5.png", name: "" },
                              { pic: "/slideshow/nintendo/purah/113573933_p0.jpg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Hylian, Gerudo", "Yiga", "YES", "YES", ""]
                     this.muse.kinksA.relation = ["", "YES", "YES", "YES", "Zelda", "Mommy (Self, tease)"]
                     this.muse.kinksA.clothing = ["", "", "Nylon, Latex", "YES", "YES"]
                     this.muse.kinksA.bodyMod = ["", "YES", "", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.transform = ["Partner", "Self", "YES", "Partner"]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", ""]
                     this.muse.kinksB.consent = ["", "YES", "", "YES", "", ""]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "", "YES"]
                     this.muse.kinksB.bondage = ["Chains, Tentacles", "YES", "YES", "YES", "YES"]
                     break
                  case 'edel'://need Hegemon Husk picture
                     this.muse.Uni = "Fire Emblem";
                     this.muse.Reg = "Fódlan";
                     this.muse.Desc = "A woman with the weight of the world in her shoulders, carrying great and dark secrets, and dedicated to her goals to dangerous heights. She maintains formality and composure, and trusts in others abilities, but forgets to relax, and her trust does not means she lets her own guard down emotionally. ";
                     this.muse.DescSh = "Has a massive crush on her teacher, Byleth, and if she won't fuck Edelgard herself she'll make sure to fuck Byleth instead.";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Whatever Byleth requires";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/edelgard/991a0b9a63afe274ca6ad64d7d013984.jpg", name: "Default (Student)" },
                              { pic: "/slideshow/nintendo/edelgard/edelgard_von_hresvelg_fire_emblem_and_1_more_drawn_by_lee_domino__a4f0e585d5dc3739397e75d394eef0f2.jpg", name: "Default (Empress)" },
                              { pic: "/slideshow/nintendo/edelgard/3347b98d2a0cbe3ad12f3d6b57077885.jpeg", name: "Summer" },
                              { pic: "/slideshow/nintendo/edelgard/sample-b00beb7c605ded6564f35bec996f76fe.jpg", name: "Modern" },
                           ];
                           break
                        case 'venom':
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.SubDom = "Possessively Dominant";
                           this.muse.Desc = "A girls who's acquired the power to secretly take care of all her foes, and to assert herself against the more socially accepted evils of her society. It's also made her a tad more aggressive in her romantic pursuit of Byleth. ";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/nintendo/edelgard/Inktober_2022_Day_11.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["YES", "", "", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["", "YES", "Nylon, Latex", "School", ""]
                     this.muse.kinksA.bodyMod = ["", "", "Teacher's Pet", "Self"]
                     this.muse.kinksA.mindMod = ["YES", "", "YES", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "", "", "", ""]
                     this.muse.kinksB.consent = ["", "YES", "", "", "YES", ""]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Rope", "", "YES", "YES", "YES"]
                     break
               };
               break
            case 2:
               switch (char) {
                  case 'lisa':
                     this.muse.Uni = "Genshin Impact";
                     this.muse.Reg = "Teyvat, Mondstat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Lisa Minci";
                           this.muse.SubDom = "Soft Mommy";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A totally normal librarian who enjoys resting and relaxation, teasing, and a penchant for action and violence when her peace is threatened, almost to the point of sadism. ";
                           this.muse.DescSh = "Fantasizes of being a mindless slave/drone to greater evils and let herself be used, just for peace of mind.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/lisa/04edc71f920c94af0ad9a98e5c029ff2.jpeg", name: "" },
                              { pic: "/slideshow/games/lisa/e35a3dab594977f6cfe3f4803d1ccf20.jpeg", name: "" },
                              { pic: "/slideshow/games/lisa/F2fwFIJXcAAGvN-.jpeg", name: "" },
                           ];
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescSh = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: true }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                              { pic: "/slideshow/games/lisa/105578655_p2.jpg", name: "Partial (Unmasked)" },
                              { pic: "/slideshow/games/lisa/105578655_p3.jpg", name: "Partial (Masked)" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Fatui", "", "Churls", ""]
                     this.muse.kinksA.relation = ["YES", "Partner", "Self", "YES", "", "Mommy/Daughter (Self/Partner)"]
                     this.muse.kinksA.clothing = ["YES", "", "Nylon, Living", "Fatui", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", ""]
                     this.muse.kinksA.mindMod = ["", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.transform = ["YES", "", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", ""]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'mira':
                     this.muse.Name = "None";
                     this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                     this.muse.Uni = "Genshin Impact";
                     this.muse.Spec = "Mirror Maiden";
                     this.muse.Reg = "Teyvat";
                     this.muse.Desc = "Beautiful minions of the Fatui, with a wicked disposition to others, a loving one to their sisters, and a subservient one to their masters. *They will accept only from their Mistress the diminishing treatment they give to non-Fatui partners*. Most of them look alike, though some a bit different, familiar. Always looking for new recruits. ";
                     this.muse.DescSh = "Said recruits are always unwilling..at first. The Maidens always get them to understand in the end. And they get to keep their appearances on hold to show or discard if it helps them get more recruits.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                        { pic: "/slideshow/games/mirror/56e8db939619057f5a332b49b078fecb.jpg", name: "w/La Signora" },
                        { pic: "/slideshow/games/mirror/105578655_p3.jpg", name: "Lisa?" },
                        { pic: "/slideshow/games/mirror/71bd3c8fecba812bfdd12f7b121e8a27.png", name: "Lumine?" },
                        { pic: "/slideshow/games/mirror/9ed3afc83ac02265959fc2b0c072abb8.jpg", name: "Yelan? (no mask)" },
                        { pic: "/slideshow/games/mirror/7583993d6e254cd277e19d41ac96e952.jpg", name: "Jean? (no mask)" },
                     ];
                     this.muse.kinksA.partner = ["Human", "Fatui, Mirror Maidens", "", "Churls", ""]
                     this.muse.kinksA.relation = ["YES", "YES*", "YES*", "Selves (By Mistress)", "", "Sisters, Mommy (Selves)"]
                     this.muse.kinksA.clothing = ["", "", "Latex, Nylon, Living", "Mirror Maiden", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "Fatui Emblem", "Height, Boobs"]
                     this.muse.kinksA.mindMod = ["Partner", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.transform = ["", "", "", "Mirror Maidens"]
                     this.muse.kinksB.treatment = ["Selves, Mistress", "YES*", "YES*", "YES*", "YES*"]
                     this.muse.kinksB.consent = ["Selves (For Mistress)", "Partners", "Partners", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "", "Inside", "", ""]
                     this.muse.kinksB.bondage = ["Chains: YES*", "YES*", "YES*", "YES*", "YES*"]
                     break
                  case 'lumi':
                     this.muse.Uni = "Genshin Impact";
                     this.muse.Reg = "Teyvat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Lumine";
                           this.muse.SubDom = "Submissive unless suficiently aroused";
                           this.muse.Spec = "Traveler";
                           this.muse.Desc = "A girl who's come from far, far away, many many years ago, to look for her brother. She found him allied with the evil Fatui, and told her to see the world, and so she has, helping every other person who crosses her way, fighting monsters and foes, and dealing with far too much archon bullshit.";
                           this.muse.DescSh = "The pressures of being the Traveler, always helping, always going everywhere, tires her out to the point she'd rather just do nothing but masturbate to the unfairly hot women of Teyvat.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/lumine/11e66b7b5cc1419e1b0858e4be9544bb.png", name: "" },
                              { pic: "/slideshow/games/lumine/__lumine_genshin_impact_drawn_by_pjman__c0ff1ffe67bbb9860f2f7d9766902cd3.jpg", name: "" },
                              { pic: "/slideshow/games/lumine/__lumine_genshin_impact_drawn_by_anzu0130__65bef3508270d2142ffbb33d069624d9.jpg", name: "Bunny" },
                              { pic: "/slideshow/games/lumine/eb0015f4f4e05d944d5b8cb8e644170d.jpg", name: "Nun" },
                              { pic: "/slideshow/games/lumine/c3ad1803736c9b0694187fe12363b1d4.jpg", name: "" },
                              { pic: "/slideshow/games/lumine/727d06a00d853d5c5208f2f4e9f1e5fb.jpg", name: "" },
                              { pic: "/slideshow/games/lumine/4e701b583cb639d9314b27b4f3b1428d.jpg", name: "" },
                           ];
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescSh = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: true }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                              { pic: "/slideshow/games/lumine/105048056_p0.jpg", name: "Partial" },
                              { pic: "/slideshow/games/lumine/71bd3c8fecba812bfdd12f7b121e8a27.png", name: "Partial" },
                              { pic: "/slideshow/games/lumine/188a432e10b889aedd7582634224dd79.jpg", name: "Partial" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Fatui, Eremites", "Automatons", "Churls, Slime", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksA.clothing = ["YES", "YES", "Latex, Nylon, Living", "Fatui", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "YES", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", "Self as Partner"]
                     this.muse.kinksB.treatment = ["Partner", "YES", "", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "Self", "Self", "", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", ""]
                     this.muse.kinksB.bondage = ["Tentacles, Chains, Rope", "YES", "", "", "YES"]
                     break
                  case 'saria':
                     this.muse.Uni = "Genshin Impact";
                     this.muse.Reg = "Teyvat, Mondstat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Rosaria";
                           this.muse.SubDom = "Degenerate Tease or Mommy";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "An utterly terrible yet loyal nun of the Church of Favonius. While she's grateful and indebted to it due to giving her a chance at a better life, she has no focus or interest on the actual religion of it, and uses her self-percieved wickedness she came with to do the more insidious tasks for the sake of them.	";
                           this.muse.DescSh = "Such a thing is quite taxing on her, and so besides smoking, she unwinds by doing all sorts of filthy unchurchlike things with every man and woman that catches her by.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/rosaria/0bbbdc559fe6f196c0c57cc9af267060.png", name: "" },
                              { pic: "/slideshow/games/rosaria/97869340_p0.jpg", name: "" },
                              { pic: "/slideshow/games/rosaria/F7XDgWCXgAABq5Q.jpeg", name: "" },
                              { pic: "/slideshow/games/rosaria/20230217_223805.jpg", name: "" },
                              { pic: "/slideshow/games/rosaria/F11C_ZyWcAABjme.jpeg", name: "" },
                           ];
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescSh = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: true }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                              { pic: "/slideshow/games/rosaria/Koikatu-2023-11-06-21-29-03-Render.png", name: "Partial (Mask)" },
                              { pic: "/slideshow/games/rosaria/Koikatu-2023-11-06-21-29-11-Render.png", name: "Partial (No Mask)" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Fatui", "", "Churls", ""]
                     this.muse.kinksA.relation = ["YES", "", "YES", "", "", "Mommy (Self, Tease)"]
                     this.muse.kinksA.clothing = ["", "", "Nylon, Fishnets", "Nun, Fatui", ""]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", "YES"]
                     this.muse.kinksB.transform = ["", "Partner", "", "YES"]
                     this.muse.kinksB.treatment = ["Self", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "YES", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "", "YES", "YES", "Smoking, Drinking"]
                     this.muse.kinksB.bondage = ["Rope, Chains", "", "YES", "YES", "YES"]
                     break
                  case 'yelan':
                     this.muse.Uni = "Genshin Impact";
                     this.muse.Reg = "Liyue, Mondstat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Yelan";
                           this.muse.SubDom = "Whatever gets her what she wants";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A woman of many ways, mysterious as she is easygoing. She's an intelligence agent with many affiliations, a tragic tale, and an endless amount of dedication to whatever task is given, if still needing to take the most pragmatical route to conserve energy. ";
                           this.muse.DescSh = "Depending on her role, her personage changes. The Lady of the Yanshang Teahouse, is an utter tease, a confident goddess people should kneel for, and a very gallant rewarder of those who's gambles go well.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/yelan/37807d1082c93cb300d668ec6fd162a4.jpg", name: "" },
                              { pic: "/slideshow/games/yelan/3de0f5dd3b5c5fce3c05e719d32d2198.jpeg", name: "" },
                              { pic: "/slideshow/games/yelan/F7HiXdjaIAAT0YG.jpeg", name: "" },
                              { pic: "/slideshow/games/yelan/26c77485d920f775686bd7c6c519e42d.jpeg", name: "Racing" },
                              { pic: "/slideshow/games/yelan/67166677fa5caea77d0d95623f3335fe.jpeg", name: "Racing 2" },
                              { pic: "/slideshow/games/yelan/81e9d623229e4962b5af1a5ec308e065.jpeg", name: "Slingkini" },
                              { pic: "/slideshow/games/yelan/04868b1e8ca68fc517537ddf3e4a2d67.jpeg", name: "Bikini 1" },
                              { pic: "/slideshow/games/yelan/803777a1729723cc52c8619ce949b436.jpeg", name: "Bikini 2" },
                              { pic: "/slideshow/games/yelan/FlRvv0MaYAA2Sk-.jpeg", name: "Gala" },
                           ];
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescSh = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                              { pic: "/slideshow/games/mirror/9ed3afc83ac02265959fc2b0c072abb8.jpg", name: "Partial (no mask)" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Spinerette";
                           this.muse.SubDom = "Eagerly Dominant";
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.Desc = "A woman who's acquired a dear species that has fixed her frail disposition, and fully embraces the persona she had as a lady of the teahouse/casino, more eager than ever to experiment with the more physically and emotionally exhausting kinks she has dreamed of her whole life. ";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', area: 2, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: true }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/yelan/5c802d646cdaff47494e46691638a12c.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Fatui", "", "Churls", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "", "Mommy (Self, Tease)"]
                     this.muse.kinksA.clothing = ["YES", "YES", "Latex, Threads, Fur, Living", "Fatui", "YES"]
                     this.muse.kinksA.bodyMod = ["", "", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", "YES"]
                     this.muse.kinksB.treatment = ["Self", "YES", "", "", "YES"]
                     this.muse.kinksB.consent = ["Self", "", "Partner", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", "Drinking"]
                     this.muse.kinksB.bondage = ["Tentacles, Rope, Threads", "YES", "", "YES", "YES"]
                     break
                  case 'luci':
                     this.muse.Name = "Lucifer Morningstar";
                     this.muse.SubDom = "Absolutely Dominant";
                     this.muse.SubDomSh = " unless genuinely romantically approached, or left powerless";
                     this.muse.Uni = "Helltaker";
                     this.muse.Spec = "Demon ";
                     this.muse.SpecSh = "(Fallen Angel)";
                     this.muse.Reg = "Hell";
                     this.muse.Desc = "A smooth-talking woman who's done the best of her situation. Despite her charm, she's a black-hearted queen with only a few soft spots, fine dining, drinking, worship. She flusters if her authority is upended. ";
                     this.muse.DescSh = "She's very weak outside of actual hell, and secretly likes it when she is abused on her weakness. She will repay when returning to hell, however.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/lucifer/b2732de2b2873cb3abf2b9dc4c893b3d.png", name: "" },
                        { pic: "/slideshow/games/lucifer/8367f54276c4588eb7ace2300782b644.jpeg", name: "Maid" },
                        { pic: "/slideshow/games/lucifer/d64e05cd98c07974eb080c65e152588a.jpg", name: "Falling" },
                        { pic: "/slideshow/games/lucifer/127ea3e69a1d8ccfd4680b14846269f1.jpg", name: "Angel" },
                     ];
                     this.muse.kinksA.partner = ["Devil, Human, Angel", "YES", "", "YES", "YES"]
                     this.muse.kinksA.relation = ["Self: Worshipped", "YES", "YES", "YES", "YES", "Mommy/Daughter"]
                     this.muse.kinksA.clothing = ["YES", "YES", "Leather", "Suit", ""]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["YES", "Partner", "", ""]
                     this.muse.kinksB.treatment = ["Self", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["YES", "YES", "YES", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Tentacles, Chains", "", "YES", "YES", "YES"]
                     break
                  case 'tae':
                     this.muse.Uni = "Persona";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Japan, Yongen-Jaya";
                     this.muse.SubDom = "Dominant unless experimentation requires otherwise";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Tae Takemi";
                           this.muse.Desc = "An excellent, innovative doctor, who got her reputation ruined by standard medical arrogance of others. She has become a black-alley doctor, and while the things she's accused for tend to be fake, she has a sadistic side to her that would put those accusations to shame. ";
                           this.muse.DescSh = "Sometimes she takes advantage of patients' unconscious or unwell state to have her way with them, or test even more dangerous, lascivious products on them.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/tae/0ddb58d96fab71d7f2050bbcc190f0c3.jpg", name: "" },
                              { pic: "/slideshow/games/tae/7ad241cbb4d794ae34f9c75b1fe02306.png", name: "Bimbo" },
                              { pic: "/slideshow/games/tae/1847b8e95a39bc591f3cb57ad764d436.png", name: "Swimwear" },
                              { pic: "/slideshow/games/tae/c50fe2cea710a8a9948c1947d8bd605c2b78f008.jpg", name: "Casual" },
                           ];
                           break
                        case 'phantom':
                           this.muse.Name = "Medic";
                           this.muse.Desc = "A disgraced doctor hired by the Phantom Whores, after being sufficiently perverted in the metaverse. She works undercover at Shujin to provide spaces and tools for sexual recreation, test fertility and arousal drugs, and overall assist in Ann and company's mission. While not active in the cognitive world, her real life contributions make her a worthy Phantom Whore.";
                           //this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: true }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/tae/nyt5qejlays21.jpg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Shadows", "YES", "", ""]
                     this.muse.kinksA.relation = ["", "Partner", "Partner", "Partner", "", ""]
                     this.muse.kinksA.clothing = ["", "", "Latex, Fishnet, Leather, Living", "Doctor", "Punk/Goth"]
                     this.muse.kinksA.bodyMod = ["", "YES", "", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "Partner", "Partner", "Partner", ""]
                     this.muse.kinksB.transform = ["YES", "Partner", "YES", "Partner as Self"]
                     this.muse.kinksB.treatment = ["Self", "Partner", "", "Partner", "Partner"]
                     this.muse.kinksB.consent = ["YES", "Partner", "Partner", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", "Medical, Smoking"]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'ann':
                     this.muse.Uni = "Persona";
                     this.muse.Reg = "Japan, Yongen-Jaya";
                     switch (au) {
                        case 'base':
                           this.muse.SubDom = "Mood-depending switch";
                           this.muse.Spec = "Human";
                           this.muse.Name = "Ann Takamaki";
                           this.muse.Desc = "A fiery girl who works as a model, and goes to school like an average girl. She loves sweets, her girlfriend Shiho, and hates injustice. Feels strongly about how she's perceived by others, be it her womanhood, her sexuality, her race, or her body. And she's perfectly willing to take control and show them all wrong. ";
                           this.muse.DescSh = "Though at times, she just wants to give in to everyone's perception of her as a bimbo and a slut, and drag her girlfriend down with her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/ann/ddzrqzu-c2aead5f-8e50-44d3-9e36-4df4e8f92a8e.jpg", name: "Ann & Shiho" },
                              { pic: "/slideshow/games/ann/1b3478397473a7764793fa6798b43046.jpeg", name: "Student" },
                              { pic: "/slideshow/games/ann/F1vsf5oWAAE4tQa.jpeg", name: "Goth" },
                              { pic: "/slideshow/games/ann/FxuL3tnXwAASXjS.jpeg", name: "Maid" },
                              { pic: "/slideshow/games/ann/20230923_185839.jpg", name: "Dance" },
                           ];
                           break
                        case 'phantom':
                           this.muse.SubDom = "Whatever she feels like";
                           this.muse.Name = "Panther/Kitten";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "After Ann and Shiho fused with the cognitive versions of themselves in Kamoshida's palace, Ann became every bit the slut she was seen as, but her persona kept her fiery dominance and hatred of Kamoshida. After his defeat, this new Ann has decided to kick the world's libido into high gear, seducing shadows in the cognitive world to turn everyone into perverts, alongside her slutty bunny girlfriend Shiho.";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/ann/F2OiSsGWMAAj2iI.jpeg", name: "Panther" },
                              { pic: "/slideshow/games/ann/c6b8c952fe76a4f01ac29006cfe25b86.png", name: "Cognitive" },
                              { pic: "/slideshow/games/ann/FzrkC7LaMAE7cAH.jpeg", name: "Cognitive Corruption" },
                              { pic: "/slideshow/games/ann/LDlnggKn.jpg", name: "Kitty and Bunny (1)" },
                              { pic: "/slideshow/games/ann/a2b26d0aff5a9a572a7dce7acd156883.jpg", name: "Kitty and Bunny (2)" },
                           ];
                           break
                        case 'venom':
                           this.muse.SubDom = "Whatever she feels like";
                           this.muse.Name = "Puma";
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.Desc = "Found a strange shadow which fused with her, endowing her with the greatest power for a model (clothing control), and an even greater penchant for violence. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/ann/venomann.jpeg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Shadows", "", "", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "Already has one, would love more", ""]
                     this.muse.kinksA.clothing = ["YES", "YES (Kitten, Panther)", "Latex, Living", "", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["Partner", "YES", "", ""]
                     this.muse.kinksB.treatment = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["Self", "YES", "YES", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'sae':
                     this.muse.Uni = "Persona";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Japan, Yongen-Jaya";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Sae Nijima";
                           this.muse.SubDom = "Dominant unless tired";
                           this.muse.Desc = "A fierce prosecutor who's eternally overworked, undervalued, and ready to strike. She cares deeply for her sister Makoto, but having to care for her as a mother has greatly twisted and strained their relationship. ";
                           this.muse.DescSh = "She sees the law as a game of chance that she must manipulate in her favor, and intends to place everyone beneath her heel, with her sister to serve her instead.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/sae/49744d416f80de61bff47499c55b651f.png", name: "" },
                              { pic: "/slideshow/games/sae/9a9779b01d27cf2f6384cc5a187dcbe7.jpg", name: "Suit" },
                              { pic: "/slideshow/games/sae/a69df5bd0e5f00e82f3f327741d388a9.jpg", name: "Fancy" },
                              { pic: "/slideshow/games/sae/49744d416f80de61bff47499c55b651f.png", name: "" },
                           ];
                           break
                        case 'phantom':
                           this.muse.Name = "Lady Luck";
                           this.muse.SubDom = "Whatever the fortune might bring.";
                           this.muse.SubDomSh = "..though she cheats to always win and dominate.";
                           this.muse.Desc = "The twisted true self of a prosecutor, fed up with the gambles of the law and intending to make it her own. With assistance from the Phantom Whores, she fused with her non-cognitive self, and made it to the top of the legal ladder through trickery and perversion, letting the PW's perverted actions and goals slide, as they provide pleasure for her as well, in real life or in the metaverse. "
                           this.muse.DescSh = "The shadows of those who stand against perversion, or use it for their own without the enjoyment of the other, are let to suffer and wander her casino forever, their real selves too lost to commit further crimes against lust.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: false },
                              { au: 'phantom', emblem: '/versions/annemblem.jpg', area: 2, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/sae/0e07e37e851c260fc012ab67adfaedfc.jpeg", name: "Shadow" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "Shadows", "", "", ""]
                     this.muse.kinksA.relation = ["", "Partner", "Partner", "Partner", "", "Sisters"]
                     this.muse.kinksA.clothing = ["", "", "Nylon", "Suit", ""]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "Partner", "", "", ""]
                     this.muse.kinksB.transform = ["Partner", "YES", "", ""]
                     this.muse.kinksB.treatment = ["", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.consent = ["", "Partner", "Partner", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains, Rope", "YES", "YES", "YES", ""]
                     break
                  case 'moni':
                     this.muse.Name = "Monika";
                     this.muse.NameSh = ".chr";
                     this.muse.SubDom = "She'll take charge if necessary, but if you want otherwise she's up for it.";
                     this.muse.Uni = "DDLC";
                     this.muse.Spec = "Human ";
                     this.muse.SpecSh = "Character File";
                     this.muse.Reg = "Close. ";
                     this.muse.RegSh = "In your computer, DDLC.exe";
                     this.muse.Desc = "The smartest, kindest, most beautiful girl in school, who's decided you are her soulmate, and is distraught by you focusing on the other members of her Literature Club. She will happily use her dedication to make sure you only look at her. ";
                     this.muse.DescSh = "Though, she does find the girls rather attractive herself...she wouldn't mind them around, if they acknowledge her as the head girlfriend. She'll make sure they love her too. She has her ways.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }];
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/monika/e2548ef163462a384ffa9d2787baeced.jpg", name: "" },
                        { pic: "/slideshow/games/monika/e4256a99d841fce08cf74f9d6bbba1d9.png", name: "Swimwear" },
                        { pic: "/slideshow/games/monika/8bb01a4fb48429db486cdef5a9610d39.jpg", name: "Gynoid/AI" },
                        { pic: "/slideshow/games/monika/5c8304651e0ab2dad5050a5494ffb0fb.jpg", name: "Dress" },
                        { pic: "/slideshow/games/monika/FwvhopNagAEefYk.jpeg", name: "Maid" },
                        { pic: "/slideshow/games/monika/3d5dc32389b6dc0da7b2df788f971697.jpg", name: "Nurse" },
                        { pic: "/slideshow/games/monika/715e3b9ad2c785a39651e16c15eacfdc.jpeg", name: "" },
                        { pic: "/slideshow/games/monika/b5fc6dbea7ede96b837f2c9c92d2fc08.png", name: "" },
                     ];
                     this.muse.kinksA.partner = ["YES", "", "", "", ""]
                     this.muse.kinksA.relation = ["", "", "You", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "YES", "Nylon", "School", "Dresses"]
                     this.muse.kinksA.bodyMod = ["YES", "", "YES", ""]
                     this.muse.kinksA.mindMod = ["Her", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["Her", "Her", "Her", ""]
                     this.muse.kinksB.treatment = ["You", "Her", "Her", "Her", "Her"]
                     this.muse.kinksB.consent = ["Her", "You", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'roty':
                     this.muse.Name = "Rottytops";
                     this.muse.SubDom = "YES";
                     this.muse.Uni = "Shantae";
                     this.muse.Spec = "Zombie";
                     this.muse.Reg = "Zombie Caravan";
                     this.muse.Desc = "A cheerful zombie who enjoys cosplay and teasing, Rotty is Shantae's bestest undead friend. Despite genuinely caring for Shantae, she's conniving, tricky and naughty in every single way. It's part of her charm, and sorely wishes to 'corrupt' Shantae. ";
                     this.muse.DescSh = "Preferably by dating her, kissing her, eating her out, and doing all sorts of fun stuff to her body.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }];
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/rotty/feffd59b4324254193be6491a4b2f2fc.jpeg", name: "" },
                        { pic: "/slideshow/games/rotty/5b74be007d3c3ee411f6656123cfee21.png", name: "Alive" },
                        { pic: "/slideshow/games/rotty/1c2d488bd0e56fcfdcd3bf22f978e67e.jpeg", name: "Royal Princess" },
                        { pic: "/slideshow/games/rotty/73e9f9723e59f1f8b70ae9f26bd2f163.jpeg", name: "Racing" },
                        { pic: "/slideshow/games/rotty/7b77b2e003914d464fdb413c41878edd.png", name: "Genie" },
                     ];
                     this.muse.kinksA.partner = ["Human, Half-Genies", "", "YES", "YES", ""]
                     this.muse.kinksA.relation = ["", "YES", "YES", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "YES", "", "YES", "YES"]
                     this.muse.kinksA.bodyMod = ["", "YES", "YES", "Splitting"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.transform = ["YES", "YES", "YES", "Partner: Zombiefication"]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", ""]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'shan':
                     this.muse.Uni = "Shantae";
                     this.muse.Reg = "Scuttle Town";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Shantae";
                           this.muse.Spec = "Genie/Human";
                           this.muse.SubDom = "Sub when approached, Dom when approaching";
                           this.muse.Desc = "A half-genie hero, worthy of said title by her care for others and dedication to helping...even if it is thwarted by annoyances, both villainous and even allied. She rarely holds any ill will regardless, and has helped her foes if need be a good amount of times. ";
                           this.muse.DescSh = "She is rather aware that she's surrounded by very hot gals, and has given serious thought to fooling around with all of them. Even Risky Boots.";
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/shantae/da9f39f2daf65c877b9010f3879319c6.jpeg", name: "Default" },
                              { pic: "/slideshow/games/shantae/F69UEkKaEAAEjkU.jpeg", name: "Royal Princess" },
                              { pic: "/slideshow/games/shantae/e773b81e7a0e17b9cd7b3ef7b23c2a46.png", name: "Bunny" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 2, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 2, check: false }
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Kali";
                           this.muse.Spec = "Genie/Human/Symbiote";
                           this.muse.SubDom = "Teasing Switch";
                           this.muse.Desc = "A transformation gone awry, Shantae has not transformed back since she found this form. It's made her much more willing to use sex appeal, flirt with her foes, and more flexible with her morals. ";
                           this.muse.DescSh = "";
                           this.muse.slideArray = [
                              { pic: "/slideshow/games/shantae/F9ewFlgakAA5rNo.jpeg", name: "" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 1, check: true }
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human, Zombie", "YES", "YES", "YES", ""]
                     this.muse.kinksA.relation = ["YES", "Self", "Self", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["", "", "Nylon, Satin", "", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "", "YES"]
                     this.muse.kinksA.mindMod = ["Self", "Self", "Self", "Self", ""]
                     this.muse.kinksB.transform = ["", "", "Self", "YES"]
                     this.muse.kinksB.treatment = ["YES", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["", "Self", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Self: Rope, Tentacle, Chains", "YES", "Self", "Self", "Self"]
                     break
                  case 'junko':
                     this.muse.Name = "Junko Enoshima";
                     this.muse.SubDom = "Dominant unless submission causes her despair";
                     this.muse.Uni = "Danganronpa";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Japan";
                     this.muse.Desc = "The ultimate fashionista, but ultimately just a girl who turns despair into pleasure for herself, she wants nothing but to share what she feels with everyone in the world. She's twisted, switches between states of self constantly, and her victory and defeat taste equally good to someone as utterly despairful as herself. There's nothing to hide anymore.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/junko/F5aj5MiWIAA58us.jpeg", name: "Default" },
                        { pic: "/slideshow/games/junko/F3lnjAXbwAE9xc_.jpeg", name: "Bunny" },
                        { pic: "/slideshow/games/junko/108590748_p0.png", name: "Succubus" },
                     ];
                     this.muse.kinksA.partner = ["Human", "YES", "YES", "YES", "YES"]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "", "Sisters"]
                     this.muse.kinksA.clothing = ["YES", "YES", "", "YES", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.transform = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksB.treatment = ["Self", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "", "YES", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.bondage = ["YES", "YES", "YES", "YES", "YES"]
                     break
                  case 'nami':
                     this.muse.Name = "Chiaki Nanami";
                     this.muse.SubDom = "Weak submissive, Shy dom";
                     this.muse.Uni = "Danganronpa";
                     this.muse.Spec = "Human";
                     this.muse.SpecSh = ", then Program";
                     this.muse.Reg = "Japan";
                     this.muse.Desc = "The ultimate gamer, all but for dating sims. She's rather soft-spoken, and gentle, to the point of even second-guessing her own statements and ideas. But ultimately she is well-meaning and easy to get along with by everyone. ";
                     this.muse.DescSh = "Recently she's really been getting into lewd games...with all the kinks they teach. Still as bad at them as in dating sims however.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/chiaki/Fzk7OxkWIAMQZ0s.jpeg", name: "Default" },
                        { pic: "/slideshow/games/chiaki/Fzk7OxkXwAEx93B.jpeg", name: "Bunny" },
                     ];
                     this.muse.kinksA.partner = ["Human", "YES", "YES", "YES", ""]
                     this.muse.kinksA.relation = ["", "Self", "Self", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["", "YES (Bunny)", "Nylon, Fur, Living", "YES", "Hoodie"]
                     this.muse.kinksA.bodyMod = ["YES", "", "", "YES"]
                     this.muse.kinksA.mindMod = ["Self", "Self", "Self", "Self", ""]
                     this.muse.kinksB.transform = ["Self", "Self", "Self", "Self as Partner"]
                     this.muse.kinksB.treatment = ["YES", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["", "Self", "", "", "", ""]
                     this.muse.kinksB.substance = ["Milk", "", "Inside", "YES", ""]
                     this.muse.kinksB.bondage = ["Self: Rope, Tentacles, Chains", "Self", "Self", "Self", "Self"]
                     break
                  case 'layer':
                     this.muse.Name = "Layer";
                     this.muse.SubDom = "Subby until she gains confidence in the relationship";
                     this.muse.Uni = "Megaman";
                     this.muse.Spec = "Reploid";
                     this.muse.Reg = "Galápagos Islands";
                     this.muse.Desc = "The picture of a professional and capable Navigator Reploid..until romance comes into play. At which point she'll become a flustered, shy disaster. Good thing her bangs cover her eyes...even if her top doesn't cover the bottom of her chest."
                     this.muse.DescSh = "Gaining enough confidence in her romantic situation unlocks her confident mommy side...but it's a slow burn to get there. Before however? She'll let her interest do whatever they want to her."
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/layer/19052cd52d469549743b2096679d6be4.jpeg", name: "Default" },
                        { pic: "/slideshow/games/layer/Mega_Man_X_DiVE_Hunter_Program_Bridal_Layer.png", name: "Swimsuit" },
                        { pic: "/slideshow/games/layer/Mega_Man_X_DiVE_Hunter_Program_Swimsuit_Layer.png", name: "Bridal" },
                     ];
                     this.muse.kinksA.partner = ["Human, Reploids", "", "YES", "", ""]
                     this.muse.kinksA.relation = ["", "", "", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["", "", "Nylon, Armor", "", "YES"]
                     this.muse.kinksA.bodyMod = ["Wants to", "", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "", "", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "Partner", ""]
                     this.muse.kinksB.treatment = ["YES", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Tentacles", "", "YES", "YES", "YES"]
                     break
                  case 'ruler':
                     this.muse.Name = "Ruler";
                     this.muse.NameSh = ": Artoria Pendragon"
                     this.muse.SubDom = "Dominant unless you win";
                     this.muse.Uni = "Type Moon";
                     this.muse.Spec = "Heroic Spirit ";
                     this.muse.SpecSh = " (Heavenly)";
                     this.muse.Reg = "???";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.Desc = "A woman who enjoys food and battle, turned human heroic spirit, and grown into a Heaven Heroic Spirit. While much more composed due to her growth, flashes of her battle-hungry (and general appetite hungry) self still shine through at times. Currently she is enjoying the world once more, this time as the greatest casino dealer. ";
                     this.muse.DescSh = "Another kind of hunger has awakened in her more mature form, and she will feed on it kindly if finding a victor, or harshly if finding a cheater.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/ruler/6cae2a91e24c15c17082e35557406a46.jpeg", name: "" },
                        { pic: "/slideshow/games/ruler/artoria_pendragon_and_artoria_pendragon_fate_and_1_more_drawn_by_rororo__a46e6055325da9723b6ef05053ffdca3.jpg", name: "" },
                        { pic: "/slideshow/games/ruler/F2F6pTlboAAJnal.png", name: "" },
                        { pic: "/slideshow/games/ruler/4537316e91107122c94ad05602b19ada.jpeg", name: "Lancer" },
                        { pic: "/slideshow/games/ruler/Lancer.Artoria.Pendragon.full.2237522.png", name: "Lancer" },
                     ];
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["Worshipped", "Partner", "Partner", "Partner", "", "Mommy (Self)"]
                     this.muse.kinksA.clothing = ["", "Yes (Bunny)", "Nylon, Fishnet, Fur", "", "Armor"]
                     this.muse.kinksA.bodyMod = ["YES", "", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["", "", "", "Partner as Self"]
                     this.muse.kinksB.treatment = ["Self", "", "YES", "", ""]
                     this.muse.kinksB.consent = ["", "Partner", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["YES", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains, Rope", "", "YES", "YES", "YES"]
                     break
                  case 'ridem':
                     this.muse.Name = "Rider";
                     this.muse.NameSh = ": Medusa"
                     this.muse.SubDom = "Indifferent switch";
                     this.muse.Uni = "Type Moon";
                     this.muse.Spec = "Heroic Spirit";
                     this.muse.Reg = "???";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.Desc = "A woman who conceals both her emotions and eyes, hiding beauty and horrors behind both. She is completely loyal to her Master, and is not ultimately cruel, though she is hampered by a great deal of self-consciousness. ";
                     this.muse.DescSh = "She also hides a lot of care, for those who reciprocate loyalty to her, or those who remind of herself. Only with them will she let her emotions out...all of them. Very enthusiastically.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/games/rider/sample_8065e084ae67fde06ae486da56da9c0a.jpg", name: "" },
                        { pic: "/slideshow/games/rider/sample_681b7b7ed08478e804c3661dcf1bc50a.jpg", name: "Casual" },
                        { pic: "/slideshow/games/rider/f119fe4107115f09b54a57fd09217fe4.jpg", name: "Maid" },
                        { pic: "/slideshow/games/rider/718b96f51aff0a11aff04e36281960e8.png", name: "Office" },
                        { pic: "/slideshow/games/rider/abe9a44ba429c07cd692c74f83465f1b.jpeg", name: "Gorgon" },
                        { pic: "/slideshow/games/rider/5ed5e2c9d755f14431620e791c860406.png", name: "Charming Bunny" },
                        { pic: "/slideshow/games/rider/Medusa's_Mobile_Woman_Miss_Medusa.png", name: "Mecha Lady" },
                     ];
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["Self", "", "Self", "Self", "YES", ""]
                     this.muse.kinksA.clothing = ["", "YES (Bunny)", "Living", "Office, Maid", "Covering"]
                     this.muse.kinksA.bodyMod = ["", "YES", "YES", ""]
                     this.muse.kinksA.mindMod = ["", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["", "", "YES", ""]
                     this.muse.kinksB.treatment = ["Partner", "", "", "", ""]
                     this.muse.kinksB.consent = ["", "YES", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains, Tentacles (Snakes)", "YES", "YES", "", "YES"]
                     break
               };
               break
            case 3:
               switch (char) {
                  case 'mei':
                     this.muse.Name = "Mei Hatsume";
                     this.muse.SubDom = "Dom when hyperfocused, Subby when taken out of focus";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "The greatest engineer in quirked history, she's brilliant, bombastic, and can't remember silly things like names, hygiene, or shame. All she needs in her world are her babies, and what girls may take an interest in her and her babies. ";
                     this.muse.DescSh = "Is more into machines than humans, would roboticize every hot girl she meets if she could.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/mei/sample_dda6ea4d54a7ac6dd6890edb42a5f486.jpg", name: "" },
                        { pic: "/slideshow/mha/mei/a9ded8aca3a918724306724dfae98c6c.jpeg", name: "" },
                        { pic: "/slideshow/mha/mei/dee8ffe4aeba3829d392b04b012b9b6a.png", name: "" },
                        { pic: "/slideshow/mha/mei/0643ecd531e0fdfd8c251b574e78a2c3.jpeg", name: "" },
                        { pic: "/slideshow/mha/mei/070936212164736786b2096bf6b69085.jpeg", name: "Bunny" },
                        { pic: "/slideshow/mha/mei/b3ee48710e50498d7b22659dbf6dcb2e.jpeg", name: "Bimbo" },
                        { pic: "/slideshow/mha/mei/FyOb2p6XgAQugw1.jpeg", name: "Cheerleader" },
                     ];
                     this.muse.kinksA.partner = ["", "", "YES", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "", "", "Partner", "", ""]
                     this.muse.kinksA.clothing = ["YES", "", "Spandex, Latex", "", ""]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "", ""]
                     this.muse.kinksA.mindMod = ["Already lacks morals", "", "YES", "YES", ""]
                     this.muse.kinksB.transform = ["", "", "YES", ""]
                     this.muse.kinksB.treatment = ["YES", "", "", "Partner", ""]
                     this.muse.kinksB.consent = ["", "YES", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Tentacles, Chains", "YES", "YES", "YES", "YES"]
                     break
                  case 'tsu':
                     this.muse.Name = "Tsuyu Asui (Froppy)";
                     this.muse.SubDom = "Whatever strikes the mood";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A hero in training with big dreams, a long tongue, and zero ability to hold either in. She is adored by many, and her quirks (pun intended) are charming to many, just as she adores her classmates. ";
                     this.muse.DescSh = "She has enough sense not to bring up how often she wants to wrap and tongue-fuck her female classmates daily...unless they ask.";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked), Frog";
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/tsuyu/9a02873a1ed31a5408ac382c372cd71d.jpeg", name: "" },
                              { pic: "/slideshow/mha/tsuyu/5377be761b1701aaa96419f804dd6865.jpeg", name: "" },
                              { pic: "/slideshow/mha/tsuyu/vVSBMMhF.jpeg", name: "Bunny" },
                              { pic: "/slideshow/mha/tsuyu/96d509440c6e1e571c7a900948b7f823.jpg", name: "Bimbo" },
                              { pic: "/slideshow/mha/tsuyu/88948762_p0.png", name: "Club" },
                              { pic: "/slideshow/mha/tsuyu/FyOb0OkXgAEQOtz.jpeg", name: "Cheerleader" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: false }
                           ]
                           break
                        case 'venom':

                           this.muse.Spec = "Human (Quirked), Frog, Symbiote";
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/tsuyu/b06239b9ccbd228ae22a0770e4e02716.jpeg", name: "" },
                              { pic: "/slideshow/mha/tsuyu/Inktober_Day_12.png", name: "" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: true }
                           ]
                           break
                     }
                     this.muse.kinksA.partner = ["Mutant", "", "", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "YES", "", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "YES", "Spandex", "School", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "", "Tongue (Self)"]
                     this.muse.kinksA.mindMod = ["YES", "", "YES", "", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "", ""]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", "YES"]
                     this.muse.kinksB.consent = ["YES", "", "", "", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", "Hallucinogens"]
                     this.muse.kinksB.bondage = ["Chain, Tentacle", "YES", "YES", "YES", "YES"]
                     break
                  case 'mina':
                     this.muse.Name = "Mina Ashido (Pinky)";
                     this.muse.SubDom = "YES";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A funky, spunky, alien-looking gal with a good heart, and a gooder sense of fun. She will spend her days scheming over her friends love lives, organize games, and save the world dancing away. ";
                     this.muse.DescSh = "With all her boundless energy come hours upon hours of sex, and she's specifically tailored her hero suit to attract that attention. Midnight is her icon for a reason.";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked), Alien";
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/mina/f2e72c4b41eef9e924bba8f63ad38829ce26f846.png", name: "" },
                              { pic: "/slideshow/mha/mina/4c88350d822bb0e36b36a2a0e2d8b802.jpeg", name: "" },
                              { pic: "/slideshow/mha/mina/bcee4ce87c56f6bd3b16b032f48f664d.png", name: "Non-Mutant" },
                              { pic: "/slideshow/mha/mina/FyOb0tJWwAE5-3s.jpeg", name: "Cheerleader" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: false }
                           ]
                           break
                        case 'venom':
                           this.muse.Spec = "Human (Quirked), Alien, Symbiote";
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/mina/f3fce8bb8e3594bc4babb4714b330c0e.jpeg", name: "" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: true }
                           ]
                           break
                     }
                     this.muse.kinksA.partner = ["Human, Mutant", "YES", "", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "", "Self", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "YES", "Fishnets, Spandex, Fur, Living", "Cheerleader", "Gyaru, Eye-searing"]
                     this.muse.kinksA.bodyMod = ["YES", "Nipple Piercings", "Tramp Stamp, Body Writing", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["Partner", "YES", "", ""]
                     this.muse.kinksB.treatment = ["YES", "YES", "", "", "YES"]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["Milk", "Likes Partner's, NO from Self (likely toxic)", "YES", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Tentacles", "", "YES", "YES", ""]
                     break
                  case 'momo':
                     this.muse.Name = "Momo Yaoyorozu (Creati)";
                     this.muse.SubDom = "Shyly submissive until gaining confidence to engage Mommy Momo mode";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Nat = "Regal";
                     this.muse.Reg = "Japan, Musatafu";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked)";
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/momo/main-qimg-8cb39c71ad6f086a1c4078a37074b43c-lq.jpeg", name: "" },
                              { pic: "/slideshow/mha/momo/60f9a161cd4a6c83ff862ee65469b6af.jpg", name: "" },
                              { pic: "/slideshow/mha/momo/77f00e118042523f81d3998708bda4ef.jpeg", name: "Reverse Hero Suit" },
                              { pic: "/slideshow/mha/momo/852964f1599670989925113718dbe889.png", name: "Gala" },
                              { pic: "/slideshow/mha/momo/e0c6ac1780d9529c4cd0ec8f8c0f7dc9.jpeg", name: "Villain (Empress)" },
                              { pic: "/slideshow/mha/momo/20230828_000331.jpg", name: "Swimwear" },
                              { pic: "/slideshow/mha/momo/89683124_p0.png", name: "Club" },
                              { pic: "/slideshow/mha/momo/FyOb1nVWAAExxkE.jpeg", name: "Cheerleader" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: false }
                           ]
                           break
                        case 'venom':

                           this.muse.Spec = "Human (Quirked)/Symbiote";
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/momo/0320b9e112924d7772bbc7edeee25df0.jpeg", name: "" },
                           ];
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: true }
                           ]
                           break
                     }
                     this.muse.Desc = "A girl born of wealth with a genuine heart of gold and a mind that holds great knowledge. Despite her dazzling intellect, astonishing quirk, and stunning beauty, her confidence needs some serious work. But she will always stand by the side of her friends. ";
                     this.muse.DescSh = "Headmistress Midnight has taken her in as a pseudo-daughter and a successor to her spirit, and she intends to work hard on her confidence to live up to it and become the newest Mistress of heroics.";

                     this.muse.kinksA.partner = ["Human", "", "YES", "Noumu", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "YES", "Mommy/Daughter"]
                     this.muse.kinksA.clothing = ["YES", "YES", "Latex, Living", "Cheerleader, Student", "Fancy"]
                     this.muse.kinksA.bodyMod = ["YES", "", "Body Writing", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "", "YES", "YES", ""]
                     this.muse.kinksB.transform = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksB.treatment = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains, Rope", "", "YES", "YES", "YES"]
                     break
                  case 'toru':
                     this.muse.Name = "Tooru Hagakure (Invisible Girl)";
                     this.muse.SubDom = "Casual Switch";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A girl born invisible, pushing herself to be loud and bright and seen. Thanks to her friends and training, she has become more visible than ever at UA, thus aiming as a hero to look out for others who might be left unseen. ";
                     this.muse.DescSh = "People watching is her hobby, which has often veered into very perverted situations...not that she minds the show, or interrupts, or even leaves. Also has developed a nudist streak.";

                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/tooru/Hagakure.Tooru.full.3919308.jpg", name: "" },
                        { pic: "/slideshow/mha/tooru/F71bqI2WoAA14BG.jpeg", name: "" },
                        { pic: "/slideshow/mha/tooru/F71bqI0XIAAc-2a.jpeg", name: "" },
                        { pic: "/slideshow/mha/tooru/F71bqIzXEAAMMYQ.jpeg", name: "" },
                        { pic: "/slideshow/mha/tooru/112018813_p0.jpg", name: "Maid" },
                        { pic: "/slideshow/mha/tooru/1cbd4b178a48020590b106d2c06e42c9.jpg", name: "Cheerleader" },
                     ];
                     this.muse.kinksA.partner = ["Human", "YES", "", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "", "", "", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "", "", "School, Cheerleader", "YES"]
                     this.muse.kinksA.bodyMod = ["", "YES", "", ""]
                     this.muse.kinksA.mindMod = ["", "", "", "", "YES"]
                     this.muse.kinksB.transform = ["", "", "YES", ""]
                     this.muse.kinksB.treatment = ["YES", "", "", "", "YES"]
                     this.muse.kinksB.consent = ["YES", "Partner", "Partner", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "", "Outside", "YES", ""]
                     this.muse.kinksB.bondage = ["Rope, Tape", "", "YES", "YES", ""]
                     break
                  case 'kendo':
                     this.muse.Name = "Itsuka Kendo (Battle Fist)";
                     this.muse.SubDom = "Submissive to any request, but dominant if requested";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";

                     this.muse.Desc = "A martial artist with a big brain, big heart, and bigger hands, the class representative of class B is as ruthless with her criticism as her combative disposition. She does however have a tendency to let go for others, neglecting her own wants and needs. ";
                     this.muse.DescSh = "One can only hope her friend slash crush Setsuna does not take advantage of that...or that she lets herself go along the rather sexualized world of female pro-heroism.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/kendo/6f68458d1b5ac5fb59c26bb25bbb1bcf.png", name: "" },
                        { pic: "/slideshow/mha/kendo/1616255971cf8e9f0e65efcfafdd7010.jpeg", name: "" },
                        { pic: "/slideshow/mha/kendo/e9128f106e5477929a83861375a43608.jpeg", name: "" },
                        { pic: "/slideshow/mha/kendo/f70abb85fd8a0b54b1bba4983e33f616.jpeg", name: "" },
                        { pic: "/slideshow/mha/kendo/FyOb3udXoAA4PhX.jpeg", name: "Cheerleader" },
                     ];
                     this.muse.kinksA.partner = ["Human, Mutant", "YES", "YES", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "", "Self", "Self", "YES", ""]
                     this.muse.kinksA.clothing = ["", "YES", "Spandex, Living", "Cheerleader", "Martial Arts, Exercise"]
                     this.muse.kinksA.bodyMod = ["Self", "", "Body Writing", "Self"]
                     this.muse.kinksA.mindMod = ["Self", "Self", "", "", ""]
                     this.muse.kinksB.transform = ["Self", "Self", "", "Of Partner"]
                     this.muse.kinksB.treatment = ["Partner", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["Self", "Self", "", "", "Self", "Self"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", "Self"]
                     this.muse.kinksB.bondage = ["Self: Chains, Ropes, Tentacles, Tape", "Self", "YES", "Self", "Self"]
                     break
                  case 'camie':
                     this.muse.Name = "Camie Utsushimi (Illus-o-Camie)";
                     this.muse.SubDom = "Dominant unless finding something kinky and fun worth subbing for.";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.Desc = "A Ketsubutsu-taught pro-heroine in training, with a bubbly and absentminded demeanor that's hard to understand at times, but covering for remarkable cleverness of both quirk use and emotional insight. ";
                     this.muse.DescSh = "Her hero outfit and flirtatiousness bely the fact that she likes to draw in the attention, the only question being, what she will do with that attention. She knows quite well the answer will be 'whatever Camie desires'.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/camie/sample_cd5a72fff0811bf699eac745d9558f8b.jpg", name: "" },
                        { pic: "/slideshow/mha/camie/eddc0a669bd753cd7351dc43ed73eacf.jpg", name: "" },
                        { pic: "/slideshow/mha/camie/7c726c4ed8294737a4b890f72bc2a8ed.jpg", name: "School Uniform" },
                        { pic: "/slideshow/mha/camie/221f426d40a6f06f27525a6126d6faae.jpg", name: "" },
                        { pic: "/slideshow/mha/camie/3401d01aa678a8bebbf233a2143ecdba.png", name: "X-mas" },
                        { pic: "/slideshow/mha/camie/406e48e10251345bd347defdb117fda9.jpeg", name: "Swimwear" },
                     ];
                     this.muse.kinksA.partner = ["Human", "YES", "", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "YES", "YES", "", "", ""]
                     this.muse.kinksA.clothing = ["", "YES", "Latex, Leather, Living", "", "YES"]
                     this.muse.kinksA.bodyMod = ["", "YES", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "", "YES", "", ""]
                     this.muse.kinksB.transform = ["Partner", "YES", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["Self", "", "", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", "Smoking, Hallucinogens"]
                     this.muse.kinksB.bondage = ["Tentacles, Chains, Ropes", "YES", "YES", "YES", "YES"]
                     break
                  case 'mel':
                     this.muse.Name = "Melissa Shield";
                     this.muse.SubDom = "Experimental switch, sub-leaning";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "I-Island";

                     this.muse.Desc = "A quirkless american girl who wants to save people, and has decided to do so through her inventions. Despite her outgoing nature, she doesn't have many friends. Something she intends to fix as well. ";
                     this.muse.DescSh = "She is not blind to how her looks makes others feel. She hopes the acquisition of friends will facilitate experimenting with that.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/melissa/95843a1c147d5c1a5b99f5a717b6d382.jpg", name: "" },
                        { pic: "/slideshow/mha/melissa/028b645171936117aa4fbfd755463c1a.jpeg", name: "" },
                        { pic: "/slideshow/mha/melissa/sample_35f90aad98b0b6ae2dc3d7e960d1bd4f.jpg", name: "Fancy Dress" },
                        { pic: "/slideshow/mha/melissa/7b55bf9ad8a8c27edd780d1d4e403e90.jpeg", name: "Gyaru" },
                        { pic: "/slideshow/mha/melissa/3548d69186e45b12e393c06b4c8eeb4e.png", name: "Cowgirl" },
                        { pic: "/slideshow/mha/melissa/a142dd804c2acb1c6cf9d1ff30d4185a.jpeg", name: "Cheerleader" },
                     ];
                     this.muse.kinksA.partner = ["Human", "YES", "YES", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "", "", "YES", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "", "", "", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "Self, Nipple", "Body Writing, Tattoos", ""]
                     this.muse.kinksA.mindMod = ["Self", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.transform = ["Self", "", "Self", ""]
                     this.muse.kinksB.treatment = ["YES", "Self", "", "Self", ""]
                     this.muse.kinksB.consent = ["Self", "Self", "Self", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "", ""]
                     this.muse.kinksB.bondage = ["Tentacles, Rope", "Self", "", "", ""]
                     break
                  case 'joke':
                     this.muse.Name = "Emi Fukukado (Ms. Joke)";
                     this.muse.SubDom = "Mostly subby, for Midnight";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";

                     this.muse.Desc = "A pro-hero who uses the power of comedy to save people! And beat up dead cows. She flirts and laughs and loves, and never quite shuts up, to the chagrin of many. Has a book of jokes on every topic under the rising sun. ";
                     this.muse.DescSh = "Still wants to meet a hot villainess to happily surrender to, already has a suit, name and theme planned to serve her.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/emi/sample_1cd1eb7dfd1971a8cbe501d4ac3847f6.jpg", name: "" },
                        { pic: "/slideshow/mha/emi/70c9550242736097495219cdb4e141f2.jpeg", name: "" },
                        { pic: "/slideshow/mha/emi/b1cde34e41a43fd3de7b690946e9081c.png", name: "" },
                        { pic: "/slideshow/mha/emi/F4jJu1Va0AA7n_t.jpeg", name: "" },
                        { pic: "/slideshow/mha/emi/MidJoke13.jpg", name: "" },
                     ];
                     this.muse.kinksA.partner = ["Human, Devil", "", "", "Noumu", ""]
                     this.muse.kinksA.relation = ["", "YES", "", "YES", "Midnight", ""]
                     this.muse.kinksA.clothing = ["", "", "Latex, Spandex, Nylon", "", ""]
                     this.muse.kinksA.bodyMod = ["", "YES", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "", "", "", ""]
                     this.muse.kinksB.transform = ["YES", "Self", "", ""]
                     this.muse.kinksB.treatment = ["YES", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["", "Self", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Inside", "YES", "Gas"]
                     this.muse.kinksB.bondage = ["Tentacles, Rope", "YES", "YES", "", "YES"]
                     break
                  case 'kai':
                     this.muse.Name = "Kaina Tsutsumi (Lady Nagant)";
                     this.muse.SubDom = "Dominant";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";

                     this.muse.Desc = "A former hero turned assassin for the Hero Association, Nagant once wanted to truly help people, but was used as a weapon of subterfuge, until she killed her own boss who led her down that path. Free now, as a villain, she sprawls the streets ready to aim and shoot. ";
                     this.muse.DescSh = "Has an interest in female pro-heroes, and teaching them a tough lesson...however they may need it.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/kaina/bc0b40d3de502b9b5008cd3095258df7.jpeg", name: "" },
                        { pic: "/slideshow/mha/kaina/8d83dd60c9f71fe2c5da87115b3e0e21.jpeg", name: "" },
                        { pic: "/slideshow/mha/kaina/57c76e7ae99979da0866957d011f65a0.png", name: "" },
                        { pic: "/slideshow/mha/kaina/f0dbeeaf05f0b5cfd5954245c99ed30d.jpeg", name: "" },
                        { pic: "/slideshow/mha/kaina/b0965f9d905b2395e0549c68d47bc13b.jpeg", name: "Bunny" },
                        { pic: "/slideshow/mha/kaina/d963259f8c800a3ba15fd37160a40b6d.jpeg", name: "Virgin Killer Sweater" },
                     ];
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["", "Partner", "Partner", "", "", ""]
                     this.muse.kinksA.clothing = ["YES", "", "Latex", "", ""]
                     this.muse.kinksA.bodyMod = ["", "YES", "Partner", ""]
                     this.muse.kinksA.mindMod = ["Partner", "Partner", "", "", ""]
                     this.muse.kinksB.transform = ["", "Partner", "", ""]
                     this.muse.kinksB.treatment = ["", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.consent = ["", "Partner", "Partner", "", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", ""]
                     this.muse.kinksB.bondage = ["Rope", "", "Partner", "Partner", "Partner"]
                     break
                  case 'rumi':
                     this.muse.Name = "Rumi Usagiyama (Miruko)";
                     this.muse.SubDom = "Rough Dommy unless beaten in a fight or romantically approached";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "An incredibly aggressive, lone wolf rabbit-like woman who kicks ass, in every concievable way. She has made her way to the top three through sheer force of..well, force, hiding a care for others under the spite of her quirk's perception. ";
                     this.muse.DescSh = "Her viciousness sometimes goes out of hand, and she will get it out through more fighting..or breeding like her quirksake. Any woman nearby is at risk. But if you manage to beat her, you'll have a very willing horny bunny in your grasp";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked), Bunny";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: false }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/rumi/331b5c920d275f94911f0274c8c1685a.png", name: "" },
                              { pic: "/slideshow/mha/rumi/78b64a6e60771d6e04f5ed0407a1c944.jpeg", name: "" },
                              { pic: "/slideshow/mha/rumi/FlG4mrBWYAEDFJ3.png", name: "Gym" },
                              { pic: "/slideshow/mha/rumi/r7olagk82nj81.jpg", name: "UA Uniform" },
                              { pic: "/slideshow/mha/rumi/493e59e27d67918a99bd7a0ad672f2a0.jpeg", name: "Underwear" },
                              { pic: "/slideshow/mha/rumi/89738596_p1.png", name: "Club" },
                           ];
                           break
                        case 'venom':
                           this.muse.Spec = "Human (Quirked), Bunny, Symbiote";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 3, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 3, check: true }
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/mha/rumi/cb3385a46bf51ba01e14ae718a5bce76.jpeg", name: "" },
                              { pic: "/slideshow/mha/rumi/f3e93f8e6e6299d2a5bcc1a7d48433fa.png", name: "" },
                              { pic: "/slideshow/mha/rumi/9f0ba280ddfddd18115704ce6b346fc1.jpeg", name: "" },
                              { pic: "/slideshow/mha/rumi/9e49b43cba5dc9c74088d82dc1d7c3e0.jpeg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human, Mutant", "", "", "Noumu", ""]
                     this.muse.kinksA.relation = ["Self: Worshipped", "YES", "YES", "Partner", "YES", ""]
                     this.muse.kinksA.clothing = ["YES", "Partner", "", "", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "", ""]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["", "", "", "Partner as Self"]
                     this.muse.kinksB.treatment = ["Self", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "", "YES", "", "", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains", "", "YES", "YES", "YES"]
                     break
                  case 'yama':
                     this.muse.Name = "Yu Takeyama (Mt. Lady)";
                     this.muse.SubDom = "Submissive Brat";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A recent pro-hero who seems to be everything wrong with them. Vain, lazy, cocky, lustful, spiteful. Despite this, she has a strong heart that will shine in the worst of times. Even if the rest of times she spends bickering and teasing. ";
                     this.muse.DescSh = "Often expresses her attraction to her fellow pro-heroes by mockery, argument and teasing, desperate to push them to snap and do as they will with her. Most of them know this and don't want to give her the satisfaction.";

                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/yu/6c61ccb499304914f544b9c011204eae.jpeg", name: "" },
                        { pic: "/slideshow/mha/yu/575190c2b7a8d768bf3af7aa32ed6039.jpeg", name: "" },
                        { pic: "/slideshow/mha/yu/d71851232adc6e0fb11001fb6fe2a479.png", name: "" },
                        { pic: "/slideshow/mha/yu/02a4488ecbf54308bcacb8b0789c90ef.jpeg", name: "Cow" },
                     ];
                     this.muse.kinksA.partner = ["Human", "YES", "", "Noumu", "YES"]
                     this.muse.kinksA.relation = ["Partner (Worshipped)", "Self", "Self", "Partner", "", ""]
                     this.muse.kinksA.clothing = ["YES", "YES", "Latex, Spandex, Nylon, Living", "", ""]
                     this.muse.kinksA.bodyMod = ["Self", "Self", "Self", "YES"]
                     this.muse.kinksA.mindMod = ["", "Self", "", "", ""]
                     this.muse.kinksB.transform = ["YES", "", "", ""]
                     this.muse.kinksB.treatment = ["", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["", "Self", "Self", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Self: Rope, Chain, Tentacles", "Self", "Self", "Self", "Self"]
                     break
                  case 'nana':
                     this.muse.Name = "Nana Shimura (???)";
                     this.muse.SubDom = "Dominant unless flustered.";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
                     this.muse.Desc = "An old hero, who always puts a smile on her face. Despite coming from a rather dark age, she does not let it put her down, and is training her successor to the quirk she holds, and hoping for him to become something greater, a symbol. ";
                     this.muse.DescSh = "She's very proud of her body, and does enjoy some of the reactions her muscles get. Especially from some of the ladies. Though she's not strong enough to handle a turnabout.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/nana/319bc1e6f9667d2f8762290a012fb337.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/5151aea1e5129ee96b1e8cc6ac6298ea.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/364cdab97b673dc744b99911c005d3ea.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/be9b776c6e028687eecf0727ab4bcbb3.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/ef0a1c9e3147a809edd1593432a0f4ba.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/b947de3aed249fe8cb7e93584b6f5fdd.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/61c4eb7a82e4a7532fd403ac8f588294.jpg", name: "" },
                        { pic: "/slideshow/mha/nana/GJSaGclawAAnyPm.jpeg", name: "" },
                     ];
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["", "", "", "Partner", "YES", "Mommy"]
                     this.muse.kinksA.clothing = ["", "", "Nylon", "", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "", ""]
                     this.muse.kinksA.mindMod = ["", "Partner", "", "", ""]
                     this.muse.kinksB.transform = ["", "", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "", "", "", ""]
                     this.muse.kinksB.consent = ["", "", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["", "YES", "Outside", "YES", ""]
                     this.muse.kinksB.bondage = ["", "", "YES", "", ""]
                     break
                  case 'fumi':
                     this.muse.Name = "Fuyumi Todoroki";
                     this.muse.SubDom = "Mostly Submissive";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";

                     this.muse.Desc = "A woman who's spent her life trying to keep things together for her family, or her idea of it. She's a preschool teacher, with a weak quirk, and often percieved as weak herself. But it takes great strength to be kind and want better under her circumstances. ";
                     this.muse.DescSh = "Something less than wonderful brews beneath her softness, and if pushed, it will no doubt come out.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/fuyumi/74b93d5f8086a2980432cbdb1a1fc068.png", name: "" },
                        { pic: "/slideshow/mha/fuyumi/d26740d22c8db3e60855a7fb75fb49da.jpeg", name: "" },
                        { pic: "/slideshow/mha/fuyumi/791f6a395977b6d04df854456c16787c.png", name: "" },
                        { pic: "/slideshow/mha/fuyumi/1e174637809e09602585e59dd1793086.jpeg", name: "" },
                        { pic: "/slideshow/mha/fuyumi/1f54aefdf231cde4cf80b11d8bc86540.png", name: "" },
                        { pic: "/slideshow/mha/fuyumi/89683176_p1.png", name: "Club" },
                        { pic: "/slideshow/mha/fuyumi/FyOb4NHWAAAFoFC.jpeg", name: "Cheerleader" },
                     ];
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["", "", "SLAVE", "YES", "YES", "Mommy/Daughter (Partner/Self)"]
                     this.muse.kinksA.clothing = ["", "YES", "Latex, Nylon", "Suit", "YES"]
                     this.muse.kinksA.bodyMod = ["", "", "YES", ""]
                     this.muse.kinksA.mindMod = ["YES", "", "", "", ""]
                     this.muse.kinksB.transform = ["Self", "Self", "", ""]
                     this.muse.kinksB.treatment = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.consent = ["", "YES", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Rope", "YES", "YES", "YES", "YES"]
                     break
                  case 'inko':
                     this.muse.Name = "Inko Midoriya";
                     this.muse.SubDom = "Middle Ground Switch";
                     this.muse.Uni = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";

                     this.muse.Desc = "A mother, no longer a lover, at least in her mind. With her son on the dangerous paths of heroism (yet doing well) and a great deal of regret and time left on her own, she listlessly spends her days watching soap operas, and wondering on what could be. ";
                     this.muse.DescSh = "Few have met the steel behind the tears, when it comes to her heart. Perhaps someone out there may yet be for her.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/mha/inko/4035f001bfba537109f40777ac8633c1.png", name: "" },
                        { pic: "/slideshow/mha/inko/F5H7djmXcAAez5F.jpeg", name: "" },
                        { pic: "/slideshow/mha/inko/eaf211f152bbcbcd8c372b0e92a748e9.jpeg", name: "Virgin Killer Sweater" },
                        { pic: "/slideshow/mha/inko/d8553589ce4dbd302c615fd9f1bc23fd.jpeg", name: "Pre-Time Skip" },
                        { pic: "/slideshow/mha/inko/3d62cc8c709d6312077c9898c3e7e8fb.png", name: "Cheerleader" },
                     ];
                     this.muse.kinksA.partner = ["Human", "", "", "", ""]
                     this.muse.kinksA.relation = ["", "", "", "", "YES", "Mommy/Daughter"]
                     this.muse.kinksA.clothing = ["YES", "YES", "", "Secretary", ""]
                     this.muse.kinksA.bodyMod = ["YES", "", "", ""]
                     this.muse.kinksA.mindMod = ["YES", "YES", "", "", ""]
                     this.muse.kinksB.transform = ["", "Self", "", ""]
                     this.muse.kinksB.treatment = ["Partner", "", "", "", ""]
                     this.muse.kinksB.consent = ["", "", "", "", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "", "YES", "", ""]
                     this.muse.kinksB.bondage = ["Rope", "", "YES", "", "YES"]
                     break
               };
               break
            case 4:
               switch (char) {
                  case 'beni':
                     this.muse.Name = "Kobeni Higashiyama";
                     this.muse.SubDom = "Broken Submissive";
                     this.muse.Uni = "Chainsaw Man";
                     this.muse.Spec = "Human";
                     this.muse.SpecSh = " (Makima's Puppy, Power's Cow)";
                     this.muse.Reg = "Japan";
                     this.muse.Desc = "A hot mess and nervous wreck of a girl who's found some level of safety and ease in following the commands of her fellow coworkers and superiors, particularly Makima and Power. ";
                     this.muse.DescSh = "She enjoy being their pet, what bodily additions they've made her get, and wants everyone to drink her milk, and know she's owned. Really really likes it when Power yells at her.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/anime/kobeni/sample_98d1bc30ef9137ecb4811771420f786a.jpg", name: "" },
                        { pic: "/slideshow/anime/kobeni/RDT_20230217_1430108780495567735061611.jpg", name: "" },
                        { pic: "/slideshow/anime/kobeni/F6Px10tXoAA39fh.jpeg", name: "" },
                        { pic: "/slideshow/anime/kobeni/f0fca9f1f164d9a8045bb4650d48aa61.png", name: "Cow" },
                        { pic: "/slideshow/anime/kobeni/33e1f0e365fd03a28c4ac306a13c9af4200bd46b.jpg", name: "Puppy" },
                     ];
                     this.muse.kinksA.partner = ["Human, Devil", "", "", "YES", ""]
                     this.muse.kinksA.relation = ["", "Self (Dog, Cow)", "Self", "", "YES", ""]
                     this.muse.kinksA.clothing = ["", "Self (Dog, Cow)", "", "Suit", ""]
                     this.muse.kinksA.bodyMod = ["Self", "Self", "Self", "Boobs"]
                     this.muse.kinksA.mindMod = ["Self", "Self", "", "", ""]
                     this.muse.kinksB.transform = ["Self", "Self", "", ""]
                     this.muse.kinksB.treatment = ["Partner", "Self", "Self", "Self", "Self"]
                     this.muse.kinksB.consent = ["Self", "", "", "", "", "Self"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains", "", "YES", "YES", "YES"]
                     break
                  case 'marin':
                     this.muse.SubDom = "YES";
                     this.muse.Uni = "Dress Up Darling";
                     this.muse.Reg = "Japan";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Marin Kitagawa";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A girl who loves what she loves, and isn't ashamed of it. In this case, it's eroges, and cosplay, and her beloved Shizuku-tan (who she has cosplayed, from an eroge). For all her lack of shame in body and tastes, she gets quite flustered at romantic affairs. ";
                           this.muse.DescSh = "She will shamelessly endorse and enjoy the most degenerate, girl-degrading stuff, having internalized a lot of stuff from her porn.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 4, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/marin/0.jpg", name: "" },
                              { pic: "/slideshow/anime/marin/student2.jpeg", name: "Student" },
                              { pic: "/slideshow/anime/marin/bikini1.jpeg", name: "Bikini" },
                              { pic: "/slideshow/anime/marin/bunny2.png", name: "Bunny" },
                              { pic: "/slideshow/anime/marin/shiny2.png", name: "Shiny" },
                              { pic: "/slideshow/anime/marin/shizu2.jpeg", name: "Shizuku-tan (Marin)" },
                              { pic: "/slideshow/anime/marin/rizu2.jpeg", name: "Rizu-kyun (Marin)" },
                              { pic: "/slideshow/anime/marin/veronica.png", name: "Veronica (Marin)" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Model";
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.Desc = "A girl who's found herself a way to get every cosplay ever, look iconic in blonde and red eyes naturally, test some more fantastic kinks, and all it costs is actively being the slut she's always dreamed of. She has found true happiness and will become anyone and anything at her pleasure. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 4, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/marin/symb.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "YES", "YES", "YES", "YES"]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "YES", "YES", "Mother/Daughter (Partner/Self), Sister"]
                     this.muse.kinksA.clothing = ["", "YES", "Latex, Nylon, Living", "School, Military", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "Ear, Nipples", "Tattoos, Body Writing", "Booooobs"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["Partner", "YES", "YES", "YES"]
                     this.muse.kinksB.treatment = ["YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["YES", "YES", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", ""]
                     this.muse.kinksB.bondage = ["Chains, Tentacle, Rope, Tape", "YES", "YES", "", "YES"]
                     break
                  case 'lucy':
                     this.muse.Name = "Lucyna Kushinada";
                     this.muse.SubDom = "Totally in control";
                     this.muse.Uni = "Cyberpunk";
                     this.muse.Spec = "Human (Enhanced)";
                     this.muse.Reg = "Night City, California";
                     this.muse.Desc = "An introverted netrunner who uses her looks for her advantage, as innocent or seductive as is needed to survive. She dreams of one day reaching the Moon and escaping the prison that is the city she lives in. ";
                     this.muse.DescSh = "Sometimes she fantasizes of taking over AND rule from the moon, make the world her bitch, starting with one short, loud girl who she'd love to pick up and break.";
                     this.muse.slideArray = [
                        { pic: "/slideshow/anime/lucynda/025cdddb58148617a9e0038a548c2ba3.png", name: "" },
                        { pic: "/slideshow/anime/lucynda/6b9b4409e557e6c6167ff50eb5b50feb.png", name: "" },
                        { pic: "/slideshow/anime/lucynda/F24WVvJbYAA520f.jpeg", name: "" },
                        { pic: "/slideshow/anime/lucynda/F52RzoZaYAEK6Fb.jpeg", name: "" },
                        { pic: "/slideshow/anime/lucynda/550de0a6117fa76e06ca72bc8d0eef20.jpeg", name: "" },
                     ];
                     this.muse.kinksA.partner = ["Human, Cyber", "", "YES", "", ""]
                     this.muse.kinksA.relation = ["", "", "Partner", "YES", "", ""]
                     this.muse.kinksA.clothing = ["YES", "YES", "Latex, Leather, Nylon", "YES", "YES"]
                     this.muse.kinksA.bodyMod = ["", "YES", "Partner", ""]
                     this.muse.kinksA.mindMod = ["YES", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.transform = ["Partner", "Partner", "YES", ""]
                     this.muse.kinksB.treatment = ["YES", "Partner", "Partner", "Partner", "Partner"]
                     this.muse.kinksB.consent = ["YES", "Partner", "", "YES", "YES", "YES"]
                     this.muse.kinksB.substance = ["", "YES", "YES", "YES", "Smoking, Alcohol"]
                     this.muse.kinksB.bondage = ["Partner: Chains, Tentacles", "Partner", "Partner", "Partner", "Partner"]
                     break
                  case 'yor':
                     this.muse.Uni = "Spy X Family";
                     this.muse.Reg = "Ostonia";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Yor Forger nee Briar";
                           this.muse.NameSh = " (Thorn Princess)";
                           this.muse.SubDom = "Dommy Mommy until genuinely cared and adored for";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "The greatest assassin and mother, Yor took up killing to provide for her brother, and now her family. She's terrible at lying and cooking, but she gives her all for who she cares for. There are no more secrets between her and her 'fake' husband. ";
                           this.muse.DescSh = "He's okay with her sleeping around, so long as she does it in secret. She finds it thrilling, and has fooled around with her coworkers, his coworkers, Eden parents, and even some survivors of her missions.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 4, check: false },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/yor/FB_IMG_1652684055020.jpg", name: "Thorn Princess" },
                              { pic: "/slideshow/anime/yor/FB_IMG_1653121355186.jpg", name: "Office, Assassin, Home" },
                              { pic: "/slideshow/anime/yor/F7eK1pDXcAAwI6A.jpeg", name: "" },
                              { pic: "/slideshow/anime/yor/0994bfb4e34cf0f7b46add23e713667f.jpeg", name: "Bunnygirl" },
                              { pic: "/slideshow/anime/yor/F2C18a6aMAA2yYU.jpeg", name: "Shinobi 1" },
                              { pic: "/slideshow/anime/yor/FW-JxwyVsAAGfEy.jpeg", name: "Shinobi 2" },
                              { pic: "/slideshow/anime/yor/ed6747df1ed2251b0e3838379b7d3907.jpeg", name: "Yorticia 1" },
                              { pic: "/slideshow/anime/yor/3d2cc3b1be93d57e25e8ef81e59d27bd.png", name: "Yorticia 2" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Thorn";
                           this.muse.SubDom = "Domme Monster";
                           this.muse.Spec = "Human/Symbiote";
                           this.muse.Desc = "A monster borne of an assassin and a symbiote, lust for blood and sex perfectly in tune. With an infinite armory at her disposal, Thorn has gotten rid of the Garden, so that they may never threathen her family, yet continues to do her work, partly because of the necessity of ridding her country of evil, and partly out of pleasure of the dance of death. ";
                           this.muse.DescSh = "Those who are collateral tend to die less from her deadliness, only to be drained as she kidnaps and rapes them for days, and dumps her bodies once she's done with them.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 4, check: true },
                           ]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/yor/Inktober_2023_Day_15.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "", "YES", "", ""]
                     this.muse.kinksA.relation = ["", "Partner", "Partner", "YES", "YES", "Mommy/Daughter (Self/Partner)"]
                     this.muse.kinksA.clothing = ["", "", "Latex, Leather", "Suit", "YES"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "", ""]
                     this.muse.kinksA.mindMod = ["YES", "Partner", "", "", ""]
                     this.muse.kinksB.transform = ["YES", "Partner", "", "Partner as Self"]
                     this.muse.kinksB.treatment = ["YES", "", "YES", "YES", ""]
                     this.muse.kinksB.consent = ["", "YES", "", "", "YES", ""]
                     this.muse.kinksB.substance = ["Milk", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Chains, Tentacles, Rope", "Partner", "YES", "Partner", "YES"]
                     break
                  case 'stock':
                     this.muse.Uni = "Panty & Stocking";
                     this.muse.Reg = "Japanifornia, Daten City";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Stocking Anarchy";
                           this.muse.SubDom = "Dominant unless given the right motivation";
                           this.muse.Spec = "Angel";
                           this.muse.SpecSh = " or Demon";
                           this.muse.Desc = "A relatively professional ghost-destroying angel, Stocking adores sweets and mocks sex, in defiance of her loose and sweet-hating sister. She perfectly combines gothic and sweet lolita styles, just as well as she is both sweetness and seriousness. ";
                           this.muse.DescSh = "Despite often making fun of Scanty and Kneesocks for their incestual, BDSM-heavy life, she herself is aroused by those things as well. And she will do anything for sweets.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: true },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 4, check: false },]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/stocking/ac859ef61a1c5ce86a280c94982dabd4.jpeg", name: "" },
                              { pic: "/slideshow/anime/stocking/da36b0a7000a59a5436015286b8137cb.jpg", name: "Bikini" },
                              { pic: "/slideshow/anime/stocking/F0xu8JhaIAoNehs.jpg", name: "" },
                              { pic: "/slideshow/anime/stocking/F6-kxkuW4AAPjBq.jpeg", name: "" },
                              { pic: "/slideshow/anime/stocking/F7nMHnIWQAAYiMB.png", name: "" },
                              { pic: "/slideshow/anime/stocking/f7134750b938e5620f8d2ec4fe69231c.png", name: "Bunnygirl" },
                           ];
                           break
                        case 'venom':
                           this.muse.Name = "Stocking Anarchy";
                           this.muse.SubDom = "Dominant++";
                           this.muse.Spec = "Angel/Symbiote ";
                           this.muse.SpecSh = "or Demon/Symbiote";
                           this.muse.Desc = "A girl who's union with a slimy, shiny, sticky shapeshifting entity has made her greater at her job, more appealing, enjoy chocolate even more...and further enhancing her libido. ";
                           this.muse.DescSh = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: false },
                              { au: 'venom', emblem: '/versions/symbiote.png', area: 4, check: true },]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/stocking/Inktober_2023_Day_16.png", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human, Angel, Ghost, Devil", "", "YES", "YES", ""]
                     this.muse.kinksA.relation = ["YES", "YES", "YES", "", "YES", "Sisters"]
                     this.muse.kinksA.clothing = ["", "YES", "Frills, Leather", "YES", "Lolita"]
                     this.muse.kinksA.bodyMod = ["YES", "YES", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["Self", "Partner", "", "YES"]
                     this.muse.kinksB.treatment = ["", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.consent = ["", "YES", "YES", "YES", "", "YES"]
                     this.muse.kinksB.substance = ["Sweets, Milk", "YES", "YES", "YES", "YES"]
                     this.muse.kinksB.bondage = ["Tentacles, Chains", "YES", "YES", "YES", "YES"]
                     break
                  case 'frie':
                     this.muse.Uni = "Beyond Journey's End";
                     this.muse.Reg = "N/A: Traveling";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Frieren";
                           this.muse.SubDom = "Experimental Switch";
                           this.muse.Spec = "Elf";
                           this.muse.Desc = "An ancient elf who loves magic, hates demons, and is otherwise a mess. Despite being the world's greatest mage, she has rookie mistakes, and can't resist mimics. She's still getting the hang of human lifespans. ";
                           this.muse.DescSh = "While elves have a low sex drive, she IS interested in the topic, and having fun with it. Just as magic, she looks for objects and tomes about it, and she's the greatest layer, even if she has some gaps.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: true },
                              { au: 'mimic', emblem: '/versions/mimic.png', area: 4, check: false },]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/frieren/25ee231e74cdaa1ca90f0b3da59d39f4.jpg", name: "" },
                              { pic: "/slideshow/anime/frieren/sample_c589e7469d22af5e76c8259bec181567.jpg", name: "" },
                              { pic: "/slideshow/anime/frieren/sample_d778d31c3dfe6d8ab0497bcd50d662eb.jpg", name: "" },
                              { pic: "/slideshow/anime/frieren/GJJMI0vXcAApQw6.jpeg", name: "" },
                              { pic: "/slideshow/anime/frieren/GJ72Vh1W0AAQ9LF.jpeg", name: "" },
                              { pic: "/slideshow/anime/frieren/GAirPEfWIAAJCUL.jpeg", name: "" },
                           ];
                           break
                        case 'mimic':
                           this.muse.Name = "Jägerin";
                           this.muse.SubDom = "Carnivore";
                           this.muse.Spec = "???";
                           this.muse.Desc = "Once a great mage, she is now a monster of sorts herself. Her outfit can change to what she wills, even if it'll always be a little tight. She goes around breeding women for new mimic eggs, and alluring travelers into some more advanced mimics. Demons love the new Frieren, and she quite loves herself too. ";
                           this.muse.DescSh = "None know if she's still Frieren but too fallen into pleasure to retrieve, or a mimic that's copied her form and mannerisms. Not even herself.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', area: 4, check: false },
                              { au: 'mimic', emblem: '/versions/mimic.png', area: 4, check: true },]
                           this.muse.slideArray = [
                              { pic: "/slideshow/anime/frieren/GJix1u1WUAAGdmh.jpeg", name: "" },
                              { pic: "/slideshow/anime/frieren/20231215_125840.jpg", name: "" },
                           ];
                           break
                     }
                     this.muse.kinksA.partner = ["Human", "", "", "Mimic, Demons", ""]
                     this.muse.kinksA.relation = ["", "", "", "", "", "Mommy - Self"]
                     this.muse.kinksA.clothing = ["YES", "", "", "", ""]
                     this.muse.kinksA.bodyMod = ["", "", "YES", "YES"]
                     this.muse.kinksA.mindMod = ["YES", "YES", "YES", "", ""]
                     this.muse.kinksB.transform = ["", "", "", "YES"]
                     this.muse.kinksB.treatment = ["YES", "", "", "YES", "YES"]
                     this.muse.kinksB.consent = ["YES", "", "", "YES", "YES", ""]
                     this.muse.kinksB.substance = ["", "", "Outside", "YES", "Potions"]
                     this.muse.kinksB.bondage = ["YES", "YES", "", "YES", "YES"]
                     break
               };
               break
         };
         this.museDialog = true;
         this.currentMuseCode = char;
      },
      cleanData() {
         this.muse.Name = ""
         this.muse.NameSh = ""
         this.muse.SubDom = ""
         this.muse.SubDomSh = ""
         this.muse.Uni = ""
         this.muse.UniSh = ""
         this.muse.Spec = ""
         this.muse.SpecSh = ""
         this.muse.Reg = ""
         this.muse.RegSh = ""
         this.muse.Desc = ""
         this.muse.DescSh = ""
         this.muse.slideArray = []
         this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', area: 1, check: false }]
         this.muse.kinksA.partner = ["Human", "GROUP", "MACHINE", "MONSTER", "ANIMAL"]
         this.muse.kinksA.relation = ["CULTIST", "PET", "SLAVE", "ASSISTANT", "LOVER", "FAMILY"]
         this.muse.kinksA.clothing = ["NONE", "ANIMAL", "MATERIAL", "UNIFORM", "FASHION"]
         this.muse.kinksA.bodyMod = ["BREED", "PIERCE", "BRAND", "GROW"]
         this.muse.kinksA.mindMod = ["CORRUPT", "MINDBREAK", "BRAINWASH", "MINDBLANK", "HIVEMIND"]
         this.muse.kinksB.transform = ["BIMBO", "GOTH", "MECHA", "TWIN"]
         this.muse.kinksB.treatment = ["PRAISE", "DEGRADE", "RYONA", "OBJECT", "HUMILIATE"]
         this.muse.kinksB.consent = ["FREE", "DUB", "NONE", "WATCH", "STEALTH", "EXHIBIT"]
         this.muse.kinksB.substance = ["FOOD", "SWEAT", "CUM", "PISS", "DRUGS"]
         this.muse.kinksB.bondage = ["BIND", "HYPNO", "GRAPPLE", "WORLD", "SENSE"]
         this.slide = 0;
      },
   },
})
</script>
<style>
@media screen and (min-width: 730px) {
   .museImg {
      font-size: 120px;
   }
}

@media screen and (max-width: 730px) {
   .museImg {
      font-size: 85px;
   }

   .button {
      font-size: 12px;
      padding-left: 4px;
      padding-right: 4px;
   }
}

@media screen and (min-width: 643px) {
   .allmuseimg {
      font-size: 72px;
   }

   .groupIcon {
      font-size: 80px;
   }

   .grupMuseImg {
      font-size: 75px;
   }
}

@media screen and (max-width: 643px) {
   .allmuseimg {
      font-size: 60px;
   }

   .groupIcon {
      font-size: 70px;
   }

   .grupMuseImg {
      font-size: 58px;
   }
}

@media screen and (max-width: 412px) {
   .museImg {
      font-size: 72px;
   }

   .allmuseimg {
      font-size: 48px;
   }

   .groupIcon {
      font-size: 56px;
   }

   .grupMuseImg {
      font-size: 48px;
   }
}

@media screen and (max-width: 384px) {
   .button {
      font-size: 10px;
   }
}

.cardHolder {
   margin-bottom: 12px;
   padding: 0 4%;
   gap: 12px;
}

.button {
   background: white;
   color: black;
}

.button[disabled] {
   background: rgb(158, 158, 158);
   color: rgb(92, 92, 92);
   opacity: 1 !important
}

p {
   margin: 0px;
   padding: 0px;
}

.secret {
   color: black;
   background-color: black;
}

.secret:hover {
   color: white;
}

.museslideText {
   color: purple;
   background-color: rgba(0, 0, 0, 0.6);
}

.q-expansion-item {
   text-transform: uppercase;
}

.kinkitem {
   text-transform: none;
   background: #bc36b5;
}

.card {
   background: #CF4CC9D9;
   color: white;
   width: 100%;
   max-width: 720px;
}

.kinklist {
   background: #8a2a85;
   width: 820px;
}

.cardMuse {
   background: #CF4CC9D9;
   color: white;
   max-width: 970px;
   width: fit-content;
}

.cardAllMuse {
   background: #CF4CC9D9;
   color: white;
   max-width: 1240px;
   width: fit-content;
}

#muse {
   background: #CF4CC9;
   color: white;
   max-width: 900px;
   width: fit-content;
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