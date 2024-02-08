<script setup lang="ts">
/**
 * suna hai
 *
 * @link        https://suna-hai.afaan.dev
 *
 * @author      Afaan Bilal
 * @link        https://afaan.dev
 * @link        https://github.com/AfaanBilal/suna-hai
 * @license     MIT
 * @copyright   2024 Afaan Bilal
 */

import { ref } from 'vue';

const sunaHai = [
    ['sunā hai log use aañkh bhar ke dekhte haiñ', 'so us ke shahr meñ kuchh din Thahar ke dekhte haiñ'],
    ['sunā hai rabt hai us ko ḳharāb-hāloñ se', 'so apne aap ko barbād kar ke dekhte haiñ'],
    ['sunā hai dard kī gāhak hai chashm-e-nāz us kī', 'so ham bhī us kī galī se guzar ke dekhte haiñ'],
    ['sunā hai us ko bhī hai sher o shā.irī se shaġhaf', 'so ham bhī mo.ajize apne hunar ke dekhte haiñ'],
    ['sunā hai bole to bātoñ se phuul jhaḌte haiñ', 'ye baat hai to chalo baat kar ke dekhte haiñ'],
    ['sunā hai raat use chāñd taktā rahtā hai', 'sitāre bām-e-falak se utar ke dekhte haiñ'],
    ['sunā hai din ko use titliyāñ satātī haiñ', 'sunā hai raat ko jugnū Thahar ke dekhte haiñ'],
    ['sunā hai hashr haiñ us kī ġhazāl sī āñkheñ', 'sunā hai us ko hiran dasht bhar ke dekhte haiñ'],
    ['sunā hai raat se baḌh kar haiñ kākuleñ us kī', 'sunā hai shaam ko saa.e guzar ke dekhte haiñ'],
    ['sunā hai us kī siyah-chashmagī qayāmat hai', 'so us ko surma-farosh aah bhar ke dekhte haiñ'],
    ['sunā hai us ke laboñ se gulāb jalte haiñ', 'so ham bahār pe ilzām dhar ke dekhte haiñ'],
    ['sunā hai aa.ina timsāl hai jabīñ us kī', 'jo saada dil haiñ use ban-sañvar ke dekhte haiñ'],
    ['sunā hai jab se hamā.il haiñ us kī gardan meñ', 'mizāj aur hī laal o guhar ke dekhte haiñ'],
    ['sunā hai chashm-e-tasavvur se dasht-e-imkāñ meñ', 'palañg zāviye us kī kamar ke dekhte haiñ'],
    ['sunā hai us ke badan kī tarāsh aisī hai', 'ki phuul apnī qabā.eñ katar ke dekhte haiñ'],
    ['vo sarv-qad hai magar be-gul-e-murād nahīñ', 'ki us shajar pe shagūfe samar ke dekhte haiñ'],
    ['bas ik nigāh se luTtā hai qāfila dil kā', 'so rah-ravān-e-tamannā bhī Dar ke dekhte haiñ'],
    ['sunā hai us ke shabistāñ se muttasil hai bahisht', 'makīñ udhar ke bhī jalve idhar ke dekhte haiñ'],
    ['ruke to gardisheñ us kā tavāf kartī haiñ', 'chale to us ko zamāne Thahar ke dekhte haiñ'],
    ['kise nasīb ki be-pairahan use dekhe', 'kabhī kabhī dar o dīvār ghar ke dekhte haiñ'],
    ['kahāniyāñ hī sahī sab mubālġhe hī sahī', 'agar vo ḳhvāb hai tābīr kar ke dekhte haiñ'],
    ['ab us ke shahr meñ Thahreñ ki kuuch kar jaa.eñ', 'farāz aao sitāre safar ke dekhte haiñ'],
];

const index = ref(Math.floor(Math.random() * (sunaHai.length)));
const fullView = ref(false);

</script>

<template>
    <div class="flex flex-col items-center justify-center min-h-full p-2 bg-beige">
        <div class="flex items-center justify-center flex-1">
            <div class="flex flex-col gap-2">
                <div class="flex items-center gap-2 pb-2 mb-4 border-b border-orange-400">
                    <div class="flex-1 text-4xl italic">sunā hai</div>
                    <div v-if="!fullView"
                        class="p-2 px-4 text-xl bg-orange-300 rounded cursor-pointer select-none hover:bg-orange-400 active:bg-orange-500"
                        title="Random" @click="index = Math.floor(Math.random() * (sunaHai.length))">
                        &#10227;
                    </div>
                    <div class="p-2 px-4 text-xl rounded cursor-pointer select-none hover:bg-orange-400 active:bg-orange-500"
                        :class="{ 'bg-orange-400': fullView, 'bg-orange-300': !fullView }" title="View full"
                        @click="fullView = !fullView">
                        {{ fullView ? '&#8613;' : '&#8615;' }}
                    </div>
                </div>

                <div v-if="fullView" class="flex flex-col gap-2">
                    <div v-for="v in sunaHai" class="italic min-w-80">
                        <div>{{ v[0] }}</div>
                        <div>{{ v[1] }}</div>
                    </div>
                </div>

                <div v-if="!fullView" class="flex flex-col gap-2 italic text-md min-w-80">
                    <div>{{ sunaHai[index][0] }}</div>
                    <div>{{ sunaHai[index][1] }}</div>
                </div>

                <div class="my-4 border-b border-orange-400"></div>

                <div class="text-center">Z</div>
            </div>
        </div>

        <div class="flex items-center justify-end gap-2 p-2 text-sm">
            <a href="https://github.com/AfaanBilal/suna-hai" target="_blank" rel="noopener" class="hover:text-blue-500">
                GitHub
            </a>
            &middot;
            <a href="https://afaan.dev" target="_blank" rel="noopener" class="hover:text-blue-500">
                Copyright &copy; Afaan Bilal
            </a>
        </div>
    </div>
</template>
