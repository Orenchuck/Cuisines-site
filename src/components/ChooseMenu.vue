<template>
    <div class="menus-restaurant__head">
    <div class="head__bg">
    <div 
        v-for="(i, idx) in cuisines"
        :key="idx"
        :class="{bg__img_active: i.toShow}"
        :style="i.picture" 
        :data-show="i.toShow"
        class="bg__img">
    </div>
    </div> 
    <div class="head__title">
        <div class="main-container">
        <h1 class="title__h u-heading--h5">
        Choose menu
        </h1>
        </div>
    </div> 
    <div class="head__selector">
        <div class="main-container">
        <div class="selector__one selector__one_active">
            <h2
            v-for="(i, index) in cuisines"
            :key="index"
            @click="handlerClick(index)"
            class="head__selector-title u-heading--h1">
            {{ i.name }}
            </h2>
        </div>
        </div>
    </div>
    </div> 
</template>

<script>
import { reactive } from 'vue'

export default {
  name: 'ChooseMenu',
  setup() {
    const cuisines = reactive ([
        {
            name: 'West',
            picture: "background-image: url('https://www.oblixrestaurant.com/wp-content/uploads/2019/09/menus-1.jpg');",
            toShow: true,
        }, 
        {
            name: 'East ',
            picture: "background-image: url('https://www.oblixrestaurant.com/wp-content/uploads/2019/09/lunch-zeplin-zip.jpg');",
            toShow: false,
        }, 
        {
            name: 'Bar',
            picture: 'background-image: url("https://www.oblixrestaurant.com/wp-content/uploads/2019/09/menus-1.jpg");',
            toShow: false,
        }
        ]);
    const handlerClick = (index) => {
        cuisines.map(i => i['toShow'] = false)
        cuisines[index].toShow = true;
    } 
    return {
        cuisines,
        handlerClick,
    }
},
  props: [],

};
</script>

<style lang="scss" scoped>
    
</style>
