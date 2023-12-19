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
                        <div class="row flex-center"><q-btn class="button" :disabled="section == 1"
                                @click="section = 1">Rules</q-btn>
                        </div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :disabled="section == 2"
                                @click="section = 2">Lore</q-btn></div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :disabled="section == 3"
                                @click="section = 3">Muses</q-btn></div>
                    </div>
                    <div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :disabled="section == 4"
                                @click="section = 4">Affiliates</q-btn></div>
                    </div>
                    
                    <!--<div class="col-xs-auto q-pa-sm">
                        <div class="row flex-center"><q-btn class="button" :disabled="section == 5"
                                @click="section = 5">Kinks</q-btn></div>
                    </div>-->
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
        <q-card id="cardMuse">
            <q-card-section>
                <div class="row flex-center q-pa-xs">
                    <q-btn-group class="button">
                        <q-btn class="button" @click="museSect = 1" :disabled="museSect == 1" label="Nintendo" />
                        <q-btn class="button" @click="museSect = 2" :disabled="museSect == 2" label="Games" />
                        <q-btn class="button" @click="museSect = 3" :disabled="museSect == 3" label="MHA" />
                        <q-btn class="button" @click="museSect = 4" :disabled="museSect == 4" label="Anime" />
                    </q-btn-group>
                </div>
                <div class="row flex-center q-pa-sm" v-if="museSect == 1">
                    <q-btn v-for="(char, c) in charArray.gamenintendobtn" :name="c" :key="c" square padding="xs" flat
                        @click="museProfileOpen(museSect, char.code)">
                        <q-avatar square class="musebutton">
                            <img :src="char.avatar">
                        </q-avatar>
                    </q-btn>
                </div>
                <div class="row flex-center q-pa-sm" v-if="museSect == 2">
                    <q-btn v-for="(char, c) in charArray.gameotherbtn" :name="c" :key="c" square padding="xs" flat
                        @click="museProfileOpen(museSect, char.code)">
                        <q-avatar square class="musebutton">
                            <img :src="char.avatar">
                        </q-avatar>
                    </q-btn>
                </div>
                <div class="row flex-center q-pa-sm" v-if="museSect == 3">
                    <q-btn v-for="(char, c) in charArray.animemhabtn" :name="c" :key="c" square padding="xs" flat
                        @click="museProfileOpen(museSect, char.code)">
                        <q-avatar square class="musebutton">
                            <img :src="char.avatar">
                        </q-avatar>
                    </q-btn>
                </div>
                <div class="row flex-center q-pa-sm" v-if="museSect == 4">
                    <q-btn v-for="(char, c) in charArray.animeotherbtn" :name="c" :key="c" square padding="xs" flat
                        @click="museProfileOpen(museSect, char.code)">
                        <q-avatar square class="musebutton">
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
                        <q-avatar circle size="60px">
                            <img :src="group.emblem">
                        </q-avatar>
                    </q-btn>
                </div>
                <div class="row text-subtitle2 q-pa-sm justify-center" v-if="ally.title != ''"> {{ ally.title }}</div>
                <div class="row text-body2 q-pa-sm justify-start" v-if="ally.description != ''"> {{ ally.description }}
                </div>
                <div class="row text-body2 q-pa-sm justify-start" v-if="ally.muses != ''"><b>Mirror Muses Involved:&nbsp</b>
                    {{ ally.muses }}
                </div>
            </q-card-section>
        </q-card>
    </div>
    <div class="cardHolder flex-center q-pt-sm" v-if="section == 5">
        <q-card class="card">
            <q-card-section>
                <div class="row text-body2 q-pa-sm justify-start"> A glossary and definition of kinks shared by the members
                    of the Mirror, albeit in diverse intensities </div>
                <div class="row q-pa-sm justify-center">
                    <div class="col-xs-3 col-md-3">
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 1"
                                @click="kinkGlossary(1)">Relation</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 2"
                                @click="kinkGlossary(2)">Partner</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 3"
                                @click="kinkGlossary(3)">Clothing</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 4"
                                @click="kinkGlossary(4)">Body Modification</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 5"
                                @click="kinkGlossary(5)">Mind Modification</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 6"
                                @click="kinkGlossary(6)">Transformation</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 7"
                                @click="kinkGlossary(7)">Treatment</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 8"
                                @click="kinkGlossary(8)">Consent/Visibility</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 9"
                                @click="kinkGlossary(9)">Substances</q-btn>
                        </div>
                        <div class="row flex-center"><q-btn style="width: 150px" class="button" :disabled="kinkCat == 10"
                                @click="kinkGlossary(10)">Bondage</q-btn>
                        </div>
                    </div>
                    <div class="col-xs-9 col-md-9">
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
                        <!--<div class="row justify-center q-pa-xs">
                            <q-btn-group class="button">
                                <q-btn class="button" @click="museDataCheck = 1" :disabled="museDataCheck == 1"
                                    label="Data" />
                                <q-btn class="button" @click="museDataCheck = 2" :disabled="museDataCheck == 2"
                                    label="Kinks" />
                            </q-btn-group>
                        </div>-->
                        <div v-if="museDataCheck == 1">
                            <div class="row text-body2 q-pa-xs justify-start">
                                <div class="col-xs-3 col-sm-2"><b>Name:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.Name }}<span class="secret">{{ muse.NameSh }}</span></div>
                                <div class="col-xs-3 col-sm-2"><b>Species:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.Spec }}<span class="secret">{{ muse.SpecSh }}</span>
                                </div>
                            </div>
                            <div class="row text-body2 q-pa-xs justify-start">
                                <div class="col-xs-3 col-sm-2"><b>Dom/Sub:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.SD }}<span class="secret">{{ muse.SDSh }}</span></div>
                                <div class="col-xs-3 col-sm-2"><b>Nature:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.Nat }}<span class="secret">{{ muse.NatSh }}</span></div>
                            </div>
                            <div class="row text-body2 q-pa-xs justify-start">
                                <div class="col-xs-3 col-sm-2"><b>Universe:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.Uni }}<span class="secret">{{ muse.UniSh }}</span></div>
                                <div class="col-xs-3 col-sm-2"><b>Region:</b></div>
                                <div class="col-xs-9 col-sm-4">{{ muse.Reg }}<span class="secret">{{ muse.RegSh }}</span></div>
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
                                                <q-expansion-item group="kinks" label="Relation" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.relation.cultist != ''">Cultist: {{
                                                                    kink.relation.cultist }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.relation.pet != ''">Pet: {{ kink.relation.pet }}
                                                            </div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.relation.slave != ''">Slave: {{
                                                                    kink.relation.slave }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.relation.assist != ''">Assistant: {{
                                                                    kink.relation.assist }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.relation.lover != ''">Lover</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.relation.family != ''">Family: {{
                                                                    kink.relation.family }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Partner" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.partner.person != ''">{{
                                                                    kink.partner.person }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.partner.group != ''">Group</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.partner.machine != ''">Machine</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.partner.monster != ''">Monster: {{
                                                                    kink.partner.monster }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.partner.animal != ''">Animal: {{
                                                                    kink.partner.animal }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Clothing" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.clothing.none != ''">None: {{
                                                                    kink.clothing.none }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.clothing.animal != ''">Animal: {{
                                                                    kink.clothing.animal }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.clothing.material != ''">Material: {{
                                                                    kink.clothing.material }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.clothing.uniform != ''">Uniform: {{
                                                                    kink.clothing.uniform }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.clothing.fashion != ''">Fashion: {{
                                                                    kink.clothing.fashion }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Body Modification" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.physMod.breeding != ''">Breeding: {{
                                                                    kink.physMod.breeding }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.physMod.piercing != ''">Piercing: {{
                                                                    kink.physMod.piercing }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.physMod.branding != ''">Branding: {{
                                                                    kink.physMod.branding }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.physMod.growth != ''">Growth: {{
                                                                    kink.physMod.growth }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Mind Modification" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.mindMod.corruption != ''">Corruption: {{
                                                                    kink.mindMod.corruption }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.mindMod.mindBreak != ''">Mind Break: {{
                                                                    kink.mindMod.mindBreak }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.mindMod.brainWash != ''">Brainwash: {{
                                                                    kink.mindMod.brainWash }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.mindMod.brainBlank != ''">Blank State: {{
                                                                    kink.mindMod.brainBlank }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.mindMod.brainHive != ''">Hivemind: {{
                                                                    kink.mindMod.brainHive }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                            </div>
                                            <div class="col-xs-6">
                                                <q-expansion-item group="kinks" label="Transformation" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.transform.bimbo != ''">Bimbofication: {{
                                                                    kink.transform.bimbo }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.transform.goth != ''">Gothification: {{
                                                                    kink.transform.goth }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.transform.mecha != ''">Mechanization: {{
                                                                    kink.transform.mecha }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.transform.twin != ''">Twinning: {{
                                                                    kink.transform.twin }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Treatment" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.treat.praise != ''">Praise: {{
                                                                    kink.treat.praise }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.treat.degrade != ''">Degradation: {{
                                                                    kink.treat.degrade }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.treat.hurt != ''">Ryona: {{
                                                                    kink.treat.hurt }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.treat.object != ''">Objectification: {{
                                                                    kink.treat.object }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.treat.humiliate != ''">Humiliation: {{
                                                                    kink.treat.humiliate }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Consent/Visibility" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.consent.free != ''">Free Consent: {{
                                                                    kink.consent.free }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.consent.dub != ''">Dub-Con: {{
                                                                    kink.consent.dub }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.consent.none != ''">Non-Con: {{
                                                                    kink.consent.none }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.visibility.watch != ''">Voyeur: {{
                                                                    kink.visibility.watch }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.visibility.stealth != ''">Stealthing: {{
                                                                    kink.visibility.stealth }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.visibility.exhibit != ''">Exhibitionism: {{
                                                                    kink.visibility.exhibit }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Substances" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.substance.milk != ''">Milk: {{
                                                                    kink.substance.milk }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.substance.sweat != ''">Sweat: {{
                                                                    kink.substance.sweat }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.substance.cum != ''">Semen: {{
                                                                    kink.substance.cum }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.substance.piss != ''">Urine: {{
                                                                    kink.substance.piss }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.substance.food != ''">Food: {{
                                                                    kink.substance.food }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.substance.drug != ''">Drugs: {{
                                                                    kink.substance.drug }}</div>
                                                        </q-card-section>
                                                    </q-card>
                                                </q-expansion-item>
                                                <q-separator />
                                                <q-expansion-item group="kinks" label="Bondage" dense>
                                                    <q-card class="kinkitem">
                                                        <q-card-section>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.bondage.tentacle != ''">Tentacles: {{
                                                                    kink.bondage.tentacle }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.bondage.hypno != ''">Hypnosis: {{
                                                                    kink.bondage.hypno }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.bondage.hold != ''">Grappling: {{
                                                                    kink.bondage.hold }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.bondage.world != ''">Environment: {{
                                                                    kink.bondage.world }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.bondage.sense != ''">Sensory Deprivation: {{
                                                                    kink.bondage.sense }}</div>
                                                            <div class="row text-body2 justify-start"
                                                                v-if="kink.bondage.tie != ''">Bindings: {{
                                                                    kink.bondage.tie }}</div>
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
                                            {{
                                                version.name }}
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
        section: 0,
        kinkCat: 0,
        
        museDataCheck: 1,
        currentMuseCode: "",


        charArray: {
            emptyblank: [],
            gamenintendobtn: [
                { code: "rosa", avatar: "/vue carrd muse icon/nintendo/rosa.jpg", },
                { code: "nem", avatar: "/vue carrd muse icon/nintendo/nemona.png", },
                { code: "marn", avatar: "/vue carrd muse icon/nintendo/marnie.jpg", },
                { code: "ida", avatar: "/vue carrd muse icon/nintendo/irida.jpg", },
                { code: "iris", avatar: "/vue carrd muse icon/nintendo/iris.jpeg", },
                { code: "sam", avatar: "/vue carrd muse icon/nintendo/samus.jpg", },
                { code: "bow", avatar: "/vue carrd muse icon/nintendo/bowsette.jpg", },
                { code: "pich", avatar: "/vue carrd muse icon/nintendo/peach.jpg", },
                { code: "lina", avatar: "/vue carrd muse icon/nintendo/rosalina.jpg", },
                { code: "lin", avatar: "/vue carrd muse icon/nintendo/linkle.jpeg", },
                { code: "pura", avatar: "/vue carrd muse icon/nintendo/purah.jpeg", },
                { code: "edel", avatar: "/vue carrd muse icon/nintendo/edelgard.jpg", },
            ],
            gameotherbtn: [
                { code: "lisa", avatar: "/vue carrd muse icon/genshin/lisa.jpg", },
                { code: "mira", avatar: "/vue carrd muse icon/genshin/mirror.jpeg", },
                //{ code: "lumi", avatar: "/vue carrd muse icon/genshin/lumi.jpeg", },
                //{ code: "saria", avatar: "/vue carrd muse icon/genshin/.jpeg", },
                //{ code: "yelan", avatar: "/vue carrd muse icon/genshin/yelan.jpeg", },
                { code: "luci", avatar: "/vue carrd muse icon/games/lucifer.jpg", },
                { code: "tae", avatar: "/vue carrd muse icon/games/tae.png", },
                { code: "ann", avatar: "/vue carrd muse icon/games/ann.png", },
                { code: "sae", avatar: "/vue carrd muse icon/games/sae1.jpeg", },
                { code: "moni", avatar: "/vue carrd muse icon/games/monika.png", },
                { code: "roty", avatar: "/vue carrd muse icon/games/rotty.png", },
                { code: "shan", avatar: "/vue carrd muse icon/games/shantae.jpeg", },
                { code: "junko", avatar: "/vue carrd muse icon/games/junko.jpg", },
                { code: "nami", avatar: "/vue carrd muse icon/games/chiaki.jpg", },
                { code: "layer", avatar: "/vue carrd muse icon/games/layer.jpeg", },
                { code: "ruler", avatar: "/vue carrd muse icon/fate/ruler.jpeg", },
                { code: "ridem", avatar: "/vue carrd muse icon/fate/riderM.jpg", },
            ],
            animemhabtn: [
                { code: "mei", avatar: "/vue carrd muse icon/mha/mei.jpeg", },
                { code: "tsu", avatar: "/vue carrd muse icon/mha/tsuyu.jpeg", },
                { code: "mina", avatar: "/vue carrd muse icon/mha/mina.jpeg", },
                { code: "momo", avatar: "/vue carrd muse icon/mha/momo.jpeg", },
                { code: "toru", avatar: "/vue carrd muse icon/mha/tooru.jpeg", },
                { code: "kendo", avatar: "/vue carrd muse icon/mha/kendo.jpeg", },
                { code: "camie", avatar: "/vue carrd muse icon/mha/camie.jpeg", },
                { code: "mel", avatar: "/vue carrd muse icon/mha/melissa.jpeg", },
                { code: "joke", avatar: "/vue carrd muse icon/mha/msjoke.jpeg", },
                { code: "kai", avatar: "/vue carrd muse icon/mha/nagant.jpeg", },
                { code: "rumi", avatar: "/vue carrd muse icon/mha/miruko.jpeg", },
                { code: "yama", avatar: "/vue carrd muse icon/mha/mtlady.jpeg", },
                { code: "fumi", avatar: "/vue carrd muse icon/mha/fuyumi.jpeg", },
                { code: "inko", avatar: "/vue carrd muse icon/mha/inko.png", },
            ],
            animeotherbtn: [
                { code: "beni", avatar: "/vue carrd muse icon/anime/kobeni.jpeg", },
                { code: "marin", avatar: "/vue carrd muse icon/anime/marin.jpg", },
                { code: "lucy", avatar: "/vue carrd muse icon/anime/lucynda.png", },
                { code: "yor", avatar: "/vue carrd muse icon/anime/yor.png", },
                { code: "stock", avatar: "/vue carrd muse icon/anime/stock.jpg", },
            ],
        },
        allygroups: [
            { name: 'rocket', emblem: '/groups/hypnorocket.png' },
            { name: 'shy', emblem: '/groups/shy.png' },
            //{ name: 'yiga', emblem: '/groups/' },
            { name: 'mirror', emblem: '/groups/Mirror_Maiden_Icon.png' },
            //{ name: 'phantom', emblem: '/groups/' },
            { name: 'ua', emblem: '/groups/uagirls.png' },
            { name: 'venom', emblem: '/groups/symbiote.png' },
        ],
        ally: {
            title: "",
            description: "",
            muses: "",
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
        kink: {
            relation: {
                cultist: "",
                pet: "",
                slave: "",
                assist: "",
                lover: "",
                family: "",
            },
            partner: {
                person: "",
                group: "",
                machine: "",
                monster: "",
                animal: "",
            },
            clothing: {
                none: "",
                animal: "",
                material: "",
                uniform: "",
                fashion: "",
            },
            physMod: {
                breeding: "",
                piercing: "",
                branding: "",
                growth: "",
            },
            mindMod: {
                corruption: "",
                mindBreak: "",
                brainWash: "",
                brainBlank: "",
                brainHive: "",
            },
            transform: {
                bimbo: "",
                goth: "",
                mecha: "",
                twin: "",
            },
            treat: {
                praise: "",
                degrade: "",
                hurt: "",
                object: "",
                humiliate: "",
            },
            consent: {
                free: "",
                dub: "",
                none: "",
            },
            substance: {
                milk: "",
                sweat: "",
                cum: "",
                piss: "",
                food: "",
                drug: "",
            },
            bondage: {
                tentacle: "",
                hypno: "",
                hold: "",
                world: "",
                sense: "",
                tie: "",
            },
            visibility: {
                watch: "",
                exhibit: "",
                stealth: "",
            },
        },
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
                    this.kinkGloss.catDescription = "Category for the preferred forms of relationship between Muse and third parties with which to indulge in pleasure."
                    this.kinkGloss.catKink1 = "Cultist: Being part of a cult towards third party, share in the delight of worship with third party, or be worshipped."
                    this.kinkGloss.catKink2 = "Pet: Being third party's pet (particular animals mentioned), or having third party as a pet."
                    this.kinkGloss.catKink3 = "Slave: Being subservient under threat and harm to a third party's will entirely, even imprisoned by them, or rather having third party subservient to/imprisoned by her."
                    this.kinkGloss.catKink4 = "Assistant: Being third party's assistant, secretary, henchwoman, etc, or having one."
                    this.kinkGloss.catKink5 = "Lover: Being third party's genuine romantic partner and for that third party to be hers."
                    this.kinkGloss.catKink6 = "Family: Being third party's Mommy or Sister or Daughter, or third party being her Mommy/Sister/Daughter."
                    break
                case 2:
                    this.kinkGloss.catDescription = "Category for the preferred third parties by the Muse to have some pleasure with."
                    this.kinkGloss.catKink1 = "Person: The species of the local humanoid entity/entities that Muse enjoys playing with."
                    this.kinkGloss.catKink2 = "Group: A gang, or a cult, or any more than two people working together towards pleasure."
                    this.kinkGloss.catKink3 = "Machine: Mechanical non-sentient device or devices to toy with, or be toyed by someone else with."
                    this.kinkGloss.catKink4 = "Monster: A being with mostly inhuman anatomy and/or thought, mostly dangerous, usually antagonistic."
                    this.kinkGloss.catKink5 = "Animal: A common inhuman non-speaking entity that can be had as a pet, or be wrecked by as something lesser."
                    break
                case 3:
                    this.kinkGloss.catDescription = "Category for the preferred forms of attire to arouse Muse and others."
                    this.kinkGloss.catKink1 = "None: To go au naturale, or see others forgo their clothing."
                    this.kinkGloss.catKink2 = "Animal: Animal-themed outfits, such as cowkinis, playboy bunnies, etc."
                    this.kinkGloss.catKink3 = "Material: Particular materials that entice and arouse Muse, being worn by her or others, such as latex, fur, mesh, and even living"
                    this.kinkGloss.catKink4 = "Uniform: To don the same outfit (or similar enough) to others in a group experience, such as a school or military uniform"
                    this.kinkGloss.catKink5 = "Fashion: To have a tendency to shop, accessorize, and generally mess around with clothing styles and dresses."
                    break
                case 4:
                    this.kinkGloss.catDescription = "Category for the preferred forms Muse enjoys having hers or others' bodies changed, either for a time or forever"
                    this.kinkGloss.catKink1 = "Breeding: To stuff or be stuffed with cum with the purpose of getting knocked up."
                    this.kinkGloss.catKink2 = "Piercing: Standard obvious, appeal for embedded jewelry, particularly nipple and earrings"
                    this.kinkGloss.catKink3 = "Branding: Artistic marks or writing to denote things about the person, be it tattoos, body writing, or magical emblems"
                    this.kinkGloss.catKink4 = "Growth: The expansion, through flesh or silicone, of bodily assets, including ass and breasts, or general size and such."
                    break
                case 5:
                    this.kinkGloss.catDescription = "Category for the preferred forms Muse enjoys having hers or others' minds changed, either for a time or forever"
                    this.kinkGloss.catKink1 = "Corruption: To fall for vices or temptations, or by fear and hurt, away from their usual behaviour, and enjoy their new way of life"
                    this.kinkGloss.catKink2 = "Mind Break: To iron away all thought and/or personality through force and overwhelming abuse turned to pleasure"
                    this.kinkGloss.catKink3 = "Brainwash: To peacefully wash away all thought, memory and/or self and replacing it with new ones, often with the person unaware of the change"
                    this.kinkGloss.catKink4 = "Blank State: The first step of brainwashing, left at that. Very suggestible, not a lot of content. Can be more technologically oriented, with commands and programming."
                    this.kinkGloss.catKink5 = "Hive Mind: To connect one's mind to others, or assimilate it into a whole."
                    break
                case 6:
                    this.kinkGloss.catDescription = "Category for the preferred forms Muse enjoys having hers or others' personhood altered, body and mind and soul, either for a time or forever"
                    this.kinkGloss.catKink1 = "Bimbofication: Combined with Gyaru fashion, it includes blonde hair, preference for pinks, skimpy clothing, massive tits and ass, sometimes a tan, and a general excess of libido and lack of intelligence (or a need for it)"
                    this.kinkGloss.catKink2 = "Gothification: Black or alternative hair colors and tips (purple, red, blue, green), often wearing leather, latex and mesh, in black and sometimes alternative color accents. Lots of piercing and tattoos common too."
                    this.kinkGloss.catKink3 = "Mechanization/Droneification: Covered in technology, or fused with it, or turned into a machine being, often Blank State'd or in a Hivemind."
                    this.kinkGloss.catKink4 = "Twinning: To look and act exactly as someone else, or as their twin that has always existed."
                    this.kinkGloss.catKink5 = "*Note: You can mix and match these too. Goth Bimbos, Bimbo Drones, Goth Twins, etc."
                    break
                case 7:
                    this.kinkGloss.catDescription = "Category for the ways Muse prefers to be treated, or treat the third parties"
                    this.kinkGloss.catKink1 = "Praise: To be lavished and loved and adored."
                    this.kinkGloss.catKink2 = "Degradation: To be treated as a lesser, pathetic being, who's lucky to get to hear even the words of disdain"
                    this.kinkGloss.catKink3 = "Ryona: Mild physical abuse such as choking, slapping, pinching, even some punching. And it turns you on."
                    this.kinkGloss.catKink4 = "Objectification: Treatment as an item or prop, no more sapient than a lamp or seat."
                    this.kinkGloss.catKink5 = "Humiliation: To use any combination of degradation, ryona and objectification, as well as torture and bondage and such, to openly devalue and mock one."
                    break
                case 8:
                    this.kinkGloss.catDescription = "Category for both how Muse prefers regarding the consent of hers or others' to engage in lewd activity, and how visible the acts shall be"
                    this.kinkGloss.catKink1 = "Free Consent: Available to fuck at every single moment, waking or unconscious, busy or free, doesn't matter."
                    this.kinkGloss.catKink2 = "Dub-Con: To use any sort of body and/or mind modification or substance that makes the judgement of consent questionable"
                    this.kinkGloss.catKink3 = "Non-Con: To fuck or be fucked against one's wishes expressed verbally and openly."
                    this.kinkGloss.catKink4 = "Voyeur: Watching sexual activity happen."
                    this.kinkGloss.catKink5 = "Stealthing: A middle point of private and public, such as gloryholes, or doing it somewhere with little traffic, or behind an obstacle unseen."
                    this.kinkGloss.catKink6 = "Exhibitionism: Let them all see what depravities to be enjoyed."
                    break
                case 9:
                    this.kinkGloss.catDescription = "Category for the fluids and otherwise that the Muse or the third parties enjoy indulging in, sharing, and more"
                    this.kinkGloss.catKink1 = "Milk"
                    this.kinkGloss.catKink2 = "Sweat"
                    this.kinkGloss.catKink3 = "Semen"
                    this.kinkGloss.catKink4 = "Urine"
                    this.kinkGloss.catKink5 = "Food"
                    this.kinkGloss.catKink6 = "Drug: Includes smoking, drinking, and biological drugs in trial without medical check."
                    break
                case 10:
                    this.kinkGloss.catDescription = "Category for the ways in which Muse likes herself or others to be restrained and forced into positions for play"
                    this.kinkGloss.catKink1 = "Tentacles"
                    this.kinkGloss.catKink2 = "Hypnosis"
                    this.kinkGloss.catKink3 = "Grappling"
                    this.kinkGloss.catKink4 = "Environment"
                    this.kinkGloss.catKink5 = "Sensory Deprivation"
                    this.kinkGloss.catKink6 = "Bindings"
                    break
            }
        },
        groupShow(value) {
            switch (value) {
                case 'rocket':
                    this.ally.title = "TEAM HYPNO ROCKET";
                    this.ally.description = "A girls-only offshoot of Team Rocket, focused on acquisition and training of Pokemon trainers, leaders, champions, etc. ";
                    this.ally.muses = "Rosa Whitley (Grunt), Nemona Victoria (Leader), Marnie Mary (Undercover)";
                    break
                case 'shy':
                    this.ally.title = "SHY GAL GROUP";
                    this.ally.description = "A group of girls wearing the same mask, making no noise but for light grunts and moans, watching with glowing lights from the mask's eyes ";
                    this.ally.muses = "Bowsette Koopa, Peach Toadstool, Rosalina Estela, Samus Aran";
                    break
                case 'mirror':
                    this.ally.title = "MIRROR MAIDENS";
                    this.ally.description = "A group of assimilated illusionist women who work out of Teyvat, allied with the Fatui. Their assimilation inspired the Mistress' style. ";
                    this.ally.muses = "Lisa Minci, Lumine";
                    break
                case 'ua':
                    this.ally.title = "UA HEROINE UNIVERSITY";
                    this.ally.description = "A girls-only college ran by Headmistress Midnight to teach all the trades of being a hero...though it often ends with rather horny heroines, and unlocked sapphic tendencies.";
                    this.ally.muses = "Momo Yaoyorozu, Mina Ashido, Tsuyu Asui, Tooru Hagakure, Itsuka Kendo, Mei Hatsume, Melissa Shield, Camie Utsushimi (Students), Rumi Usagiyama, Emi Fukukado, Yu Takeyama, Fuyumi Todoroki, Inko Midoriya (Staff), Kaina Tsutsumi (Guest)";
                    break
                case 'venom':
                    this.ally.title = "VENOM SYMBIOTE";
                    this.ally.description = "A parasite that fuses to bodies, evolved to feed on pleasure and with a little more interest in their host's desires. Thanks to the Mirror Mistress, available in many more worlds. ";
                    this.ally.muses = "Samus Aran, Bowsette Koopa, Rosalina Estela, Purah, Edelgard von Hresvelg, Tsuyu Asui, Rumi Usagiyama, Ann Takamaki, Shantae, Marin Kitagawa, Yor Forger, Stocking Anarchy ";
                    break
            }
        },
        museProfileOpen(area, char) {
            this.cleanData();
            console.log(char)
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
                            this.kink.relation.cultist = "Member (Self)"
                            this.kink.relation.pet = "Dog, Cow, Bun (Self)"
                            this.kink.relation.slave = "Slave (Self)"
                            this.kink.relation.assist = "Assistant (Self)"
                            this.kink.relation.lover = "YES"
                            this.kink.relation.family = "Mommy/Daughter (Other/Self), Sister"
                            this.kink.partner.person = "Human"
                            this.kink.partner.group = "YES"
                            this.kink.partner.monster = "Pokemon"
                            this.kink.partner.animal = "Pokemon"
                            this.kink.clothing.animal = "Pokemon (Dog, Cow, Bun)"
                            this.kink.clothing.material = "Latex, Nylon"
                            this.kink.clothing.uniform = "Evil Team (Rocket, Plasma)"
                            this.kink.clothing.fashion = "YES"
                            this.kink.physMod.breeding = "YES"
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            //this.kink.relation.cultist = "YES"
                            this.kink.relation.pet = "Dog"
                            //this.kink.relation.slave = "YES"
                            this.kink.relation.assist = "YES"
                            this.kink.relation.lover = "YES"
                            //this.kink.relation.family = ""
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                        case 'mira':
                            this.muse.Name = "None";
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Genshin Impact";
                            this.muse.Spec = "Mirror Maiden";
                            this.muse.Nat = "Mirage";
                            this.muse.Reg = "Teyvat";
                            this.muse.SedSh = "Thanks to new recruit 'Lisa', they got in contact to strike a deal. Mirror shards send them girls willingly, and these are conditionally allowed visits to the Mirror Dimension. There is mutual respect between La Signora and the Mistress, and the Mirror Maidens and the Mirror muse community/collection."
                            this.muse.VarSh = "Lisa, Lumine, Yelan, Jean";
                            this.muse.Desc = "Beautiful minions of the Fatui, with a wicked, domineering disposition to others, a compassionate one to their sisters, and a subservient one to their masters. Most of them look alike, though some look a bit different, and familiar. Always looking for new recruits. ";
                            this.muse.DescSh = "Said recruits are always unwilling..at first. The Maidens always get them to understand in the end. And they get to keep their appearances on hold to show or discard if it helps them get more recruits.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/mirror/5efced2f976bca00d362f4cf3c4170ae.jpeg", name: "True" },
                                { pic: "/slideshow/games/mirror/56e8db939619057f5a332b49b078fecb.jpg", name: "w/La Signora" },
                                { pic: "/slideshow/games/mirror/105578655_p3.jpg", name: "Lisa?" },
                                { pic: "/slideshow/games/mirror/71bd3c8fecba812bfdd12f7b121e8a27.png", name: "Lumine?" },
                                { pic: "/slideshow/games/mirror/9ed3afc83ac02265959fc2b0c072abb8.jpg", name: "Yelan? (no mask)" },
                                { pic: "/slideshow/games/mirror/7583993d6e254cd277e19d41ac96e952.jpg", name: "Jean? (no mask)" },
                            ];
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.muse.Desc = "The smartest, kindest, most beautiful girl in school, who's decided you are her soulmate, and is distraught by them focusing on the other members of her Literature Club. She will happily use her dedication to make sure they only look at her. ";
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                        case 'junko':
                            this.muse.Name = "Junko Enoshima";
                            this.muse.SD = "90/10";
                            this.muse.Uni = "Danganronpa";
                            this.muse.Spec = "Human";
                            this.muse.NatSh = "Despairful";
                            this.muse.Reg = "Japan";
                            this.muse.SedSh = ""
                            this.muse.Var = "Succubus";
                            this.muse.Desc = "The ultimate fashionista, but ultimately just a girl who turns despair into pleasure for herself, she wants nothing but to share what she feels with everyone in the world. She's twisted, switches between states of self constantly, and her victory and defeat taste equally good to someone as utterly despairful as herself. There's nothing to hide anymore.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/junko/F5aj5MiWIAA58us.jpeg", name: "Default" },
                                { pic: "/slideshow/games/junko/F3lnjAXbwAE9xc_.jpeg", name: "Bunny" },
                                { pic: "/slideshow/games/junko/108590748_p0.png", name: "Succubus" },
                            ];
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                        case 'nami':
                            this.muse.Name = "Chiaki Nanami";
                            this.muse.SD = "10/90";
                            this.muse.Uni = "Danganronpa";
                            this.muse.Spec = "Human";
                            this.muse.SpecSh = ", then Program";
                            this.muse.Nat = "Soft";
                            this.muse.Reg = "Japan";
                            this.muse.SedSh = ""
                            this.muse.Var = "Mastermind";
                            this.muse.Desc = "The ultimate gamer, all but for dating sims. She's rather soft-spoken, and gentle, to the point of even second-guessing her own statements and ideas. But ultimately she is well-meaning and easy to get along with by everyone. ";
                            this.muse.DescSh = "Recently she's really been getting into lewd games...with all the kinks they teach. Still as bad at them as in dating sims however.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/chiaki/Fzk7OxkWIAMQZ0s.jpeg", name: "Default" },
                                { pic: "/slideshow/games/chiaki/Fzk7OxkXwAEx93B.jpeg", name: "Bunny" },
                            ];
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                        case 'layer':
                            this.muse.Name = "Layer";
                            this.muse.SD = "40/60";
                            this.muse.Uni = "Megaman";
                            this.muse.Spec = "Reploid";
                            this.muse.Nat = "Soft";
                            this.muse.Reg = "Galápagos Islands";
                            this.muse.SedSh = ""
                            this.muse.Var = "Swimsuit, Bridal";
                            this.muse.Desc = "The picture of a professional and capable Navigator Reploid..until romance comes into play. At which point she'll become a flustered, shy disaster. Good thing her bangs cover her eyes...even if her top doesn't cover the bottom of her chest."
                            this.muse.DescSh = "Gaining enough confidence in her romantic situation unlocks her confident mommy side...but it's a slow burn to get there. Before however? She'll let her interest do whatever they want to her."
                            this.muse.versionsArray = [
                                { pic: "/slideshow/games/layer/19052cd52d469549743b2096679d6be4.jpeg", name: "Default" },
                                { pic: "/slideshow/games/layer/Mega_Man_X_DiVE_Hunter_Program_Bridal_Layer.png", name: "Swimsuit" },
                                { pic: "/slideshow/games/layer/Mega_Man_X_DiVE_Hunter_Program_Swimsuit_Layer.png", name: "Bridal" },
                            ]
                            break
                        case 'ruler':
                            this.muse.Name = "Ruler";
                            this.muse.NameSh = ": Artoria Pendragon"
                            this.muse.SD = "90/10";
                            this.muse.Uni = "Type Moon";
                            this.muse.Spec = "Heroic Spirit ";
                            this.muse.SpecSh = " (Heavenly)";
                            this.muse.Nat = "Composed";
                            this.muse.Reg = "???";
                            this.muse.SedSh = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                        case 'ridem':
                            this.muse.Name = "Rider";
                            this.muse.NameSh = ": Medusa"
                            this.muse.SD = "80/20";
                            this.muse.Uni = "Type Moon";
                            this.muse.Spec = "Heroic Spirit";
                            this.muse.Nat = "Standoff-ish";
                            this.muse.Reg = "???";
                            this.muse.SedSh = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                        case 'momo':
                            this.muse.Name = "Momo Yaoyorozu (Creati)";
                            this.muse.SD = "70/30";
                            this.muse.Uni = "Hero Academia";
                            this.muse.Spec = "Human (Quirked)";
                            this.muse.Nat = "Regal";
                            this.muse.Reg = "Japan, Musatafu";
                            this.muse.SedSh = "Acquired through the assistance of Headmistress Midnight of UA Heroine University"
                            this.muse.Var = "Villain (Empress)";
                            this.muse.Desc = "A girl born of wealth with a genuine heart of gold and a mind that holds great knowledge. Despite her dazzling intellect, astonishing quirk, and stunning beauty, her confidence needs some serious work. But she will always stand by the side of her friends. ";
                            this.muse.DescSh = "While her heart is in the right place, enough confidence might unlock the sort of domineering, Midnight-like might that her qualities and raising should have led to.";
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.muse.DescSh = "Her viciousness sometimes goes out of hand, and she will get it out through more fighting..or breeding like her quirksake. Any woman nearby is at risk.";
                            this.muse.versionsArray = [
                                { pic: "/slideshow/mha/rumi/331b5c920d275f94911f0274c8c1685a.png", name: "" },
                                { pic: "/slideshow/mha/rumi/78b64a6e60771d6e04f5ed0407a1c944.jpeg", name: "" },
                                { pic: "/slideshow/mha/rumi/9f0ba280ddfddd18115704ce6b346fc1.jpeg", name: "Symbiote" },
                                { pic: "/slideshow/mha/rumi/FlG4mrBWYAEDFJ3.png", name: "Gym" },
                                { pic: "/slideshow/mha/rumi/r7olagk82nj81.jpg", name: "UA Uniform" },
                                { pic: "/slideshow/mha/rumi/493e59e27d67918a99bd7a0ad672f2a0.jpeg", name: "Underwear" },
                                { pic: "/slideshow/mha/rumi/89738596_p1.png", name: "Club" },
                            ];
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                                { pic: "/slideshow/anime/marin/1.png", name: "" },
                                { pic: "/slideshow/anime/marin/student2.jpeg", name: "Student" },
                                { pic: "/slideshow/anime/marin/bikini1.jpeg", name: "Bikini" },
                                { pic: "/slideshow/anime/marin/futa.jpeg", name: "Bikini (Dick)" },
                                { pic: "/slideshow/anime/marin/bunny2.png", name: "Bunny" },
                                { pic: "/slideshow/anime/marin/shiny2.png", name: "Shiny" },
                                { pic: "/slideshow/anime/marin/shizu2.jpeg", name: "Shizuku-tan (Marin)" },
                                { pic: "/slideshow/anime/marin/rizu2.jpeg", name: "Rizu-kyun (Marin)" },
                                { pic: "/slideshow/anime/marin/veronica.png", name: "Veronica (Marin)" },
                                { pic: "/slideshow/anime/marin/symb.png", name: "Symbiote" },
                            ];
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
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
                            this.kink.partner.person = ""
                            this.kink.partner.group = ""
                            this.kink.partner.machine = ""
                            this.kink.partner.monster = ""
                            this.kink.partner.animal = ""
                            this.kink.clothing.animal = ""
                            this.kink.clothing.none = ""
                            this.kink.clothing.material = ""
                            this.kink.clothing.uniform = ""
                            this.kink.clothing.fashion = ""
                            this.kink.physMod.breeding = ""
                            this.kink.physMod.piercing = ""
                            this.kink.physMod.branding = ""
                            this.kink.physMod.growth = ""
                            this.kink.mindMod.corruption = ""
                            this.kink.mindMod.mindBreak = ""
                            this.kink.mindMod.brainWash = ""
                            this.kink.mindMod.brainBlank = ""
                            this.kink.mindMod.brainHive = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.transform = ""
                            this.kink.treat.praise = ""
                            this.kink.treat.degrade = ""
                            this.kink.treat.hurt = ""
                            this.kink.treat.humiliate = ""
                            this.kink.treat.object = ""
                            this.kink.consent.free = ""
                            this.kink.consent.dub = ""
                            this.kink.consent.none = ""
                            this.kink.visibility.watch = ""
                            this.kink.visibility.exhibit = ""
                            this.kink.visibility.stealth = ""
                            this.kink.substance.milk = ""
                            this.kink.substance.sweat = ""
                            this.kink.substance.cum = ""
                            this.kink.substance.piss = ""
                            this.kink.substance.food = ""
                            this.kink.substance.drug = ""
                            this.kink.bondage.tentacle = ""
                            this.kink.bondage.hypno = ""
                            this.kink.bondage.hold = ""
                            this.kink.bondage.world = ""
                            this.kink.bondage.sense = ""
                            this.kink.bondage.tie = ""
                            break
                    };
                    break
            };
            this.museDialog = true;
            this.currentMuseCode = char;
        },
        museSwitch(move) {
            var arr = [];
            var tempMSect = 0;
            switch (this.museSect) {
                case 1:
                    arr = this.charArray.gamenintendobtn
                    tempMSect = 1
                    break
                case 2:
                    arr = this.charArray.gameotherbtn
                    tempMSect = 2
                    break
                case 3:
                    arr = this.charArray.animemhabtn
                    tempMSect = 3
                    break
                case 4:
                    arr = this.charArray.animeotherbtn
                    tempMSect = 4
                    break
            }
            var newCode = "";
            switch (move) {
                case 1:
                    for (var i = 0; i < arr.length; i++) {
                        if (this.currentMuseCode == arr[i].code) {
                            if (i - 1 < 0) {
                                newCode = arr[arr.length - 1].code
                            } else {
                                newCode = arr[i - 1].code
                            }
                        }
                    }
                    break
                case 2:
                    for (var i = 0; i < arr.length; i++) {
                        if (this.currentMuseCode == arr[i].code) {
                            if (i + 1 > arr.length - 1) {
                                newCode = arr[0].code
                            } else {
                                newCode = arr[i + 1].code
                            }
                        }
                    }
                    break
            }
            this.museProfileOpen(tempMSect, newCode)
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
            var countMuse = 1
            for (let property in this.muse) {
                if (countMuse + 1 > this.muse.length) {
                    this.muse[property] = []
                } else {
                    this.muse[property] = ""
                }
                countMuse++
            }
            this.slide = 0;
            for (let category in this.kink) {
                for (let subkink in this.kink[category]) {
                    this.kink[category][subkink] = "";
                }
            }
        },
    },

})
</script>
<style>
@media screen and (min-width: 610px) {
    .musebutton {
        font-size: 120px;
    }
}

@media screen and (max-width: 610px) {
    .musebutton {
        font-size: 85px;
    }

    .button {
        font-size: 12px;
    }
}

@media screen and (max-width: 412px) {
    .musebutton {
        font-size: 72px;
    }
}

.cardHolder {
    margin-bottom: 12px;
    padding: 0 4%;
    gap: 12px;
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
    background: #bc36b5;
}

.kinklist {
    background: #8a2a85;
    width: 820px;
}

#cardMuse {
    background: #CF4CC9D9;
    color: white;
    max-width: 970px;
    width: fit-content;
}

#muse {
    background: #CF4CC9;
    color: white;
    max-width: 890px;
    width: fit-content;
}

.button {
    background: white;
    color: black;
}

.button[disabled] {
    background: rgb(128, 128, 128);
}

.q-body--fullscreen-mixin,
.q-body--prevent-scroll {
    position: relative !important;
}
</style>