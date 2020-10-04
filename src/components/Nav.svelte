<script>
	import Atom from "../../static/atom.svg";
	export let segment;
</script>

<div>
	<header>
		<Atom width="50" height="50" />
		<h1>Sapper Demo -- Todo List</h1>
	</header>

	<nav>
		<ul>
			<li>
				<a href="/" class='{ segment === undefined ? 'current' : '' }'>
					Listings
				</a>
			</li>
			<li>
				<a href="about" class='{ segment === 'about' ? 'current' : '' }'>
					About
				</a>
			</li>
		</ul>
	</nav>
</div>


<style>
	div {
		display: flex;
		flex-direction: column;
		padding-top: 1rem;
		text-align: center;
	}

	h1 {
		font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
		font-size: 1.2rem;
		text-transform: uppercase;
	}

	ul {
		border-bottom: 1px solid #dfdfdf;
		border-top: 1px solid #dfdfdf;
		display: flex;
		justify-content: center;
		padding-bottom: 1rem;
		padding-top: 1rem;
	}

	li {
		margin-right: 1rem;
	}

	a {
		text-decoration: none;
	}

	.current {
		text-decoration: underline;
	}
</style>

