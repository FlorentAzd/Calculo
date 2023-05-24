<script>
	import { writable } from 'svelte/store';
	import {result, dataOnScreen} from "../../store.ts"
</script>

<flexboxLayout row="0" height="100%" flexDirection="column" alignItems="flex-end" paddingLeft="10" paddingRight="10">
	<label bind:text={$dataOnScreen} color="white"/>
	<label bind:text={$result} color="#969696" />
</flexboxLayout>

<style>
	label {
		font-size: 48px;
	}
</style>