<script lang="ts">
    export let title:string;
</script>

<section class="header">
	<h1>{title}</h1>
</section>

<style>
    .header {
    height: 40vh;
    min-height: 100px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}
</style>