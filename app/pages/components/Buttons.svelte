<script>
	import {result, dataOnScreen} from "../../store.ts"
	import {Expression} from 'hyoka';
	
	let lastInput = null

	const setNumberValue = (input)=> {
		dataOnScreen.update((data)=> data+=input.toString())
	}
	const displayResult = ()=> {
		const inputOnScreen = $dataOnScreen.replaceAll("x", "*")
		const data = new Expression(inputOnScreen).evaluate();
		result.set(data)
	}

	const clearResult = () => {
		dataOnScreen.set("")
		result.set(0)
	}

</script>

<gridLayout row="1" height="100%" rows="*, *, *, *, *" columns="*, *, *, *">
	<button text="AC" row="0" column="0" on:tap={clearResult} backgroundColor="orange"/>
	<button text="()" row="0" column="1" />
	<button text="%" row="0" column="2" />
	<button text="/" row="0" column="3" backgroundColor="orange" on:tap={()=>(setNumberValue("/"))}/>
	<!--  -->
	<button text="7" row="1" column="0" on:tap={()=>(setNumberValue(7))}/>
	<button text="8" row="1" column="1" on:tap={()=>(setNumberValue(8))}/>
	<button text="9" row="1" column="2" on:tap={()=>(setNumberValue(9))}/>
	<button text="x" row="1" column="3" backgroundColor="orange" on:tap={()=>(setNumberValue("x"))}/>
	<!--  -->
	<button text="4" row="2" column="0" on:tap={()=>(setNumberValue(4))}/>
	<button text="5" row="2" column="1" on:tap={()=>(setNumberValue(5))}/>
	<button text="6" row="2" column="2" on:tap={()=>(setNumberValue(6))}/>
	<button text="-" row="2" column="3" backgroundColor="orange" on:tap={()=>(setNumberValue("-"))}/>
	<!--  -->
	<button text="1" row="3" column="0" on:tap={()=>(setNumberValue(1))}/>
	<button text="2" row="3" column="1" on:tap={()=>(setNumberValue(2))}/>
	<button text="3" row="3" column="2" on:tap={()=>(setNumberValue(3))}/>
	<button text="+" row="3" column="3" backgroundColor="orange" on:tap={()=>(setNumberValue("+"))}/>
	<!--  -->
	<button text="+/-" row="4" column="0"/>
	<button text="0" row="4" column="1" on:tap={()=>setNumberValue(0)}/>
	<button text="." row="4" column="2" on:tap={()=>(setNumberValue("."))}/>
	<button text="=" row="4" column="3" backgroundColor="orange" on:tap={displayResult}/>
</gridLayout>

<style>
	button {
		background-color: #343434;
		color: white;
		font-size: 36px;
		height: 75;
		width: 75;
		border-radius: 8;
	}
</style>