<template>
   <div class="cardHolder flex-center q-pt-sm">
      <q-card class="cardMuse">
         <q-card-section>
            <div class="row flex-center text-subtitle2 text-center q-pa-sm">Characters I have/will roleplay, their
               characteristics, preferences, and such information, canon or personal.</div>

            <div class="row justify-center">
               <q-table row-key="name" :columns="museColumns" flat bordered dark class="my-sticky-header-table"
                  hide-bottom virtual-scroll auto-width :rows-per-page-options="[0]" :rows="finalCharArr">
                  <template v-slot:top>
                     <q-select v-model="museSect" :options="museSectLst" option-label="label" option-value="value"
                        input-debounce="0" dark outlined dense />

                     <q-toggle v-model="nsfwSwitch" color="black" />
                     <span v-show="nsfwSwitch">NSFW</span>
                     <span v-show="!nsfwSwitch">SFW</span>

                  </template>
                  <template v-slot:body-cell-icon="props">
                     <q-td :props="props">
                        <q-avatar size="64px" rounded class="shadow-10">
                           <img :src="props.row.avatar">
                        </q-avatar>
                     </q-td>
                  </template>
                  <template v-slot:body-cell-state="props">
                     <q-td :props="props">
                        <q-select v-model="props.row.state" :options="props.row.states" fill-input input-debounce="0"
                           dark outlined dense v-if="props.row.states.length > 1"></q-select>
                        <div v-else>
                           {{ props.row.state }}
                        </div>
                     </q-td>
                  </template>
                  <template v-slot:body-cell-actions="props">
                     <q-td :props="props">
                        <q-btn-group class="button">
                           <q-btn class="button"
                              @click="museProfileOpen(props.row.sect, props.row.code, props.row.state); museDataCheck = 1"
                              label="Data" />
                           <q-btn class="button"
                              @click="museProfileOpen(props.row.sect, props.row.code, props.row.state); museDataCheck = 2"
                              label="Desc." />
                           <!--<q-btn class="button"
                              @click="museProfileOpen(props.row.sect, props.row.code, props.row.state); museDataCheck = 3"
                              label="Kinks" v-show="nsfwSwitch" />-->
                        </q-btn-group>
                     </q-td>
                  </template>
               </q-table>
            </div>
         </q-card-section>
      </q-card>
   </div>
   <q-dialog v-model="museDialog" @keyup.left="museSwitch(1)" @keyup.right="museSwitch(2)"
      @keyup.down="slideKeyboard(2)" @keyup.up="slideKeyboard(1)" @keyup.x="museDialog = false">
      <q-card id="muse">
         <q-card-section class="q-pa-sm flex-center">
            <div class="row q-pa-sm flex-center">
               <div class="col-xs-12">
                  <div class="row justify-center q-pa-xs">
                     <q-btn-group class="button">
                        <q-btn class="button" @click="museDataCheck = 1" :disabled="museDataCheck == 1" label="Data" />
                        <q-btn class="button" @click="museDataCheck = 2" :disabled="museDataCheck == 2" label="Desc." />
                        <!--<q-btn class="button" @click="museDataCheck = 3" :disabled="museDataCheck == 3" label="Kinks"
                           v-show="nsfwSwitch" />-->
                     </q-btn-group>
                  </div>
                  <div v-if="museDataCheck == 1">
                     <div class="row text-body2 q-pa-xs justify-start">
                        <div class="col-xs-3 col-sm-2"><b>Universe:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Title }}<span class="secret">{{ muse.TitleSh }}</span>
                        </div>
                        <div class="col-xs-3 col-sm-2"><b>Name:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Name }}<span class="secret">{{ muse.NameSh }}</span>
                        </div>
                     </div>
                     <div class="row text-body2 q-pa-xs justify-start">
                        <div class="col-xs-3 col-sm-2"><b>Species:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Spec }}<span class="secret">{{ muse.SpecSh }}</span>
                        </div>
                        <div class="col-xs-3 col-sm-2"><b>Region:</b></div>
                        <div class="col-xs-9 col-sm-4">{{ muse.Reg }}<span class="secret">{{ muse.RegSh }}</span>
                        </div>
                     </div>
                     <div class="row text-body2 q-pa-xs justify-start" v-show="nsfwSwitch">
                        <div class="col-sm-12 col-md-2"><b>Dom/Sub:</b></div>
                        <div class="col-sm-12 col-md-10">{{ muse.SubDom }}<span class="secret">{{ muse.SubDomSh
                              }}</span>
                        </div>
                     </div>

                  </div>
                  <div v-if="museDataCheck == 2">
                     <div class="row q-pa-sm justify-start">
                        <div class="row text-body2 q-pa-xs justify-start">
                           <div class="col-sm-12 col-md-2"><b>Bio:</b></div>
                           <div class="col-sm-12 col-md-10">{{ muse.Desc }}<span class="secret" v-show="nsfwSwitch">{{
                  muse.DescLewd
               }}</span>
                           </div>
                        </div>
                     </div>
                  </div>
                  <div v-if="museDataCheck == 3">
                     <div class="row q-pa-sm justify-start">

                     </div>
                  </div>
                  <div class="row text-body2 q-pa-xs justify-start items-center" v-if="muse.auArray.length != 1">
                     <div class="col-sm-2"><b>Variants:</b></div>
                     <div class="col-sm-auto">
                        <q-btn v-for=" variant  in  muse.auArray " :key="variant.au" circle flat padding="xs"
                           :disabled="variant.check"
                           @click="museProfileOpen(currentAreaCode, currentMuseCode, variant.au)">
                           <q-avatar circle size="45px">
                              <img :src="variant.emblem">
                           </q-avatar>
                        </q-btn>
                     </div>
                     <div class="col-sm-2">
                        <q-toggle v-model="nsfwSwitch" color="black" />
                     </div>
                     <div class="col-sm-2">
                        <span v-show="nsfwSwitch">NSFW</span>
                        <span v-show="!nsfwSwitch">SFW</span>
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
      museSect: { label: "All", value: 0 },
      museDialog: false,
      nsfwSwitch: false,
      museDataCheck: 1,
      currentMuseCode: "",
      currentAreaCode: 0,
      currentAU: "",
      museColumns: [
         { name: "icon", label: "", align: "start", field: "avatar" },
         { name: "character", label: "Character", align: "center", field: "name" },
         { name: "state", label: "State", align: "center", field: "" },
         { name: "free", label: "Free", align: "center", field: "free" },
         { name: "franchise", label: "Universe", align: "center", field: "uni" },
         { name: "actions", label: "", align: "end", field: "" },
      ],
      museSectLst: [
         { label: "All", value: 0 },
         { label: "Pokémon", value: 1 },
         { label: "Hoyo", value: 2 },
         { label: "MHA", value: 3 },
         { label: "Games", value: 4 },
         { label: "Series", value: 5 },
      ],
      allCharArr: [
         { code: "rosa", sect: 1, name: "Rosa", state: "base", free: "YES", states: ["base", "rocket", "plasma", "ua"], uni: "Pokémon", avatar: "/museicon/rosa.jpg", },
         { code: "nem", sect: 1, name: "Nemona", state: "base", free: "NO", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/nemona.png", },
         { code: "marn", sect: 1, name: "Marnie", state: "base", free: "YES", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/marnie.jpg", },
         { code: "ida", sect: 1, name: "Irida", state: "base", free: "NO", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/irida.jpg", },
         { code: "iris", sect: 1, name: "Iris", state: "base", free: "NO", states: ["base", "rocket", "plasma"], uni: "Pokémon", avatar: "/museicon/iris.jpeg", },
         { code: "sere", sect: 1, name: "Serena", state: "base", free: "NO", states: ["base", "rocket", "flare"], uni: "Pokémon", avatar: "/museicon/serena.png", },
         { code: "brina", sect: 1, name: "Sabrina", state: "base", free: "NO", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/sabrina.jpg", },
         { code: "cyn", sect: 1, name: "Cynthia", state: "base", free: "YES", states: ["base", "rocket", "galactic"], uni: "Pokémon", avatar: "/museicon/cyn.jpg", },
         { code: "nesa", sect: 1, name: "Nessa", state: "base", free: "NO", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/nesa.png", },
         { code: "jess", sect: 1, name: "Jessie", state: "base", free: "NO", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/jessie.jpg", },
         { code: "ele", sect: 1, name: "Elesa", state: "base", free: "NO", states: ["base", "rocket", "plasma"], uni: "Pokémon", avatar: "/museicon/ele.gif", },
         { code: "lusa", sect: 1, name: "Lusamine", state: "base", free: "NO", states: ["base", "rocket", "aether"], uni: "Pokémon", avatar: "/museicon/lusa.jpg", },
         { code: "clair", sect: 1, name: "Clair", state: "base", free: "NO", states: ["base", "rocket"], uni: "Pokémon", avatar: "/museicon/clair.jpg", },
         { code: "lumi", sect: 2, name: "Lumine", state: "base", free: "NO", states: ["base", "mirror"], uni: "Genshin Impact", avatar: "/museicon/lumi.jpeg", },
         { code: "lisa", sect: 2, name: "Lisa Minci", state: "base", free: "NO", states: ["base", "mirror"], uni: "Genshin Impact", avatar: "/museicon/lisa.jpg", },
         { code: "saria", sect: 2, name: "Rosaria", state: "base", free: "NO", states: ["base", "mirror"], uni: "Genshin Impact", avatar: "/museicon/rosaria.jpg", },
         { code: "yelan", sect: 2, name: "Yelan", state: "base", free: "NO", states: ["base", "mirror"], uni: "Genshin Impact", avatar: "/museicon/yelan.jpeg", },
         { code: "mira", sect: 2, name: "Mirror Maidens", state: "base", free: "NO", states: ["base"], uni: "Genshin Impact", avatar: "/museicon/mirror.jpeg", },
         { code: "mei", sect: 3, name: "Mei Hatsume", state: "base", free: "YES", states: ["base"], uni: "Hero Academia", avatar: "/museicon/mei.jpeg", },
         { code: "tsu", sect: 3, name: "Tsuyu Asui", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/tsuyu.jpeg", },
         { code: "mina", sect: 3, name: "Mina Ashido", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/mina.jpeg", },
         { code: "momo", sect: 3, name: "Momo Yaoyorozu", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/momo.jpeg", },
         //{ code: "toru", sect: 3, name:"Tooru Hagakure",state: "base", free: "NO", states:[ "base" ], uni: "Hero Academia", avatar: "/museicon/tooru.jpeg", }, DORMANT
         { code: "kendo", sect: 3, name: "Itsuka Kendo", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/kendo.jpeg", },
         { code: "kino", sect: 3, name: "Kinoko Komori", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/kinoko.png", },
         { code: "mel", sect: 3, name: "Melissa Shield", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/melissa.jpeg", },
         { code: "camie", sect: 3, name: "Camie Utsushimi", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/camie.jpeg", },
         { code: "joke", sect: 3, name: "Emi Fukukado", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/msjoke.jpeg", },
         { code: "rumi", sect: 3, name: "Rumi Usagiyama", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/miruko.jpeg", },
         { code: "yama", sect: 3, name: "Yu Takeyama", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/mtlady.jpeg", },
         { code: "nana", sect: 3, name: "Nana Shimura", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/nana.jpeg", },
         { code: "kai", sect: 3, name: "Kaina Tsutsumi", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/nagant.jpeg", },
         { code: "fumi", sect: 3, name: "Fuyumi Todoroki", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/fuyumi.jpeg", },
         { code: "inko", sect: 3, name: "Inko Midoriya", state: "base", free: "NO", states: ["base"], uni: "Hero Academia", avatar: "/museicon/inko.png", },
         { code: "sam", sect: 4, name: "Samus Aran", state: "base", free: "YES", states: ["base", "shy"], uni: "Metroid", avatar: "/museicon/samus.jpg", },
         { code: "bow", sect: 4, name: "Bowsette Koopa", state: "base", free: "YES", states: ["base", "shy"], uni: "Super Mario", avatar: "/museicon/bowsette.jpg", },
         { code: "pich", sect: 4, name: "Peach Toadstool", state: "base", free: "NO", states: ["base", "shy", "bow", "shadow"], uni: "Super Mario", avatar: "/museicon/peach.jpg", },
         { code: "lina", sect: 4, name: "Rosalina", state: "base", free: "NO", states: ["base", "shy", "bow"], uni: "Super Mario", avatar: "/museicon/rosalina.jpg", },
         { code: "lin", sect: 4, name: "Linkle", state: "base", free: "YES", states: ["base"], uni: "Legend of Zelda", avatar: "/museicon/linkle.jpeg", },
         { code: "pura", sect: 4, name: "Purah", state: "base", free: "YES", states: ["base", "aoc", "yiga"], uni: "Legend of Zelda", avatar: "/museicon/purah.jpeg", },
         { code: "edel", sect: 4, name: "Edelgard von Hresvelg", state: "base", free: "NO", states: ["base"], uni: "Fire Emblem", avatar: "/museicon/edelgard.jpg", },
         { code: "luci", sect: 4, name: "Lucifer Morningstar", state: "base", free: "YES", states: ["base"], uni: "Helltaker", avatar: "/museicon/lucifer.jpg", },
         { code: "tae", sect: 4, name: "Tae Takemi", state: "base", free: "YES", states: ["base", "lust"], uni: "Persona 5", avatar: "/museicon/tae.png", },
         { code: "ann", sect: 4, name: "Ann Takamaki", state: "base", free: "NO", states: ["base", "lust"], uni: "Persona 5", avatar: "/museicon/ann.png", },
         { code: "sae", sect: 4, name: "Sae Nijima", state: "base", free: "NO", states: ["base", "lust"], uni: "Persona 5", avatar: "/museicon/sae1.jpeg", },
         //{ code: "roty", sect: 4, name:"",state: "base", free: "NO", states:[ "base" ], uni: "Shantae", avatar: "/museicon/rotty.png", }, DORMANT
         { code: "moni", sect: 4, name: "Monika", state: "base", free: "YES", states: ["base"], uni: "Doki Doki Literature Club", avatar: "/museicon/monika.png", },
         { code: "junko", sect: 4, name: "Junko Enoshima", state: "base", free: "YES", states: ["base"], uni: "Danganronpa", avatar: "/museicon/junko.jpg", },
         { code: "nami", sect: 4, name: "Chiaki Nanami", state: "base", free: "YES", states: ["base"], uni: "Danganronpa", avatar: "/museicon/chiaki.jpg", },
         { code: "shan", sect: 4, name: "Shantae", state: "base", free: "NO", states: ["base"], uni: "Shantae", avatar: "/museicon/shantae.jpeg", },
         { code: "ruler", sect: 4, name: "Artoria Pendragon", state: "base", free: "NO", states: ["base"], uni: "Fate", avatar: "/museicon/ruler.jpeg", },
         { code: "ridem", sect: 4, name: "Medusa", state: "base", free: "NO", states: ["base"], uni: "Fate", avatar: "/museicon/riderM.jpg", },
         { code: "layer", sect: 4, name: "Layer", state: "base", free: "YES", states: ["base"], uni: "Megaman X", avatar: "/museicon/layer.jpeg", },
         { code: "brdgt", sect: 4, name: "Bridget ", state: "base", free: "YES", states: ["base"], uni: "Guilty Gear", avatar: "/museicon/bridge.png", },
         { code: "marin", sect: 5, name: "Marin Kitagawa", state: "base", free: "YES", states: ["base"], uni: "Dress-Up Darling", avatar: "/museicon/marin.jpg", },
         { code: "lucy", sect: 5, name: "Lucynda Kushinada", state: "base", free: "NO", states: ["base"], uni: "Cyberpunk Edgerunners", avatar: "/museicon/lucynda.png", },
         { code: "yor", sect: 5, name: "Yor Forger neé Briar", state: "base", free: "YES", states: ["base"], uni: "Spy X Family", avatar: "/museicon/yor.png", },
         { code: "stock", sect: 5, name: "Stocking", state: "base", free: "YES", states: ["base"], uni: "Panty & Stocking w/Garterbelt", avatar: "/museicon/stock.jpg", },
         { code: "frie", sect: 5, name: "Frieren", state: "base", free: "NO", states: ["base", "mimic"], uni: "Sousou no Frieren", avatar: "/museicon/frie.jpg", },
         { code: "fern", sect: 5, name: "Fern", state: "base", free: "NO", states: ["base"], uni: "Sousou no Frieren", avatar: "/museicon/fern.jpg", },
         { code: "paru", sect: 5, name: "PA-san", state: "base", free: "YES", states: ["base"], uni: "Bocchi the Rock!", avatar: "/museicon/paru.jpg", },
         //{ code: "beni", sect: 5, name:"",state: "base", free: "NO", states:[ "base" ], uni: "", avatar: "/museicon/kobeni.jpeg", }, DORMANT
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
         auArray: [],
         slideArray: [],
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
      },
      museSect(newVal, oldVal) {
         this.dataFill()
      },
   },
   methods: {
      dataFill() {
         if (this.museSect.value == 0) {
            this.finalCharArr = this.allCharArr
         } else {
            this.finalCharArr = []
            for (var i = 0; i < this.allCharArr.length; i++) {
               if (this.allCharArr[i].sect == this.museSect.value) {
                  this.finalCharArr.push(this.allCharArr[i])
               }
            }
         }
      },
      museSwitch(move) {
         var newCode = "";
         var newSect = "";
         var auCheck = false;
         switch (move) {
            case 1:
               for (var i = 0; i < this.finalCharArr.length; i++) {
                  if (this.currentMuseCode == this.finalCharArr[i].code) {
                     if (i - 1 < 0) {
                        newCode = this.finalCharArr[this.finalCharArr.length - 1].code
                        newSect = this.finalCharArr[this.finalCharArr.length - 1].sect
                        for (var j = 0; j < this.finalCharArr[this.finalCharArr.length - 1].states.length; j++) {
                           if (this.finalCharArr[this.finalCharArr.length - 1].states[j] == this.currentAU) {
                              auCheck = true;
                           }
                        }
                     } else {
                        newCode = this.finalCharArr[i - 1].code
                        newSect = this.finalCharArr[i - 1].sect
                        for (var j = 0; j < this.finalCharArr[i - 1].states.length; j++) {
                           if (this.finalCharArr[i - 1].states[j] == this.currentAU) {
                              auCheck = true;
                           }
                        }
                     }
                  }
               }
               break
            case 2:
               for (var i = 0; i < this.finalCharArr.length; i++) {
                  if (this.currentMuseCode == this.finalCharArr[i].code) {
                     if (i + 1 > this.finalCharArr.length - 1) {
                        newCode = this.finalCharArr[0].code
                        newSect = this.finalCharArr[0].sect
                        for (var j = 0; j < this.finalCharArr[0].states.length; j++) {
                           if (this.finalCharArr[0].states[j] == this.currentAU) {
                              auCheck = true;
                           }
                        }
                     } else {
                        newCode = this.finalCharArr[i + 1].code
                        newSect = this.finalCharArr[i + 1].sect
                        for (var j = 0; j < this.finalCharArr[i + 1].states.length; j++) {
                           if (this.finalCharArr[i + 1].states[j] == this.currentAU) {
                              auCheck = true;
                           }
                        }
                     }
                  }
               }
               break
         }
         if (auCheck == false) {
            this.currentAU = "base"
         }
         this.museProfileOpen(newSect, newCode, this.currentAU)
      },
      museProfileOpen(area, char, au) {
         this.cleanData();
         switch (area) {
            case 1:
               switch (char) {
                  case 'rosa':
                     this.muse.Spec = "Human";
                     switch (au) {
                        case 'base':
                           this.muse.Title = "Pokemon Trainer";
                           this.muse.Reg = "Unova";
                           this.muse.Name = "Rosa Whitley";
                           this.muse.SubDom = "Submissive unless love requires dominance.";
                           this.muse.Desc = "A buntailed, peppy, flexible Unova Pokemon trainer, with a Paldean mother and Galarian the other, who loves to love, and always tries to see the bright side of life and people. Recently come into contact with her distant cousins Nemona and Marnie. ";
                           this.muse.DescLewd = "As expected of a former Team Plasma Grunt, she's eager to please, and quick to treat degradation and harm as 'love bites'.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: false },
                              { au: 'ua', emblem: '/versions/uagirls.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Title = "Rocket Grunt 'Lover'";
                           this.muse.Reg = "Unova";
                           this.muse.Name = "Rosa Whitley";
                           this.muse.SubDom = "Submissive unless mission requires dominance.";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "A loyal member of Team Rocket's most arousing division. She remains highly peppy, cheerful, and loving, even if her love is Team Rocket. She intends to share her beloved with every cute and hot girl in the world, by whatever means are asked of her, hence her grunt codename.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: false },
                              { au: 'ua', emblem: '/versions/uagirls.png', check: false },
                           ]

                           break
                        case 'plasma':
                           this.muse.Title = "Plasma Grunt 'Princess'";
                           this.muse.Reg = "Unova";
                           this.muse.Name = "Rosa Whitley";
                           this.muse.SubDom = "Broken Submissive.";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "A permanent long-time member of team Plasma, despite the royalty name she's treated as the lowest of the low, and has lost all notion of ever leaving, genuinely believing the way she's treated is only fair, be it as the team's slut, or the humiliating, arousing punishments for failure. At times she wonders what it would've been to leave, but then she's fucked and used all over and lets go of such silly notions. She is Team Plasma property, nothing else matters.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: true },
                              { au: 'ua', emblem: '/versions/uagirls.png', check: false },
                           ]
                           break
                        case 'ua':
                           this.muse.Title = "UA Support Student";
                           this.muse.Reg = "Japan, Musatafu";
                           this.muse.Name = "Shiroi 'Rosa' Mei";
                           this.muse.SubDom = "Worshipful in either direction";
                           this.muse.Desc = "A quirkless support student with greater focus on metallurgy and the arts, who's been assigned to support student Setsuna Tokage, and does so earnestly with a massive crush on her. But secretly, she's always wanted to try and be somewhat of an actual pro hero. WIth armor and sword. ";
                           this.muse.DescLewd = "She's endlessly fascinated by quirks and outfits, to the point of spending much mental power into how they can be used towards sexy shenanigans. She DOES adore Midnight after all.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: false },
                              { au: 'ua', emblem: '/versions/uagirls.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'nem':
                     this.muse.SubDom = "Whoever wins the battle doms.";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Paldea";
                     this.muse.Name = "Nemona Victoria";
                     switch (au) {
                        case 'base':
                           this.muse.Title = "Paldean Champion";
                           this.muse.Desc = "A very hyperactive girl who enjoys Pokemon battling above all else. It has led her to be a Champion-ranked student, though making her ability to relate to others much harder. Has come out of her shell a little through Juliana and Penny, and now her cousin Rosa. ";
                           this.muse.DescLewd = "She treats sex as roughly and dedicated as Pokémon battling. She has fucked and broken many girls she defeats, and intends to do the same for her new friends, longer, harder, tighter. Make them hers for good.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Title = "Rocket Leader";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "A rapidly risen leader of Team Hypno Rocket, aptly so given her thirst for competition and sex. She makes sure to take care of any girl under her care, treating them as already defeated and thus hers to play with. Had designs of starting her own evil team of the same occupations and goals, but joined Team Hypno Rocket to not start from scratch.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'marn':
                     this.muse.Name = "Marnie Mary";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Galar";
                     switch (au) {
                        case 'base':
                           this.muse.Title = "Gym Leader";
                           this.muse.SubDom = "Submissive unless irritated sufficiently. Like a Morpeko.";
                           this.muse.Desc = "A punk-ish girl who seems tough, hiding a truly shy and sweet disposition, with troubles smiling and otherwise expressing herself concisely. She has a legion of fans that cause ruckus, and two cousins that tease her endlessly, both of which she is eternally grateful to. ";
                           this.muse.DescLewd = "When she snaps, she truly embraces that toughness all see, and will use every filthy fantasy on whoever brought it on her. On the other hand, if she breaks, she'll take anything you do to her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Title = "Undercover Rocket Grunt";
                           this.muse.SubDom = "Completely submissive until ordered otherwise.";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "A former trainer put in a deep trance of hypnosis, left as a drooling mess (from either end). With a snap of her fingers, she may go back to her former self, be put in a state of dominance, or go back to her true happy mindless self. She was more aware than she let on before her hypnosis. She just wanted to have someone else take care of her, and let her emote more, or be more comfortable with her state.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'ida':
                     this.muse.SubDom = "Submissive, worshipful";
                     this.muse.Name = "Irida Kai";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Sinnoh";
                     this.muse.RegSh = " (Hisui)";
                     switch (au) {
                        case 'base':
                           this.muse.Title = "Pokemon Trainer?";
                           this.muse.Desc = "A girl thrown into the leadership of the Pearl Clan too soon, she overcompensates with a tough attitude and disposition, hiding a rather soft self. She's been flung forward in time now, to modern day Sinnoh. While happy to explore the vast world in front of her, she can't help but wonder what to do without having to lead. ";
                           this.muse.DescLewd = "Sometimes she too wishes to step down and be just one more person worshiping, as well as forget the breaking of her life's theology..or find a new one.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Title = "Rocket Grunt 'Priestess'";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "A girl flung forward in time to a confusing future, comforted by her new one and only religion: Team Hypno Rocket!! Hierarchy-wise she really is just grunt level, but her fervor and worship really earned her the special little codename. Part of her sometimes screams at her about the criminal, sometimes 'evil' actions of the team, but the comfort of worship and mindlessness soothe her too much to dwell on it too long.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'iris':
                     this.muse.SubDom = "Dominant unless Dragon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Unova";
                     this.muse.Name = "Iris Magenta";
                     switch (au) {
                        case 'base':
                           this.muse.Title = "Gym Leader, Unovan Champion";
                           this.muse.Desc = "A very wild girl who loves dragons, and Pokémon, but is rather clueless and slow to trust and learn when it comes to anything outside of that. After a great journey, she managed to become the Champion of Unova, a title which often swings between her and her claimed sister Rosa. ";
                           this.muse.DescLewd = "It is her earnest hope to be taken by a dragon as a mate and utterly ruined, only existing as a dragon's slave. Or perhaps commanded by one to execute their dominance on other victims.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Title = "Rocket Grunt 'Princess'";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "Where Rosa goes so does she, so it was only a matter of time she cornered her sister and joined. While she still has a greater interest in dragons and championship, she has no problem helping in the newly found 'family business', even if she doesn't have many opportunities to show she too can be sexy. The codename is entirely sarcastic, as those who face her will instead find a dragon, and yet she's very pampered in-team.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: false },
                           ]
                           break
                        case 'plasma':
                           this.muse.Title = "Plasma Grunt 'Dragon'";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "Kidnapped as part of a recruitment plan, and set up as Rosa's counterpart. Her spirit broke..only towards the favor of Team Plasma. Outside of that, she is brutal and cruel to all who lie in her way, or rather, in Team Plasma's way. And she takes what she wants from her sister grunt, as any proper dragon would do to a princess";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'plasma', emblem: '/versions/Team_Plasma.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'sere':
                     this.muse.Reg = "Kalos";
                     this.muse.Spec = "Human";
                     this.muse.Name = "Serena Yvonne";
                     switch (au) {
                        case 'base':
                           this.muse.Title = "Pokemon Trainer";
                           this.muse.SubDom = "Casual Switch.";
                           this.muse.Desc = "A fashionable young lady, who's very kind and polite, until she actually snaps. Rather lost in her way, she takes the time while trying to find her future by trying on all kinds of clothes...or tasting all sorts of lips. She IS Kalosian, after all. ";
                           this.muse.DescLewd = "It's not rare to find her only partially dressed, or wearing sexual parodies that barely count as clothes. This too is fashion after all!";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'flare', emblem: '/versions/team_flare_by_biochao_dezue6u-pre.png', check: false },
                           ]

                           break
                        case 'rocket':
                           this.muse.Title = "Rocket Grunt 'Model' ";
                           this.muse.SubDom = "Cheerily, teasingly Submissive";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "Infiltrated Team Rocket by wearing their uniform. On being caught, she claimed she loved the uniform so much she wanted to feel like part of its team. After several hours of hands-on tutoring by 'her superiors', workplace training videos, and physical training regimes, she can finally shine the uniform's true nature of a loyal Team Rocket member. Said tutoring involved lengthy groping, said training regimes growingly obscene poses and motions, and said workplace training videos were hypnotic. She has forgotten entirely she was ever here undercover, and she is 100% a Team Rocket member now and forever.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                              { au: 'flare', emblem: '/versions/team_flare_by_biochao_dezue6u-pre.png', check: false },
                           ]
                           break
                        case 'flare':
                           this.muse.Title = "Flare Admin ";
                           this.muse.SubDom = "Switch but always haughty.";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "Hired to model their attires as they were designed, she ultimately fell in love with their ideas of beauty and fame, which her continued (and growingly enthusiastic) modelling of their outfits and goals granted her within. Her career may be less known, but in the end, beauty will win. And she IS beauty. Some of the outfits were treated to lower personal morals, and increase pleasure based on team Flare approval. She knows now, but doesn't mind, as she asked her current outfits to have ten times the potency of her trial ones.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'flare', emblem: '/versions/team_flare_by_biochao_dezue6u-pre.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'brina':
                     this.muse.Reg = "Kanto";
                     this.muse.Spec = "Human (Psychic)";
                     this.muse.SubDom = "In Control.";
                     this.muse.Name = "Sabrina";
                     switch (au) {
                        case 'base':
                        this.muse.Title = "Saffron Gym Leader";
                           this.muse.Desc = "A confident woman who's grown a little conceited in her psychic powers, and embraced the cockiness in it, dressing, speaking, and behaving the part of a powerful villain, even when doing good for others. Despite it, shimmers of the sweet kid she couldn't be sometimes shine through. ";
                           this.muse.DescLewd = "She's obsessed with control, and she'll use whatever she's got, be it her looks or her psychic powers, to make sure they go as she wishes. You have no choice in the matter.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'rocket':
                        this.muse.Title = "Rocket Commander";
                           this.muse.Desc = "NSFW ONLY - ";
                           this.muse.DescLewd = "Finding her wicked disposition and power praised and endorsed by the team, she joined truly of her own voalition, and uses her own psychic powers towards getting more members. Some people say the growing sexualization of the female members' outfits is due to her own fetishes, but none dare ever ask. She knows they intend to, though, and she'll never say.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'cyn':
                     this.muse.Title = "Pokemon";
                     this.muse.Reg = "Unova";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Cynthia Shirona";
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Mostly Dommy Mommy.";
                           this.muse.Desc = "An adventuring archaeologist who's stumbled upon the title of champion. While not the greatest fan of battling, the title serves her well for clearance into important sites, and her team is prepared to deal with the blow of legendaries' actions. ";
                           this.muse.DescLewd = "She's well aware of the reputation and trauma her prowess does to others, and sometimes she revels in it, playing up her mystery and dominance. Other times? She surprises them with her tenderness. She enjoys either";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', check: false },
                           ]

                           break
                        case 'rocket':
                           this.muse.Name = "Rocket Scientist Cynthia";
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Vicious Dommy, Power Bottom.";
                           this.muse.Desc = "Offered quite a bit of endorsement for her help in studying mythos (as well as promises that they wouldn't use it for as dangerous goals as Team Galactic), she joined on contract, though contact with their uniforms and culture and the myriad of Sonia's inventions degraded her until she accepted to join in full. ";
                           this.muse.DescLewd = "She no longer has qualms about whether her knowledge is used for great evil, only how it'll serve team Rocket, her beloved.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', check: false },
                           ]

                           break
                        case 'galaxy':
                           this.muse.Name = "Admin Cynthia";
                           this.muse.SubDom = "Ready to obey";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "Unknowingly and accidentally helped with the archaeological/mythos side of things, realizing how much she had helped the team broke her, choosing to use their tech to be brainwashed. Now she's happily loyal, without those pesky morals that gave her guilt, and all she had to give away was her life and pride. ";
                           this.muse.DescLewd = "The errors that led to her assistance were entirely staged to wrack her with guilt, and the pleasure she gets when obeying from the brainwashing helped ensure she'd never leave.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                              { au: 'galaxy', emblem: '/versions/galactic.jpg', check: true },
                           ]

                           break
                     }
                     break
                  case 'nesa':
                     this.muse.SubDom = "Goes with the flow";
                     this.muse.Title = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Galar";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Nessa Rurina";
                           this.muse.Desc = "A model and gym leader from Galar who much like the sea, is calm until battle comes and she becomes the storm. She worries about holding onto her modelling career alongside the gym, but she continues to shine on. She always has time for Sonia though! ";
                           this.muse.DescLewd = "She absolutely adores Sonia and would do anything for her, go as far as she asks. She's taken to masturbate to her at her own pool, hoping the waters hide her own fluids shed from thinking about her closest gal pal.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]

                           break
                        case 'rocket':
                           this.muse.Name = "Coordinator Nessa";
                           this.muse.Desc = "She entered by Sonia's invitations, and her own secret sensual experiments on her left her suggestible enough to dedicate herself. Team Rocket has helped her greatly in managing her time for gym, modelling, and Rocket missions. And she always has time to assist her Sonia in the lab, grateful she got her here.";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]

                           break
                     }
                     break

                  case 'jess':
                     this.muse.Title = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Kanto";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Jessie Musashi";
                           this.muse.SubDom = "Haughty bottom and top.";
                           this.muse.Desc = "A spirited woman . ";
                           this.muse.DescLewd = ".";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Name = "Rocket Leader Jessie";
                           this.muse.SubDom = "On top, as she should've been always";
                           this.muse.Desc = "One of Team (Hypno) Rocket's leaders, finally at the place she belongs. ";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'lusa': //normal, nihilego, rocket, symbiote
                     this.muse.Title = "Pokemon";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Alola";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Jessie Musashi";
                           this.muse.SubDom = "Haughty bottom and top.";
                           this.muse.Desc = "A spirited woman . ";
                           this.muse.DescLewd = ".";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'aether', emblem: '/versions/aether.png', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'aether':
                           this.muse.Name = "Rocket Leader Jessie";
                           this.muse.SubDom = "On top, as she should've been always";
                           this.muse.Desc = "One of Team (Hypno) Rocket's leaders, finally at the place she belongs. ";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'aether', emblem: '/versions/aether.png', check: true },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: false },
                           ]
                           break
                        case 'rocket':
                           this.muse.Name = "Rocket Leader Jessie";
                           this.muse.SubDom = "On top, as she should've been always";
                           this.muse.Desc = "One of Team (Hypno) Rocket's leaders, finally at the place she belongs. ";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'aether', emblem: '/versions/aether.png', check: false },
                              { au: 'rocket', emblem: '/versions/hypnorocket.png', check: true },
                           ]
                           break
                     }
                     this.muse.kinks.partner = ["Human", "Team Rocket", "YES", "Pokemon", "Ultra Beasts"]
                     this.muse.kinks.relation = ["CULTIST", "PET", "SLAVE", "ASSISTANT", "LOVER", "FAMILY"]
                     this.muse.kinks.clothing = ["NONE", "ANIMAL", "MATERIAL", "UNIFORM", "FASHION"]
                     this.muse.kinks.bodyMod = ["BREED", "PIERCE", "BRAND", "GROW"]
                     this.muse.kinks.mindMod = ["CORRUPT", "MINDBREAK", "BRAINWASH", "MINDBLANK", "HIVEMIND"]
                     this.muse.kinks.transform = ["BIMBO", "GOTH", "MECHA", "TWIN"]
                     this.muse.kinks.treatment = ["PRAISE", "DEGRADE", "RYONA", "OBJECT", "HUMILIATE"]
                     this.muse.kinks.consent = ["FREE", "DUB", "NONE", "WATCH", "STEALTH", "EXHIBIT"]
                     this.muse.kinks.substance = ["FOOD", "SWEAT", "CUM", "PISS", "DRUGS"]
                     this.muse.kinks.bondage = ["BIND", "HYPNO", "GRAPPLE", "WORLD", "SENSE"]
                     break
                  case 'elesa': break
               };
               break
            case 2:
               switch (char) {
                  case 'lisa':
                     this.muse.Title = "Genshin Impact";
                     this.muse.Reg = "Teyvat, Mondstat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Lisa Minci";
                           this.muse.SubDom = "Soft Mommy";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A totally normal librarian who enjoys resting and relaxation, teasing, and a penchant for action and violence when her peace is threatened, almost to the point of sadism. ";
                           this.muse.DescLewd = "Fantasizes of being a mindless slave/drone to greater evils and let herself be used, just for peace of mind.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: false }
                           ]
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescLewd = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: true }
                           ]
                           break
                     }
                     break
                  case 'mira':
                     this.muse.Name = "None";
                     this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                     this.muse.Title = "Genshin Impact";
                     this.muse.Spec = "Mirror Maiden";
                     this.muse.Reg = "Teyvat";
                     this.muse.Desc = "Beautiful minions of the Fatui, with a wicked disposition to others, a loving one to their sisters, and a subservient one to their masters. *They will accept only from their Mistress the diminishing treatment they give to non-Fatui partners*. Most of them look alike, though some a bit different, familiar. Always looking for new recruits. ";
                     this.muse.DescLewd = "Said recruits are always unwilling..at first. The Maidens always get them to understand in the end. And they get to keep their appearances on hold to show or discard if it helps them get more recruits.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     break
                  case 'lumi':
                     this.muse.Title = "Genshin Impact";
                     this.muse.Reg = "Teyvat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Lumine";
                           this.muse.SubDom = "Submissive unless suficiently aroused";
                           this.muse.Spec = "Traveler";
                           this.muse.Desc = "A girl who's come from far, far away, many many years ago, to look for her brother. She found him allied with the evil Fatui, and told her to see the world, and so she has, helping every other person who crosses her way, fighting monsters and foes, and dealing with far too much archon bullshit.";
                           this.muse.DescLewd = "The pressures of being the Traveler, always helping, always going everywhere, tires her out to the point she'd rather just do nothing but masturbate to the unfairly hot women of Teyvat.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: false }
                           ]
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescLewd = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: true }
                           ]
                           break
                     }
                     break
                  case 'saria':
                     this.muse.Title = "Genshin Impact";
                     this.muse.Reg = "Teyvat, Mondstat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Rosaria";
                           this.muse.SubDom = "Degenerate Tease or Mommy";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "An utterly terrible yet loyal nun of the Church of Favonius. While she's grateful and indebted to it due to giving her a chance at a better life, she has no focus or interest on the actual religion of it, and uses her self-percieved wickedness she came with to do the more insidious tasks for the sake of them.	";
                           this.muse.DescLewd = "Such a thing is quite taxing on her, and so besides smoking, she unwinds by doing all sorts of filthy unchurchlike things with every man and woman that catches her by.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: false }
                           ]
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescLewd = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: true }
                           ]
                           break
                     }
                     break
                  case 'yelan':
                     this.muse.Title = "Genshin Impact";
                     this.muse.Reg = "Liyue, Mondstat";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Yelan";
                           this.muse.SubDom = "Whatever gets her what she wants";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A woman of many ways, mysterious as she is easygoing. She's an intelligence agent with many affiliations, a tragic tale, and an endless amount of dedication to whatever task is given, if still needing to take the most pragmatical route to conserve energy. ";
                           this.muse.DescLewd = "Depending on her role, her personage changes. The Lady of the Yanshang Teahouse, is an utter tease, a confident goddess people should kneel for, and a very gallant rewarder of those who's gambles go well.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: false },
                           ]
                           break
                        case 'mirror':
                           this.muse.Name = "???";
                           this.muse.SubDom = "Wicked and Dominant, Subservient Slave only to la Signora";
                           this.muse.Spec = "Mirror Maiden";
                           this.muse.Desc = "A woman who willfully gave herself up to the Sisters of the Mirror Maidenhood. While there's still a part of her to remember her life, name, appearance and experiences, most of the time she spends in mindless bliss as yet another Maiden, visually and mentally. ";
                           this.muse.DescLewd = "Even when she reflects her former appearence and identity, aware of who she was once, she's still utterly loyal, and happy to have done as she did.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'mirror', emblem: '/versions/Mirror_Maiden_Icon.png', check: true },
                           ]
                           break
                     }
                     break
               };
               break
            case 3:
               switch (char) {
                  case 'mei':
                     this.muse.Name = "Mei Hatsume";
                     this.muse.SubDom = "Dom when hyperfocused, Subby when taken out of focus";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "The greatest engineer in quirked history, she's brilliant, bombastic, and can't remember silly things like names, hygiene, or shame. All she needs in her world are her babies, and what girls may take an interest in her and her babies. ";
                     this.muse.DescLewd = "Is more into machines than humans, would roboticize every hot girl she meets if she could.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     break
                  case 'tsu':
                     this.muse.Name = "Tsuyu Asui (Froppy)";
                     this.muse.SubDom = "Whatever strikes the mood";
                     this.muse.Title = "Hero Academia";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A hero in training with big dreams, a long tongue, and zero ability to hold either in. She is adored by many, and her quirks (pun intended) are charming to many, just as she adores her classmates. ";
                     this.muse.DescLewd = "She has enough sense not to bring up how often she wants to wrap and tongue-fuck her female classmates daily...unless they ask.";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked), Frog";
                           this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: true },]
                           break
                     }
                     break
                  case 'mina':
                     this.muse.Name = "Mina Ashido (Pinky)";
                     this.muse.SubDom = "YES";
                     this.muse.Title = "Hero Academia";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A funky, spunky, alien-looking gal with a good heart, and a gooder sense of fun. She will spend her days scheming over her friends love lives, organize games, and save the world dancing away. ";
                     this.muse.DescLewd = "With all her boundless energy come hours upon hours of sex, and she's specifically tailored her hero suit to attract that attention. Midnight is her icon for a reason.";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked), Alien";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'momo':
                     this.muse.Name = "Momo Yaoyorozu (Creati)";
                     this.muse.SubDom = "Shyly submissive until gaining confidence to engage Mommy Momo mode";
                     this.muse.Title = "Hero Academia";
                     this.muse.Nat = "Regal";
                     this.muse.Reg = "Japan, Musatafu";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked)";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     this.muse.Desc = "A girl born of wealth with a genuine heart of gold and a mind that holds great knowledge. Despite her dazzling intellect, astonishing quirk, and stunning beauty, her confidence needs some serious work. But she will always stand by the side of her friends. ";
                     this.muse.DescLewd = "Headmistress Midnight has taken her in as a pseudo-daughter and a successor to her spirit, and she intends to work hard on her confidence to live up to it and become the newest Mistress of heroics.";
                     
                     break
                  case 'toru':
                     this.muse.Name = "Tooru Hagakure (Invisible Girl)";
                     this.muse.SubDom = "Casual Switch";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A girl born invisible, pushing herself to be loud and bright and seen. Thanks to her friends and training, she has become more visible than ever at UA, thus aiming as a hero to look out for others who might be left unseen. ";
                     this.muse.DescLewd = "People watching is her hobby, which has often veered into very perverted situations...not that she minds the show, or interrupts, or even leaves. Also has developed a nudist streak.";

                     break
                  case 'kendo':
                     this.muse.Name = "Itsuka Kendo (Battle Fist)";
                     this.muse.SubDom = "Submissive to any request, but dominant if requested";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A martial artist with a big brain, big heart, and bigger hands, the class representative of class B is as ruthless with her criticism as her combative disposition. She does however have a tendency to let go for others, neglecting her own wants and needs. ";
                     this.muse.DescLewd = "One can only hope her friend slash crush Setsuna does not take advantage of that...or that she lets herself go along the rather sexualized world of female pro-heroism.";

                     break
                  case 'camie':
                     this.muse.Name = "Camie Utsushimi (Illus-o-Camie)";
                     this.muse.SubDom = "Dominant unless finding something kinky and fun worth subbing for.";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     this.muse.Desc = "A Ketsubutsu-taught pro-heroine in training, with a bubbly and absentminded demeanor that's hard to understand at times, but covering for remarkable cleverness of both quirk use and emotional insight. ";
                     this.muse.DescLewd = "Her hero outfit and flirtatiousness bely the fact that she likes to draw in the attention, the only question being, what she will do with that attention. She knows quite well the answer will be 'whatever Camie desires'.";

                     break
                  case 'mel':
                     this.muse.Name = "Melissa Shield";
                     this.muse.SubDom = "Experimental switch, sub-leaning";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "I-Island";
                     this.muse.Desc = "A quirkless american girl who wants to save people, and has decided to do so through her inventions. Despite her outgoing nature, she doesn't have many friends. Something she intends to fix as well. ";
                     this.muse.DescLewd = "She is not blind to how her looks makes others feel. She hopes the acquisition of friends will facilitate experimenting with that.";

                     break
                  case 'joke':
                     this.muse.Name = "Emi Fukukado (Ms. Joke)";
                     this.muse.SubDom = "Mostly subby, for Midnight";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A pro-hero who uses the power of comedy to save people! And beat up dead cows. She flirts and laughs and loves, and never quite shuts up, to the chagrin of many. Has a book of jokes on every topic under the rising sun. ";
                     this.muse.DescLewd = "Still wants to meet a hot villainess to happily surrender to, already has a suit, name and theme planned to serve her.";

                     break
                  case 'kai':
                     this.muse.Name = "Kaina Tsutsumi (Lady Nagant)";
                     this.muse.SubDom = "Dominant";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A former hero turned assassin for the Hero Association, Nagant once wanted to truly help people, but was used as a weapon of subterfuge, until she killed her own boss who led her down that path. Free now, as a villain, she sprawls the streets ready to aim and shoot. ";
                     this.muse.DescLewd = "Has an interest in female pro-heroes, and teaching them a tough lesson...however they may need it.";

                     break
                  case 'rumi':
                     this.muse.Name = "Rumi Usagiyama (Miruko)";
                     this.muse.SubDom = "Rough Dommy unless beaten in a fight or romantically approached";
                     this.muse.Title = "Hero Academia";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "An incredibly aggressive, lone wolf rabbit-like woman who kicks ass, in every concievable way. She has made her way to the top three through sheer force of..well, force, hiding a care for others under the spite of her quirk's perception. ";
                     this.muse.DescLewd = "Her viciousness sometimes goes out of hand, and she will get it out through more fighting..or breeding like her quirksake. Any woman nearby is at risk. But if you manage to beat her, you'll have a very willing horny bunny in your grasp";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human (Quirked), Bunny";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'yama':
                     this.muse.Name = "Yu Takeyama (Mt. Lady)";
                     this.muse.SubDom = "Submissive Brat";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A recent pro-hero who seems to be everything wrong with them. Vain, lazy, cocky, lustful, spiteful. Despite this, she has a strong heart that will shine in the worst of times. Even if the rest of times she spends bickering and teasing. ";
                     this.muse.DescLewd = "Often expresses her attraction to her fellow pro-heroes by mockery, argument and teasing, desperate to push them to snap and do as they will with her. Most of them know this and don't want to give her the satisfaction.";

                     break
                  case 'nana':
                     this.muse.Name = "Nana Shimura (???)";
                     this.muse.SubDom = "Dominant unless flustered.";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     this.muse.Desc = "An old hero, who always puts a smile on her face. Despite coming from a rather dark age, she does not let it put her down, and is training her successor to the quirk she holds, and hoping for him to become something greater, a symbol. ";
                     this.muse.DescLewd = "She's very proud of her body, and does enjoy some of the reactions her muscles get. Especially from some of the ladies. Though she's not strong enough to handle a turnabout.";

                     break
                  case 'fumi':
                     this.muse.Name = "Fuyumi Todoroki";
                     this.muse.SubDom = "Mostly Submissive";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A woman who's spent her life trying to keep things together for her family, or her idea of it. She's a preschool teacher, with a weak quirk, and often percieved as weak herself. But it takes great strength to be kind and want better under her circumstances. ";
                     this.muse.DescLewd = "Something less than wonderful brews beneath her softness, and if pushed, it will no doubt come out.";

                     break
                  case 'inko':
                     this.muse.Name = "Inko Midoriya";
                     this.muse.SubDom = "Middle Ground Switch";
                     this.muse.Title = "Hero Academia";
                     this.muse.Spec = "Human (Quirked)";
                     this.muse.Reg = "Japan, Musatafu";
                     this.muse.Desc = "A mother, no longer a lover, at least in her mind. With her son on the dangerous paths of heroism (yet doing well) and a great deal of regret and time left on her own, she listlessly spends her days watching soap operas, and wondering on what could be. ";
                     this.muse.DescLewd = "Few have met the steel behind the tears, when it comes to her heart. Perhaps someone out there may yet be for her.";

                     break
               };
               break
            case 4:
               switch (char) {
                  case 'sam':
                     this.muse.Title = "Metroid";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Samus Aran";
                           this.muse.SubDom = "Whatever the 'mission' requires";
                           this.muse.Spec = "Human / Chozo / Metroid";
                           this.muse.Reg = "Space";
                           this.muse.Desc = "A capable yet sensibly muted warrior who unwinds through sex, and carries on her mission to the end, but has trouble emoting, connecting, or sensing. ";
                           this.muse.DescLewd = "She'd happily surrender to an evil alien force if it returned her the ability to feel joy and pleasure and love.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                           ]
                           break
                        case 'shy':
                           this.muse.Name = "Blue";
                           this.muse.SubDom = "Submissive unless orders";
                           this.muse.Spec = "Shy Gal";
                           this.muse.Reg = "Mushroom Kingdom";
                           this.muse.Desc = "A shy gal who makes even less noises than the usual, but shows little shyness in offering herself up for pleasure and flirtation. She seems almost thrilled to be in this position of anonimity. ";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'bow':
                     this.muse.Title = "Mario";
                     this.muse.Reg = "Dark World";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Bowsette Koopa";
                           this.muse.SubDom = "Dominant unless trapped into it or flipped by a gorgeous princess";
                           this.muse.Spec = "Koopa/Human";
                           this.muse.Desc = "A newfound boisterous girl with a thirst for cute princesses and world domination. Despite her added human, she's still strong, brash, possessive...and weak to the beauty of princesses. Her dream is all princesses to adore her, and fall for her charms to be hers. ";
                           this.muse.DescLewd = "Though sometimes, she'd like to see what it'd be like if the princesses turned the tables on her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                           ]
                           break
                        case 'shy':
                           this.muse.Name = "Yellow";
                           this.muse.SubDom = "Coy, bratty submissive";
                           this.muse.Spec = "Shy Gal";
                           this.muse.Desc = "The very leader of the shy gals, going undercover to see what they get up to, and doing it many more times to enjoy the supposed anonimity of the mask to take a break from being bossy and the top. ";
                           this.muse.DescLewd = "Actually, every shy gal knows it's her, but it's alright by them. The masks will ensure she does as they do, after all...";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'pich':
                     this.muse.Title = "Mario";
                     this.muse.Reg = "Mushroom Kingdom";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Peach Toadstool";
                           this.muse.SubDom = "Submissive unless her partner wants a taste";
                           this.muse.Spec = "Toad/Human";
                           this.muse.Desc = "A bubbly princess with great enthusiasm and love for the people of her kingdom. She may be a princess, but she doesn't always stay in the sidelines. Loves to bake, and dress-up, and do all sorts of sports. She either happily enjoys activities with people, or stubbornly refuses. ";
                           this.muse.DescLewd = "Often, her stubbornness is just in order to invite further pressuring and convincing, as well as playing the part of a good kidnapped princess corrupted. If well convinced, she could assist in corrupting and kidnapping fellow princesses";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', check: false },
                           ]
                           break
                        case 'bow':
                           this.muse.Name = "Peachy";
                           this.muse.SubDom = "Submissive Slave";
                           this.muse.Spec = "Toad/Human";
                           this.muse.Desc = "The Koopa King/Queen's happy little slave, fucked into utter blissful submission after a succesful moon wedding. While legally and technically a wife, Peach knows well from her treatment and the comings of other princesses that she's nothing but Bowsette's slave...and it couldn't have gotten her happier.  ";
                           this.muse.DescLewd = "Currently acts as though nothing happened, but observant folk can tell she's a little messier when being rescued than when taken, and the flashes of a very familiar emblem as a tattoo on her body.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: true },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', check: false },
                           ]
                           break
                        case 'shy':
                           this.muse.Name = "Pink";
                           this.muse.SubDom = "Endearingly Submissive";
                           this.muse.Spec = "Shy Gal";
                           this.muse.Desc = "A pink spunky shy gal, who's bashful in a very endearing way, as though hoping you'd catch her and do as you wish to her body. She is permitted the sounds of her giggles, melodious and seductive as they are, as well as her soft moans, which are quite frequent. ";
                           this.muse.DescLewd = "She too finds freedom in the anonimity of the mask, and sometimes she forgets she's a princess at all...or her name, or her face. Surely, doing it again won't be a danger?";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: true },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', check: false },
                           ]
                           break
                        case 'shadow':
                           this.muse.Name = "Shadow Queen";
                           this.muse.SubDom = "Dominant even when amused enough to recieve.";
                           this.muse.Spec = "Toad/Human/Shadow";
                           this.muse.Desc = "A dark queen who took over the world many years ago, now possessing Princess Peach to have a second hand at it. The fusion has completed between them, making her agreeable enough to talk, cordial enough to not destroy it all, and physical enough to appreciate pleasures of the flesh. ";
                           this.muse.DescLewd = "For the perfect fusion to happen, Peach agreed to combine with the Shadow Queen in full. Neither are as they were before, and the new one carries all of Peach's darker sides...and her tastes.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: false },
                              { au: 'shadow', emblem: '/versions/PMTTYD_Staff_Credits_45.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'lina':
                     this.muse.Title = "Mario";
                     this.muse.Reg = "Comet Observatory";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Rosalina Estela";
                           this.muse.SubDom = "Soft Dommy Mommy unless convinced otherwise by great force.";
                           this.muse.Spec = "Human/Goddess";
                           this.muse.Desc = "The mother of all stars, Rosalina is a greatly capable mechanic and mother, traveling space for centuries and seeing her babies turn into planets and galaxies. ";
                           this.muse.DescLewd = "But even a mother and goddess has needs, and space gets very cold and lonely. Hence her frequent visits to the Mushroom Kingdom, or how she sometimes adopts people as her kids and also does lewd activities with them.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: false },
                           ]
                           break
                        case 'bow':
                           this.muse.Name = "Rosie";
                           this.muse.SubDom = "Broken Submissive.";
                           this.muse.Spec = "Human/Goddess";
                           this.muse.Desc = "The former mother of all stars, lowered to a pathetic slut after Bowser destroyed her space station and decided to kidnap her on the way. While less of a frequent visitor than Peachy (given Bow's long time love of the Mushroom Princess) she's no less loyal to her monarch. ";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: false },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: true },
                           ]
                           break
                        case 'shy':
                           this.muse.Name = "Cyan";
                           this.muse.SubDom = "Cuddly Submissive.";
                           this.muse.Spec = "Human/Goddess";
                           this.muse.Desc = "A particularly clingy shy gal, who does her best to stick to you while happily offering her holes. Something is rather ethereal about her, leading to being treated as a rare and lucky find. ";
                           this.muse.DescLewd = "She's rather a glutton for semen, and the more she drinks the bigger her boobs grow.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'shy', emblem: '/versions/shy.png', check: true },
                              { au: 'bow', emblem: '/versions/bow.jpg', check: false },
                           ]
                           break
                     }
                     break
                  case 'lin':
                     this.muse.Name = "Linkle Ordona";
                     this.muse.SubDom = "Happy Submissive";
                     this.muse.Title = "Zelda";
                     this.muse.Spec = "Hylian";
                     this.muse.Reg = "Hyrule";
                     this.muse.Desc = "A farmer who believes herself to be the hero of Hyrule, winning over hearts with a sweet smile. She will befriend anyone, as she keeps getting lost and finding herself anywhere. ";
                     this.muse.DescLewd = "Fantasizes about taking care of the animals with her body, as well as being defeated by the monsters, only to take the upper hand after loooong long hours of fun sex with them.";
                     break
                  case 'pura':
                     this.muse.Name = "Purah";
                     this.muse.SubDom = "Dominant unless coerced by greater power.";
                     this.muse.Title = "Zelda";
                     this.muse.Reg = "Hyrule";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Sheikah Hylian";
                           this.muse.Desc = "A pre-Calamity science who aged herself to match the hero and princess (though not without error), she strives to work her way up to the wisdom of the ancient sheikah scientists. Her latest look has drawn much attention. ";
                           this.muse.DescLewd = "Ultimately, her eagerness for science is just a tad higher than her ethics, and the only reason she's stuck by the royal family is due to finding a connection with Zelda. Otherwise, she would do anything and anyone if it'd take her tech to greater heights.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', check: false },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', check: false },
                           ]
                           break
                        case 'aoc':
                           this.muse.Spec = "Sheikah Hylian";
                           this.muse.Desc = "A very eccentric researcher, older sister to Impa, and working for the royal family of Hyrule. She has found a likeminded soul in Zelda, and does her best to get the tech up to speed to her and the champions' needs, even if sometimes she forgets the world around for her. ";
                           this.muse.DescLewd = "It is a great tragedy that all her efforts will not come to help, and she'll have to wait a century to see the world truly safe AND Zelda well and at ease.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', check: true },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', check: false },
                           ]
                           break
                        case 'yiga':
                           this.muse.Spec = "Yiga Hylian";
                           this.muse.Desc = "A woman who defected from the modern Sheikah for refusing technology, and joined up the Yiga to get them back on track for their original ideology. Despite being ruthless and deeply anti-royalty, under her care the Yiga are much less cruel overall, and more affable to non-Hylian Royalty and Sheikah. ";
                           this.muse.DescLewd = "She has no intent to harm or destroy the princess, and would much rather kidnap her, keep her to herself, and perhaps use the ancient sheikah tech to brainwash her into an obedient puppet for Ganon...and herself";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'aoc', emblem: '/versions/HWAoC_Purah_Icon.png', check: false },
                              { au: 'yiga', emblem: '/versions/Yiga_Eye.png', check: true },
                           ]
                           break
                     }
                     break
                  case 'edel'://need Hegemon Husk picture
                     this.muse.Title = "Fire Emblem";
                     this.muse.Reg = "Fódlan";
                     this.muse.Desc = "A woman with the weight of the world in her shoulders, carrying great and dark secrets, and dedicated to her goals to dangerous heights. She maintains formality and composure, and trusts in others abilities, but forgets to relax, and her trust does not means she lets her own guard down emotionally. ";
                     this.muse.DescLewd = "Has a massive crush on her teacher, Byleth, and if she won't fuck Edelgard herself she'll make sure to fuck Byleth instead.";
                     switch (au) {
                        case 'base':
                           this.muse.Spec = "Human";
                           this.muse.SubDom = "Whatever Byleth requires";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'luci':
                     this.muse.Name = "Lucifer Morningstar";
                     this.muse.SubDom = "Absolutely Dominant";
                     this.muse.SubDomSh = " unless genuinely romantically approached, or left powerless";
                     this.muse.Title = "Helltaker";
                     this.muse.Spec = "Demon ";
                     this.muse.SpecSh = "(Fallen Angel)";
                     this.muse.Reg = "Hell";
                     this.muse.Desc = "A smooth-talking woman who's done the best of her situation. Despite her charm, she's a black-hearted queen with only a few soft spots, fine dining, drinking, worship. She flusters if her authority is upended. ";
                     this.muse.DescLewd = "She's very weak outside of actual hell, and secretly likes it when she is abused on her weakness. She will repay when returning to hell, however.";
                     break
                  case 'tae':
                     this.muse.Title = "Persona";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Japan, Yongen-Jaya";
                     this.muse.SubDom = "Dominant unless experimentation requires otherwise";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Tae Takemi";
                           this.muse.Desc = "An excellent, innovative doctor, who got her reputation ruined by standard medical arrogance of others. She has become a black-alley doctor, and while the things she's accused for tend to be fake, she has a sadistic side to her that would put those accusations to shame. ";
                           this.muse.DescLewd = "Sometimes she takes advantage of patients' unconscious or unwell state to have her way with them, or test even more dangerous, lascivious products on them.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'lust', emblem: '/versions/annemblem.jpg', check: false }
                           ]
                           break
                        case 'lust':
                           this.muse.Name = "Medic";
                           this.muse.Desc = "A disgraced doctor hired by the Phantom Whores, after being sufficiently perverted in the metaverse. She works undercover at Shujin to provide spaces and tools for sexual recreation, test fertility and arousal drugs, and overall assist in Ann and company's mission. While not active in the cognitive world, her real life contributions make her a worthy Phantom Whore.";
                           //this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'lust', emblem: '/versions/annemblem.jpg', check: true }
                           ]
                           break
                     }
                     break
                  case 'ann':
                     this.muse.Title = "Persona";
                     this.muse.Reg = "Japan, Yongen-Jaya";
                     switch (au) {
                        case 'base':
                           this.muse.SubDom = "Mood-depending switch";
                           this.muse.Spec = "Human";
                           this.muse.Name = "Ann Takamaki";
                           this.muse.Desc = "A fiery girl who works as a model, and goes to school like an average girl. She loves sweets, her girlfriend Shiho, and hates injustice. Feels strongly about how she's perceived by others, be it her womanhood, her sexuality, her race, or her body. And she's perfectly willing to take control and show them all wrong. ";
                           this.muse.DescLewd = "Though at times, she just wants to give in to everyone's perception of her as a bimbo and a slut, and drag her girlfriend down with her.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'lust', emblem: '/versions/annemblem.jpg', check: false },
                           ]
                           break
                        case 'lust':
                           this.muse.SubDom = "Whatever she feels like";
                           this.muse.Name = "Panther/Kitten";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "After Ann and Shiho fused with the cognitive versions of themselves in Kamoshida's palace, Ann became every bit the slut she was seen as, but her persona kept her fiery dominance and hatred of Kamoshida. After his defeat, this new Ann has decided to kick the world's libido into high gear, seducing shadows in the cognitive world to turn everyone into perverts, alongside her slutty bunny girlfriend Shiho.";
                           this.muse.DescLewd = "";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'lust', emblem: '/versions/annemblem.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'sae':
                     this.muse.Title = "Persona";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Japan, Yongen-Jaya";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Sae Nijima";
                           this.muse.SubDom = "Dominant unless tired";
                           this.muse.Desc = "A fierce prosecutor who's eternally overworked, undervalued, and ready to strike. She cares deeply for her sister Makoto, but having to care for her as a mother has greatly twisted and strained their relationship. ";
                           this.muse.DescLewd = "She sees the law as a game of chance that she must manipulate in her favor, and intends to place everyone beneath her heel, with her sister to serve her instead.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'lust', emblem: '/versions/annemblem.jpg', check: false },
                           ]
                           break
                        case 'lust':
                           this.muse.Name = "Lady Luck";
                           this.muse.SubDom = "Whatever the fortune might bring.";
                           this.muse.SubDomSh = "..though she cheats to always win and dominate.";
                           this.muse.Desc = "The twisted true self of a prosecutor, fed up with the gambles of the law and intending to make it her own. With assistance from the Phantom Whores, she fused with her non-cognitive self, and made it to the top of the legal ladder through trickery and perversion, letting the PW's perverted actions and goals slide, as they provide pleasure for her as well, in real life or in the metaverse. "
                           this.muse.DescLewd = "The shadows of those who stand against perversion, or use it for their own without the enjoyment of the other, are let to suffer and wander her casino forever, their real selves too lost to commit further crimes against lust.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'lust', emblem: '/versions/annemblem.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'moni':
                     this.muse.Name = "Monika";
                     this.muse.NameSh = ".chr";
                     this.muse.SubDom = "She'll take charge if necessary, but if you want otherwise she's up for it.";
                     this.muse.Title = "DDLC";
                     this.muse.Spec = "Human ";
                     this.muse.SpecSh = "Character File";
                     this.muse.Reg = "Close. ";
                     this.muse.RegSh = "In your computer, DDLC.exe";
                     this.muse.Desc = "The smartest, kindest, most beautiful girl in school, who's decided you are her soulmate, and is distraught by you focusing on the other members of her Literature Club. She will happily use her dedication to make sure you only look at her. ";
                     this.muse.DescLewd = "Though, she does find the girls rather attractive herself...she wouldn't mind them around, if they acknowledge her as the head girlfriend. She'll make sure they love her too. She has her ways.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }];
                     break
                  case 'roty':
                     this.muse.Name = "Rottytops";
                     this.muse.SubDom = "YES";
                     this.muse.Title = "Shantae";
                     this.muse.Spec = "Zombie";
                     this.muse.Reg = "Zombie Caravan";
                     this.muse.Desc = "A cheerful zombie who enjoys cosplay and teasing, Rotty is Shantae's bestest undead friend. Despite genuinely caring for Shantae, she's conniving, tricky and naughty in every single way. It's part of her charm, and sorely wishes to 'corrupt' Shantae. ";
                     this.muse.DescLewd = "Preferably by dating her, kissing her, eating her out, and doing all sorts of fun stuff to her body.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }];
                     break
                  case 'shan':
                     this.muse.Title = "Shantae";
                     this.muse.Reg = "Scuttle Town";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Shantae";
                           this.muse.Spec = "Genie/Human";
                           this.muse.SubDom = "Sub when approached, Dom when approaching";
                           this.muse.Desc = "A half-genie hero, worthy of said title by her care for others and dedication to helping...even if it is thwarted by annoyances, both villainous and even allied. She rarely holds any ill will regardless, and has helped her foes if need be a good amount of times. ";
                           this.muse.DescLewd = "She is rather aware that she's surrounded by very hot gals, and has given serious thought to fooling around with all of them. Even Risky Boots.";

                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ];
                           break
                     }
                     break
                  case 'junko':
                     this.muse.Name = "Junko Enoshima";
                     this.muse.SubDom = "Dominant unless submission causes her despair";
                     this.muse.Title = "Danganronpa";
                     this.muse.Spec = "Human";
                     this.muse.Reg = "Japan";
                     this.muse.Desc = "The ultimate fashionista, but ultimately just a girl who turns despair into pleasure for herself, she wants nothing but to share what she feels with everyone in the world. She's twisted, switches between states of self constantly, and her victory and defeat taste equally good to someone as utterly despairful as herself. There's nothing to hide anymore.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     break
                  case 'nami':
                     this.muse.Name = "Chiaki Nanami";
                     this.muse.SubDom = "Weak submissive, Shy dom";
                     this.muse.Title = "Danganronpa";
                     this.muse.Spec = "Human";
                     this.muse.SpecSh = ", then Program";
                     this.muse.Reg = "Japan";
                     this.muse.Desc = "The ultimate gamer, all but for dating sims. She's rather soft-spoken, and gentle, to the point of even second-guessing her own statements and ideas. But ultimately she is well-meaning and easy to get along with by everyone. ";
                     this.muse.DescLewd = "Recently she's really been getting into lewd games...with all the kinks they teach. Still as bad at them as in dating sims however.";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     break
                  case 'layer':
                     this.muse.Name = "Layer";
                     this.muse.SubDom = "Subby until she gains confidence in the relationship";
                     this.muse.Title = "Megaman";
                     this.muse.Spec = "Reploid";
                     this.muse.Reg = "Galápagos Islands";
                     this.muse.Desc = "The picture of a professional and capable Navigator Reploid..until romance comes into play. At which point she'll become a flustered, shy disaster. Good thing her bangs cover her eyes...even if her top doesn't cover the bottom of her chest."
                     this.muse.DescLewd = "Gaining enough confidence in her romantic situation unlocks her confident mommy side...but it's a slow burn to get there. Before however? She'll let her interest do whatever they want to her."
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     break
                  case 'ruler':
                     this.muse.Name = "Ruler";
                     this.muse.NameSh = ": Artoria Pendragon"
                     this.muse.SubDom = "Dominant unless you win";
                     this.muse.Title = "Type Moon";
                     this.muse.Spec = "Heroic Spirit ";
                     this.muse.SpecSh = " (Heavenly)";
                     this.muse.Reg = "???";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     this.muse.Desc = "A woman who enjoys food and battle, turned human heroic spirit, and grown into a Heaven Heroic Spirit. While much more composed due to her growth, flashes of her battle-hungry (and general appetite hungry) self still shine through at times. Currently she is enjoying the world once more, this time as the greatest casino dealer. ";
                     this.muse.DescLewd = "Another kind of hunger has awakened in her more mature form, and she will feed on it kindly if finding a victor, or harshly if finding a cheater.";
                     break
                  case 'ridem':
                     this.muse.Name = "Rider";
                     this.muse.NameSh = ": Medusa"
                     this.muse.SubDom = "Indifferent switch";
                     this.muse.Title = "Type Moon";
                     this.muse.Spec = "Heroic Spirit";
                     this.muse.Reg = "???";
                     this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
                     this.muse.Desc = "A woman who conceals both her emotions and eyes, hiding beauty and horrors behind both. She is completely loyal to her Master, and is not ultimately cruel, though she is hampered by a great deal of self-consciousness. ";
                     this.muse.DescLewd = "She also hides a lot of care, for those who reciprocate loyalty to her, or those who remind of herself. Only with them will she let her emotions out...all of them. Very enthusiastically.";
                     break

               };
               break
            case 5:
               switch (char) {
                  case 'beni':
                     this.muse.Name = "Kobeni Higashiyama";
                     this.muse.SubDom = "Broken Submissive";
                     this.muse.Title = "Chainsaw Man";
                     this.muse.Spec = "Human";
                     this.muse.SpecSh = " (Makima's Puppy, Power's Cow)";
                     this.muse.Reg = "Japan";
                     this.muse.Desc = "A hot mess and nervous wreck of a girl who's found some level of safety and ease in following the commands of her fellow coworkers and superiors, particularly Makima and Power. ";
                     this.muse.DescLewd = "She enjoy being their pet, what bodily additions they've made her get, and wants everyone to drink her milk, and know she's owned. Really really likes it when Power yells at her.";
                  case 'marin':
                     this.muse.SubDom = "YES";
                     this.muse.Title = "Dress Up Darling";
                     this.muse.Reg = "Japan";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Marin Kitagawa";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "A girl who loves what she loves, and isn't ashamed of it. In this case, it's eroges, and cosplay, and her beloved Shizuku-tan (who she has cosplayed, from an eroge). For all her lack of shame in body and tastes, she gets quite flustered at romantic affairs. ";
                           this.muse.DescLewd = "She will shamelessly endorse and enjoy the most degenerate, girl-degrading stuff, having internalized a lot of stuff from her porn.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'lucy':
                     this.muse.Name = "Lucyna Kushinada";
                     this.muse.SubDom = "Totally in control";
                     this.muse.Title = "Cyberpunk";
                     this.muse.Spec = "Human (Enhanced)";
                     this.muse.Reg = "Night City, California";
                     this.muse.Desc = "An introverted netrunner who uses her looks for her advantage, as innocent or seductive as is needed to survive. She dreams of one day reaching the Moon and escaping the prison that is the city she lives in. ";
                     this.muse.DescLewd = "Sometimes she fantasizes of taking over AND rule from the moon, make the world her bitch, starting with one short, loud girl who she'd love to pick up and break.";
                     break
                  case 'yor':
                     this.muse.Title = "Spy X Family";
                     this.muse.Reg = "Ostonia";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Yor Forger nee Briar";
                           this.muse.NameSh = " (Thorn Princess)";
                           this.muse.SubDom = "Dommy Mommy until genuinely cared and adored for";
                           this.muse.Spec = "Human";
                           this.muse.Desc = "The greatest assassin and mother, Yor took up killing to provide for her brother, and now her family. She's terrible at lying and cooking, but she gives her all for who she cares for. There are no more secrets between her and her 'fake' husband. ";
                           this.muse.DescLewd = "He's okay with her sleeping around, so long as she does it in secret. She finds it thrilling, and has fooled around with her coworkers, his coworkers, Eden parents, and even some survivors of her missions.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'stock':
                     this.muse.Title = "Panty & Stocking";
                     this.muse.Reg = "Japanifornia, Daten City";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Stocking Anarchy";
                           this.muse.SubDom = "Dominant unless given the right motivation";
                           this.muse.Spec = "Angel";
                           this.muse.SpecSh = " or Demon";
                           this.muse.Desc = "A relatively professional ghost-destroying angel, Stocking adores sweets and mocks sex, in defiance of her loose and sweet-hating sister. She perfectly combines gothic and sweet lolita styles, just as well as she is both sweetness and seriousness. ";
                           this.muse.DescLewd = "Despite often making fun of Scanty and Kneesocks for their incestual, BDSM-heavy life, she herself is aroused by those things as well. And she will do anything for sweets.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                           ]
                           break
                     }
                     break
                  case 'frie':
                     this.muse.Title = "Beyond Journey's End";
                     this.muse.Reg = "N/A: Traveling";
                     switch (au) {
                        case 'base':
                           this.muse.Name = "Frieren";
                           this.muse.SubDom = "Experimental Switch";
                           this.muse.Spec = "Elf";
                           this.muse.Desc = "An ancient elf who loves magic, hates demons, and is otherwise a mess. Despite being the world's greatest mage, she has rookie mistakes, and can't resist mimics. She's still getting the hang of human lifespans. ";
                           this.muse.DescLewd = "While elves have a low sex drive, she IS interested in the topic, and having fun with it. Just as magic, she looks for objects and tomes about it, and she's the greatest layer, even if she has some gaps.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: true },
                              { au: 'mimic', emblem: '/versions/mimic.png', check: false },]

                           break
                        case 'mimic':
                           this.muse.Name = "Jägerin";
                           this.muse.SubDom = "Carnivore";
                           this.muse.Spec = "???";
                           this.muse.Desc = "Once a great mage, she is now a monster of sorts herself. Her outfit can change to what she wills, even if it'll always be a little tight. She goes around breeding women for new mimic eggs, and alluring travelers into some more advanced mimics. Demons love the new Frieren, and she quite loves herself too. ";
                           this.muse.DescLewd = "None know if she's still Frieren but too fallen into pleasure to retrieve, or a mimic that's copied her form and mannerisms. Not even herself.";
                           this.muse.auArray = [
                              { au: 'base', emblem: '/versions/mirror.jpg', check: false },
                              { au: 'mimic', emblem: '/versions/mimic.png', check: true },]

                           break
                     }
                     break
               }
               break
         };
         this.museDialog = true;
         this.currentMuseCode = char;
         this.currentAreaCode = area;
         this.currentAU = au;
      },
      cleanData() {
         this.muse.Name = ""
         this.muse.NameSh = ""
         this.muse.SubDom = ""
         this.muse.SubDomSh = ""
         this.muse.Title = ""
         this.muse.Spec = ""
         this.muse.SpecSh = ""
         this.muse.Reg = ""
         this.muse.RegSh = ""
         this.muse.Desc = ""
         this.muse.DescLewd = ""
         this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
      },
   },
   mounted() {
      this.dataFill();
   }
})
</script>
<style>
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

/*.q-select {
    text-transform: uppercase;
 }*/
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
   width: 500px;
}

.my-sticky-header-table {
   height: 500px;
   width: 1000px;
}


.q-table__top,
.q-table__bottom,
thead tr:first-child th {
   background-color: #5a0a58
}

thead tr th {
   position: sticky;
   z-index: 1
}

thead tr:first-child th {
   top: 0
}

.q-table--loading thead tr:last-child th {
   top: 48px
}


tbody {
   scroll-margin-top: 48px
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
