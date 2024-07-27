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
      this.muse.FreePlay = "";
      this.muse.MetaTupper = "YES"
      this.muse.kinks.partner = "NEUTRAL"
      this.muse.kinks.organ = "NEUTRAL"
      this.muse.kinks.clothing = "NEUTRAL"
      this.muse.kinks.relation = "NEUTRAL"
      this.muse.kinks.consent = "NEUTRAL"
      this.muse.kinks.substance = "NEUTRAL"
      this.muse.kinks.treatment = "NEUTRAL"
      this.muse.kinks.bondage = "NEUTRAL"
      this.muse.kinks.mindMod = "NEUTRAL"
      this.muse.kinks.bodyMod = "NEUTRAL"
      this.muse.kinks.transform = "NEUTRAL"

    },
  },
})
</script>
