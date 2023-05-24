<script>
	import Screen from "./components/Screen.svelte"
	import Buttons from "./components/Buttons.svelte"
	import { setContext, getContext } from 'svelte';

	/*setContext("result", getContext("result"))*/

</script>
<page actionBarHidden="true" statusBarStyle="dark" androidStatusBarBackground="#151515">
	<gridLayout rows="250, *" columns="*" height="100%" backgroundColor="#151515">
		<Screen />
		<Buttons on:number={(event)=>(alert(event.detail))} on:operand={()=>(alert("Operande"))} />
	</gridLayout>
</page>