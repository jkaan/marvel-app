<template>

	<v-progress-linear class="progress-linear-global" color="warning" :indeterminate="true" :active="isActive"></v-progress-linear>

</template>

<script>

	export default {
		name: 'AppLoader',
		data: () => ({
			isActive: false
		}),
		created() {

			this.$bus.$on('loader:toggle', (status) => {
				this.isActive = status;
			});

		}
	};

</script>

<style lang="scss" scoped>

	.progress-linear {

		&.progress-linear-global {
			margin: 0;
			z-index: 100;
			top: 0;
			position: fixed;
		}

	}

</style>
