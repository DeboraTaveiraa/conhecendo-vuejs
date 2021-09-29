<template>
	<div id="app">
		<div>
			<button @click="activeComponent = 'Gifs'">Gifs</button>
			<button @click="activeComponent = 'Sobre'">Sobre</button>
		</div>
		<div class="component-container">
			<component :is="activeComponent"/>		
		</div>
	</div>
</template>

<script>
import Gifs from './components/Gifs'
import Sobre from './components/Sobre'

export default {
	components: { Gifs, Sobre },
	data() {
		return {
			activeComponent: 'Sobre'
		}
	}
}
</script>

<style>
	#app {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		height: 100vh;
		font-size: 1.6rem;
	}

	.component-container {
		height: 250px;

	}

	button {
        outline: none;
        padding: 5px 15px 10px;
        margin: 10px 5px;
        border-radius: 3px;
		border: none;
        font-size: 2rem;
        font-weight: 300;
        color: #FFF;
        background: linear-gradient(90deg, rgba(101,190,255,1) 35%, rgba(123,41,255,1) 100%);
    }

	button:hover {
		background: linear-gradient(90deg, rgba(101,190,255,0.8) 35%, rgba(123,41,255,0.8) 100%);
	}
</style>