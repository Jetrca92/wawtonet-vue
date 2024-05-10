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
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Cena do</option>
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
                                <option>Letnik od</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Letnik do</option>
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
                                <option>Prevoženih km do</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Gorivo</option>
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
import { ref, computed } from 'vue'

const znamkeAvtomobilov = ref(znamke.znamke)
const izbranaZnamka = ref('Vse znamke')
const izbranModel = ref('Model')
const izbranaZnamkaModeli = computed(() => {
    const najdenaZnamka = znamkeAvtomobilov.value.find(brand => brand.ime === izbranaZnamka.value)
    return najdenaZnamka ? najdenaZnamka.modeli : []
})
const resetModel = () => {
    izbranModel.value = 'Model'
}
</script>