<script lang="ts">
	export let title: string;
</script>

<section class="header">
	<div class="box">
		<h1>{title}</h1>
	</div>
</section>
<div class="divider"></div>

<style>
	.header {
		margin-top: 80px;
		height: 100%;
		max-height: 40vh;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
	}
	.divider {
		margin-top: auto;
	}

	.box {
		padding: 2.4rem;
	}
</style>
