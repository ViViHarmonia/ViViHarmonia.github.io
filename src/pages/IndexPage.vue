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
      this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]
      this.muse.slideArray = []
      this.muse.kinks.partner = "CHANGE"
      this.muse.kinks.organ = "CHANGE"
      this.muse.kinks.clothing = "CHANGE"
      this.muse.kinks.relation = "CHANGE"
      this.muse.kinks.consent = "CHANGE"
      this.muse.kinks.substance = "CHANGE"
      this.muse.kinks.treatment = "CHANGE"
      this.muse.kinks.bondage = "CHANGE"
      this.muse.kinks.mindMod = "CHANGE"
      this.muse.kinks.bodyMod = "CHANGE"
      this.muse.kinks.transform = "CHANGE"

      this.muse.auArray = [{ au: 'base', emblem: '/versions/mirror.jpg', check: false }]

    },
  },
})
</script>
