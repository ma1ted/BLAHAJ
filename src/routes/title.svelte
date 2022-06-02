<section class="container">
	<a href="https://www.ikea.com/gb/en/p/blahaj-soft-toy-shark-30373588/">
		<h1>BLÅHAJ</h1>
	</a>
	<h2>Soft toy, shark, trans icon, 100cm</h2>
	<div id="money">
		<h3>£19</h3>
		<p id="apr">0% APR Interest-free credit from £99, T&Cs apply</p>
	</div>
	<div id="rating">
		<div id="stars">
			{#each Array(5) as _}
				<svg
					xmlns="http://www.w3.org/2000/svg"
					class="h-5 w-5"
					viewBox="0 0 20 20"
					fill="white"
				>
					<path
						d="M9.049 2.927c.3-.921 1.603-.921 1.902 0l1.07 3.292a1 1 0 00.95.69h3.462c.969 0 1.371 1.24.588 1.81l-2.8 2.034a1 1 0 00-.364 1.118l1.07 3.292c.3.921-.755 1.688-1.54 1.118l-2.8-2.034a1 1 0 00-1.175 0l-2.8 2.034c-.784.57-1.838-.197-1.539-1.118l1.07-3.292a1 1 0 00-.364-1.118L2.98 8.72c-.783-.57-.38-1.81.588-1.81h3.461a1 1 0 00.951-.69l1.07-3.292z"
					/>
				</svg>
			{/each}
		</div>
		<p>(2,593)</p>
	</div>
</section>

<style>
	.container {
		display: flex;
		flex-direction: column;
		align-items: center;
		margin: 3rem;
		gap: 1rem;
		text-align: center;
	}
	a {
		text-decoration: none;
	}
	h1 {
		font-size: 4rem;
		font-weight: 700;
	}
	h2 {
		font-weight: 400;
	}
	h3 {
		font-size: 1.5rem;
	}
	#money {
		display: flex;
		flex-direction: column;
		align-items: center;
	}
	#apr {
		font-size: 0.8rem;
	}
	#rating {
		display: flex;
		flex-direction: row;
		gap: 0.5rem;
	}
	#stars {
		display: flex;
		flex-direction: row;
	}
	#stars > svg {
		width: 1rem;
	}
</style>
