<script>
	import Screen from "./components/Screen.svelte"
	import Buttons from "./components/Buttons.svelte"
</script>
<page actionBarHidden="true" statusBarStyle="dark" androidStatusBarBackground="#151515">
	<gridLayout rows="250, *" columns="*" height="100%" backgroundColor="#151515">
		<Screen />
		<Buttons />
	</gridLayout>
</page>