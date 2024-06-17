<template>
  <q-page class="flex flex-center">
    <img alt="Quasar logo" src="~assets/quasar-logo-vertical.svg" style="width: 200px; height: 200px">
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'IndexPage',
  //use ^\s*$\n to find blank spaces
  //@keyup.left="museSwitch(1)" @keyup.right="museSwitch(2)" @keyup.down="slideKeyboard(2)" @keyup.up="slideKeyboard(1)" @keyup.x="museDialog = false"
  methods: {
    placeholderKinkFillText() {
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
      this.muse.auArray = []
      this.muse.slideArray = []
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

      this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
      
    },
  },
})
</script>
