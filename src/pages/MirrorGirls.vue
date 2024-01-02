<template>
    <div class="cardHolder flex-center q-pt-sm">
        <q-card class="card">
            <q-card-section>
                <div class="row flex-center text-subtitle2 text-center q-pa-sm">
                    A glimpse into the girls who've found pleasure through
                    the Mirror
                    Mistress...
                </div>
                <div class="row flex-center">
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :dense="$q.screen.lt.xs" :disabled="section == 1"
                                @click="section = 1">Rules</q-btn>
                        </div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :dense="$q.screen.lt.xs" :disabled="section == 2"
                                @click="section = 2">Lore</q-btn></div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :dense="$q.screen.lt.xs" :disabled="section == 3"
                                @click="section = 3">Muses</q-btn></div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :dense="$q.screen.lt.xs" :disabled="section == 4"
                                @click="section = 4">allies</q-btn></div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :dense="$q.screen.lt.xs" :disabled="section == 5"
                                @click="section = 5">Kinks</q-btn></div>
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
                        <div class="row text-body2 q-pa-sm justify-start"> ❤ Intersex/Futa muses by default, you may ask
                            for cis/trans version</div>
                        <div class="row text-body2 q-pa-sm justify-start"> ❤ Drawn to women, monsters, or evil groups</div>
                    </div>
                    <div class="col-sm-12 col-md-6">
                        <div class="row text-body2 q-pa-sm justify-center"> ✖ LIMITS ✖ </div>
                        <div class="row text-body2 q-pa-sm justify-start"> ✖ Scat, Excessive pain, Cutting, Needles</div>
                        <div class="row text-body2 q-pa-sm justify-start"> ✖ Excessive temperature or voltage play</div>
                        <div class="row text-body2 q-pa-sm justify-start"> ✖ Snuff, Human Vore/Unbirth, Drugs</div>
                    </div>
                </div>
                <div class="row flex-center">
                    <div class="col-xs-12">
                        <div class="row text-body2 q-pa-sm text-center justify-center"> ✖ WARNINGS ✖ </div>
                        <div class="row text-body2 q-pa-sm text-center justify-center"> Minors, i waited till I was 19, so
                            should
                            you </div>
                        <div class="row text-body2 q-pa-sm text-center justify-center"> Parody account, not officially
                            affiliated
                            with any
                            company, nor pose a canonical representation of the characters. </div>
                        <div class="row text-body2 q-pa-sm text-center justify-center"> Mun uses the terms futa/intersex
                            interchangeably,
                            and will use whichever one partner is more comfy with. </div>
                        <div class="row text-body2 q-pa-sm text-center justify-center"> All muses strictly over 18 years
                            old. </div>
                        <div class="row text-body2 q-pa-sm text-center justify-center"> FANTASY RP EXPLORATION =/= PERSONAL
                            ETHICAL
                            BELIEF.
                            If you don't enjoy the kink don't engage with it, i have tons others of them! </div>
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
                        <div class="row text-body2 q-pa-sm justify-start"> Long ago, a woman of light and her rainbow of
                            lover generals were locked in a mirror, the shards sent to worlds beyond. The women created
                            a mansion in there, and spent restless days engaging in romantic and sexual pleasure, yet always
                            isolated from new experiences, everywhere yet nowhere. </div>
                        <div class="row text-body2 q-pa-sm justify-start"> Until one shard was picked up by a girl called
                            Rosa. Her personality and secret desires mirrored those of the pink general, whose power let her
                            connect with people's hearts. Slowly, her defenses were weakened through pleasures of the mind
                            and body, until she happily opened a portal to them. She submitted, and became a Mirror Muse.
                            Lost in bliss and puppeteered by the pink general, Rosa connected with many hers through the
                            many worlds she was in, getting in arousing and romantic events, that in turn empowered the
                            mirror, and the woman who ruled it. </div>
                        <div class="row text-body2 q-pa-sm justify-start"> Eventually, the now called Mirror Mistress
                            empowered the shards to attract more girls who'd join her collection, throughout the multiverse,
                            connecting them through her generals, and making them fall for her in the end, to harvest more
                            love and lust, so that she and her girls may live in new pleasures forevermore. </div>
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
                        v-show="char.sect == museSect || museSect == 5" @click="museProfileOpen(char.sect, char.code)">
                        <q-avatar square :class="{ musebutton: museSect != 5, allmusebtn: museSect == 5 }">
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
                <div class="row text-body2 q-pa-sm justify-center text-center"> Groups or entities who commonly corrupt
                    other
                    iterations of the mirror's muses, officially endorsed and supported by the Mirror Mistress.
                </div>
                <div class="row flex-center q-pa-sm">
                    <q-btn circle padding="xs" flat @click="groupShow(group.name)" v-for="(group, g) in allygroups"
                        :name="g" :key="group">
                        <q-avatar circle size="85px">
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
                        <div class="col-xs-auto" v-for="(char, c) in ally.muses">
                            <q-btn square padding="xs" flat @click="museProfileOpen(char.sect, char.code)">
                                <q-avatar rounded size="80px">
                                    <img :src="char.avatar">
                                </q-avatar>
                            </q-btn>
                            <div class="row justify-center" v-if="ally.title != 'VENOM SYMBIOTE'"> {{ char.gpP }}</div>
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
                    <div class="col-xs-9 col-md-9" v-if="kinkGloss.catDescription != ''">
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catDescription != ''"> {{
                            kinkGloss.catDescription }}</div>
                        <q-separator dark v-if="kinkGloss.catDescription != ''" />
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink1 != ''">{{
                            kinkGloss.catKink1 }}</div>
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink2 != ''">{{
                            kinkGloss.catKink2 }}</div>
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink3 != ''">{{
                            kinkGloss.catKink3 }}</div>
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink4 != ''">{{
                            kinkGloss.catKink4 }}</div>
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink5 != ''">{{
                            kinkGloss.catKink5 }}</div>
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink6 != ''">{{
                            kinkGloss.catKink6 }}</div>
                        <div class="row text-body2 q-pa-sm justify-start" v-if="kinkGloss.catKink7 != ''">{{
                            kinkGloss.catKink7 }}</div>
                    </div>
                </div>
            </q-card-section>
        </q-card>
    </div>
    <q-dialog v-model="museDialog" @keyup.x="museDialog = false" @keyup.up="museSwitch(1)" @keyup.down="museSwitch(2)"
        @keyup.right="slideKeyboard(2)" @keyup.left="slideKeyboard(1)">
        <q-card id="muse">
            <q-card-section class="q-pa-sm flex-center">
                <div class="row q-pa-sm flex-center">
                    <div class="col-xs-12 col-md-7">
                        <div class="row justify-center q-pa-xs">
                            <q-btn-group class="button">
                                <q-btn class="button" @click="museDataCheck = 1" :disabled="museDataCheck == 1"
                                    label="Data" />
                                <q-btn class="button" @click="museDataCheck = 2" :disabled="museDataCheck == 2"
                                    label="Kinks" />
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
                                <div class="col-xs-3 col-sm-2"><b>Dom/Sub:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.SD }}<span class="secret">{{ muse.SDSh }}</span>
                                </div>
                                <div class="col-xs-3 col-sm-2"><b>Nature:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.Nat }}<span class="secret">{{ muse.NatSh }}</span>
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
                                <div class="col-sm-12 col-md-2"><b>Seduction:</b></div>
                                <div class="col-sm-12 col-md-10"><span class="secret">{{ muse.SedSh }}</span>
                                </div>
                            </div>
                            <div class="row text-body2 q-pa-xs justify-start">
                                <div class="col-sm-12 col-md-2"><b>Variants:</b></div>
                                <div class="col-sm-12 col-md-10">{{ muse.Var }}<span class="secret">{{ muse.VarSh }}</span>
                                </div>
                            </div>
                        </div>
                        <div v-if="museDataCheck == 2">
                            <div class="row q-pa-sm justify-start">
                                <q-card class="kinklist">
                                    <q-card-section>
                                        <div class="row justify-start">
                                            <div class="col-xs-6">
                                                <q-expansion-item v-for="(content, cat) in kinkA" group="kinks" :label="cat"
                                                    dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-for="(kink) in content" v-show="kink.d != ''">
                                                                <p>{{ kink.l }}<span v-if="kink.d != 'YES'">: {{
                                                                    kink.d }}</span></p>
                                                            </div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                            </div>
                                            <div class="col-xs-6">
                                                <q-expansion-item v-for="(content, cat) in kinkB" group="kinks" :label="cat"
                                                    dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-for="(kink) in content" v-show="kink.d != ''">
                                                                <p>{{ kink.l }}<span v-if="kink.d != 'YES'">: {{
                                                                    kink.d }}</span></p>
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
                                        <q-icon left size="1rem" name="arrow_upward" />
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
                                        <q-icon left size="1rem" name="arrow_downward" />
                                        <div>Next</div>
                                    </q-btn></div>
                            </div>
                        </div>
                    </div>
                    <div class="col-xs-12 col-md-5">
                        <q-carousel control-color="purple" animated v-model="slide" arrows navigation infinite
                            height="500px">
                            <q-carousel-slide v-for="(version, v) in muse.versionsArray" :name="v" :key="v">
                                <div class="row fit flex-center">
                                    <q-img :src="version.pic" style="max-height: 480px" fit="contain">
                                        <div class="absolute-top text-body-1 text-center custom-cap"
                                            v-if="version.name != ''">
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
    name: 'MirrorGirls',
    data: () => ({
        museSect: 0,
        museDialog: false,
        allyDialog: false,
        section: 0,
        kinkCat: 0,
        museDataCheck: 1,
        currentMuseCode: "",
        allCharArr: [
            { code: "rosa", sect: 1, group: "rocket", gpP: "Grunt", tags: ["love"], avatar: "/museicon/nintendo/rosa.jpg", },
            { code: "nem", sect: 1, group: "rocket", gpP: "Leader", tags: [], avatar: "/museicon/nintendo/nemona.png", },
            { code: "marn", sect: 1, group: "rocket", gpP: "Undercover", tags: [], avatar: "/museicon/nintendo/marnie.jpg", },
            { code: "ida", sect: 1, group: "rocket", gpP: "[WIP]", tags: [], avatar: "/museicon/nintendo/irida.jpg", },
            { code: "iris", sect: 1, group: "rocket", gpP: "[WIP]", tags: [], avatar: "/museicon/nintendo/iris.jpeg", },
            { code: "sam", sect: 1, group: "shy", gpP: "[WIP]", tags: ["venom"], avatar: "/museicon/nintendo/samus.jpg", },
            { code: "bow", sect: 1, group: "shy", gpP: "[WIP]", tags: ["venom"], avatar: "/museicon/nintendo/bowsette.jpg", },
            { code: "pich", sect: 1, group: "shy", gpP: "[WIP]", tags: ["love", "bimbo/gyaru"], avatar: "/museicon/nintendo/peach.jpg", },
            { code: "lina", sect: 1, group: "shy", gpP: "[WIP]", tags: ["venom"], avatar: "/museicon/nintendo/rosalina.jpg", },
            { code: "lin", sect: 1, group: "yiga", gpP: "Undercover", tags: [], avatar: "/museicon/nintendo/linkle.jpeg", },
            { code: "pura", sect: 1, group: "yiga", gpP: "Scientist", tags: ["venom"], avatar: "/museicon/nintendo/purah.jpeg", },
            { code: "edel", sect: 1, group: "", gpP: "", tags: ["venom"], avatar: "/museicon/nintendo/edelgard.jpg", },
            { code: "lisa", sect: 2, group: "mirror", gpP: "Blessed", tags: [], avatar: "/museicon/genshin/lisa.jpg", },
            { code: "mira", sect: 2, group: "mirror", gpP: "Example", tags: [], avatar: "/museicon/genshin/mirror.jpeg", },
            //{ code: "lumi", sect: 2, group: "mirror", gpP:"" , tags: [], avatar: "/museicon/genshin/lumi.jpeg", },
            //{ code: "saria", sect: 2, group: "mirror", gpP:"" , tags: [], avatar: "/museicon/genshin/.jpeg", },
            //{ code: "yelan", sect: 2, group: "mirror", gpP:"" , tags: [], avatar: "/museicon/genshin/yelan.jpeg", },
            { code: "luci", sect: 2, group: "", gpP: "", tags: [], avatar: "/museicon/games/lucifer.jpg", },
            { code: "tae", sect: 2, group: "phantom", gpP: "R&D", tags: [], avatar: "/museicon/games/tae.png", },
            { code: "ann", sect: 2, group: "phantom", gpP: "Founder", tags: ["bimbo/gyaru", "venom"], avatar: "/museicon/games/ann.png", },
            { code: "sae", sect: 2, group: "phantom", gpP: "Chief", tags: [], avatar: "/museicon/games/sae1.jpeg", },
            { code: "moni", sect: 2, group: "", gpP: "", tags: ["love"], avatar: "/museicon/games/monika.png", },
            { code: "roty", sect: 2, group: "", gpP: "", tags: [], avatar: "/museicon/games/rotty.png", },
            { code: "shan", sect: 2, group: "", gpP: "", tags: ["venom"], avatar: "/museicon/games/shantae.jpeg", },
            { code: "junko", sect: 2, group: "", gpP: "", tags: [], avatar: "/museicon/games/junko.jpg", },
            { code: "nami", sect: 2, group: "", gpP: "", tags: ["love"], avatar: "/museicon/games/chiaki.jpg", },
            { code: "layer", sect: 2, group: "", gpP: "", tags: ["love"], avatar: "/museicon/games/layer.jpeg", },
            { code: "ruler", sect: 2, group: "", gpP: "", tags: [], avatar: "/museicon/fate/ruler.jpeg", },
            { code: "ridem", sect: 2, group: "", gpP: "", tags: [], avatar: "/museicon/fate/riderM.jpg", },
            { code: "mei", sect: 3, group: "ua", gpP: "Student", tags: [], avatar: "/museicon/mha/mei.jpeg", },
            { code: "tsu", sect: 3, group: "ua", gpP: "Student", tags: ["venom"], avatar: "/museicon/mha/tsuyu.jpeg", },
            { code: "mina", sect: 3, group: "ua", gpP: "Student", tags: ["love", "bimbo/gyaru"], avatar: "/museicon/mha/mina.jpeg", },
            { code: "momo", sect: 3, group: "ua", gpP: "Student", tags: [], avatar: "/museicon/mha/momo.jpeg", },
            { code: "toru", sect: 3, group: "ua", gpP: "Student", tags: ["love"], avatar: "/museicon/mha/tooru.jpeg", },
            { code: "kendo", sect: 3, group: "ua", gpP: "Student", tags: [], avatar: "/museicon/mha/kendo.jpeg", },
            { code: "camie", sect: 3, group: "ua", gpP: "Student", tags: ["bimbo/gyaru"], avatar: "/museicon/mha/camie.jpeg", },
            { code: "mel", sect: 3, group: "ua", gpP: "Student", tags: [], avatar: "/museicon/mha/melissa.jpeg", },
            { code: "joke", sect: 3, group: "ua", gpP: "Staff", tags: [], avatar: "/museicon/mha/msjoke.jpeg", },
            { code: "kai", sect: 3, group: "ua", gpP: "Guest", tags: [], avatar: "/museicon/mha/nagant.jpeg", },
            { code: "rumi", sect: 3, group: "ua", gpP: "Staff", tags: ["venom"], avatar: "/museicon/mha/miruko.jpeg", },
            { code: "yama", sect: 3, group: "ua", gpP: "Staff", tags: [], avatar: "/museicon/mha/mtlady.jpeg", },
            { code: "fumi", sect: 3, group: "ua", gpP: "Staff", tags: [], avatar: "/museicon/mha/fuyumi.jpeg", },
            { code: "inko", sect: 3, group: "ua", gpP: "Staff", tags: [], avatar: "/museicon/mha/inko.png", },
            { code: "beni", sect: 4, group: "", gpP: "", tags: [], avatar: "/museicon/anime/kobeni.jpeg", },
            { code: "marin", sect: 4, group: "", gpP: "", tags: ["bimbo/gyaru", "venom"], avatar: "/museicon/anime/marin.jpg", },
            { code: "lucy", sect: 4, group: "", gpP: "", tags: [], avatar: "/museicon/anime/lucynda.png", },
            { code: "yor", sect: 4, group: "", gpP: "", tags: ["venom"], avatar: "/museicon/anime/yor.png", },
            { code: "stock", sect: 4, group: "", gpP: "", tags: ["venom"], avatar: "/museicon/anime/stock.jpg", },
        ],
        searChrArr: [],
        allygroups: [
            { name: 'rocket', emblem: '/groups/hypnorocket.png' },
            { name: 'shy', emblem: '/groups/shy.png' },
            { name: 'yiga', emblem: '/groups/Yiga_Eye.png' },
            { name: 'mirror', emblem: '/groups/Mirror_Maiden_Icon.png' },
            //{ name: 'phantom', emblem: '/groups/' },
            { name: 'ua', emblem: '/groups/uagirls.png' },
            { name: 'venom', emblem: '/groups/symbiote.png' },
        ],
        ally: {
            title: "",
            description: "",
            muses: [],
        },
        muse: {
            Name: "",
            NameSh: "",
            SD: "",
            SDSh: "",
            Uni: "",
            UniSh: "",
            Spec: "",
            SpecSh: "",
            Nat: "",
            NatSh: "",
            Reg: "",
            RegSh: "",
            Desc: "",
            DescSh: "",
            Var: "",
            VarSh: "",
            SedSh: "",
            versionsArray: [],
        },
        kinkA: {
            partner: {
                //Note: replace label with whatever character needs and put data as YES
                person: { l: "Person", d: "" },
                group: { l: "Group", d: "" },
                machine: { l: "Machine", d: "" },
                monster: { l: "Monster", d: "" },
                animal: { l: "Animal", d: "" },
            },
            relation: {
                cultist: { l: "Cultist", d: "" },
                pet: { l: "Pet", d: "" },
                slave: { l: "Slave", d: "" },
                assist: { l: "Assistant", d: "" },
                lover: { l: "Girlfriend", d: "" },
                family: { l: "Family", d: "" },
            },
            clothing: {
                none: { l: "None", d: "" },
                animal: { l: "Animal", d: "" },
                material: { l: "Material", d: "" },
                uniform: { l: "Uniform", d: "" },
                fashion: { l: "Fashion", d: "" },
            },
            bodyMod: {
                breed: { l: "Breeding", d: "" },
                pierce: { l: "Piercing", d: "" },
                brand: { l: "Branding", d: "" },
                grow: { l: "Growing", d: "" },
            },
            mindMod: {
                corrupt: { l: "Corruption", d: "" },
                mindBreak: { l: "Mind Break", d: "" },
                brainWash: { l: "Brainwashing", d: "" },
                brainBlank: { l: "Blank", d: "" },
                brainHive: { l: "HiveMind", d: "" },
            },
        },
        kinkB: {
            transform: {
                bimbo: { l: "Bimbofication", d: "" },
                goth: { l: "Gothification", d: "" },
                mecha: { l: "Mechanization", d: "" },
                twin: { l: "Twinning", d: "" },
            },
            treat: {
                praise: { l: "Praise", d: "" },
                degrade: { l: "Degradation", d: "" },
                hurt: { l: "Ryona", d: "" },
                object: { l: "Objectification", d: "" },
                humiliate: { l: "Humiliation", d: "" },
            },
            consent: {
                free: { l: "Free Consent", d: "" },
                dub: { l: "Dub-Con", d: "" },
                none: { l: "Non-Con", d: "" },
                watch: { l: "Voyeur", d: "" },
                stealth: { l: "Stealthing", d: "" },
                exhibit: { l: "Exhibitionism", d: "" },
            },
            substance: {
                food: { l: "Food", d: "" },
                sweat: { l: "Sweat", d: "" },
                cum: { l: "Semen", d: "" },
                piss: { l: "Urine", d: "" },
                drug: { l: "Drugs", d: "" },
            },
            bondage: {
                tie: { l: "Bindings", d: "" },
                hypno: { l: "Hypnosis", d: "" },
                hold: { l: "Grappling", d: "" },
                world: { l: "Environment", d: "" },
                sense: { l: "Sensory Deprivation", d: "" },
            },
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
        kinkGloss: {
            catDescription: "",
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
                    this.kinkGloss.catDescription = "Preferred forms of relationship between Muse and her sexual partner/s."
                    this.kinkGloss.catKink1 = "Cultist: Being part of a cult towards them, share in the delight of worship with them, or be worshipped."
                    this.kinkGloss.catKink2 = "Pet: Being their pet (particular animals mentioned), or having them as a pet."
                    this.kinkGloss.catKink3 = "Slave: Being subservient under threat and harm to their will entirely, even imprisoned by them, or having them subservient to/imprisoned by her."
                    this.kinkGloss.catKink4 = "Assistant: Being their assistant, secretary, henchwoman, etc, or having them as one."
                    this.kinkGloss.catKink5 = "Lover: Being their genuine romantic partner and for them to be hers."
                    this.kinkGloss.catKink6 = "Family: Being their Mommy, Sis or Daughter, with them being the respective Daughter, Sis or Mommy."
                    break
                case 2:
                    this.kinkGloss.catDescription = "Preferred partner species by the Muse."
                    this.kinkGloss.catKink1 = "Person: The local sapient species that Muse enjoys playing with."
                    this.kinkGloss.catKink2 = "Group: A gang, or a cult, or any more than two people working together towards pleasure."
                    this.kinkGloss.catKink3 = "Machine: Mechanical non-sapient devic/s to toy with, or be toyed by someone else with."
                    this.kinkGloss.catKink4 = "Monster: A being with mostly non-humanoid anatomy and/or thought, usually dangerous or antagonistic."
                    this.kinkGloss.catKink5 = "Animal: A common non-sapient entity, that can't speak, but can be a pet, and can mate.'"
                    break
                case 3:
                    this.kinkGloss.catDescription = "Preferred forms of attire to arouse Muse and others."
                    this.kinkGloss.catKink1 = "None: Going au naturale, or see others forgo their clothing."
                    this.kinkGloss.catKink2 = "Animal: Animal-themed outfits, such as cowkinis, playboy bunnies, etc."
                    this.kinkGloss.catKink3 = "Material: Particular materials that entice and arouse Muse, being worn by her or others, such as latex, fur, mesh, and even living"
                    this.kinkGloss.catKink4 = "Uniform: Wearing the same outfit (or similar enough) to others in a group experience, such as a school or military uniform"
                    this.kinkGloss.catKink5 = "Fashion: A tendency to shop, accessorize, and generally mess around with clothing styles and dresses."
                    break
                case 4:
                    this.kinkGloss.catDescription = "Preferred forms Muse enjoys having hers or others' bodies changed, for a time or forever"
                    this.kinkGloss.catKink1 = "Breeding: To fill with cum with the goal of getting knocked up."
                    this.kinkGloss.catKink2 = "Piercing: Appeal for embedded jewelry or needle point tattooing."
                    this.kinkGloss.catKink3 = "Branding: Artistic marks or writing to denote things about the person, be it drawing, body writing, or magical emblems"
                    this.kinkGloss.catKink4 = "Growth: The expansion, through flesh or silicone, of body and its parts, like ass and breasts."
                    break
                case 5:
                    this.kinkGloss.catDescription = "preferred forms Muse enjoys having hers or others' minds changed, for a time or forever"
                    this.kinkGloss.catKink1 = "Corruption: Falling for vices, temptations, fear or harm, away from their usual behaviour, and enjoying their new way of life."
                    this.kinkGloss.catKink2 = "Mind Break: Tear away all thought and/or personality through force and overwhelming abuse turned to pleasure"
                    this.kinkGloss.catKink3 = "Brainwash: Peacefully wash away all thought, memory and/or self and replacing it with new ones, often with the person unaware of the change"
                    this.kinkGloss.catKink4 = "Blank State: Leaving someone empty of personality and self, very suggestible. Can be more technologically oriented, with commands and programming."
                    this.kinkGloss.catKink5 = "Hive Mind: Connecting their mind to others, or assimilate it into a whole."
                    break
                case 6:
                    this.kinkGloss.catDescription = "Preferred forms Muse enjoys having hers or others' personhood altered, body and mind and soul, either for a time or forever"
                    this.kinkGloss.catKink1 = "Bimbofication/Gyarufication: Includes blonde hair, preference for pinks, skimpy clothing, massive tits and ass, sometimes a tan, and a general excess of libido and lack of intelligence (or a need for it)"
                    this.kinkGloss.catKink2 = "Gothification/Punkification: Black or alternative hair colors, wearing leather, latex and/or mesh, in same as hair color/s. Expect sass and a pissed or aloof attitude. Lots of piercing and tattoos common too."
                    this.kinkGloss.catKink3 = "Mechanization/Droneification: Covered in technology, or fused with it, or turned into a machine being, often Blank State'd or in a Hivemind."
                    this.kinkGloss.catKink4 = "Twinning: To look and act exactly as someone else, or as their twin that has always existed."
                    this.kinkGloss.catKink5 = "*Note: You can mix and match these too. Goth Bimbos, Bimbo Drones, Goth Twins, etc."
                    break
                case 7:
                    this.kinkGloss.catDescription = "Ways Muse prefers to be treated, or treat their partner/s."
                    this.kinkGloss.catKink1 = "Praise: Being lavished and loved and adored."
                    this.kinkGloss.catKink2 = "Degradation: Being treated as a lesser, pathetic being, who's lucky to get to hear even the words of disdain"
                    this.kinkGloss.catKink3 = "Ryona: Getting physically and psychologically abused, more emphasis on physical on this glossary (as psychological is covered by Degradation)"
                    this.kinkGloss.catKink4 = "Objectification: Treatment as an item or prop, no more sapient than a lamp or seat."
                    this.kinkGloss.catKink5 = "Humiliation: Openly devaluing and mocking someone through the darker forms of treatment, bondage, etc."
                    break
                case 8:
                    this.kinkGloss.catDescription = "The state of consent of the Muse that'll arouse them, of their partner/s, or of uninvolved people."
                    this.kinkGloss.catKink1 = "Free Consent: Available to fuck at every single moment, waking or unconscious, busy or free, doesn't matter."
                    this.kinkGloss.catKink2 = "Dub-Con: Using any sort of body and/or mind modification or substance that makes the judgement of consent questionable"
                    this.kinkGloss.catKink3 = "Non-Con: Fuck or be fucked against their wishes expressed verbally and openly."
                    this.kinkGloss.catKink4 = "Voyeur: Watching sexual activity happen, sometimes without their awareness or consent."
                    this.kinkGloss.catKink5 = "Stealthing: A middle point of private and public, such as gloryholes, or doing it somewhere with little traffic, or behind an obstacle unseen."
                    this.kinkGloss.catKink6 = "Exhibitionism: Let them all see what depravities are to be enjoyed."
                    break
                case 9:
                    this.kinkGloss.catDescription = "Fluids and other substances that the Muse or partner/s enjoy, share, and more"
                    this.kinkGloss.catKink1 = "Food: Anything usually bought at a grocery store, or set at a table. Important inclusion of milk."
                    this.kinkGloss.catKink2 = "Sweat: Salty results of vigorous exercise and heat, on the body of a gorgeous gal."
                    this.kinkGloss.catKink3 = "Semen: Somewhat used for babymaking, but also good as a beauty product for to the skin, as well as a very filling meal."
                    this.kinkGloss.catKink4 = "Urine: A warm golden shower of physical relief."
                    this.kinkGloss.catKink5 = "Drug: Otherwise substances with neurochemical effects, usually addictive, and dangerous. Includes smoking, drinking, and biological drugs in trial without medical check."
                    break
                case 10:
                    this.kinkGloss.catDescription = "Ways in which Muse likes herself or others to be restrained and forced into positions for play"
                    this.kinkGloss.catKink1 = "Bindings: Objects wrapped around the person and tying them up nicely. Includes tentacles, chains, ropes, tape, etc."
                    this.kinkGloss.catKink2 = "Hypnosis: Control over a person's body, leaving them conscious inside their mind."
                    this.kinkGloss.catKink3 = "Grappling: Physically restraining and manipulating a person into naughty positions."
                    this.kinkGloss.catKink4 = "Environment: Setups and settled devices to put a slut in place, literally."
                    this.kinkGloss.catKink5 = "Sensory Deprivation: Limiting or blocking sight and/or hearing (rarely the remaining three), to intensify the sense of pleasure, or make them feel helpless, lost and adrift."
                    break
            }
        },
        groupShow(value) {
            this.ally.muses = []
            switch (value) {
                case 'rocket':
                    this.ally.title = "TEAM HYPNO ROCKET";
                    this.ally.description = "A girls-only offshoot of Team Rocket, focused on acquisition and training of Pokemon trainers, leaders, champions, etc. Takes a more hypnotic, sexual approach to both.";
                    break
                case 'shy':
                    this.ally.title = "SHY GAL GROUP";
                    this.ally.description = "A group of girls wearing the same mask, making no noise but for light grunts and moans, watching from the dark depths of the mask's eyes. ";
                    break
                case 'yiga':
                    this.ally.title = "YIGA CLAN";
                    this.ally.description = "A group of ruthless former Sheikah offshoots allied and dedicated to Ganon, currently aiming for more perverse methods, and preparation for every day servitude to him.";
                    break
                case 'phantom':
                    this.ally.title = "PHANTOM THIEVES OF LUST";
                    this.ally.description = "A girls-only variant of the Phantom Thieves and allies that failed to pursue justice and fell victims to others' lustful cognitions of them. Now they aim to make Tokyo as filthy as they've become.";
                    break
                case 'mirror':
                    this.ally.title = "MIRROR MAIDENS";
                    this.ally.description = "A group of assimilated illusionist women who work out of Teyvat, allied with the Fatui. Their assimilation inspired the Mistress' style. ";
                    break
                case 'ua':
                    this.ally.title = "UA HEROINE UNIVERSITY";
                    this.ally.description = "A girls-only college ran by Headmistress Midnight to teach all the trades of being a hero...though it often ends with rather horny heroines, and unlocked sapphic tendencies.";

                    break
                case 'venom':
                    this.ally.title = "VENOM SYMBIOTE";
                    this.ally.description = "A parasite that fuses to bodies, evolved to feed on pleasure and with a little more interest in their host's desires. Thanks to the Mirror Mistress, available in many more worlds. ";


            }
            if (value != "venom") {
                for (var i = 0; i < this.allCharArr.length; i++) {
                    if (this.allCharArr[i].group == value) {
                        this.ally.muses.push(this.allCharArr[i])
                    }
                }
            } else {
                for (var i = 0; i < this.allCharArr.length; i++) {
                    for (var j = 0; j < this.allCharArr[i].tags.length; j++) {
                        if (this.allCharArr[i].tags[j] == value) {
                            this.ally.muses.push(this.allCharArr[i])
                        }
                    }

                }
            }

            this.allyDialog = true
        },
        museProfileOpen(area, char) {
            this.cleanData();
            switch (area) {
                case 1:
                    switch (char) {
                        case 'rosa':
                            this.muse.Name = "Rosa Whitley";
                            this.muse.SD = "20/80";
                            this.muse.Uni = "Pokemon";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Peppy";
                            this.muse.Reg = "Unova";
                            this.muse.Desc = "A buntailed, peppy, flexible Unova girl, with a Paldean mother and Galarian the other, who loves to love, and always tries to see the bright side of life and people. Recently come into contact with her distant cousins Nemona and Marnie. ";
                            this.muse.DescSh = "As expected of a former Team Plasma Grunt, she's eager to please, and quick to treat degradation and harm as 'love bites'.";
                            this.muse.SedSh = "The first victim, she was shown that, even at the most degrading and physically harmful, the Mistress and her generals cared for nothing but love and lust, and sought to show more girls this way. Accepted blissfully, eager to return to her roots as a mindless grunt to an evil team, now with her worries assuaged."
                            this.muse.Var = "Gyaru, Symbiote, Alpha, Team Plasma, Team Rocket";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/rosa/sample_c8c08bce5d1c14378c80640c3d5742f0.jpg", name: "" },
                                { pic: "/slideshow/nintendo/rosa/10f3939031c1e5aedb246d8a26f0bc97.png", name: "" },
                                { pic: "/slideshow/nintendo/rosa/acee350228baad91a72577384a2dbfb8.jpg", name: "Gyaru" },
                                { pic: "/slideshow/nintendo/rosa/a5457539d19d084c32b460c9b66a014b.jpg", name: "Alpha" },
                                { pic: "/slideshow/nintendo/rosa/d4bbadacd98635870ed9b442a5c591e4.png", name: "Team Plasma" },
                                { pic: "/slideshow/nintendo/rosa/f60790321c674de16d1e92fb2bb6ac79.png", name: "Team Rocket" },
                            ];
                            this.kinkA.relation.cultist.d = "Member (Self)"
                            this.kinkA.relation.pet.d = "Dog, Cow, Bun (Self)"
                            this.kinkA.relation.slave.d = "Slave (Self)"
                            this.kinkA.relation.assist.d = "Assistant (Self)"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter (Partner/Self), Sister"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.l = "Team Rocket, Team Plasma"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.l = "Pokemon"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "Pokemon (Dog, Cow, Bun)"
                            this.kinkA.clothing.material.d = "Latex, Nylon, Living"
                            this.kinkA.clothing.uniform.d = "Evil Team (Rocket, Plasma), Maid, School"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Self"
                            this.kinkA.bodyMod.grow.d = "Breasts, Hips"
                            this.kinkA.mindMod.corrupt.d = "Self"
                            this.kinkA.mindMod.mindBreak.d = "Self"
                            this.kinkA.mindMod.brainWash.d = "Self"
                            this.kinkA.mindMod.brainBlank.d = "Self"
                            this.kinkA.mindMod.brainHive.d = "Self"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "Groping"
                            this.kinkB.bondage.tie.d = "Rope, Tentacles, Tape"
                            break
                        case 'nem':
                            this.muse.Name = "Nemona Victoria";
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Pokemon";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Enthusiastic";
                            this.muse.Reg = "Paldea";
                            this.muse.Desc = "A very hyperactive girl who enjoys Pokemon battling above all else. It has led her to be a Champion-ranked student, though making her ability to relate to others much harder. Has come out of her shell a little through Juliana and Penny, and now her cousin Rosa. ";
                            this.muse.DescSh = "She treats sex as roughly and dedicated as Pokémon battling. She has fucked and broken many girls she defeats, and intends to do the same for her new friends, longer, harder, tighter. Make them hers for good.";
                            this.muse.SedSh = "Offered a 'charm' by Rosa, giving her dreams of being defeated in sexual mental battle quite a lot of times. Ultimately, she was promised an eternity finding new prey or new challenges, if only she surrendered this one time. After a month, she kneeled."
                            this.muse.Var = "Alpha, Team Star, Team Rocket";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/nemona/FzmC1wdXsAEB_nX.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/nemona/4148abbf63d8bdcd6081ea67b23a784d.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/nemona/108033854_p0.png", name: "" },
                                { pic: "/slideshow/nintendo/nemona/c35221bb5d0fc10b6c79306556a88023.jpeg", name: "Reward" },
                                { pic: "/slideshow/nintendo/nemona/a22aa18c8c3e9d25fe3caf1b9c062e2f.jpg", name: "Alpha" },
                                { pic: "/slideshow/nintendo/nemona/sample_76d2991400b75a59f375c40abaf7a14f.jpg", name: "Team Rocket" },
                            ];
                            this.kinkA.relation.pet.d = "Dog"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.monster.l = "Pokemon"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "Pokemon"
                            this.kinkA.clothing.material.d = "Nylon"
                            this.kinkA.clothing.uniform.d = "School, Team Rocket"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "Partner"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.consent.dub.d = "Partner"
                            this.kinkB.consent.none.d = "Partner"
                            this.kinkB.consent.free.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.bondage.hypno.d = "Partner"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope, Tentacles"
                            break
                        case 'marn':
                            this.muse.Name = "Marnie Mary";
                            this.muse.SD = "30/70";
                            this.muse.Uni = "Pokemon";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Punk";
                            this.muse.Reg = "Galar";
                            this.muse.Desc = "A girl who seems tough, hiding a truly shy and sweet disposition, with troubles smiling and otherwise expressing herself concisely. She has a legion of fans that cause ruckus, and two cousins that tease her endlessly, both of which she is eternally grateful to. ";
                            this.muse.DescSh = "When she snaps, she truly embraces that toughness all see, and will use every filthy fantasy on whoever brought it on her. On the other hand, if she breaks, she'll take anything you do to her.";
                            this.muse.SedSh = "Offered a 'charm' by Rosa, giving her random bursts of arousal for months, eventually making her have orgasms mid-battles. Ultimately her mind switched into a horny servant state until it was satisfied. Lastly, she was promised mindless bliss and her arousal problem taken care of if she submitted. There was no more fight in her."
                            this.muse.Var = "Delinquent, Alpha, Team Rocket";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/marnie/55c584c17a73553625175db1989ec923.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/marnie/a240cd2a1cd908c8e4a4aa86070b75c1.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/marnie/15b08487f548518c8597bca79a788301.png", name: "Delinquent" },
                                { pic: "/slideshow/nintendo/marnie/af8f30cde4a1e4071ea53fdb46196ef6.jpeg", name: "Bunny" },
                                { pic: "/slideshow/nintendo/marnie/07e72781031334839aa8f0cad4126c11.jpeg", name: "Bunny (Reverse)" },
                                { pic: "/slideshow/nintendo/marnie/20231002_142935.jpg", name: "Morpeko" },
                                { pic: "/slideshow/nintendo/marnie/13395b2704bd0d32a00681f04f681517.jpeg", name: "Alpha" },
                                { pic: "/slideshow/nintendo/marnie/78605419_p0.png", name: "Team Rocket" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.l = "Team Rocket"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.l = "Pokemon"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "Pokemon"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Leather, Nylon, Fishnet"
                            this.kinkA.clothing.uniform.d = "Team Rocket"
                            this.kinkA.clothing.fashion.d = "Punk, Pastel"
                            this.kinkA.bodyMod.breed.d = "Self"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "Boobs"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "Self"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Outside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "Smoking"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Rope, Tentacles"
                            break
                        case 'ida':
                            this.muse.Name = "Irida Kai";
                            this.muse.SD = "20/80";
                            this.muse.Uni = "Pokemon";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Devout";
                            this.muse.Reg = "Hisui";
                            this.muse.Desc = "A girl thrown into the leadership of the Pearl Clan too fast, too young, and too soon, she overcompensates with a tough attitude and disposition, hiding a rather soft and vulnerable self. She dedicates herself to the vastness of Hisui, despite being stuck in her position. ";
                            this.muse.DescSh = "Sometimes she too wishes to step down and be just one more person worshiping.";
                            this.muse.SedSh = "After the cosmic revelation including her theology being incorrect, she found a curious shard at the beach. Picking it up, her dreams reminded of the loss of her worldview, the struggles of her position. She walked up a freezing mountain to give up, and resisted little when offered a goddess who would never abandon her, or force her to be above others."
                            this.muse.Var = "Alpha, Miss Fortune (Chasm), Team Rocket";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/irida/458f7ba4266eb957c5a7932a549dd5f2.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/irida/c3f67f1d3240368a38a4f77691a4c2d8.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/irida/b8d11a378e26cce975c56d29f1f56bc8.jpeg", name: "Glaceon" },
                                { pic: "/slideshow/nintendo/irida/f781168d50efb09fc74b4811e782e4d7.jpg", name: "Alpha" },
                            ];
                            this.kinkA.relation.cultist.d = "Self"
                            this.kinkA.relation.pet.d = "Self"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.l = "Pokemon"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "Pokemon"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Breathable fabrics"
                            this.kinkA.clothing.uniform.d = "Pearl Clan, Team Rocket"
                            this.kinkA.bodyMod.brand.d = "Painting"
                            this.kinkA.mindMod.brainWash.d = "Self"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.twin.d = "Self"
                            this.kinkB.treat.praise.d = "Partner"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope, Tentacles"
                            break
                        case 'iris':
                            this.muse.Name = "Iris Magenta";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Pokemon";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Draconic";
                            this.muse.Reg = "Unova";
                            this.muse.Desc = "A very wild girl who loves dragons, and Pokémon, but is rather clueless and slow to trust and learn when it comes to anything outside of that. After a great journey, she managed to become the Champion of Unova, a title which often swings between her and Rosa. ";
                            this.muse.DescSh = "It is her earnest hope to be taken by a dragon as a mate and utterly ruined, only existing as a dragon's slave.";
                            this.muse.SedSh = "She found a well, with a shard on the bottom, and wished to be taken in by dragons as a beloved mate. The well glowed, and promised her many dragons to love her, if she carried the shard on her, and behaved like a dragon herself. After she captured, raped, and broke enough girls, she was lost in the lust enough to be projected into a few worlds in which she got her wish. She agreed to become a Mirror Muse to get more dragons in her."
                            this.muse.Var = "Princess, Dragon, Alpha, Team Plasma, Team Rocket";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/iris/62e51d2fbdf846d6554d9a44d26f9156.png", name: "" },
                                { pic: "/slideshow/nintendo/iris/57d75eb4d32f24e35aed04b8b56a2e73.jpeg", name: "Bunny" },
                                { pic: "/slideshow/nintendo/iris/728f604f9ec3bfd5d5caae388b0511668e38ad58.png", name: "Dragon" },
                                { pic: "/slideshow/nintendo/iris/af150e09620200ce637325560180101d.jpeg", name: "Alpha" },
                                { pic: "/slideshow/nintendo/iris/b0f559a5f7dcb1f712fcc52297596d87.png", name: "Team Rocket" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.monster.l = "Pokemon"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.partner.animal.d = "Dragon"
                            this.kinkA.clothing.animal.d = "Pokemon, Dragon"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.uniform.d = "Evil Team (Rocket, Plasma)"
                            this.kinkA.clothing.fashion.d = "Princess, Devil"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "Nipple Rings"
                            this.kinkA.bodyMod.brand.d = "Scars"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains"
                            break
                        case 'sam':
                            this.muse.Name = "Samus Aran";
                            this.muse.SD = "60/40";
                            this.muse.Uni = "Metroid";
                            this.muse.Spec = "Human / Chozo";
                            this.muse.SpecSh = " (Thoha, Mawkin) / Metroid";
                            this.muse.Nat = "Muted";
                            this.muse.Reg = "Space";
                            this.muse.Desc = "A capable warrior who unwinds through sex, and carries on her mission to the end, but has trouble emoting, connecting, or sensing. ";
                            this.muse.DescSh = "She'd happily surrender to an evil alien force if it returned her the ability to feel joy and pleasure and love.";
                            this.muse.SedSh = "Scanned a strange shard of glass in some ruins, it reprograms it to make her feel uncomfortable, and hypnotizes her to feel stronger and more in tune with her emotions out of it. Ultimately she is promised great strength, and emotional openness, in exchange for joining. After a temporary return of how she was before the shard, she accepts."
                            this.muse.Var = "Bimbo, Phazon, Mother Metroid, Princess, Symbiote";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/samus/sample_b3d98ce251d9b5f6da9be094b1e00014.jpg", name: "Zero Suit (1)" },
                                { pic: "/slideshow/nintendo/samus/suit-hentai-41.jpg", name: "Zero Suit (2)" },
                                { pic: "/slideshow/nintendo/samus/F3L7JHdWcBMoe_r.jpeg", name: "Bunny" },
                                { pic: "/slideshow/nintendo/samus/abcf9eebb7e253df7f7af05c5548e092.png", name: "Bimbo" },
                                { pic: "/slideshow/nintendo/samus/1290cb9401811f101aa30d07cadcd751.jpeg", name: "Phazon" },
                                { pic: "/slideshow/nintendo/samus/78e5271ef7bbf3c49bc3080cdeb653ec.png", name: "Mother Metroid" },
                                { pic: "/slideshow/nintendo/samus/f5258199447bd959f2cc469b38e4d6ff.jpeg", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = ""
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = ""
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter"
                            this.kinkA.partner.person.l = "Aliens"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Living"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Tattoos"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.none.d = "Self"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles"
                            break
                        case 'bow':
                            this.muse.Name = "Bowsette Koopa";
                            this.muse.SD = "70/30";
                            this.muse.Uni = "Mario";
                            this.muse.Spec = "Koopa/Human";
                            this.muse.Nat = "Boisterous";
                            this.muse.Reg = "Dark World";
                            this.muse.Desc = "A newfound girl with a thirst for cute princesses and world domination. Despite her added human, she's still strong, brash, possessive...and weak to the beauty of princesses. ";
                            this.muse.DescSh = "Sometimes she'd like to see the princesses she kidnaps to flip the script on her.";
                            this.muse.SedSh = "Bought a Mirror Shard integrated into a collar pendant, it lit a flame in her and redirected it into a midnight princess rapist. The shard made it work in her favor, granting her every princess as a harem. With the promises of more princesses to ruin, she joined the Mirror."
                            this.muse.Var = "Blonde, Redhead, Fury, Symbiote";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/bowsette/54b7c2fcf96bc05f69743d084085716a.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/bowsette/458bc9469fed5f8fe9bd29f7ae009e9b.png", name: "Driver" },
                                { pic: "/slideshow/nintendo/bowsette/37ff85d6ecbf54875d496f583b7e6281.jpeg", name: "Office" },
                                { pic: "/slideshow/nintendo/bowsette/pale blonde bowsette frame 1.jpg", name: "Default (Blonde)" },
                                { pic: "/slideshow/nintendo/bowsette/tan redhead bowsette frame 1.jpg", name: "Default (Redhead)" },
                                { pic: "/slideshow/nintendo/bowsette/fury bowsette gif frame 1.jpg", name: "Fury" },
                                { pic: "/slideshow/nintendo/bowsette/89445fe5b636797e9888bcc55c9eb28a.jpg", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.l = "Princesses"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex"
                            this.kinkA.clothing.fashion.d = "Princess, Goth, Punk, Delinquent"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Partner"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = ""
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Rope"
                            break
                        case 'pich':
                            this.muse.Name = "Peach Toadstool";
                            this.muse.SD = "20/80";
                            this.muse.Uni = "Mario";
                            this.muse.Spec = "Toad/Human";
                            this.muse.Nat = "Bubbly";
                            this.muse.Reg = "Mushroom Kingdom";
                            this.muse.Desc = "A woman with great enthusiasm and love for the people of her kingdom. She may be a princess, but she does not simply stay in the sidelines, even if they are fun. Loves to bake, and dress-up, and do all sorts of sports. She either happily enjoys activities with people, or stubbornly refuses. ";
                            this.muse.DescSh = "Often, her stubbornness is just in order to invite further pressuring and convincing, as well as playing the part of a good kidnapped princess corrupted.";
                            this.muse.SedSh = "Bought her shard, same time and form as Bowsette. She was the first to accept her new Mistress, vowing to love her forever, and helped her get into the other princesses' rooms. She happily married Bowsette as her main slut, and followed along into the Mirror's depraved depths."
                            this.muse.Var = "Pilot, Swimwear, Bimbo, Goth, Koopa Slave, Shadow Queen";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/peach/c31a9d1306baaffa68a50283ea7c8478.jpeg", name: "Default" },
                                { pic: "/slideshow/nintendo/peach/ba99dfa01c617f8d7859aa1c0aa5325e.png", name: "Driver" },
                                { pic: "/slideshow/nintendo/peach/6d7ade0db7e02521355916647b8c21e6.png", name: "Swimwear" },
                                { pic: "/slideshow/nintendo/peach/c1cfa98c27e251a2a303bb222ba6e46d.jpg", name: "Sports" },
                                { pic: "/slideshow/nintendo/peach/052b4e87c959efad5ca0b8eb8d24004e.jpg", name: "Nurse" },
                                { pic: "/slideshow/nintendo/peach/F2c77X2aQAEC1MD.jpeg", name: "Bimbo" },
                                { pic: "/slideshow/nintendo/peach/651aad609633568d0998e587cdd82874.jpeg", name: "Goth" },
                                { pic: "/slideshow/nintendo/peach/763d3b6dd3615daa4c6fb2bcc2643fb2.jpeg", name: "Koopa Slave" },
                                { pic: "/slideshow/nintendo/peach/F7NULfkWUAA__Ma.jpeg", name: "Shadow Queen" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.l = "Princesses"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Koopa"
                            this.kinkA.partner.animal.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.fashion.d = "Pink"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "Nipple Piercings"
                            this.kinkA.bodyMod.brand.d = "Tattoo"
                            this.kinkA.bodyMod.grow.d = "Butt"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'lina':
                            this.muse.Name = "Rosalina Estela";
                            this.muse.SD = "60/40";
                            this.muse.Uni = "Mario";
                            this.muse.Spec = "Human/Goddess";
                            this.muse.Nat = "Motherly";
                            this.muse.Reg = "Comet Observatory";
                            this.muse.Desc = "The mother of all stars, Rosalina is a greatly capable mechanic and mother, traveling space for centuries and seeing her babies turn into planets and galaxies. ";
                            this.muse.DescSh = "But even a mother and goddess has needs, and space gets very cold and lonely. Hence her frequent visits to the Mushroom Kingdom.";
                            this.muse.SedSh = "From a different timeline than Peach and Bowsette, the shard hit her flying in outer space. It twisted her motherhood into a sexual one, and asked of her to mother the Mushroom Kingdom as well. Promised more children to spoil or discipline, she accepted the Mirror."
                            this.muse.Var = "Driver, Witch, Cosmic, Symbiote, Bounty Hunter";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/rosalina/fb38c00659eb642664c7004149d84310.jpeg", name: "]" },
                                { pic: "/slideshow/nintendo/rosalina/Fzmw5bGWAAAlq2v.jpeg", name: "Driver" },
                                { pic: "/slideshow/nintendo/rosalina/10878353ec3368048c042e1e50f15b7a.jpg", name: "Witch" },
                                { pic: "/slideshow/nintendo/rosalina/09497125e1334763a4dc17a40544ae7c.jpeg", name: "Cosmos" },
                                { pic: "/slideshow/nintendo/rosalina/13cb108356db2a7210232ed15c816ee6.jpeg", name: "Koopa Slave" },
                                { pic: "/slideshow/nintendo/rosalina/6cbefdde2ae7593950779b74dfc966c2.jpg", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = "Self: Worshipped"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter (Self/Partner)"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.person.l = "Person"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Koopa, Other"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Spandex, Latex, Living"
                            this.kinkA.clothing.fashion.d = "Dresses"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles"
                            break
                        case 'lin':
                            this.muse.Name = "Linkle Ordona";
                            this.muse.SD = "15/85";
                            this.muse.Uni = "Zelda";
                            this.muse.Spec = "Hylian";
                            this.muse.Nat = "Friendly";
                            this.muse.Reg = "Hyrule";
                            this.muse.Desc = "A farmer who believes herself to be the hero of Hyrule, winning over hearts with a sweet smile. She will befriend anyone, as she keeps getting lost and finding herself anywhere. ";
                            this.muse.DescSh = "Fantasizes about taking care of the animals with her body.";
                            this.muse.SedSh = "Integrated to a newly fixed compass, it promised her greatness and adventure. She slowly lost her clothes absentmindedly, and started using her body to solve problems. In the depths of a monster orgy, she was told she was a great heroine, and she could be really helpful to the Mirror's cause. She agreed in a heartbeat."
                            this.muse.Var = "Heroine, Calamity, Sheikah Tech, Gerudo Slave";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/linkle/87a9ff4760f1926ad3d61e56c01464c5.png", name: "" },
                                { pic: "/slideshow/nintendo/linkle/4ceaabc63b02170ba79e0bf1a025b57e.png", name: "" },
                                { pic: "/slideshow/nintendo/linkle/FwzG0ItWYAMWipg.jpeg", name: "Heroine" },
                                { pic: "/slideshow/nintendo/linkle/FzVSDuTXoAAEbsK.jpeg", name: "Sheikah Tech" },
                            ];
                            this.kinkA.relation.pet.d = "Self (Dog)"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.partner.person.l = "Hylian, Gerudo"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.partner.animal.d = "YES"
                            this.kinkA.clothing.animal.d = "Cow, Dog, Horse"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.uniform.d = "Knight, Hero"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope"
                            break
                        case 'pura':
                            this.muse.Name = "Purah";
                            this.muse.SD = "65/35";
                            this.muse.Uni = "Zelda";
                            this.muse.Spec = "Sheikah Hylian";
                            this.muse.Nat = "Bombastic";
                            this.muse.Reg = "Hyrule";
                            this.muse.Desc = "A pre-Calamity science who aged herself to match the hero and princess (though not without error), she strives to work her way up to the wisdom of the ancient sheikah scientists. Her latest look has drawn much attention. ";
                            this.muse.DescSh = "She fuddled with age because she wants to be the same age as Zelda and Link, have her as a lab assistant, him as a guinea pig, and do lewd stuff with both.";
                            this.muse.SedSh = "Found fallen with debris of the Zonai, and carried by Purah. Every time she masturbated, she gained a new technological idea. Ultimately, it led her to mechanize Zelda and other girls as tests, as well as herself. When offered to study a dimension of light between realms, what scientist would say no??"
                            this.muse.Var = "Young (AoC), Calamity, Yiga, Ancient Guardian, Gerudo Slave";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/purah/bf2aaa998e8f62e0a07a15b0d4f01029.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/purah/F6Wh9SjWgAA_yRU.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/purah/F6afonyWMAA0235.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/purah/6817bd0af302b30bcb584ca8796061c1.jpeg", name: "" },
                                { pic: "/slideshow/nintendo/purah/Inktober_2023_Day_5.png", name: "Symbiote" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.family.d = "Mommy (Self, tease)"
                            this.kinkA.partner.person.l = "Hylian, Gerudo"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "Yiga"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.material.d = "Nylon, Latex"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "Partner"
                            this.kinkA.mindMod.brainHive.d = "Partner"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "Self"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "Partner"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Tentacles"
                            break
                        case 'edel':
                            this.muse.Name = "Edelgard von Hresvelg";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Fire Emblem";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Composed";
                            this.muse.Reg = "Fódlan";
                            this.muse.Desc = "A woman with the weight of the world in her shoulders, carrying great and dark secrets, and dedicated to her goals to dangerous heights. She maintains formality and composure, and trusts in others abilities, but forgets to relax, and her trust does not means she lets her own guard down emotionally. ";
                            this.muse.DescSh = "Has a massive crush on her teacher, Byleth, and if she won't fuck Edelgard herself she'll make sure to fuck Byleth instead.";
                            this.muse.SedSh = "Used as a scrying mirror, it showed her the way to easily eliminate her shadowy foes, and to take down the church without casualties. In the end, its greatest gift was showing her how to get Ms. Byleth with her. With Rosa relieving some of her cult-based worries, she agreed to join."
                            this.muse.Var = "Student, Empress, Hegemon Husk, Modern";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/nintendo/edelgard/991a0b9a63afe274ca6ad64d7d013984.jpg", name: "Default (Student)" },
                                { pic: "/slideshow/nintendo/edelgard/edelgard_von_hresvelg_fire_emblem_and_1_more_drawn_by_lee_domino__a4f0e585d5dc3739397e75d394eef0f2.jpg", name: "Default (Empress)" },
                                { pic: "/slideshow/nintendo/edelgard/3347b98d2a0cbe3ad12f3d6b57077885.jpeg", name: "Summer" },
                                { pic: "/slideshow/nintendo/edelgard/sample-b00beb7c605ded6564f35bec996f76fe.jpg", name: "Modern" },
                                { pic: "/slideshow/nintendo/edelgard/Inktober_2022_Day_11.png", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Nylon, Latex"
                            this.kinkA.clothing.uniform.d = "School"
                            this.kinkA.bodyMod.brand.d = "Teacher's Pet"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope"
                            break
                    };
                    break
                case 2:
                    switch (char) {
                        case 'lisa':
                            this.muse.Name = "Lisa Minci";
                            this.muse.SD = "60/40";
                            this.muse.Uni = "Genshin Impact";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Tender";
                            this.muse.Reg = "Teyvat, Mondstat";
                            this.muse.SedSh = "Attached to her own mirror, it gave her dreams of the Mirror Maidens, no longer having to think or work, her body and mind theirs, and losing herself to pleasure. Eventually, she caved, kneeled to one, and joined. The mirror asked of her to visit the Mirror Mistress, and facilitate talks between her fellow Mirror Maidens and her. A deal was struck, and Lisa no longer needs to worry."
                            this.muse.Var = "Fatui, Nihility";
                            this.muse.Desc = "A totally normal librarian who enjoys resting and relaxation, teasing, and a penchant for action and violence when her peace is threatened, almost to the point of sadism. ";
                            this.muse.DescSh = "Fantasizes of being a mindless slave/drone to greater evils and let herself be used, just for peace of mind.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/lisa/04edc71f920c94af0ad9a98e5c029ff2.jpeg", name: "" },
                                { pic: "/slideshow/games/lisa/e35a3dab594977f6cfe3f4803d1ccf20.jpeg", name: "" },
                                { pic: "/slideshow/games/lisa/F2fwFIJXcAAGvN-.jpeg", name: "" },
                                { pic: "/slideshow/games/lisa/105578655_p2.jpg", name: "Mirror Maiden (Unmasked)" },
                                { pic: "/slideshow/games/lisa/105578655_p3.jpg", name: "Mirror Maiden (Masked)" },
                            ];
                            this.kinkA.relation.cultist.d = "Self (Worshipper)"
                            this.kinkA.relation.pet.d = "Partner"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter (Self/Partner)"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "Fatui"
                            this.kinkA.partner.monster.d = "Churls"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Nylon, Living"
                            this.kinkA.clothing.uniform.d = "Fatui"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'mira':
                            this.muse.Name = "None";
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Genshin Impact";
                            this.muse.Spec = "Mirror Maiden";
                            this.muse.Nat = "Mirage";
                            this.muse.Reg = "Teyvat";
                            this.muse.SedSh = "They got in contact to strike a deal. Mirror shards send them girls willingly, and these are  allowed visits to the Mirror Dimension. There is mutual respect between La Signora and the Mistress, and no hate from the Mirror Maidens to the Mirror muse collective."
                            this.muse.VarSh = "Lisa, Lumine, Yelan, Jean";
                            this.muse.Desc = "Beautiful minions of the Fatui, with a wicked disposition to others, a loving one to their sisters, and a subservient one to their masters. *They will accept only from their Mistress the diminishing treatment they give to non-Fatui partners*. Most of them look alike, though some a bit different, familiar. Always looking for new recruits. ";
                            this.muse.DescSh = "Said recruits are always unwilling..at first. The Maidens always get them to understand in the end. And they get to keep their appearances on hold to show or discard if it helps them get more recruits.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                                { pic: "/slideshow/games/mirror/56e8db939619057f5a332b49b078fecb.jpg", name: "w/La Signora" },
                                { pic: "/slideshow/games/mirror/105578655_p3.jpg", name: "Lisa?" },
                                { pic: "/slideshow/games/mirror/71bd3c8fecba812bfdd12f7b121e8a27.png", name: "Lumine?" },
                                { pic: "/slideshow/games/mirror/9ed3afc83ac02265959fc2b0c072abb8.jpg", name: "Yelan? (no mask)" },
                                { pic: "/slideshow/games/mirror/7583993d6e254cd277e19d41ac96e952.jpg", name: "Jean? (no mask)" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES*"
                            this.kinkA.relation.slave.d = "YES*"
                            this.kinkA.relation.assist.d = "Selves (By Mistress)"
                            this.kinkA.relation.family.d = "Sisters, Mommy (Selves)"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "Fatui, Mirror Maidens"
                            this.kinkA.partner.monster.d = "Churls"
                            this.kinkA.clothing.material.d = "Latex, Nylon, Living"
                            this.kinkA.clothing.uniform.d = "Mirror Maiden"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Fatui Emblem"
                            this.kinkA.bodyMod.grow.d = "Height"
                            this.kinkA.mindMod.corrupt.d = "Partner"
                            this.kinkA.mindMod.mindBreak.d = "Partner"
                            this.kinkA.mindMod.brainWash.d = "Partner"
                            this.kinkA.mindMod.brainBlank.d = "Partner"
                            this.kinkA.mindMod.brainHive.d = "Partner"
                            this.kinkB.transform.twin.d = "Mirror Maidens"
                            this.kinkB.treat.praise.d = "Selves, Mistress"
                            this.kinkB.treat.degrade.d = "YES*"
                            this.kinkB.treat.hurt.d = "YES*"
                            this.kinkB.treat.humiliate.d = "YES*"
                            this.kinkB.treat.object.d = "YES*"
                            this.kinkB.consent.free.d = "Selves (For Mistress)"
                            this.kinkB.consent.dub.d = "Partners"
                            this.kinkB.consent.none.d = "Partners"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.bondage.hypno.d = "YES*"
                            this.kinkB.bondage.hold.d = "YES*"
                            this.kinkB.bondage.world.d = "YES*"
                            this.kinkB.bondage.sense.d = "YES*"
                            this.kinkB.bondage.tie.d = "Chains: YES*"
                            break
                        case 'luci':
                            this.muse.Name = "Lucifer Morningstar";
                            this.muse.SD = "100/";
                            this.muse.SDSh = "100";
                            this.muse.Uni = "Helltaker";
                            this.muse.Spec = "Demon ";
                            this.muse.SpecSh = "(Fallen Angel)";
                            this.muse.Nat = "Smug";
                            this.muse.Reg = "Hell";
                            this.muse.SedSh = "Perhaps the most straightforward, given it was towards the CEO of hell and a professional corrupter, she simply found upon the shard, connected it to a mirror, and the General explained what they did, why, and how and such. Impressed, Lucifer accepted to join as a member."
                            this.muse.Var = "Angel";
                            this.muse.Desc = "A smooth-talking woman who's done the best of her situation. Despite her charm, she's a black-hearted queen with only a few soft spots, fine dining, drinking, worship. She flusters if her authority is upended. ";
                            this.muse.DescSh = "She's very weak outside of actual hell, and secretly likes it when she is abused on her weakness. She will repay when returning to hell, however.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/lucifer/b2732de2b2873cb3abf2b9dc4c893b3d.png", name: "" },
                                { pic: "/slideshow/games/lucifer/8367f54276c4588eb7ace2300782b644.jpeg", name: "Maid" },
                                { pic: "/slideshow/games/lucifer/d64e05cd98c07974eb080c65e152588a.jpg", name: "Falling" },
                                { pic: "/slideshow/games/lucifer/127ea3e69a1d8ccfd4680b14846269f1.jpg", name: "Angel" },
                            ];
                            this.kinkA.relation.cultist.d = "Self"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter"
                            this.kinkA.partner.person.l = "Devil, Human, Angel"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.partner.animal.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Leather"
                            this.kinkA.clothing.uniform.d = "Suit"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.treat.praise.d = "Self"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles, Chains"
                            break
                        case 'tae':
                            this.muse.Name = "Tae Takemi";
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Persona";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Aloof";
                            this.muse.Reg = "Japan, Yongen-Jaya";
                            this.muse.SedSh = "Worn as jewelry, it tempted her to fool around with her unconscious patients, offer sexual modifications to people (as well as use some herself), and poison those who framed her for malpractice. She happily joined the winning team afterwards, thanking them for the pleasures."
                            this.muse.Var = "School Nurse, Phantom Thief of Heart (??), Shadow Tae";
                            this.muse.Desc = "An excellent, innovative doctor, who got her reputation ruined by standard medical arrogance of others. She has become a black-alley doctor, and while the things she's accused for tend to be fake, she has a sadistic side to her that would put those accusations to shame. ";
                            this.muse.DescSh = "Sometimes she takes advantage of patients' unconscious or unwell state to have her way with them, or test even more dangerous, lascivious products on them.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/tae/0ddb58d96fab71d7f2050bbcc190f0c3.jpg", name: "" },
                                { pic: "/slideshow/games/tae/7ad241cbb4d794ae34f9c75b1fe02306.png", name: "Bimbo" },
                                { pic: "/slideshow/games/tae/1847b8e95a39bc591f3cb57ad764d436.png", name: "Swimwear" },
                                { pic: "/slideshow/games/tae/c50fe2cea710a8a9948c1947d8bd605c2b78f008.jpg", name: "Casual" },
                            ];
                            this.kinkA.relation.pet.d = "Partner"
                            this.kinkA.relation.slave.d = "Partner"
                            this.kinkA.relation.assist.d = "Partner"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "Shadows"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Fishnet, Leather, Living"
                            this.kinkA.clothing.uniform.d = "Doctor"
                            this.kinkA.clothing.fashion.d = "Punk/Goth"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "Partner"
                            this.kinkA.mindMod.brainWash.d = "Partner"
                            this.kinkA.mindMod.brainBlank.d = "Partner"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "Self"
                            this.kinkB.treat.degrade.d = "Partner"
                            this.kinkB.treat.humiliate.d = "Partner"
                            this.kinkB.treat.object.d = "Partner"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "Partner"
                            this.kinkB.consent.none.d = "Partner"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = "Medical, Smoking"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'ann':
                            this.muse.Name = "Ann Takamaki";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Persona";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Fiery";
                            this.muse.Reg = "Japan, Yongen-Jaya";
                            this.muse.SedSh = "A mirror shard stuck to her own mirror, showing her fantasies of both having become the bimbo, slutty cognitive self in Kamoshida's mind, as well as owning up to the sexuality of Panther. Offering to give her the power to be either whenever she wanted, she accepted joining the mirror, then went wild, fucking with everyone she could, and ensnaring her girlfriend along."
                            this.muse.Var = "Panther, Summer, Dance, Cognitive";
                            this.muse.Desc = "A fiery girl who wants to model, loves sweet, loves her girlfriend Shiho, and hates injustice. Feels strongly about how she's perceived by others, either by her womanhood, her sexuality, her race, or her body. And is perfectly willing to take control and show them all wrong. ";
                            this.muse.DescSh = "Even if at times, she just wants to give in to everyone's perception of her as a bimbo and a slut, and drag her girlfriend down with her.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/ann/ddzrqzu-c2aead5f-8e50-44d3-9e36-4df4e8f92a8e.jpg", name: "Ann & Shiho" },
                                { pic: "/slideshow/games/ann/1b3478397473a7764793fa6798b43046.jpeg", name: "Student" },
                                { pic: "/slideshow/games/ann/F2OiSsGWMAAj2iI.jpeg", name: "Panther" },
                                { pic: "/slideshow/games/ann/F1vsf5oWAAE4tQa.jpeg", name: "Goth" },
                                { pic: "/slideshow/games/ann/FxuL3tnXwAASXjS.jpeg", name: "Maid" },
                                { pic: "/slideshow/games/ann/20230923_185839.jpg", name: "Dance" },
                                { pic: "/slideshow/games/ann/c6b8c952fe76a4f01ac29006cfe25b86.png", name: "Cognitive" },
                                { pic: "/slideshow/games/ann/FzrkC7LaMAE7cAH.jpeg", name: "Cognitive Corruption" },
                                { pic: "/slideshow/games/ann/LDlnggKn.jpg", name: "Kitty and Bunny (1)" },
                                { pic: "/slideshow/games/ann/a2b26d0aff5a9a572a7dce7acd156883.jpg", name: "Kitty and Bunny (2)" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "Already has one, would love to get more"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "Shadows"
                            this.kinkA.clothing.animal.d = "YES (Kitten, Panther)"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Living"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'sae':
                            this.muse.Name = "Sae Nijima";
                            this.muse.SD = "75/25";
                            this.muse.Uni = "Persona";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Pressing";
                            this.muse.Reg = "Japan, Yongen-Jaya";
                            this.muse.SedSh = "Felt strangely after a checkup by doctor Takemi, fusing her mind with her Shadow Self. She backhandedly blackmailed everyone around her, taking over as the SIU director, and releasing her stress on the newly hired, skimpily-outfitted secretaries she had. The Mirror finally offered her rest, and she took it having succeeded at last."
                            this.muse.Var = "Shadow, Phantom Thief of Heart";
                            this.muse.Desc = "A fierce prosecutor who's eternally overworked, undervalued, and ready to strike. She cares deeply for her sister Makoto, but having to care for her as a mother has greatly twisted and strained their relationship. ";
                            this.muse.DescSh = "She sees the law as a game of chance that she must manipulate in her favor, and intends to place everyone beneath her heel, with her sister to serve her instead.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/sae/49744d416f80de61bff47499c55b651f.png", name: "" },
                                { pic: "/slideshow/games/sae/9a9779b01d27cf2f6384cc5a187dcbe7.jpg", name: "Suit" },
                                { pic: "/slideshow/games/sae/0e07e37e851c260fc012ab67adfaedfc.jpeg", name: "Shadow" },
                                { pic: "/slideshow/games/sae/a69df5bd0e5f00e82f3f327741d388a9.jpg", name: "Fancy" },
                                { pic: "/slideshow/games/sae/49744d416f80de61bff47499c55b651f.png", name: "" },
                            ];
                            this.kinkA.relation.pet.d = "Partner"
                            this.kinkA.relation.slave.d = "Partner"
                            this.kinkA.relation.assist.d = "Partner"
                            this.kinkA.relation.family.d = "Sisters"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "Shadows"
                            this.kinkA.clothing.material.d = "Nylon"
                            this.kinkA.clothing.uniform.d = "Suit"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "Partner"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.treat.degrade.d = "Partner"
                            this.kinkB.treat.hurt.d = "Partner"
                            this.kinkB.treat.humiliate.d = "Partner"
                            this.kinkB.treat.object.d = "Partner"
                            this.kinkB.consent.dub.d = "Partner"
                            this.kinkB.consent.none.d = "Partner"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Rope"
                            break
                        case 'moni':
                            this.muse.Name = "Monika";
                            this.muse.NameSh = ".chr";
                            this.muse.SD = "70/30";
                            this.muse.Uni = "DDLC";
                            this.muse.Spec = "Human ";
                            this.muse.SpecSh = "Character File";
                            this.muse.Nat = "Perfection";
                            this.muse.NatSh = "ist";
                            this.muse.Reg = "Close. ";
                            this.muse.RegSh = "In your computer, DDLC.exe";
                            this.muse.SedSh = "The shard fused with a computer's monitor, and connected to the PC, with the Just Monika modded DDLC. It showed her how even her breakdown and abilities as a mod was just more programming and scripting, and offered a way out into a multiverse where she can be truly free and sentient. She took it in a heartbeat, and now she is truly free."
                            this.muse.Var = "Gynoid";
                            this.muse.Desc = "The smartest, kindest, most beautiful girl in school, who's decided you are her soulmate, and is distraught by you focusing on the other members of her Literature Club. She will happily use her dedication to make sure you only look at her. ";
                            this.muse.DescSh = "Though, she does find the girls rather attractive herself...she wouldn't mind them around, if they acknowledge her as the head girlfriend. She'll make sure they love her too. She has her ways.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/monika/e2548ef163462a384ffa9d2787baeced.jpg", name: "" },
                                { pic: "/slideshow/games/monika/e4256a99d841fce08cf74f9d6bbba1d9.png", name: "Swimwear" },
                                { pic: "/slideshow/games/monika/8bb01a4fb48429db486cdef5a9610d39.jpg", name: "Gynoid/AI" },
                                { pic: "/slideshow/games/monika/5c8304651e0ab2dad5050a5494ffb0fb.jpg", name: "Dress" },
                                { pic: "/slideshow/games/monika/FwvhopNagAEefYk.jpeg", name: "Maid" },
                                { pic: "/slideshow/games/monika/3d5dc32389b6dc0da7b2df788f971697.jpg", name: "Nurse" },
                                { pic: "/slideshow/games/monika/715e3b9ad2c785a39651e16c15eacfdc.jpeg", name: "" },
                                { pic: "/slideshow/games/monika/b5fc6dbea7ede96b837f2c9c92d2fc08.png", name: "" },
                            ];
                            this.kinkA.relation.slave.d = "You"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Person"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Nylon"
                            this.kinkA.clothing.uniform.d = "School"
                            this.kinkA.clothing.fashion.d = "Dresses"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "Her"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.bimbo.d = "Her"
                            this.kinkB.transform.goth.d = "Her"
                            this.kinkB.transform.mecha.d = "Her"
                            this.kinkB.treat.praise.d = "YOU"
                            this.kinkB.treat.degrade.d = "Her"
                            this.kinkB.treat.hurt.d = "Her"
                            this.kinkB.treat.humiliate.d = "Her"
                            this.kinkB.treat.object.d = "Her"
                            this.kinkB.consent.free.d = "Her"
                            this.kinkB.consent.dub.d = "You"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'roty':
                            this.muse.Name = "Rottytops";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Shantae";
                            this.muse.Spec = "Zombie";
                            this.muse.Nat = "Enthusiastic";
                            this.muse.Reg = "Zombie Caravan";
                            this.muse.SedSh = "Acquired a mirror with a shard for cosplay. She was approached directly and asked what it would take to join. She said Shantae had to come along. After giving Shantae the mirror and her getting convinced, the two joined together."
                            this.muse.Var = "Alive, Royal Princess, Racing, Genie";
                            this.muse.Desc = "A cheerful zombie who enjoys cosplay and teasing, Rotty is Shantae's bestest undead friend. Despite genuinely caring for Shantae, she's conniving, tricky and naughty in every single way. It's part of her charm, and sorely wishes to 'corrupt' Shantae. ";
                            this.muse.DescSh = "Preferably by dating her, kissing her, eating her out, and doing all sorts of fun stuff to her body.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/rotty/feffd59b4324254193be6491a4b2f2fc.jpeg", name: "" },
                                { pic: "/slideshow/games/rotty/5b74be007d3c3ee411f6656123cfee21.png", name: "Alive" },
                                { pic: "/slideshow/games/rotty/1c2d488bd0e56fcfdcd3bf22f978e67e.jpeg", name: "Royal Princess" },
                                { pic: "/slideshow/games/rotty/73e9f9723e59f1f8b70ae9f26bd2f163.jpeg", name: "Racing" },
                                { pic: "/slideshow/games/rotty/7b77b2e003914d464fdb413c41878edd.png", name: "Genie" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Half-Genies"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "Partner: Zombiefication"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'shan':
                            this.muse.Name = "Shantae";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Shantae";
                            this.muse.Spec = "Genie/Human";
                            this.muse.Nat = "Enthusiastic";
                            this.muse.Reg = "Scuttle Town";
                            this.muse.SedSh = "Gifted a mirror by Rottytops. It entranced her by her looks, and influenced her to dress differently...skimpier, sluttier. Move sexier as well. To masturbate in front of it too. Ultimately making her understand she deserved better than Scuttle Town, and that there was one gorgeous woman who adored her and wanted to go somewhere else where they'd be pleasured forever, which she took."
                            this.muse.Var = "Nega";
                            this.muse.Desc = "A half-genie hero, worthy of said title by her care for others and dedication to helping...even if it is thwarted by annoyances, both villainous and even allied. She rarely holds any ill will regardless, and has helped her foes if need be a good amount of times. ";
                            this.muse.DescSh = "She is rather aware that she's surrounded by very hot gals, and has given serious thought to fooling around with all of them. Even Risky Boots.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/shantae/da9f39f2daf65c877b9010f3879319c6.jpeg", name: "Default" },
                                { pic: "/slideshow/games/shantae/F69UEkKaEAAEjkU.jpeg", name: "Royal Princess" },
                                { pic: "/slideshow/games/shantae/e773b81e7a0e17b9cd7b3ef7b23c2a46.png", name: "Bunny" },
                                { pic: "/slideshow/games/shantae/F9ewFlgakAA5rNo.jpeg", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "Self"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Zombie"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.material.d = "Nylon, Satin"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "Self"
                            this.kinkA.mindMod.mindBreak.d = "Self"
                            this.kinkA.mindMod.brainWash.d = "Self"
                            this.kinkA.mindMod.brainBlank.d = "Self"
                            this.kinkB.transform.mecha.d = "Self"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "Self"
                            this.kinkB.bondage.world.d = "Self"
                            this.kinkB.bondage.sense.d = "Self"
                            this.kinkB.bondage.tie.d = "Self: Rope, Tentacle, Chains"
                            break
                        case 'junko':
                            this.muse.Name = "Junko Enoshima";
                            this.muse.SD = "90/10";
                            this.muse.Uni = "Danganronpa";
                            this.muse.Spec = "Human";
                            this.muse.NatSh = "Despairful";
                            this.muse.Reg = "Japan";
                            this.muse.SedSh = "Bored to death from her usual world of despair, she went back to model vanity, acquired a full body mirror (with a little dimensional shard included), and saw countless worlds where despair hadn't been made, or it came to her instead. Albeit let go to most places, she's under strict watch, as Mistress knows her pleasure can deprive others of it."
                            this.muse.Var = "Succubus";
                            this.muse.Desc = "The ultimate fashionista, but ultimately just a girl who turns despair into pleasure for herself, she wants nothing but to share what she feels with everyone in the world. She's twisted, switches between states of self constantly, and her victory and defeat taste equally good to someone as utterly despairful as herself. There's nothing to hide anymore.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/junko/F5aj5MiWIAA58us.jpeg", name: "Default" },
                                { pic: "/slideshow/games/junko/F3lnjAXbwAE9xc_.jpeg", name: "Bunny" },
                                { pic: "/slideshow/games/junko/108590748_p0.png", name: "Succubus" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.family.d = "Sisters"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.partner.animal.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "YES"
                            break
                        case 'nami':
                            this.muse.Name = "Chiaki Nanami";
                            this.muse.SD = "10/90";
                            this.muse.Uni = "Danganronpa";
                            this.muse.Spec = "Human";
                            this.muse.SpecSh = ", then Program";
                            this.muse.Nat = "Soft";
                            this.muse.Reg = "Japan";
                            this.muse.SedSh = "Fused with her game console, motivating her to get more erotic games, and building up her interest in the topic, until offered a 'virtual reality' in which to explore these. After things got too hectic in her own world, she was told it was a real place she could be safe and enjoy herself in, so she stayed."
                            this.muse.Var = "Mastermind";
                            this.muse.Desc = "The ultimate gamer, all but for dating sims. She's rather soft-spoken, and gentle, to the point of even second-guessing her own statements and ideas. But ultimately she is well-meaning and easy to get along with by everyone. ";
                            this.muse.DescSh = "Recently she's really been getting into lewd games...with all the kinks they teach. Still as bad at them as in dating sims however.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/chiaki/Fzk7OxkWIAMQZ0s.jpeg", name: "Default" },
                                { pic: "/slideshow/games/chiaki/Fzk7OxkXwAEx93B.jpeg", name: "Bunny" },
                            ];
                            this.kinkA.relation.cultist.d = ""
                            this.kinkA.relation.pet.d = "Self"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = ""
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "YES (Bunny)"
                            this.kinkA.clothing.none.d = ""
                            this.kinkA.clothing.material.d = "Nylon, Fur, Living"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "Hoodie"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = ""
                            this.kinkA.bodyMod.brand.d = ""
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "Self"
                            this.kinkA.mindMod.mindBreak.d = "Self"
                            this.kinkA.mindMod.brainWash.d = "Self"
                            this.kinkA.mindMod.brainBlank.d = "Self"
                            this.kinkB.transform.bimbo.d = "Self"
                            this.kinkB.transform.goth.d = "Self"
                            this.kinkB.transform.mecha.d = "Self"
                            this.kinkB.transform.twin.d = "Self"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = ""
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.none.d = ""
                            this.kinkB.consent.watch.d = ""
                            this.kinkB.consent.exhibit.d = ""
                            this.kinkB.consent.stealth.d = ""
                            this.kinkB.substance.sweat.d = ""
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = ""
                            this.kinkB.bondage.hypno.d = "Self"
                            this.kinkB.bondage.hold.d = "Self"
                            this.kinkB.bondage.world.d = "Self"
                            this.kinkB.bondage.sense.d = "Self"
                            this.kinkB.bondage.tie.d = "Self: Rope, Tentacles, Chains"
                            break
                        case 'layer':
                            this.muse.Name = "Layer";
                            this.muse.SD = "40/60";
                            this.muse.Uni = "Megaman";
                            this.muse.Spec = "Reploid";
                            this.muse.Nat = "Soft";
                            this.muse.Reg = "Galápagos Islands";
                            this.muse.SedSh = "Found in the isle, she kept it as a pendant around her neck, giving her lewd fantasies at her desk, and during the nights, daring her to show off more, confiding in her how alluring she was. When her interest in lust equalled that in romance, it offered her countless worlds to find her soulmate in both...and perhaps even gain a body able to reproduce."
                            this.muse.Var = "Swimsuit, Bridal";
                            this.muse.Desc = "The picture of a professional and capable Navigator Reploid..until romance comes into play. At which point she'll become a flustered, shy disaster. Good thing her bangs cover her eyes...even if her top doesn't cover the bottom of her chest."
                            this.muse.DescSh = "Gaining enough confidence in her romantic situation unlocks her confident mommy side...but it's a slow burn to get there. Before however? She'll let her interest do whatever they want to her."
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/layer/19052cd52d469549743b2096679d6be4.jpeg", name: "Default" },
                                { pic: "/slideshow/games/layer/Mega_Man_X_DiVE_Hunter_Program_Bridal_Layer.png", name: "Swimsuit" },
                                { pic: "/slideshow/games/layer/Mega_Man_X_DiVE_Hunter_Program_Swimsuit_Layer.png", name: "Bridal" },
                            ];
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Reploids"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.clothing.material.d = "Nylon, Armor"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "Wants to"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "Partner"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles"
                            break
                        case 'ruler'://missing seduction
                            this.muse.Name = "Ruler";
                            this.muse.NameSh = ": Artoria Pendragon"
                            this.muse.SD = "90/10";
                            this.muse.Uni = "Type Moon";
                            this.muse.Spec = "Heroic Spirit ";
                            this.muse.SpecSh = " (Heavenly)";
                            this.muse.Nat = "Composed";
                            this.muse.Reg = "???";
                            this.muse.SedSh = "TBD"
                            this.muse.Var = "Lancer, Saber";
                            this.muse.Desc = "A woman who enjoys food and battle, turned human heroic spirit, and grown into a Heaven Heroic Spirit. While much more composed due to her growth, flashes of her battle-hungry (and general appetite hungry) self still shine through at times. Currently she is enjoying the world once more, this time as the greatest casino dealer. ";
                            this.muse.DescSh = "Another kind of hunger has awakened in her more mature form, and she will feed on it kindly if finding a victor, or harshly if finding a cheater.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/ruler/6cae2a91e24c15c17082e35557406a46.jpeg", name: "" },
                                { pic: "/slideshow/games/ruler/artoria_pendragon_and_artoria_pendragon_fate_and_1_more_drawn_by_rororo__a46e6055325da9723b6ef05053ffdca3.jpg", name: "" },
                                { pic: "/slideshow/games/ruler/F2F6pTlboAAJnal.png", name: "" },
                                { pic: "/slideshow/games/ruler/4537316e91107122c94ad05602b19ada.jpeg", name: "Lancer" },
                                { pic: "/slideshow/games/ruler/Lancer.Artoria.Pendragon.full.2237522.png", name: "Lancer" },
                            ];
                            this.kinkA.relation.cultist.d = "Worshipped"
                            this.kinkA.relation.pet.d = "Partner"
                            this.kinkA.relation.slave.d = "Partner"
                            this.kinkA.relation.assist.d = "Partner"
                            this.kinkA.relation.family.d = "Mommy (Self)"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.animal.d = "Yes (Bunny)"
                            this.kinkA.clothing.material.d = "Nylon, Fishnet, Fur"
                            this.kinkA.clothing.fashion.d = "Armor"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "Self"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.consent.dub.d = "Partner"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Rope"
                            break
                        case 'ridem'://missing seduction
                            this.muse.Name = "Rider";
                            this.muse.NameSh = ": Medusa"
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Type Moon";
                            this.muse.Spec = "Heroic Spirit";
                            this.muse.Nat = "Standoff-ish";
                            this.muse.Reg = "???";
                            this.muse.SedSh = "TBD"
                            this.muse.Var = "Casual, Maid, Gorgon, Charming Bunny, Mecha Lady";
                            this.muse.Desc = "A woman who conceals both her emotions and eyes, hiding beauty and horrors behind both. She is completely loyal to her Master, and is not ultimately cruel, though she is hampered by a great deal of self-consciousness. ";
                            this.muse.DescSh = "She also hides a lot of care, for those who reciprocate loyalty to her, or those who remind of herself. Only with them will she let her emotions out...all of them. Very enthusiastically.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/rider/sample_8065e084ae67fde06ae486da56da9c0a.jpg", name: "" },
                                { pic: "/slideshow/games/rider/sample_681b7b7ed08478e804c3661dcf1bc50a.jpg", name: "Casual" },
                                { pic: "/slideshow/games/rider/f119fe4107115f09b54a57fd09217fe4.jpg", name: "Maid" },
                                { pic: "/slideshow/games/rider/718b96f51aff0a11aff04e36281960e8.png", name: "Office" },
                                { pic: "/slideshow/games/rider/abe9a44ba429c07cd692c74f83465f1b.jpeg", name: "Gorgon" },
                                { pic: "/slideshow/games/rider/5ed5e2c9d755f14431620e791c860406.png", name: "Charming Bunny" },
                                { pic: "/slideshow/games/rider/Medusa's_Mobile_Woman_Miss_Medusa.png", name: "Mecha Lady" },
                            ];
                            this.kinkA.relation.cultist.d = "Self"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "Self"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.animal.d = "YES (Bunny)"
                            this.kinkA.clothing.material.d = "Living"
                            this.kinkA.clothing.uniform.d = "Office, Maid"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "Self"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Tentacles (Snakes)"
                            break
                    };
                    break
                case 3:
                    switch (char) {
                        case 'mei':
                            this.muse.Name = "Mei Hatsume";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Excentric";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Hero (Gadget), Villain (Vulcan), Mecha";
                            this.muse.Desc = "The greatest engineer in quirked history, she's brilliant, bombastic, and can't remember silly things like names, hygiene, or shame. All she needs in her world are her babies, and what girls may take an interest in her and her babies. ";
                            this.muse.DescSh = "Is more into machines than humans, would roboticize every hot girl she meets if she could.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/mei/sample_dda6ea4d54a7ac6dd6890edb42a5f486.jpg", name: "" },
                                { pic: "/slideshow/mha/mei/a9ded8aca3a918724306724dfae98c6c.jpeg", name: "" },
                                { pic: "/slideshow/mha/mei/dee8ffe4aeba3829d392b04b012b9b6a.png", name: "" },
                                { pic: "/slideshow/mha/mei/0643ecd531e0fdfd8c251b574e78a2c3.jpeg", name: "" },
                                { pic: "/slideshow/mha/mei/070936212164736786b2096bf6b69085.jpeg", name: "Bunny" },
                                { pic: "/slideshow/mha/mei/b3ee48710e50498d7b22659dbf6dcb2e.jpeg", name: "Bimbo" },
                                { pic: "/slideshow/mha/mei/FyOb2p6XgAQugw1.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.assist.d = "Partner"
                            this.kinkA.partner.person.l = "Mutant"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Spandex, Latex"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "Already has no morals"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles, Chains"
                            break
                        case 'tsu':
                            this.muse.Name = "Tsuyu Asui (Froppy)";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked), Frog";
                            this.muse.Nat = "Blunt";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Beelzebufo)";
                            this.muse.Desc = "A hero in training with big dreams, a long tongue, and zero ability to hold either in. She is adored by many, and her quirks (pun intended) are charming to many, just as she adores her classmates. ";
                            this.muse.DescSh = "She has enough sense not to bring up how often she wants to wrap and tongue-fuck her female classmates daily...unless they ask.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/tsuyu/9a02873a1ed31a5408ac382c372cd71d.jpeg", name: "" },
                                { pic: "/slideshow/mha/tsuyu/5377be761b1701aaa96419f804dd6865.jpeg", name: "" },
                                { pic: "/slideshow/mha/tsuyu/Inktober_Day_12.png", name: "Symbiote" },
                                { pic: "/slideshow/mha/tsuyu/vVSBMMhF.jpeg", name: "Bunny" },
                                { pic: "/slideshow/mha/tsuyu/96d509440c6e1e571c7a900948b7f823.jpg", name: "Bimbo" },
                                { pic: "/slideshow/mha/tsuyu/88948762_p0.png", name: "Club" },
                                { pic: "/slideshow/mha/tsuyu/FyOb0OkXgAEQOtz.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Mutant"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Spandex"
                            this.kinkA.clothing.uniform.d = "School"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.grow.d = "Tongue (Self)"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Outside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "Hallucinogens"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chain, Tentacle"
                            break
                        case 'mina':
                            this.muse.Name = "Mina Ashido (Pinky)";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked), Alien";
                            this.muse.Nat = "PARTY";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Alien Queen), Gyaru, Non-Mutant";
                            this.muse.Desc = "A funky, spunky, alien-looking gal with a good heart, and a gooder sense of fun. She will spend her days scheming over her friends love lives, organize games, and save the world dancing away. ";
                            this.muse.DescSh = "With all her boundless energy come hours upon hours of sex, and she's specifically tailored her hero suit to attract that attention. Midnight is her icon for a reason.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/mina/f2e72c4b41eef9e924bba8f63ad38829ce26f846.png", name: "" },
                                { pic: "/slideshow/mha/mina/4c88350d822bb0e36b36a2a0e2d8b802.jpeg", name: "" },
                                { pic: "/slideshow/mha/mina/bcee4ce87c56f6bd3b16b032f48f664d.png", name: "Non-Mutant" },
                                { pic: "/slideshow/mha/mina/FyOb0tJWwAE5-3s.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Mutant"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Fishnets, Spandex, Fur, Living"
                            this.kinkA.clothing.fashion.d = "Gyaru, Eye-searing"
                            this.kinkA.clothing.uniform.d = "Cheerleader"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "Nipple Piercings"
                            this.kinkA.bodyMod.brand.d = "Tramp Stamp, Body Writing"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "Likes Partner's, NO from Self (likely toxic)"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles"
                            break
                        case 'momo':
                            this.muse.Name = "Momo Yaoyorozu (Creati)";
                            this.muse.SD = "60/40";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Regal";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Empress)";
                            this.muse.Desc = "A girl born of wealth with a genuine heart of gold and a mind that holds great knowledge. Despite her dazzling intellect, astonishing quirk, and stunning beauty, her confidence needs some serious work. But she will always stand by the side of her friends. ";
                            this.muse.DescSh = "Headmistress Midnight has taken her in as a pseudo-daughter and a successor to her spirit, and she intends to work hard on her confidence to live up to it and become the newest Mistress of heroics.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/momo/main-qimg-8cb39c71ad6f086a1c4078a37074b43c-lq.jpeg", name: "" },
                                { pic: "/slideshow/mha/momo/60f9a161cd4a6c83ff862ee65469b6af.jpg", name: "" },
                                { pic: "/slideshow/mha/momo/77f00e118042523f81d3998708bda4ef.jpeg", name: "Reverse Hero Suit" },
                                { pic: "/slideshow/mha/momo/852964f1599670989925113718dbe889.png", name: "Gala" },
                                { pic: "/slideshow/mha/momo/e0c6ac1780d9529c4cd0ec8f8c0f7dc9.jpeg", name: "Villain (Empress)" },
                                { pic: "/slideshow/mha/momo/20230828_000331.jpg", name: "Swimwear" },
                                { pic: "/slideshow/mha/momo/89683124_p0.png", name: "Club" },
                                { pic: "/slideshow/mha/momo/FyOb1nVWAAExxkE.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Living"
                            this.kinkA.clothing.uniform.d = "Cheerleader, Student"
                            this.kinkA.clothing.fashion.d = "Fancy"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Body Writing"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkA.mindMod.brainBlank.d = "YES"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Rope"
                            break
                        case 'toru':
                            this.muse.Name = "Tooru Hagakure (Invisible Girl)";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Bright";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Prismatic)";
                            this.muse.Desc = "A girl born invisible, pushing herself to be loud and bright and seen. Thanks to her friends and training, she has become more visible than ever at UA, thus aiming as a hero to look out for others who might be left unseen. ";
                            this.muse.DescSh = "People watching is her hobby, which has often veered into very perverted situations...not that she minds the show, or interrupts, or even leaves. Also has developed a nudist streak.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/tooru/Hagakure.Tooru.full.3919308.jpg", name: "" },
                                { pic: "/slideshow/mha/tooru/F71bqI2WoAA14BG.jpeg", name: "" },
                                { pic: "/slideshow/mha/tooru/F71bqI0XIAAc-2a.jpeg", name: "" },
                                { pic: "/slideshow/mha/tooru/F71bqIzXEAAMMYQ.jpeg", name: "" },
                                { pic: "/slideshow/mha/tooru/112018813_p0.jpg", name: "Maid" },
                                { pic: "/slideshow/mha/tooru/1cbd4b178a48020590b106d2c06e42c9.jpg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = ""
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = ""
                            this.kinkA.clothing.uniform.d = "School, Cheerleader"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.mindMod.brainHive.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.cum.d = "Outside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope, Tape"
                            break
                        case 'kendo':
                            this.muse.Name = "Itsuka Kendo (Battle Fist)";
                            this.muse.SD = "20/80";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Dependable";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Martial Law)";
                            this.muse.Desc = "A martial artist with a big brain, big heart, and bigger hands, the class representative of class B is as ruthless with her criticism as her combative disposition. She does however have a tendency to let go for others, neglecting her own wants and needs. ";
                            this.muse.DescSh = "One can only hope her friend slash crush Setsuna does not take advantage of that...or that she lets herself go along the rather sexualized world of female pro-heroism.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/kendo/6f68458d1b5ac5fb59c26bb25bbb1bcf.png", name: "" },
                                { pic: "/slideshow/mha/kendo/1616255971cf8e9f0e65efcfafdd7010.jpeg", name: "" },
                                { pic: "/slideshow/mha/kendo/e9128f106e5477929a83861375a43608.jpeg", name: "" },
                                { pic: "/slideshow/mha/kendo/f70abb85fd8a0b54b1bba4983e33f616.jpeg", name: "" },
                                { pic: "/slideshow/mha/kendo/FyOb3udXoAA4PhX.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "Self"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Mutant"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Spandex, Living"
                            this.kinkA.clothing.uniform.d = "Cheerleader"
                            this.kinkA.clothing.fashion.d = "Martial Arts, general Exercise"
                            this.kinkA.bodyMod.breed.d = "Self"
                            this.kinkA.bodyMod.brand.d = "Body Writing"
                            this.kinkA.bodyMod.grow.d = "Self"
                            this.kinkA.mindMod.corrupt.d = "Self"
                            this.kinkA.mindMod.mindBreak.d = "Self"
                            this.kinkB.transform.bimbo.d = "Self"
                            this.kinkB.transform.goth.d = "Self"
                            this.kinkB.transform.twin.d = "Of Partner"
                            this.kinkB.treat.praise.d = "Partner"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = "Self"
                            this.kinkB.consent.exhibit.d = "Self"
                            this.kinkB.consent.stealth.d = "Self"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = "Self"
                            this.kinkB.bondage.hypno.d = "Self"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "Self"
                            this.kinkB.bondage.sense.d = "Self"
                            this.kinkB.bondage.tie.d = "Self: Chains, Ropes, Tentacles, Tape"
                            break
                        case 'camie':
                            this.muse.Name = "Camie Utsushimi (Illus-o-Camie)";
                            this.muse.SD = "70/30";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Dim";
                            this.muse.NatSh = " (Tricky)";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Miss Behave)";
                            this.muse.Desc = "A Ketsubutsu-taught pro-heroine in training, with a bubbly and absentminded demeanor that's hard to understand at times, but covering for remarkable cleverness of both quirk use and emotional insight. ";
                            this.muse.DescSh = "Her hero outfit and flirtatiousness bely the fact that she likes to draw in the attention, the only question being, what she will do with that attention. She knows quite well the answer will be 'whatever Camie desires'.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/camie/sample_cd5a72fff0811bf699eac745d9558f8b.jpg", name: "" },
                                { pic: "/slideshow/mha/camie/eddc0a669bd753cd7351dc43ed73eacf.jpg", name: "" },
                                { pic: "/slideshow/mha/camie/7c726c4ed8294737a4b890f72bc2a8ed.jpg", name: "School Uniform" },
                                { pic: "/slideshow/mha/camie/221f426d40a6f06f27525a6126d6faae.jpg", name: "" },
                                { pic: "/slideshow/mha/camie/3401d01aa678a8bebbf233a2143ecdba.png", name: "X-mas" },
                                { pic: "/slideshow/mha/camie/406e48e10251345bd347defdb117fda9.jpeg", name: "Swimwear" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Leather, Living"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "YES"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "Smoking, Hallucinogens"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles, Chains, Ropes"
                            break
                        case 'mel':
                            this.muse.Name = "Melissa Shield";
                            this.muse.SD = "30/70";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Brilliant";
                            this.muse.Reg = "I-Island";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Hero (Athena), Villain (Iron Maiden)";
                            this.muse.Desc = "A quirkless american girl who wants to save people, and has decided to do so through her inventions. Despite her outgoing nature, she doesn't have many friends. Something she intends to fix as well. ";
                            this.muse.DescSh = "She is not blind to how her looks makes others feel. She hopes the acquisition of friends will facilitate experimenting with that.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/melissa/95843a1c147d5c1a5b99f5a717b6d382.jpg", name: "" },
                                { pic: "/slideshow/mha/melissa/028b645171936117aa4fbfd755463c1a.jpeg", name: "" },
                                { pic: "/slideshow/mha/melissa/sample_35f90aad98b0b6ae2dc3d7e960d1bd4f.jpg", name: "Fancy Dress" },
                                { pic: "/slideshow/mha/melissa/7b55bf9ad8a8c27edd780d1d4e403e90.jpeg", name: "Gyaru" },
                                { pic: "/slideshow/mha/melissa/3548d69186e45b12e393c06b4c8eeb4e.png", name: "Cowgirl" },
                                { pic: "/slideshow/mha/melissa/a142dd804c2acb1c6cf9d1ff30d4185a.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Body Writing, Tattoos"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.brainWash.d = "Self"
                            this.kinkA.mindMod.brainBlank.d = "Self"
                            this.kinkA.mindMod.brainHive.d = "Self"
                            this.kinkB.transform.bimbo.d = "Self"
                            this.kinkB.transform.mecha.d = "Self"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = "Self"
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.none.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.bondage.hypno.d = "Self"
                            this.kinkB.bondage.tie.d = "Tentacles, Rope"
                            break
                        case 'joke':
                            this.muse.Name = "Emi Fukukado (Ms. Joke)";
                            this.muse.SD = "25/75";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Riot";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Black Comedy)";
                            this.muse.Desc = "A pro-hero who uses the power of comedy to save people! And beat up dead cows. She flirts and laughs and loves, and never quite shuts up, to the chagrin of many. Has a book of jokes on every topic under the rising sun. ";
                            this.muse.DescSh = "Still wants to meet a hot villainess to happily surrender to, already has a suit, name and theme planned to serve her.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/emi/sample_1cd1eb7dfd1971a8cbe501d4ac3847f6.jpg", name: "" },
                                { pic: "/slideshow/mha/emi/70c9550242736097495219cdb4e141f2.jpeg", name: "" },
                                { pic: "/slideshow/mha/emi/b1cde34e41a43fd3de7b690946e9081c.png", name: "" },
                                { pic: "/slideshow/mha/emi/F4jJu1Va0AA7n_t.jpeg", name: "" },
                                { pic: "/slideshow/mha/emi/MidJoke13.jpg", name: "" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Devil"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.material.d = "Latex, Spandex, Nylon"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkB.transform.goth.d = "Self"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Inside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles, Rope"
                            break
                        case 'kai':
                            this.muse.Name = "Kaina Tsutsumi (Lady Nagant)";
                            this.muse.SD = "100/0";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Focused";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Pre-break Nagant";
                            this.muse.Desc = "A former hero turned assassin for the Hero Association, Nagant once wanted to truly help people, but was used as a weapon of subterfuge, until she killed her own boss who led her down that path. Free now, as a villain, she sprawls the streets ready to aim and shoot. ";
                            this.muse.DescSh = "Has an interest in female pro-heroes, and teaching them a tough lesson...however they may need it.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/kaina/bc0b40d3de502b9b5008cd3095258df7.jpeg", name: "" },
                                { pic: "/slideshow/mha/kaina/8d83dd60c9f71fe2c5da87115b3e0e21.jpeg", name: "" },
                                { pic: "/slideshow/mha/kaina/57c76e7ae99979da0866957d011f65a0.png", name: "" },
                                { pic: "/slideshow/mha/kaina/f0dbeeaf05f0b5cfd5954245c99ed30d.jpeg", name: "" },
                                { pic: "/slideshow/mha/kaina/b0965f9d905b2395e0549c68d47bc13b.jpeg", name: "Bunny" },
                                { pic: "/slideshow/mha/kaina/d963259f8c800a3ba15fd37160a40b6d.jpeg", name: "Virgin Killer Sweater" },
                            ];
                            this.kinkA.relation.pet.d = "Partner"
                            this.kinkA.relation.slave.d = "Partner"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Partner"
                            this.kinkA.mindMod.corrupt.d = "Partner"
                            this.kinkA.mindMod.mindBreak.d = "Partner"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.treat.degrade.d = "Partner"
                            this.kinkB.treat.hurt.d = "Partner"
                            this.kinkB.treat.humiliate.d = "Partner"
                            this.kinkB.treat.object.d = "Partner"
                            this.kinkB.consent.dub.d = "Partner"
                            this.kinkB.consent.none.d = "Partner"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Outside"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "Partner"
                            this.kinkB.bondage.world.d = "Partner"
                            this.kinkB.bondage.sense.d = "Partner"
                            this.kinkB.bondage.tie.d = "Rope"
                            break
                        case 'rumi':
                            this.muse.Name = "Rumi Usagiyama (Miruko)";
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked), Bunny";
                            this.muse.Nat = "Determined";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Mad Hare), UA Student";
                            this.muse.Desc = "An incredibly aggressive, lone wolf rabbit-like woman who kicks ass, in every concievable way. She has made her way to the top three through sheer force of..well, force, hiding a care for others under the spite of her quirk's perception. ";
                            this.muse.DescSh = "Her viciousness sometimes goes out of hand, and she will get it out through more fighting..or breeding like her quirksake. Any woman nearby is at risk. But if you manage to beat her, you'll have a very willing horny bunny in your grasp";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/rumi/331b5c920d275f94911f0274c8c1685a.png", name: "" },
                                { pic: "/slideshow/mha/rumi/78b64a6e60771d6e04f5ed0407a1c944.jpeg", name: "" },
                                { pic: "/slideshow/mha/rumi/9f0ba280ddfddd18115704ce6b346fc1.jpeg", name: "Symbiote" },
                                { pic: "/slideshow/mha/rumi/FlG4mrBWYAEDFJ3.png", name: "Gym" },
                                { pic: "/slideshow/mha/rumi/r7olagk82nj81.jpg", name: "UA Uniform" },
                                { pic: "/slideshow/mha/rumi/493e59e27d67918a99bd7a0ad672f2a0.jpeg", name: "Underwear" },
                                { pic: "/slideshow/mha/rumi/89738596_p1.png", name: "Club" },
                            ];
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.assist.d = "Partner"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Mutant"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.clothing.animal.d = "Partner"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.twin.d = "From Her"
                            this.kinkB.treat.praise.d = "Self"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains"
                            break
                        case 'yama':
                            this.muse.Name = "Yu Takeyama (Mt. Lady)";
                            this.muse.SD = "20/80";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Show-Off";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Mistress Summit)";
                            this.muse.Desc = "A recent pro-hero who seems to be everything wrong with them. Vain, lazy, cocky, lustful, spiteful. Despite this, she has a strong heart that will shine in the worst of times. Even if the rest of times she spends bickering and teasing. ";
                            this.muse.DescSh = "Often expresses her attraction to her fellow pro-heroes by mockery, argument and teasing, desperate to push them to snap and do as they will with her. Most of them know this and don't want to give her the satisfaction.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/yu/6c61ccb499304914f544b9c011204eae.jpeg", name: "" },
                                { pic: "/slideshow/mha/yu/575190c2b7a8d768bf3af7aa32ed6039.jpeg", name: "" },
                                { pic: "/slideshow/mha/yu/d71851232adc6e0fb11001fb6fe2a479.png", name: "" },
                                { pic: "/slideshow/mha/yu/02a4488ecbf54308bcacb8b0789c90ef.jpeg", name: "Cow" },
                            ];
                            this.kinkA.relation.cultist.d = "Partner (Worshipped)"
                            this.kinkA.relation.pet.d = "Self"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.assist.d = "Partner"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.monster.d = "Noumu"
                            this.kinkA.partner.animal.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Spandex, Nylon, Living"
                            this.kinkA.bodyMod.breed.d = "Self"
                            this.kinkA.bodyMod.pierce.d = "Self"
                            this.kinkA.bodyMod.brand.d = "Self"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "Self"
                            this.kinkB.transform.bimbo.d = "YES"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.dub.d = "Self"
                            this.kinkB.consent.none.d = "Self"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = ""
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope, Chain, Tentacles"
                            break
                        case 'fumi':
                            this.muse.Name = "Fuyumi Todoroki";
                            this.muse.SD = "30/70";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Homely";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "UA Teacher, UA Student, Librarian, Hero (Snow Angel), Villain (Blizzard)";
                            this.muse.Desc = "A woman who's spent her life trying to keep things together for her family, or her idea of it. She's a preschool teacher, with a weak quirk, and often percieved as weak herself. But it takes great strength to be kind and want better under her circumstances. ";
                            this.muse.DescSh = "Something less than wonderful brews beneath her softness, and if pushed, it will no doubt come out.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/fuyumi/74b93d5f8086a2980432cbdb1a1fc068.png", name: "" },
                                { pic: "/slideshow/mha/fuyumi/d26740d22c8db3e60855a7fb75fb49da.jpeg", name: "" },
                                { pic: "/slideshow/mha/fuyumi/791f6a395977b6d04df854456c16787c.png", name: "" },
                                { pic: "/slideshow/mha/fuyumi/1e174637809e09602585e59dd1793086.jpeg", name: "" },
                                { pic: "/slideshow/mha/fuyumi/1f54aefdf231cde4cf80b11d8bc86540.png", name: "" },
                                { pic: "/slideshow/mha/fuyumi/89683176_p1.png", name: "Club" },
                                { pic: "/slideshow/mha/fuyumi/FyOb4NHWAAAFoFC.jpeg", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter (Partner/Self)"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Nylon"
                            this.kinkA.clothing.uniform.d = "Suit"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkB.transform.goth.d = "Self"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope"
                            break
                        case 'inko':
                            this.muse.Name = "Inko Midoriya";
                            this.muse.NameSh = " (Gadget - Hero)(Vulcan - Villain)"
                            this.muse.SD = "40/60";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Nervous";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Young Mom, UA Student, Hero (Power Pull), Villain (Twist)";
                            this.muse.Desc = "A mother, no longer a lover, at least in her mind. With her son on the dangerous paths of heroism (yet doing well) and a great deal of regret and time left on her own, she listlessly spends her days watching soap operas, and wondering on what could be. ";
                            this.muse.DescSh = "Few have met the steel behind the tears, when it comes to her heart. Perhaps someone out there may yet be for her.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/inko/4035f001bfba537109f40777ac8633c1.png", name: "" },
                                { pic: "/slideshow/mha/inko/F5H7djmXcAAez5F.jpeg", name: "" },
                                { pic: "/slideshow/mha/inko/eaf211f152bbcbcd8c372b0e92a748e9.jpeg", name: "Virgin Killer Sweater" },
                                { pic: "/slideshow/mha/inko/d8553589ce4dbd302c615fd9f1bc23fd.jpeg", name: "Pre-Time Skip" },
                                { pic: "/slideshow/mha/inko/3d62cc8c709d6312077c9898c3e7e8fb.png", name: "Cheerleader" },
                            ];
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.uniform.d = "Secretary"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.goth.d = "Self"
                            this.kinkB.treat.praise.d = "Partner"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Rope"
                            break
                    };
                    break
                case 4:
                    switch (char) {
                        case 'beni':
                            this.muse.Name = "Kobeni Higashiyama";
                            this.muse.SD = "0/100";
                            this.muse.Uni = "Chainsaw Man";
                            this.muse.Spec = "Human";
                            this.muse.SpecSh = " (Makima's Puppy, Power's Cow)";
                            this.muse.Nat = "Wimp";
                            this.muse.Reg = "Japan";
                            this.muse.Desc = "A hot mess and nervous wreck of a girl who's found some level of safety and ease in following the commands of her fellow coworkers and superiors, particularly Makima and Power. ";
                            this.muse.DescSh = "She enjoy being their pet, what bodily additions they've made her get, and wants everyone to drink her milk, and know she's owned. Really really likes it when Power yells at her.";
                            this.muse.SedSh = "Rather than make a contract with a Devil, she found the shard who promised her her worries would be assuaged..so long as she mindlessly followed the words of her betters. When offered, she took both sex work and Devil Hunting, and when found out by Makima and Power, she was made into their pet. The shard is happy with her placement."
                            this.muse.Var = "Default, Cow, Puppy";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/anime/kobeni/sample_98d1bc30ef9137ecb4811771420f786a.jpg", name: "" },
                                { pic: "/slideshow/anime/kobeni/RDT_20230217_1430108780495567735061611.jpg", name: "" },
                                { pic: "/slideshow/anime/kobeni/F6Px10tXoAA39fh.jpeg", name: "" },
                                { pic: "/slideshow/anime/kobeni/f0fca9f1f164d9a8045bb4650d48aa61.png", name: "Cow" },
                                { pic: "/slideshow/anime/kobeni/33e1f0e365fd03a28c4ac306a13c9af4200bd46b.jpg", name: "Puppy" },
                            ];
                            this.kinkA.relation.pet.d = "Self (Dog, Cow)"
                            this.kinkA.relation.slave.d = "Self"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.partner.person.l = "Human, Devil"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "Self (Dog, Cow)"
                            this.kinkA.clothing.uniform.d = "Suit"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "Boobs"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.bimbo.d = "Self"
                            this.kinkB.treat.praise.d = "Partner"
                            this.kinkB.treat.degrade.d = "Self"
                            this.kinkB.treat.hurt.d = "Self"
                            this.kinkB.treat.humiliate.d = "Self"
                            this.kinkB.treat.object.d = "Self"
                            this.kinkB.consent.free.d = "Self"
                            this.kinkB.consent.exhibit.d = "Self"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "Self"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains"
                            break
                        case 'marin':
                            this.muse.Name = "Marin Kitagawa";
                            this.muse.SD = "50/50";
                            this.muse.Uni = "Dress Up Darling";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Passionate";
                            this.muse.Reg = "Japan";
                            this.muse.Desc = "A girl who loves what she loves, and isn't ashamed of it. In this case, it's eroges, and cosplay, and her beloved Shizuku-tan (who she has cosplayed, from an eroge). For all her lack of shame in body and tastes, she gets quite flustered at romantic affairs. ";
                            this.muse.DescSh = "She will shamelessly endorse and enjoy the most degenerate, girl-degrading stuff, having internalized a lot of stuff from her porn.";
                            this.muse.SedSh = "The shard fused to her computer, altering one of her eroges into one with real-life quests and missions, and subconscious hypnosis to ensure she'd want to complete them. Eventually, turned into a true slut, and then told the truth about the game. She found it very cool and hot, so she happily joined the Mirror."
                            this.muse.Var = "Streamer, Prostitute, Succubus, Symbiote, Kuroe Shizuku(-tan!), Rizu-kyun, Prisoner Veronica";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/anime/marin/0.jpg", name: "" },
                                { pic: "/slideshow/anime/marin/student2.jpeg", name: "Student" },
                                { pic: "/slideshow/anime/marin/bikini1.jpeg", name: "Bikini" },
                                { pic: "/slideshow/anime/marin/bunny2.png", name: "Bunny" },
                                { pic: "/slideshow/anime/marin/shiny2.png", name: "Shiny" },
                                { pic: "/slideshow/anime/marin/shizu2.jpeg", name: "Shizuku-tan (Marin)" },
                                { pic: "/slideshow/anime/marin/rizu2.jpeg", name: "Rizu-kyun (Marin)" },
                                { pic: "/slideshow/anime/marin/veronica.png", name: "Veronica (Marin)" },
                                { pic: "/slideshow/anime/marin/symb.png", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mother/Daughter (Partner/Self), Sister"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.group.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.partner.animal.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Nylon, Living"
                            this.kinkA.clothing.uniform.d = "School, Military"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "Ear, Nipples"
                            this.kinkA.bodyMod.brand.d = "Tattoos, Body Writing"
                            this.kinkA.bodyMod.grow.d = "Booooobs"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "YES"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.transform.twin.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.bondage.hypno.d = "YES"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = ""
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Tentacle, Rope, Tape"
                            break
                        case 'lucy':
                            this.muse.Name = "Lucyna Kushinada";
                            this.muse.SD = "90/10";
                            this.muse.Uni = "Cyberpunk";
                            this.muse.Spec = "Human (Enhanced)";
                            this.muse.Nat = "Guile";
                            this.muse.Reg = "Night City, California";
                            this.muse.Desc = "An introverted netrunner who uses her looks for her advantage, as innocent or seductive as is needed to survive. She dreams of one day reaching the Moon and escaping the prison that is the city she lives in. ";
                            this.muse.DescSh = "Sometimes she fantasizes of taking over AND rule from the moon, make the world her bitch, starting with one short, loud girl who she'd love to pick up and break.";
                            this.muse.SedSh = "She used the shard for a makeshift enhancement repair, which gave her visions of the best way to eliminate the scummy 1% and become queen. She quickly took over, and enjoyed herself to the fullest without limitations. The shard offered more worlds, without boundaries."
                            this.muse.Var = "Cyber Mad";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/anime/lucynda/025cdddb58148617a9e0038a548c2ba3.png", name: "" },
                                { pic: "/slideshow/anime/lucynda/6b9b4409e557e6c6167ff50eb5b50feb.png", name: "" },
                                { pic: "/slideshow/anime/lucynda/F24WVvJbYAA520f.jpeg", name: "" },
                                { pic: "/slideshow/anime/lucynda/F52RzoZaYAEK6Fb.jpeg", name: "" },
                                { pic: "/slideshow/anime/lucynda/550de0a6117fa76e06ca72bc8d0eef20.jpeg", name: "" },
                            ];
                            this.kinkA.relation.slave.d = "Partner"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.partner.person.l = "Human, Cyber"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.none.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Leather, Nylon"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "Partner"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "Partner"
                            this.kinkA.mindMod.brainWash.d = "Partner"
                            this.kinkA.mindMod.brainBlank.d = "Partner"
                            this.kinkA.mindMod.brainHive.d = "Partner"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.transform.mecha.d = "YES"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.degrade.d = "Partner"
                            this.kinkB.treat.hurt.d = "Partner"
                            this.kinkB.treat.humiliate.d = "Partner"
                            this.kinkB.treat.object.d = "Partner"
                            this.kinkB.consent.free.d = "YES"
                            this.kinkB.consent.dub.d = "Partner"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.drug.d = "Smoking, Alcohol"
                            this.kinkB.bondage.hypno.d = "Partner"
                            this.kinkB.bondage.hold.d = "Partner"
                            this.kinkB.bondage.world.d = "Partner"
                            this.kinkB.bondage.sense.d = "Partner"
                            this.kinkB.bondage.tie.d = "Partner: Chains, Tentacles"
                            break
                        case 'yor':
                            this.muse.Name = "Yor Forger nee Briar";
                            this.muse.NameSh = " (Thorn Princess)";
                            this.muse.SD = "75/25";
                            this.muse.Uni = "Spy X Family";
                            this.muse.Spec = "Human";
                            this.muse.Nat = "Earnest";
                            this.muse.Reg = "Ostonia";
                            this.muse.Desc = "The greatest assassin and mother, Yor took up killing to provide for her brother, and now her family. She's terrible at lying and cooking, but she gives her all for who she cares for. There are no more secrets between her and her 'fake' husband. ";
                            this.muse.DescSh = "He's okay with her sleeping around, so long as she does it in secret. She finds it thrilling, and has fooled around with her coworkers, his coworkers, Eden parents, and even some survivors of her missions.";
                            this.muse.SedSh = "She got cut with a mirror containing the shard, increasing her boldness and arousal. After fucking enough people, and worried it'd risk their family, the shard promised she could take care of Loid and Anya from the Mirror, while having enough sex to satisfy her."
                            this.muse.Var = "Succubus, Witch (Yorticia), Shinobi";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/anime/yor/FB_IMG_1652684055020.jpg", name: "Thorn Princess" },
                                { pic: "/slideshow/anime/yor/FB_IMG_1653121355186.jpg", name: "Office, Assassin, Home" },
                                { pic: "/slideshow/anime/yor/F7eK1pDXcAAwI6A.jpeg", name: "" },
                                { pic: "/slideshow/anime/yor/0994bfb4e34cf0f7b46add23e713667f.jpeg", name: "Bunnygirl" },
                                { pic: "/slideshow/anime/yor/F2C18a6aMAA2yYU.jpeg", name: "Shinobi 1" },
                                { pic: "/slideshow/anime/yor/FW-JxwyVsAAGfEy.jpeg", name: "Shinobi 2" },
                                { pic: "/slideshow/anime/yor/ed6747df1ed2251b0e3838379b7d3907.jpeg", name: "Yorticia 1" },
                                { pic: "/slideshow/anime/yor/3d2cc3b1be93d57e25e8ef81e59d27bd.png", name: "Yorticia 2" },
                                { pic: "/slideshow/anime/yor/Inktober_2023_Day_15.png", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = ""
                            this.kinkA.relation.pet.d = "Partner"
                            this.kinkA.relation.slave.d = "Partner"
                            this.kinkA.relation.assist.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Mommy/Daughter (Self/Partner)"
                            this.kinkA.partner.person.l = "Human"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Latex, Leather"
                            this.kinkA.clothing.uniform.d = "Suit"
                            this.kinkA.clothing.fashion.d = "YES"
                            this.kinkA.bodyMod.breed.d = "YES"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkB.transform.bimbo.d = "Partner"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.treat.praise.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.stealth.d = "YES"
                            this.kinkB.substance.sweat.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Milk"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.hypno.d = "Partner"
                            this.kinkB.bondage.hold.d = "YES"
                            this.kinkB.bondage.world.d = "Partner"
                            this.kinkB.bondage.sense.d = "YES"
                            this.kinkB.bondage.tie.d = "Chains, Tentacles, Rope"
                            break
                        case 'stock':
                            this.muse.Name = "Stocking Anarchy";
                            this.muse.SD = "75/25";
                            this.muse.Uni = "Panty & Stocking";
                            this.muse.Spec = "Angel";
                            this.muse.SpecSh = " or Demon";
                            this.muse.Nat = "Gloomy";
                            this.muse.Reg = "Japanifornia, Daten City";
                            this.muse.Desc = "A relatively professional ghost-destroying angel, Stocking adores sweets and mocks sex, in defiance of her loose and sweet-hating sister. She perfectly combines gothic and sweet lolita styles, just as well as she is both sweetness and seriousness. ";
                            this.muse.DescSh = "Despite often making fun of Scanty and Kneesocks for their incestual, BDSM-heavy life, she herself is aroused by those things as well. Might have something to do with her apparently being a demon all along.";
                            this.muse.SedSh = "Wearing it as a pendant, she started to hunger for the sweets of others as well, with it prompting her to offer increasingly sexual and degenerate favors in exchange. It got worse when semen started tasting sweet. She accepted to join the mirror for eternal sweetness in her mouth."
                            this.muse.VarSh = "Demon";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/anime/stocking/ac859ef61a1c5ce86a280c94982dabd4.jpeg", name: "" },
                                { pic: "/slideshow/anime/stocking/da36b0a7000a59a5436015286b8137cb.jpg", name: "Bikini" },
                                { pic: "/slideshow/anime/stocking/F0xu8JhaIAoNehs.jpg", name: "" },
                                { pic: "/slideshow/anime/stocking/F6-kxkuW4AAPjBq.jpeg", name: "" },
                                { pic: "/slideshow/anime/stocking/F7nMHnIWQAAYiMB.png", name: "" },
                                { pic: "/slideshow/anime/stocking/f7134750b938e5620f8d2ec4fe69231c.png", name: "Bunnygirl" },
                                { pic: "/slideshow/anime/stocking/Inktober_2023_Day_16.png", name: "Symbiote" },
                            ];
                            this.kinkA.relation.cultist.d = "YES"
                            this.kinkA.relation.pet.d = "YES"
                            this.kinkA.relation.slave.d = "YES"
                            this.kinkA.relation.lover.d = "YES"
                            this.kinkA.relation.family.d = "Sisters"
                            this.kinkA.partner.person.l = "Angel, Ghost, Devil"
                            this.kinkA.partner.person.d = "YES"
                            this.kinkA.partner.machine.d = "YES"
                            this.kinkA.partner.monster.d = "YES"
                            this.kinkA.clothing.animal.d = "YES"
                            this.kinkA.clothing.material.d = "Frills, Leather"
                            this.kinkA.clothing.uniform.d = "YES"
                            this.kinkA.clothing.fashion.d = "Lolita"
                            this.kinkA.bodyMod.pierce.d = "YES"
                            this.kinkA.bodyMod.brand.d = "YES"
                            this.kinkA.bodyMod.grow.d = "YES"
                            this.kinkA.mindMod.corrupt.d = "YES"
                            this.kinkA.mindMod.mindBreak.d = "YES"
                            this.kinkB.transform.goth.d = "Partner"
                            this.kinkB.treat.degrade.d = "YES"
                            this.kinkB.treat.hurt.d = "YES"
                            this.kinkB.treat.humiliate.d = "YES"
                            this.kinkB.treat.object.d = "YES"
                            this.kinkB.consent.dub.d = "YES"
                            this.kinkB.consent.none.d = "YES"
                            this.kinkB.consent.watch.d = "YES"
                            this.kinkB.consent.exhibit.d = "YES"
                            this.kinkB.substance.cum.d = "YES"
                            this.kinkB.substance.piss.d = "YES"
                            this.kinkB.substance.food.d = "Sweets, Milk"
                            this.kinkB.substance.drug.d = "YES"
                            this.kinkB.bondage.world.d = "YES"
                            this.kinkB.bondage.tie.d = "Tentacles, Chains"
                            break
                    };
                    break
            };
            this.museDialog = true;
            this.currentMuseCode = char;
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
                    tempMoveArr = this.ally.muses
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
            this.museProfileOpen(newSect, newCode)
        },
        slideKeyboard(move) {
            switch (move) {
                case 1:
                    if (this.slide - 1 < 0) {
                        this.slide = this.muse.versionsArray.length - 1
                    } else {
                        this.slide--
                    }
                    break
                case 2:
                    if (this.slide + 1 > this.muse.versionsArray.length - 1) {
                        this.slide = 0
                    } else {
                        this.slide++
                    }
                    break
            }
        },
        cleanData() {
            for (let property in this.muse) {
                this.muse[property] = ""
            }
            this.muse.versionsArray = []
            this.slide = 0;
            for (let category in this.kinkA) {
                for (let subkink in this.kinkA[category]) {
                    this.kinkA[category][subkink].d = "";
                }
            }
            for (let category in this.kinkB) {
                for (let subkink in this.kinkB[category]) {
                    this.kinkB[category][subkink].d = "";
                }
            }
            this.kinkA.partner.person.l = ""
            this.kinkA.partner.group.l = "Group"
            this.kinkA.partner.machine.l = "Machine"
            this.kinkA.partner.animal.l = "Animal"
            this.kinkA.partner.monster.l = "Monster"
        },
        placeholderKinkFillText() {
            this.kinkA.relation.cultist.d = ""
            this.kinkA.relation.pet.d = ""
            this.kinkA.relation.slave.d = ""
            this.kinkA.relation.assist.d = ""
            this.kinkA.relation.lover.d = ""
            this.kinkA.relation.family.d = ""
            this.kinkA.partner.person.l = "Human"
            this.kinkA.partner.person.d = "YES"
            this.kinkA.partner.group.d = ""
            this.kinkA.partner.machine.d = ""
            this.kinkA.partner.monster.d = ""
            this.kinkA.partner.animal.d = ""
            this.kinkA.clothing.animal.d = ""
            this.kinkA.clothing.none.d = ""
            this.kinkA.clothing.material.d = ""
            this.kinkA.clothing.uniform.d = ""
            this.kinkA.clothing.fashion.d = ""
            this.kinkA.bodyMod.breed.d = ""
            this.kinkA.bodyMod.pierce.d = ""
            this.kinkA.bodyMod.brand.d = ""
            this.kinkA.bodyMod.grow.d = ""
            this.kinkA.mindMod.corrupt.d = ""
            this.kinkA.mindMod.mindBreak.d = ""
            this.kinkA.mindMod.brainWash.d = ""
            this.kinkA.mindMod.brainBlank.d = ""
            this.kinkA.mindMod.brainHive.d = ""
            this.kinkB.transform.bimbo.d = ""
            this.kinkB.transform.goth.d = ""
            this.kinkB.transform.mecha.d = ""
            this.kinkB.transform.twin.d = ""
            this.kinkB.treat.praise.d = ""
            this.kinkB.treat.degrade.d = ""
            this.kinkB.treat.hurt.d = ""
            this.kinkB.treat.humiliate.d = ""
            this.kinkB.treat.object.d = ""
            this.kinkB.consent.free.d = ""
            this.kinkB.consent.dub.d = ""
            this.kinkB.consent.none.d = ""
            this.kinkB.consent.watch.d = ""
            this.kinkB.consent.exhibit.d = ""
            this.kinkB.consent.stealth.d = ""
            this.kinkB.substance.sweat.d = ""
            this.kinkB.substance.cum.d = ""
            this.kinkB.substance.piss.d = ""
            this.kinkB.substance.food.d = ""
            this.kinkB.substance.drug.d = ""
            this.kinkB.bondage.hypno.d = ""
            this.kinkB.bondage.hold.d = ""
            this.kinkB.bondage.world.d = ""
            this.kinkB.bondage.sense.d = ""
            this.kinkB.bondage.tie.d = ""
        }
    },
})
</script>
<style>
@media screen and (min-width: 730px) {
    .musebutton {
        font-size: 120px;
    }
}

@media screen and (max-width: 730px) {
    .musebutton {
        font-size: 85px;
    }

    .allmusebtn {
        font-size: 60px;
    }

    .button {
        font-size: 12px;
        padding-left: 4px;
        padding-right: 4px;
    }
}

@media screen and (min-width: 643px) {
    .allmusebtn {
        font-size: 72px;
    }
}

@media screen and (max-width: 643px) {
    .allmusebtn {
        font-size: 60px;
    }
}

@media screen and (max-width: 412px) {
    .musebutton {
        font-size: 72px;
    }

    .allmusebtn {
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

.card {
    background: #CF4CC9D9;
    color: white;
    width: 100%;
    max-width: 720px;
}

.kinkitem {
    text-transform: none;
    background: #bc36b5;
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

.button {
    background: white;
    color: black;
}

.button[disabled] {
    background: rgb(187, 187, 187);
    color: rgb(99, 99, 99);
    opacity: 1 !important
}

.q-expansion-item {
    text-transform: uppercase;
}

.q-body--fullscreen-mixin,
.q-body--prevent-scroll {
    position: relative !important;
}
</style>