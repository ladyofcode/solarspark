<script>
	import ProfileCard from '$lib/ProfileCard.svelte';
	import tabs from '$lib/assets/images/team/tabs.jpg';
	import sachi from '$lib/assets/images/team/sachi.jpg';
	import natalie from '$lib/assets/images/team/natalie.jpg';
	import miles from '$lib/assets/images/team/miles.jpg';
	import sparticus from '$lib/assets/images/team/sophie.jpg';

	import Header from '$lib/Header.svelte';
</script>

<Header title="About" />

<section class="container">
	<p>
		Solarpsark is a Canberra-based studio building games and web experiences. We're still in an
		experimental phase, being so new, so be sure to check out our socials and streams as we update
		them.
	</p>

	<p>
		We've been rather inspired by the Solarpunk movement and its associated values. We embrace the
		idea of a sustainable future where tech and nature exist in harmony. This requires innovation
		and perhaps venturing into places where no one would normally - something we intend to do in the
		future.
	</p>
</section>

<section class="container">
	<h2>Team</h2>

	<div id="cards">
		<ProfileCard
			portrait={tabs}
			name="Tabs"
			skills="Dev & design"
			twitch="https://twitch.tv/ladyofcode"
			twitter="https://twitter.com/ladyofcode"
			instagram="https://instagram.com/ladyofcode"
			site="https://ladyofcode.com"
		/>
		<ProfileCard
			portrait={natalie}
			name="Natalie"
			skills="3D & design"
			twitch="https://www.twitch.tv/dotterine_"
			twitter="https://twitter.com/Dotterine"
			instagram="https://www.instagram.com/dotterine"
			artstation="https://dotterine.artstation.com/"
		/>
		<ProfileCard
			portrait={sachi}
			name="Sachi"
			skills="Writing"
			instagram="https://instagram.com/shipperboi_sketches"
			tumblr="https://tumblr.com/shipperboi"
		/>
		<ProfileCard
			portrait={miles}
			name="Miles"
			skills="Dev"
			twitter="https://twitter.com/Zstor2"
		/>
		<ProfileCard
			portrait={sparticus}
			name="Sparticus"
			skills="Art"
			twitter="https://twitter.com/sparticus20001"
			instagram="https://instagram.com/sparticus2000"
		/>
	</div>
</section>

<style>
	#cards {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		flex-wrap: wrap;
	}

	@media (min-width: 600px) {
		#cards {
			flex-direction: row;
		}
	}
</style>
