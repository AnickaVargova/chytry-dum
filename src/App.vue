<template>

  <div id="app">

    <header>
      <h1>Chytrý dům</h1>
    </header>

    <main>
      
      <seznam v-bind:svetla= "svetla"
              v-bind:i= "i"
              v-on:prepnuto= 'prepinac($event)'
              v-on:svetloVsude= 'budizSvetlo'
              v-on:tmaVsude= 'budizTma'>
      </seznam>

      <detail v-bind:svetla= "svetla"
              v-bind:i= "i"
              v-on:rozsviceni = "rozsvit($event)"
              v-on:zhasnuti = "zhasni($event)" >
      </detail>

    </main>

  </div>
</template>

<script>

import Seznam from './components/Seznam.vue'
import Detail from './components/Detail.vue' 

export default {
  components: {
    
    seznam: Seznam,
    detail: Detail
  },

  data: function() {
    return {
      i:0,
      
      svetla: [
        {
          nazev: 'Obývací pokoj',
          intenzita: '0'
        },
        {
          nazev: 'Ložnice',
          intenzita: '0'
        },
        {
          nazev: 'Dětský pokoj',
          intenzita: '0'
        },
        {
          nazev: 'Koupelna',
          intenzita: '0'
        },
        {
          nazev: 'Kuchyně',
          intenzita: '0'
        },
        {
          nazev: 'Chodba',
          intenzita: '0'
        },
        {
          nazev: 'Záchůdek',
          intenzita: '0'
        }
      ]
    }
  },
  methods:{
    prepinac(idx){
           this.i=idx;
    },

    rozsvit(idx){
    this.svetla[this.i].intenzita='10';
    },

    zhasni(idx){
    this.svetla[this.i].intenzita='0';
    },
   
    budizSvetlo(){
     for (let svetlo of this.svetla){
     svetlo.intenzita = '10';
     }
    },

    budizTma(){
     for(let svetlo of this.svetla){
      svetlo.intenzita = '0';
     }
    }
}
}
</script>

<style>

</style>
