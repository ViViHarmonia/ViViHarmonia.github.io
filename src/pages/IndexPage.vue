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
      this.muse.auArray = [
        {
          au: "base",
          emblem: "/versions/mirror.jpg",
          check: false,
          sfw: "Y",
        },
      ];

    },
  },
})
</script>
