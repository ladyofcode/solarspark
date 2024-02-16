<script>
	import frameLight from '$lib/assets/images/DoorFrameLight.png';
	import doorLeftLight from '$lib/assets/images/DoorLLight.png';
	import doorRightLight from '$lib/assets/images/DoorRLight.png';
	import lab from '$lib/assets/images/lab.png';
	import frameWindowLight from '$lib/assets/images/WindowLight.png';
	import whale from '$lib/assets/images/whaleFallSmall.jpg';

	import { gsap } from 'gsap';
	import { onMount } from 'svelte';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';

	onMount(() => {
		gsap.registerPlugin(ScrollTrigger);
		const tl = gsap.timeline();
		tl.to('#doorLeft', { x: -window.innerWidth * 0.5, duration: 2 })
			.to('#doorRight', { x: window.innerWidth * 0.5, duration: 2 }, 0)
			.to('#doorLeft', { x: 0, duration: 4 }, 4)
			.to('#doorRight', { x: 0, duration: 4 }, 4);

		ScrollTrigger.create({
			trigger: '#frame',
			start: 'top 50%',
			end: 'bottom 20%',
			scrub: 0.4,
			animation: tl,
			toggleActions: 'play none none reverse'
		});
	});
</script>

<svelte:head>
	<script src="https://player.twitch.tv/js/embed/v1.js"></script>
	<script type="text/javascript">
		let tabsOptions = {
			width: '100%',
			height: '100%',
			channel: '531832509'
		};

		let natalieOptions = {
			width: '100%',
			height: '100%',
			channel: '157278397'
		};

		window.onload = function () {
			let tabsPlayer = new Twitch.Player('tabsPlayer', tabsOptions);
			let nataliePlayer = new Twitch.Player('nataliePlayer', natalieOptions);
			tabsPlayer.setVolume(0.5);
			nataliePlayer.setVolume(0.5);
		};
	</script>
</svelte:head>

<section id="header">
	<div class="container">
		<div class="box">
			<h1>Solarspark</h1>
		</div>
	</div>
</section>

<section>
	<div class="container">
		<div class="portal">
			<div>
				<img id="doorLeft" class="doors" src={doorLeftLight} alt="" />
				<img id="doorRight" class="doors" src={doorRightLight} alt="" />
			</div>
			<img id="frame" src={frameLight} alt="" />
			<img id="lab" src={lab} alt="" />
		</div>
	</div>

	<div class="container" id="about">
		<p>Solarspark is an independent studio building video games and web experiences.</p>

		<p>We're building our first video game together - mostly on Twitch for now.</p>

		<p>All are welcome to join in the fun!</p>
	</div>
</section>

<section class="midsection">
	<div class="divider"></div>
	<div id="whalefall" class="container two-columns">
		<div id="whalefall-images">
			<img id="whale" src={whale} alt="" />
			<img id="frameWindow" src={frameWindowLight} alt="" />
		</div>
		<div class="box">
			<h2>Whale Fall</h2>
			<p>
				You play as a marine biologist monitoring the micro-ecosystem that has formed around a dead
				whale, a phenomenon called Whale Fall. As you observe and document the beautifully alien
				life of the deep sea, you start to think the shadows out of the corner of your eyes might be
				more than just your mounting anxiety from being trapped down here.
			</p>
		</div>
	</div>
</section>

<section class="midsection">
	<div class="divider"></div>
	<div class="container">
		<h2>Join in the antics</h2>

		<div class="card box two-columns">
			<div id="tabsPlayer"></div>
			<div>
				<h3>
					Dev, design: Tabs <br />
					<a href="https://twitch.tv/ladyofcode">@ladyofcode</a>
				</h3>
				<p>Unreal Engine, Blender, Figma, Svelte, JavaScript</p>
			</div>
		</div>

		<div class="card box two-columns">
			<div id="nataliePlayer"></div>
			<div>
				<h3>
					3D, 2D: Natalie <br />
					<a href="https://twitch.tv/dotterine_">@dotterine_</a>
				</h3>
				<p>Blender</p>
			</div>
		</div>
	</div>
</section>

<style>
	#header div {
		max-width: 800px;
		text-align: center;
		margin: 0 auto;
		margin-top: 16vh;
		padding: 1.6rem;
	}

	h1 {
		font-size: 2.4rem;
		color: var(--text-headings-color);
	}

	#about p {
		font-size: 2rem;
		line-height: 2.4rem;
		text-align: center;
		font-weight: 400;
	}

	.portal {
		max-width: 1200px;
		position: relative;
		overflow: hidden;
		max-width: 1200px;
	}

	.portal > div {
		position: absolute;
		top: 5%;
		left: 6%;
		width: 90%;
		height: 90%;
		margin: 0 auto;
		border-radius: 50%;
		overflow: hidden;
	}

	#lab {
		height: 100%;
		width: 100%;
		object-fit: cover;
	}

	#whalefall > div:last-child {
		padding: 2.4rem;
	}

	#whalefall-images {
		position: relative;
	}

	#whalefall-images > img:first-child {
		border-radius: 50%;
		padding: 12%;
	}

	#frame,
	.doors,
	#frameWindow {
		position: absolute;
		top: 0;
		filter: var(--image-frame-filter);
		transition: filter var(--transition-time);
	}

	#doorLeft {
		left: 0;
	}

	#doorRight {
		right: 0;
	}

	.card {
		width: 100%;
		padding: 2.4rem;
		margin-top: 1.6rem;
	}

	.card > div:first-of-type {
		width: 100%;
	}

	.card a{
		color: var(--text-headings-color);
	}

	.card a:hover {
		font-weight: bolder;
	}

	@media (min-width: 800px) {
		h1 {
			font-size: 6rem;
		}

		#header div {
			margin-top: 16vh;
			padding: 3.6rem;
		}

		.portal {
			margin: 2.4rem;
		}

		.card > div:first-of-type {
			max-width: 400px;
			margin-right: 2.4rem;
		}
	}
</style>
