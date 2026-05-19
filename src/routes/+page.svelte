<script lang="ts">
	type ColoreTerritorio = {
		nome: string;
		hex: string;
		nota: string;
		terroir: string;
	};

	const carta: ColoreTerritorio[] = [
		{
			nome: 'Calcare al Mattino',
			hex: '#e6e1d8',
			nota: 'Luce fredda sulla collina; finale pulito e minerale.',
			terroir: 'Pendii a giornata corta, suoli bianchi.'
		},
		{
			nome: 'Foglia Tardiva',
			hex: '#4a5c2e',
			nota: 'Verde profondo con richiami erbacei e sentori di bosco.',
			terroir: 'Filari ombreggiati, vento da nord.'
		},
		{
			nome: 'Rosso Filare',
			hex: '#6b2d3c',
			nota: 'Struttura morbida, ricorda cortecce e frutta scura.',
			terroir: 'Terriccio scuro, buona escursione termica.'
		},
		{
			nome: 'Ambra in Cantina',
			hex: '#b8895f',
			nota: 'Calore di legno stagionato e paglia asciutta.',
			terroir: 'Cella interrata, umidità costante.'
		},
		{
			nome: 'Blu Nebbia',
			hex: '#4a5f6e',
			nota: 'Arioso, con chiusura che richiude come la bruma.',
			terroir: 'Valle stretta, nebbie di fine autunno.'
		},
		{
			nome: 'Ocra del Sentiero',
			hex: '#c17f3a',
			nota: 'Sole basso sulla polvere del crinale; persistenza gentile.',
			terroir: 'Creste esposte, marne sabbiosi.'
		},
		{
			nome: 'Grigio Pietra Vecchia',
			hex: '#7d7a73',
			nota: 'Equilibrato, tra fresco e memoria del tempo.',
			terroir: 'Muretti a secco, muschi assenti dal vento.'
		},
		{
			nome: 'Notte tra i Filari',
			hex: '#1a1520',
			nota: 'Intenso, quasi silenzioso; da assaporare senza fretta.',
			terroir: 'Cielo limpido, assenza di luce artificiale.'
		}
	];
</script>

<svelte:head>
	<title>Enoteca del Territorio — carta dei colori</title>
	<meta
		name="description"
		content="Un’enoteca statica e leggera: al posto delle bottiglie, una selezione di colori ispirati al paesaggio locale."
	/>
</svelte:head>

