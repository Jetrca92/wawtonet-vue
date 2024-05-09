<template>
    <form>
        <div class="columns">
            <div class="column">

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Vse znamke</option>
                                <option v-for="znamka in znamke">{{ znamka }}</option>
                            </select>
                        </div>
                    </div>
                </div>

                <div class="field">
                    <div class="control">
                        <div class="select is-fullwidth">
                            <select>
                                <option>Model</option>
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
            </div>
        </div>
      
    </form>
</template>

<script setup>

</script>