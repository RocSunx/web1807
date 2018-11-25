<template>
  <div class="selection-component">
    <div class="selection-show" @click="showDiv">
      {{ dropdownData[nowIndex].title }}
      <div class="arrow"></div>
    </div>
    <div class="selection-list" v-show="showHide">
      <ul>
        <li @click="clickHandler(index)" v-for="(item,index) in dropdownData" :key="index">{{item.title}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
  export default {
    name:"Dropdown",
    data(){
      return{
        nowIndex:0,
        showHide:false
      }
    },
    props:{
      dropdownData:{
        type:Array,
        default:function(){
          return[
            {
              title:"初级班",
              value:1
            },
            {
              title:"中级班",
              value:2
            },
            {
              title:"高级班",
              value:3
            }
          ]
        }
      }
    },
    methods:{
      clickHandler(index){
        this.nowIndex = index;
        this.showHide = false;
      },
      showDiv(event){
        this.showHide = true
      }
    }
  }
</script>

<style scoped>

</style>