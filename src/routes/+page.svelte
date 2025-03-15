<script>
	let scores = {
		tennis: 2267,
		baseball: 1408,
		bowling: 1906,
		golf: 1291,
		boxing: 1048
	};
</script>

<head>
	<title>Wii Stats | Jining Liu</title>
</head>

<main class="vstack vcenter hcenter l-gap">
	<div class="hstack vcenter">
		<l3 id="name"><a href="https://jining.dev">Jining</a></l3>
		<l3 id="wii-stats-text">'s Wii Stats</l3>
	</div>

	<div class="scoreboard vstack d-gap">
		<h1 class="headerline">Wii Sports</h1>
		<div class="hstack l-gap">
			<div class="vstack d-gap">
				<h2>Tennis</h2>
				<h2>Baseball</h2>
				<h2>Bowling</h2>
				<h2>Golf</h2>
				<h2>Boxing</h2>
			</div>

			<div class="score-column vstack d-gap">
				<h2>{scores.tennis}</h2>
				<h2>{scores.baseball}</h2>
				<h2>{scores.bowling}</h2>
				<h2>{scores.golf}</h2>
				<h2>{scores.boxing}</h2>
			</div>
		</div>
	</div>

	<div id="footer" class="hstack vcenter">
		<footer>© 2025&nbsp;&nbsp;</footer>
		<div></div>
	</div>
</main>

<style>
	main {
		height: calc(100% - 8% - min(10vw, 2rem));
	}

	#wii-stats-text {
		font-weight: 300;
	}

	#name {
		position: relative;
	}

	#name:hover {
		cursor: pointer;
	}

	#name::before {
		content: '';
		position: absolute;
		z-index: -1;
		width: 0;
		height: 8%;
		bottom: 2%;
		left: 2%;
		background: var(--primary-color);
		transition: all ease-in-out 0.1s;
	}

	#name:hover::before {
		width: 75%;
	}

	#name::after {
		content: '↗';
		opacity: 0;
		font-size: min(5vw, 3rem);
		font-weight: 400;
		position: absolute;
		left: -30%;
		bottom: 50%;
		transform: translate(0, 50%);
		transition: all ease-in-out 0.1s;
	}

	#name:hover::after {
		opacity: 1;
	}

	div.scoreboard {
		padding: 0.8rem 1rem;
		background: var(--bg-color-1);
		box-shadow: 0 0 0.8rem 0.4rem var(--bg-color-2);
		border: solid 0.1rem var(--primary-color);
		border-radius: 0.6rem;

    .headerline {
      position: relative;
      margin-bottom: 0.8rem;
    }

		.headerline::before {
			content: '';
			position: absolute;
			/* z-index: -1; */
			width: 100%;
			height: 0.1rem;
			bottom: -0.6rem;
			left: 0;
			background: var(--primary-color);
		}

		.score-column {
			h2 {
				font-weight: 500;
				text-align: right;
			}
		}
	}

	h1 {
		font-weight: 600;
	}

	h2 {
		font-weight: 300;
	}

	#footer {
		opacity: 0.2;
		position: absolute;
		bottom: 8%;
		transition: all ease-in-out 0.2s;

		div {
			width: min(20vw, 4rem);
			height: min(10vw, 2rem);

			background-size: cover;
			background-image: url('/jl.png');
			@media (prefers-color-scheme: dark) {
				background-image: url('/jl_inverted.png');
			}
		}
	}

	#footer:hover {
		opacity: 1;
	}
</style>