<main class="page">
	<header class="hero">
		<p class="eyebrow">Primosito · territorio in tavola</p>
		<h1>Enoteca del Territorio</h1>
		<p class="lead">
			Qui non serviamo etichette: serviamo <strong>tonalità</strong> nate dalla stessa terra che
			rende memorabili i vini di zona. Una carta veloce, pensata come degustazione visiva dei
			colori del nostro paesaggio.
		</p>
		<a class="cta" href="#carta">Scopri la carta</a>
	</header>

	<section class="band" aria-labelledby="filosofia-title">
		<div class="band-inner">
			<h2 id="filosofia-title">Perché i colori</h2>
			<p>
				Il territorio si racconta anche senza bicchiere: cielo, terra, foglia, pietra e cantina
				sono materia prima della memoria. Abbiamo tradotto quelle sensazioni in una selezione di
				colori curata come una carta dei vini — con note, terroir e carattere.
			</p>
		</div>
	</section>

	<section id="carta" class="carta" aria-labelledby="carta-title">
		<div class="carta-head">
			<h2 id="carta-title">La carta dei colori</h2>
			<p class="carta-sub">Degustazione consigliata: con calma, luce naturale, zero distrazioni.</p>
		</div>

		<ul class="grid">
			{#each carta as voce (voce.hex)}
				<li class="card">
					<div class="swatch" style:--tint={voce.hex} title={voce.hex}></div>
					<div class="meta">
						<h3 class="nome">{voce.nome}</h3>
						<p class="hex" aria-label="Codice colore">{voce.hex}</p>
						<p class="nota">{voce.nota}</p>
						<p class="terroir"><span>Terroir</span> {voce.terroir}</p>
					</div>
				</li>
			{/each}
		</ul>
	</section>

	<section class="visita" aria-labelledby="visita-title">
		<h2 id="visita-title">Vieni a trovarci</h2>
		<p>
			Siamo un sito statico: niente database, niente attese. Solo pagina, colore, territorio. Per
			un’esperienza reale con bottiglie e bicchieri, passa in enoteca — stesso spirito, altro
			medium.
		</p>
		<address class="address">
			Via del Territorio 12<br />
			12050 · Primosito (CN)<br />
			<a href="mailto:ciao@enotecadelterritorio.test">ciao@enotecadelterritorio.test</a>
		</address>
	</section>

	<footer class="foot">
		<p>© {new Date().getFullYear()} Enoteca del Territorio — colori locali, respiro lento.</p>
	</footer>
</main>

<style>
	.page {
		max-width: 72rem;
		margin: 0 auto;
		padding: clamp(1.5rem, 4vw, 3rem);
	}

	.hero {
		padding: clamp(2rem, 6vw, 4rem) 0 clamp(3rem, 8vw, 5rem);
		border-bottom: 1px solid rgba(201, 169, 98, 0.25);
	}

	.eyebrow {
		margin: 0 0 0.75rem;
		font-size: 0.8rem;
		letter-spacing: 0.16em;
		text-transform: uppercase;
		color: #c9a962;
	}

	h1 {
		margin: 0 0 1rem;
		font-size: clamp(2rem, 5vw, 3.25rem);
		font-weight: 600;
		letter-spacing: -0.02em;
		line-height: 1.1;
	}

	.lead {
		margin: 0 0 1.75rem;
		max-width: 40rem;
		font-size: 1.05rem;
		color: #c9c4bc;
	}

	.lead strong {
		color: #f0ebe3;
		font-weight: 600;
	}

	.cta {
		display: inline-block;
		padding: 0.65rem 1.25rem;
		border-radius: 999px;
		border: 1px solid #c9a962;
		color: #f4ecd4;
		font-weight: 600;
		font-size: 0.95rem;
		text-decoration: none;
		transition:
			background 0.2s ease,
			color 0.2s ease;
	}

	.cta:hover {
		background: rgba(201, 169, 98, 0.15);
		color: #fff;
	}

	.band {
		margin: 0 calc(-1 * clamp(1.5rem, 4vw, 3rem));
		padding: clamp(2rem, 5vw, 3rem) clamp(1.5rem, 4vw, 3rem);
		background: linear-gradient(135deg, rgba(201, 169, 98, 0.08), transparent 55%);
	}

	.band-inner {
		max-width: 42rem;
	}

	.band h2,
	.carta-head h2,
	.visita h2 {
		margin: 0 0 0.75rem;
		font-size: 1.35rem;
		font-weight: 600;
	}

	.band p {
		margin: 0;
		color: #c9c4bc;
	}

	.carta {
		padding: clamp(2.5rem, 6vw, 4rem) 0;
	}

	.carta-head {
		margin-bottom: 2rem;
	}

	.carta-sub {
		margin: 0;
		color: #9a958c;
		font-size: 0.95rem;
	}

	.grid {
		list-style: none;
		margin: 0;
		padding: 0;
		display: grid;
		gap: 1.25rem;
		grid-template-columns: repeat(auto-fill, minmax(min(100%, 17rem), 1fr));
	}

	.card {
		display: flex;
		flex-direction: column;
		background: rgba(255, 255, 255, 0.03);
		border: 1px solid rgba(255, 255, 255, 0.06);
		border-radius: 0.75rem;
		overflow: hidden;
		transition:
			border-color 0.2s ease,
			transform 0.2s ease;
	}

	@media (prefers-reduced-motion: no-preference) {
		.card:hover {
			border-color: rgba(201, 169, 98, 0.35);
			transform: translateY(-2px);
		}
	}

	.swatch {
		aspect-ratio: 4 / 3;
		background: var(--tint);
		box-shadow: inset 0 0 0 1px rgba(255, 255, 255, 0.08);
	}

	.meta {
		padding: 1rem 1.1rem 1.15rem;
		flex: 1;
		display: flex;
		flex-direction: column;
		gap: 0.35rem;
	}

	.nome {
		margin: 0;
		font-size: 1.05rem;
		font-weight: 600;
	}

	.hex {
		margin: 0;
		font-family: ui-monospace, 'Cascadia Code', 'Segoe UI Mono', monospace;
		font-size: 0.85rem;
		color: #c9a962;
	}

	.nota {
		margin: 0.25rem 0 0;
		font-size: 0.88rem;
		color: #b8b3aa;
		flex: 1;
	}

	.terroir {
		margin: 0.75rem 0 0;
		font-size: 0.8rem;
		color: #8f8a82;
	}

	.terroir span {
		text-transform: uppercase;
		letter-spacing: 0.08em;
		font-size: 0.72rem;
		color: #c9a962;
		margin-right: 0.35rem;
	}

	.visita {
		padding: 2rem 0 3rem;
		border-top: 1px solid rgba(255, 255, 255, 0.06);
		max-width: 36rem;
	}

	.visita p {
		margin: 0 0 1.25rem;
		color: #c9c4bc;
	}

	.address {
		font-style: normal;
		color: #e8e4df;
		line-height: 1.7;
	}

	.foot {
		padding: 1.5rem 0 2rem;
		border-top: 1px solid rgba(255, 255, 255, 0.06);
		font-size: 0.8rem;
		color: #6f6a63;
	}

	.foot p {
		margin: 0;
	}
</style>
