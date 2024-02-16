<script lang="ts">
	import Header from '$lib/Header.svelte';
	import frame from '$lib/assets/images/WindowLight.png';
	import lab from '$lib/assets/images/lab.jpg';
</script>

<Header title="Whale Fall" />

<section>
	<div>
		<img src={frame} alt="Window frame" />
		<img src={lab} alt="FLoating whale hologram" />
	</div>

	<div>
		<p>
			You play as a marine biologist, alone at the bottom of the ocean, monitoring the
			micro-ecosystem that has formed around a dead whale, a phenomenon called Whale Fall. For the
			first time ever, a company has created a one-person submersible that can be used to conduct
			research - and you have bravely volunteered to be the first person to use it. As you observe
			and document the beautifully alien life of the deep sea, you start to think the shadows out of
			the corner of your eyes might be more than just your mounting anxiety from being trapped down
			here.
		</p>

		<p>
			Perhaps it is for the best that we know more about the surface of the moon than we do about
			what lies at the bottom of our ocean. Maybe there is a good reason we are kept from knowing
			the truth.
		</p>
	</div>
</section>
