<template>
	<div class="detail">
		<div class="detail-inner">

			<div class="detail-ikona">
				
				<img v-if= "svetla[i].intenzita==='10'" src="/images/light-10.svg">
				<img v-else-if= "svetla[i].intenzita==='9'" src="/images/light-9.svg">
				<img v-else-if= "svetla[i].intenzita==='8'" src="/images/light-8.svg">
				<img v-else-if= "svetla[i].intenzita==='7'" src="/images/light-7.svg">
				<img v-else-if= "svetla[i].intenzita==='6'" src="/images/light-6.svg">
				<img v-else-if= "svetla[i].intenzita==='5'" src="/images/light-5.svg">
				<img v-else-if= "svetla[i].intenzita==='4'" src="/images/light-4.svg">
				<img v-else-if= "svetla[i].intenzita==='3'" src="/images/light-3.svg">
				<img v-else-if= "svetla[i].intenzita==='2'" src="/images/light-2.svg">
				<img v-else-if= "svetla[i].intenzita==='1'" src="/images/light-1.svg">
				<img v-else-if= "svetla[i].intenzita==='0'" src="/images/light-0.svg">

			</div>

			<h2 class="detail-nazev">
				{{svetla[i].nazev}}
			</h2>

			<div class="detail-buttons">
				
				<button v-on:click = "tlacitkoRozsvit">Zapnuto</button>
				<button v-on:click = "tlacitkoZhasni">Vypnuto</button>
				 				
			</div>
			<div class='intenzita'>
				<label for="intenzita">Intenzita(mezi 0 a 10):</label>
				<input type="number"
				v-model = "svetla[i].intenzita"
				id="intenzita" name="intenzita" min="0" max="10"> 
			</div>
		</div>
	</div>
</template>

<script>
export default {
	props:['svetla','i'],
	methods:{
		tlacitkoRozsvit(){
			this.$emit('rozsviceni', this.i);
		},

		tlacitkoZhasni(){
			this.$emit('zhasnuti', this.i);
		}
	}

}
</script>

<style>
.intenzita {
	margin: 20px;
	font-weight: bold;
}
</style>