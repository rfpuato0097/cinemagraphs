<template>
	<div id="main">
		<svg id="settings_icon" v-on:click="displaySettings = !displaySettings" xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-settings" width="48" height="48" viewBox="0 0 24 24" stroke-width="1.5" stroke="#000000" fill="none" stroke-linecap="round" stroke-linejoin="round">
			<path stroke="none" d="M0 0h24v24H0z"/>
			<path d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 0 0 2.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 0 0 1.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 0 0 -1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 0 0 -2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 0 0 -2.573 -1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 0 0 -1.065 -2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 0 0 1.066 -2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
			<circle cx="12" cy="12" r="3" />
		</svg>

		<div id="settings_background" class="settings" v-if="displaySettings" v-on:click="displaySettings = !displaySettings"></div>

		<div id="settings_menu" class="settings" v-if="displaySettings">
			<h1>Cinemagraph Window</h1>

			<span>Cinemagraphs: </span>
			<select v-model="selected">
				<option v-for="cinemagraph in cinemagraphs" v-bind:key="cinemagraph">
					{{ cinemagraph }}
				</option>
			</select>
			<br>

			<p>Github</p>
			
		</div>

		<div>
			<video id="displayed" autoplay muted loop :src="videoSource"></video>
			<video id="blurred" autoplay muted loop :src="videoSource"></video>
		</div>

	</div>
</template>

<script>
export default {
	name: "Cinemagraphs",
	data: function(){
		return{
			displaySettings: false,
			selected: 'MorningDog.mp4',
			cinemagraphs: [
				'Arcade.webm',
				'AutumnNeighborHood.gif',
				'BabyYoda.gif',
				'CatTailspin.gif',
				'CatWaves.mp4',
				'ComfyDog.mp4',
				'CowboyBebobReloadingMag.mp4',
				'CreepyNight.mp4',
				'Fog.gif',
				'Guiness.gif',
				'HotRamen.mp4',
				'InsideTrain.mp4',
				'JapaneseGarden.gif',
				'MorningDog.mp4',
				'Neighborhood.gif',
				'OsakaNightTrain.webm',
				'SomberKaleidoscopicBluegill.webm',
				'StormInATeacup.mp4',
				'TeaCreamNoSugar.gif',
				'Trains.mp4',
				'WindowRain.webm'
			],
		}
	},
	computed: {
		videoSource: function(){
			return require('@/assets/Cinemagraphs/' + this.selected);
		}
	},
	mounted: function(){

	}
};
</script>

<style scoped>
#main {
	margin: 0px;
	padding: 0px;
}

#displayed {
	position: fixed;
	top: 0px;
	left: 0px;
	display: block;
	height: 100vh;
	width: 100vw;
	z-index: 99;
}

#blurred {
	position: fixed;
	top: 0px;
	left: 0px;
	width: 100vw;
	height: 100vh;
	filter: blur(10px);
	transform: scale(1.05);
	object-fit: fill;
}

#settings_icon {
	position: fixed;
	top: 25px;
	left: 25px;
	z-index: 99999;
	background: whitesmoke;
	border-radius: 50%;
	border-color: black;
	border-style: solid;
	opacity: 0.4;
}

#settings_icon:hover {
	opacity: 1;
}

#settings_background {
	position: fixed;
	top: 0px;
	left: 0px;
	background: whitesmoke;
	opacity: 0.7;
	z-index: 999;
	height: 100vh;
	width: 100vw;
	filter: blur(50px);
}

#settings_menu {
	position: fixed;
	background: white;
	z-index: 9999;
	top: 50%;
	left: 50%;
	transform: translate(-50%,-50%);

	padding: 10px;
	border-radius: 5%;
	border-style: solid;
	border-color: black;

}

h1{
	margin: 5px;
}
</style>
