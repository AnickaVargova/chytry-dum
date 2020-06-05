<template>
	<div class="svetla">
		<button v-bind:svetla= "svetla"
				v-on:click= "rozsvitVse" 
				class = 'dalsi'>Rozsvítit vše</button>
		<button v-bind:svetla= "svetla"
				v-on:click= "zhasniVse" 
				class = 'dalsi'>Zhasnout vše</button>
		<div class="svetlo"
			v-for= "(svetlo,index) in svetla"
			v-bind:key= "index"
			v-bind:i= "i"
			v-on:click= "prepinac(index)">
					
			<div  class="svetlo-intenzita" v-bind:style="{height:`${svetlo.intenzita*4}px`}">
				</div>
		
			<div class="svetlo-ikona">
				
				<img v-if= "svetlo.intenzita==='10'" src="/images/light-10.svg">
				<img v-else-if= "svetlo.intenzita==='9'" src="/images/light-9.svg">
				<img v-else-if= "svetlo.intenzita==='8'" src="/images/light-8.svg">
				<img v-else-if= "svetlo.intenzita==='7'" src="/images/light-7.svg">
				<img v-else-if= "svetlo.intenzita==='6'" src="/images/light-6.svg">
				<img v-else-if= "svetlo.intenzita==='5'" src="/images/light-5.svg">
				<img v-else-if= "svetlo.intenzita==='4'" src="/images/light-4.svg">
				<img v-else-if= "svetlo.intenzita==='3'" src="/images/light-3.svg">
				<img v-else-if= "svetlo.intenzita==='2'" src="/images/light-2.svg">
				<img v-else-if= "svetlo.intenzita==='1'" src="/images/light-1.svg">
				<img v-else-if= "svetlo.intenzita==='0'" src="/images/light-0.svg">
		
			</div> -->

			<div class="svetlo-nazev">
				
				{{svetlo.nazev}}
			</div>

		</div>

	</div>
</template>

<script>
export default {
	props:['svetla','i'],
	methods:{
		prepinac(index){
			this.$emit('prepnuto', index);
		},

		rozsvitVse(){
			this.$emit('svetloVsude');
	},

		zhasniVse(){
			this.$emit('tmaVsude');
		}
	}
}
</script>

<style>
.dalsi {
	margin: 10px;
	font-size: 15px;
	padding: 10px;
}

.svetlo-intenzita{
	border-left: 2px solid black;
	margin-left: 10px;
}

</style>