<script setup lang="ts">
// FIXME: If this script element does not have lang="ts", there is no FOUC.

const links = [
	{
		label: 'Home',
		path: '/',
	},
	{
		label: 'Foo',
		path: '/foo',
	},
	{
		label: 'Bar',
		path: '/bar',
	},
];
</script>

<template>
	<nav class="app-navbar">
		<ul class="app-navbar__link-list">
			<li v-for="link in links" class="app-navbar__item">
				<nuxt-link :to="link.path" class="app-navbar__link">
					<span class="app-navbar__label">
						{{ link.label }}
					</span>
				</nuxt-link>
			</li>
		</ul>
	</nav>
</template>

<style lang="scss">
.app-navbar {
	font-size: 1.2rem;
	display: flex;
	align-items: center;
	padding: 1rem 2rem;
	border-bottom: 1px solid hsl(214, 47%, 25%);
	background-color: hsl(0 0% 0% / 0.8);

	&__link-list {
		list-style-type: none;
		display: flex;
		justify-content: center;
		align-items: center;
		gap: 2.4em;
		margin: auto;
		max-width: 1000px;
	}

	&__link {
		text-decoration: none;
	}

	&__label {
		font-size: 1em;
		line-height: 1.4;
		color: hsl(214, 47%, 85%);
		white-space: nowrap;
	}
}
</style>
