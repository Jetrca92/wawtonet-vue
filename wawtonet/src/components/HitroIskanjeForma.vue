<template>
    <form>
        <div class="columns">
            <div class="column">

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select v-model="izbranaZnamka" @change="resetModel">
                                <option>Vse znamke</option>
                                <option v-for="znamka in znamkeAvtomobilov" :value="znamka.ime">{{ znamka.ime }}</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select v-model="izbranModel">
                                <option>Model</option>
                                <option v-for="model in izbranaZnamkaModeli" :value="model">{{ model }}</option>
                            </select>
                        </div>
                    </div>
                </div>

            </div>
            <div class="column">

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Cena od</option>
                                <option v-for="cena in cene" :value="cena">od {{ cena }} EUR</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Cena do</option>
                                <option v-for="cena in cene" :value="cena">do {{ cena }} EUR</option>
                            </select>
                        </div>
                    </div>
                </div>

            </div>
            <div class="column">    

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select v-model="izbranLetnikOd" @change="disableLetnikDo">
                                <option>Letnik od</option>
                                <option v-for="letnik in letniki" :value="letnik">od {{ letnik }}</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select v-model="izbranLetnikDo">
                                <option>Letnik do</option>
                                <option v-for="letnik in letnikiDo" :value="letnik">do {{ letnik }}</option>
                            </select>
                        </div>
                    </div>
                </div>
            </div>
            <div class="column">

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select v-model="izbraniKmdo">
                                <option>Prevoženih km do</option>
                                <option v-for="kilometer in kilometri" :value="kilometer">do {{ kilometer }} km</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select v-model="izbranoGorivo">
                                <option>Gorivo</option>
                                <option v-for="gorivo in goriva" :value="gorivo">{{ gorivo }}</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="control">
                    <button class="button is-info is-fullwidth">Iskanje vozil</button>
                </div>
            </div>
        </div>
      
    </form>
</template>

<script setup>
import znamke from '../constants/znamke.json'
import hitroIskanje from '../constants/hitroIskanje.json'
import { ref, computed } from 'vue'

const znamkeAvtomobilov = ref(znamke.znamke)
const cene = ref(hitroIskanje.cena)
const letniki = ref(hitroIskanje.letnik)
const kilometri = ref(hitroIskanje.kilometri)
const goriva = ref(hitroIskanje.gorivo)
const izbranaZnamka = ref('Vse znamke')
const izbranModel = ref('Model')
const izbraniKmdo = ref('Prevoženih km do')
const izbranoGorivo = ref('Gorivo')
const izbranLetnikDo = ref('Letnik do')
const izbranLetnikOd = ref('Letnik od')

const izbranaZnamkaModeli = computed(() => {
    const najdenaZnamka = znamkeAvtomobilov.value.find(brand => brand.ime === izbranaZnamka.value)
    return najdenaZnamka ? najdenaZnamka.modeli : []
})

const resetModel = () => {
    izbranModel.value = 'Model'
}

const letnikiDo = computed(() => {
    if (izbranLetnikOd.value === 'Letnik od') {
        return letniki.value
    }
    const noviLetniki = letniki.value.filter(letnik => letnik >= izbranLetnikOd.value)
    return noviLetniki
})
</script>