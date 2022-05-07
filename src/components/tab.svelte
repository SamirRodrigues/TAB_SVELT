<div  class="boxPane">
	<div class="tabPane">
		<div class="centralize">
			{#each tab as tabButton, index (tabButton)}
			<Buttons
				buttonText={tabButton.buttonText}
				selection={currentButton}
				index={index}
				on:selection={e => onSelection(e.detail)}
			/>
			{/each}
		</div>
		<h2 class="centralize">{currentButton >= 0 ? tab[currentButton].description : '' }</h2>
	</div>
</div>


<script lang="ts">
import Buttons from './buttons.svelte'

const tab = [
	{
		description: '1',
		buttonText: 'Tab 1'
	},
	{
		description: '2',
		buttonText: 'Tab 2'
	},
	{
		description: '3',
		buttonText: 'Tab 3'
	},
	{
		description: '4',
		buttonText: 'Tab 4'
	}
]
let currentButton: number


function onSelection(option: number) {
  currentButton = option
}

</script>

<style>
	.boxPane {
		display: flex;
		justify-content: center;
		padding-top: 50px;
	}
	.tabPane {
		padding: 20px;
		margin: 10px 0;
		width: 300px;
		border-radius: 10px;
		border: 1px solid #aaa;
		background-color: #f0f0f0;
	}
	.centralize {
		display: flex;
		justify-content: center;
	}
</style>