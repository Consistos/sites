<script context="module">
	export const prerender = true;
</script>

<script>
	import { Blurb } from '@sveltejs/site-kit';
	import Hero from './_components/Hero.svelte';
	// import Image from './_components/Image.svelte';
</script>

<svelte:head>
	<title>Wexpo • Création de sites web</title>

	<meta name="twitter:title" content="Wexpo" />
	<meta name="twitter:description" content="Création de sites web" />
	<meta name="Description" content="Création de sites web" />
</svelte:head>

<h1 class="visually-hidden">Svelte</h1>

<section>
	<h3>
		<strong>Exposez</strong> vos <strong>Services</strong>, <strong>Créations</strong> ou <strong>Vous</strong> sur le <strong>Web</strong> 
	</h3>

	<h3>
		Wexpo <strong>crée</strong> sur mesure, <strong>héberge</strong> et <strong>maintient</strong> votre <strong>site web</strong>
	</h3>

</section>
<Hero />

	<Blurb>
		<div slot="one">
			<h2>Personalisé</h2>
			<p>
				Personalisation selon ce que vous voulez mettre en avant
			</p>

			<!-- <a sveltekit:prefetch href="/blog/write-less-code" class="cta">learn more</a> -->
		</div>

		<div slot="two">
			<h2>Tout inclus</h2>
			<p>
				Hébergement, nom de domaine, courriel
			</p>
		</div>

		<div slot="three">
			<h2>Abordable</h2>
			<p>
				Tous les fonctionnalités annexes sont a la carte pour un tarif mesuré 
			</p>
		</div>
	</Blurb>


<section>
	<h2 id="Offre">Offre</h2>
	<h2 id="Comparaison">Comparaison</h2>
	<h2 id="Tarifs">Tarifs</h2>
		
	<h3>Base : 50 </h3>
	<h3>Options : </h3>
	<div>
		<input type="checkbox" id="scales" name="scales"
			   checked>
		<label for="scales">Carte interactive</label>
	  </div>
	  <div>
		<input type="checkbox" id="gallerie" name="scales"
			   checked>
		<label for="scales">Gallerie</label>
	  </div>
	  <div>
		<input type="checkbox" id="interactivité" name="horns">
		<label for="horns">Autre interactivité</label>
	  </div>
	  <p>Total : </p>
	
	
</section>

<!-- <Image data={Balls} alt="The Svelte logo in a ball pit" /> -->

<footer>
	<a href="#Offre">Offre</a>
	<a href="#Comparaison">Comparaison</a>
	<a href="#Tarifs">Tarifs</a>
</footer>

<style>
	section {
		position: relative;
		margin-inline: auto;
		margin-block: 10rem;
		padding-inline: var(--side-nav);
		max-inline-size: 120rem;
	}

	.blurb-shifter {
		margin-block-start: calc(-10rem + var(--side-nav));
	}

	footer {
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		padding: 4rem;
	}

	footer a {
		color: var(--text);
		padding-inline: 1rem;
		padding-block: 0.5rem;
		display: block;
	}

	@media (min-width: 900px) {
		.blurb-shifter {
			margin-block-start: -12em;
		}
	}
</style>
