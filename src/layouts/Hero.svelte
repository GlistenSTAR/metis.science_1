<div class="hero_component">
	{#if !$media.sm}
		<Grid stack>
			<Col col="7">
				<div class="hero_content">
					<Hero>
						<h1>Metis &mdash;</h1>
						<!-- h1 class="text-primary">virtual materials lab</h1 -->
						<h1 class="text-primary">synchrotrons as a service</h1>
					</Hero>
				</div>
			</Col>
			<Col col="5">
				<img src="assets/img/hero.webp" alt="img" />
			</Col>
		</Grid>
	{:else}
		<Grid stack>
			<Col col="12">
				<img src="assets/img/hero.webp" alt="img" />
			</Col>
			<Col col="12">
				<div class="hero_content">
					<Hero>
						<h1>Metis is your new</h1>
						<h1 class="text-primary">virtual materials lab</h1>
					</Hero>
				</div>
			</Col>
		</Grid>
	{/if}
</div>

<script lang="ts" context="module">
	import { Hero, Grid, Col } from 'svelte-spectre';
</script>

<script>
	import { media } from '@/stores/media';
</script>

<style lang="scss">
	.hero_component {
		width: 100%;
		height: calc(100vh - 145px);
		display: flex;
		align-items: center;
		margin: 0px;
		padding-left: 50px;
		padding-right: 0px;
		@media (max-width: 1024px) {
			height: 100%;
		}
		position: relative;
	}
	.hero_component .hero_content {
		display: flex;
		height: 100%;
		align-items: center;
		@media (max-width: 1024px) {
			margin-top: 48px;
		}
		@media (max-width: 768px) {
			padding-top: 100px;
			padding-bottom: 100px;
		}
	}
	.hero_component h1 {
		font-size: 112px;
		margin-bottom: 0px;
		@media (max-width: 1844px) {
			font-size: 64px;
		}
		@media (max-width: 1024px) {
			font-size: 48px;
		}
		@media (max-width: 837px) {
			font-size: 38px;
		}
	}
	.hero_component h1.text-primary {
		margin-bottom: 48px;
	}
	.hero_component img {
		width: 100%;
		height: calc(100vh - 145px);
		margin-bottom: 0px;
		@media (max-width: 1024px) {
			height: 100%;
		}
	}

	@media (max-width: 620px) {
		.hero_component {
			width: 100%;
			margin: 0px;
			padding-left: 0px;
			padding-right: 0px;
			display: flex;
			align-items: flex-start;
		}
		.hero_component img {
			height: 480px;
			margin-top: 60px;
		}
		.hero_component .hero_content {
			display: contents;
			height: 100%;
			margin-top: 20px;
			width: 100%;
			justify-content: center;
		}
		.hero_component h1 {
			font-size: 42px;
		}
	}
	@media (max-width: 425px) {
		.hero_component h1 {
			font-size: 30px;
		}
		.hero_component img {
			height: 320px;
			margin-top: 60px;
		}
	}
</style>
