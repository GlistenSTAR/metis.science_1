<footer>
	<Grid stack>
		{#if !$media.sm}
			<Col col={!$media.md ? '3' : '4'}>
				<div class="white_logo">
					<Logo size="5em" color="light" />
					<h1>Metis</h1>
				</div>
				<div class="theme_switch">
					<Switch bind:value={$darkTheme}>Dark theme</Switch>
				</div>
			</Col>
			<Col col={!$media.md ? '3' : '2'}>
				<div class="footer_about">
					<h1>About</h1>
					<li><a href="#metis-team">Team</a></li>
					<li><a href="#">Press Kit</a></li>
					<li><a href="#">Investor Relations</a></li>
				</div>
			</Col>
			<Col col="3">
				<div class="footer_product">
					<h1>Product</h1>
					<li><a href="#metis-features">Why Metis?</a></li>
					<li><a href="#metis-backend">Synchrotrons</a></li>
					<li><a href="https://app.metis.science">Try Metis</a></li>
					<li><a href="https://kit.metis.science">User Interface Kit</a></li>
				</div>
			</Col>
			<Col col="3">
				<div class="footer_legal">
					<h1>Transparency</h1>
					<li><a href="#">Terms</a></li>
					<li><a href="#">Privacy</a></li>
					<li><a href="https://github.com/metis-science/metis.science">This site on GitHub</a></li>
				</div>
			</Col>
		{:else}
			<Col col="8">
				<div class="footer_about">
					<h1>About</h1>
					<li><a href="#metis-team">Team</a></li>
					<li><a href="#">Press Kit</a></li>
					<li><a href="#">Investor Relations</a></li>
				</div>
				<div class="footer_product">
					<h1>Product</h1>
					<li><a href="#metis-features">Why Metis?</a></li>
					<li><a href="#metis-backend">Synchrotrons</a></li>
					<li><a href="https://app.metis.science">Try Metis</a></li>
					<li><a href="https://kit.metis.science">User Interface Kit</a></li>
				</div>
				<div class="footer_legal">
					<h1>Transparency</h1>
					<li><a href="#">Terms</a></li>
					<li><a href="#">Privacy</a></li>
					<li><a href="https://github.com/metis-science/metis.science">This site on GitHub</a></li>
				</div>
			</Col>
			<Col col="4">
				<div class="white_logo">
					<Logo size="3em" color="light" />
					<h1>Metis</h1>
				</div>
				<div class="theme_switch">
					<Switch bind:value={$darkTheme}>Dark theme</Switch>
				</div>
			</Col>
		{/if}
	</Grid>
</footer>

<script lang="ts" context="module">
	import { Col, Grid, Switch } from 'svelte-spectre';
	import { Logo } from '@/components/index';

	import { nodeAttribute } from '@/helpers/dom';

	import { darkTheme } from '@/stores/theme';
	import { media } from '@/stores/media';
</script>

<script lang="ts">
	$: nodeAttribute(document.documentElement, 'color-scheme', $darkTheme ? 'dark' : 'light');
</script>

<style lang="scss">
	footer {
		background: #111;
		padding: 80px 50px 50px;
		.white_logo {
			display: flex;
			align-items: center;
			h1 {
				margin-bottom: 0;
			}
		}
		.theme_switch {
			margin: 120px 0 0 30px;
		}
		li {
			list-style: none;
			font-size: 24px;
			margin-bottom: 20px;
		}
		li a,
		li a:hover {
			color: #fff !important;
		}
	}
	// :global(body),
	// :global(html) {
	// 	height: 100%;
	// 	:global(.spectre) {
	// 		min-height: 100%;
	// 		display: grid !important;
	// 		grid-template-rows: auto 1fr auto;
	// 	}
	// }
	// @media (prefers-color-scheme: dark) {
	// 	footer {
	// 		background-color: #343a51;
	// 	}
	// }
	// :global([color-scheme='dark']) {
	// 	footer {
	// 		background-color: #343a51;
	// 	}
	// }
	// :global([color-scheme='light']) {
	// 	footer {
	// 		background-color: #f1f1fc;
	// 	}
	// }

	@media (max-width: 1024px) {
		footer {
			h1 {
				font-size: 24px;
			}
			li {
				font-size: 16px;
			}
		}
	}
	@media (max-width: 620px) {
		div:nth-child(1) {
			margin-top: 0px;
		}
		div {
			margin-top: 60px;
		}
		footer .theme_switch {
			margin-left: 4px;
			margin-top: 550px;
		}
	}
</style>
