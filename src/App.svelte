<script>
	let data = []
	let dataCopy = []
	fetch('./deathrow.json')
		.then(res => res.json())
			.then(json => {
				console.log(json)
				data = json
				dataCopy = data
			})
</script>

<main>
	<div class="header">
		<h1>Den sorteste mørkeste hjemmeside</h1>
	</div>
	<div class="prisoners">
		{#each dataCopy as prisoner}
			 <div class="prisoner">
				<h2>{ prisoner["First Name"] } { prisoner["Last Name"] }</h2>
			 </div>			 
		{/each}
	</div>
</main>

<style>
	:global(body){
		background-color: black;
		color:whitesmoke;
	}
	.header{
		border:1px solid white;
		display:grid;
		place-items: center;
	}
	h1{
		font-weight:100;
		text-transform:uppercase;
	}
	.prisoners{
		display:grid;
		grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
		gap:.4rem;
	}
	.prisoner{
		border:1px solid whitesmoke;
		background-color:darkgray;
		color:#eee;
		padding:1rem;
	}
</style>