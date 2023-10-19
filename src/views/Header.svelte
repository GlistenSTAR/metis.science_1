<header class="p-1">
	<Navbar>
		<div slot="left" class="brand">
			<Logo size={!$media.sm ? '5em' : '3em'} />
			<span>Metis</span>
		</div>
		<!-- svelte-ignore a11y-click-events-have-key-events -->
		<div slot="right" class="menu_holder" on:click={ToggleMenu}>
			<div class="menu_item">
				{#if !is_open}
					<div class="burger" />
				{:else}
					<div class="cross" />
				{/if}
				<span>Menu</span>
			</div>
			{#if is_open}
				<div class="opened_menu">
					<li><a href="#metis-features">Why Metis?</a></li>
					<li><a href="#metis-backend">Synchrotrons</a></li>
					<li><a href="#metis-scientific">Simulations</a></li>
					<li><a href="https://app.metis.science">Try Metis</a></li>
				</div>
			{/if}
		</div>
	</Navbar>
</header>

<script lang="ts" context="module">
	import { Navbar } from 'svelte-spectre';
	import { Logo } from '@/components/index';
	import { media } from '@/stores/media';
</script>

<script lang="ts">
	let is_open = false;

	const ToggleMenu = () => {
		is_open = !is_open;
	};
</script>

<style lang="scss">
	header {
		position: absolute !important;
		width: 100%;
	}
	.brand {
		display: flex;
		align-items: center;
		margin-top: 36px;
		margin-left: 50px;
		h1 {
			margin-bottom: 0px;
		}
	}
	span {
		font-size: 48px;
		@media (max-width: 1024px) {
			font-size: 28px;
		}
	}
	.menu_holder {
		margin-right: 40px;
		margin-top: 36px;
		z-index: 9999;
		cursor: pointer;
		color: white;
		user-select: none;
	}
	.menu_item {
		display: flex;
		align-items: center;
	}
	.burger,
	.cross {
		width: 48px;
		height: 18px;
		margin-right: 18px;
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		cursor: pointer;
	}
	.burger:after,
	.burger:before,
	.cross::after,
	.cross::before {
		content: '';
		background: white;
		display: block;
		width: 100%;
		height: 3px;
		transition: transform 0.3s ease-in-out;
	}
	.cross::before {
		transform: translateY(7px) rotate(-148deg);
	}
	.cross::after {
		transform: translateY(-7px) rotate(148deg);
	}
	.opened_menu {
		position: absolute;
		width: 320px;
		right: 40px;
		margin-top: 10px;
		padding: 10px;
		li {
			list-style: none;
			margin-bottom: 10px;
			font-size: 36px;
			text-align: right;
			@media (max-width: 1024px) {
				font-size: 28px;
			}
			@media (max-width: 724px) {
				font-size: 24px;
				margin-bottom: 18px;
			}
		}
		li a {
			color: #ff0;
		}
	}

	@media (max-width: 620px) {
		header {
			position: fixed !important;
			width: 100%;
			z-index: 9999999;
			background-color: #fff;
			height: 52px;
		}
		.brand {
			display: flex;
			align-items: center;
			margin-top: 8px;
			margin-left: 15px;
			color: $dark-color;
		}
		span {
			font-size: 22px;
		}
		.menu_holder {
			margin-right: 17px;
			margin-top: 11px;
			color: $primary-color;
		}
		.opened_menu {
			background-color: #fff;
			margin-top: 8px;
			height: 485px;
			right: 0px;
			padding-right: 40px;
		}
		li a {
			color: $primary-color !important;
		}
		.burger,
		.cross {
			width: 30px;
			height: 12px;
		}
		.burger:after,
		.burger:before,
		.cross::after,
		.cross::before {
			background: $primary-color;
			height: 2px;
		}
	}
	@media (max-width: 425px) {
		.opened_menu {
			height: 330px;
			width: 240px;
			li {
				font-size: 18px;
			}
		}
	}
</style>
