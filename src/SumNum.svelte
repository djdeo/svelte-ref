<script>
	export let arr = [1,2]
	
	$: sum = arr.reduce((t,n)=>t+n, 0)
</script>

<p>
	{arr.join(' + ')} = {sum}
</p>

