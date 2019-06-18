<script>
	import MyComp from './MyComp.svelte' 
	import SumNum from './SumNum.svelte'
	
	const name = 'svelte';
	const profiles = [
		{name:'John', role: 'web dev'},
		{name:'Gary', role: 'dog keeper'},
		{name:'Brad', role: 'youtuber'},
	]
	
	let count = 0;
	let str = `sth <b>bold</b>`;
	let arr = [1,2,3,4]
	
	// `$:` like the `computed` prop in vuejs
	$: doubled = count * 2
	
	function add() {
		count += 1;
	}
</script>

<h1>Hello {name}! </h1>
<i>you are {@html str}</i>
<hr>
<h2>each loop</h2>
<ul>
	{#each profiles as prof, i}
	<li>guest {i+1}- {prof.name}: {prof.role} </li>
	{/each}
</ul>
<p>
	the number is: {count}
</p>
<p>
	the doubled number is {doubled}
</p>
<button on:click={add}>
	Add
</button>

<hr>
<MyComp answer={count} />
<p>
	The default value is :
</p>
<MyComp />

<hr> <span>the <code>SumNum</code> component</span>
<SumNum {arr}/>
