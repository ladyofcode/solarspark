<script>
	import frameLight from '$lib/assets/images/DoorFrameLight.png';
	import doorLeftLight from '$lib/assets/images/DoorLLight.png';
	import doorRightLight from '$lib/assets/images/DoorRLight.png';
	import lab from '$lib/assets/images/lab.png';

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
			start: 'top 40%',
			end: 'bottom 50%',
			markers: true,
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
			width: 400,
			height: 300,
			channel: '531832509'
		};

		let natalieOptions = {
			width: 400,
			height: 300,
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

<section class="header">
	<h1>Solarspark</h1>
	<p>Watch us build a videogame</p>
	<div>
		<a class="button-wide" href="https://ladyofcode.twitch.tv">
			<svg width="20" height="20" viewBox="0 0 323202 333334" id="twitch">
				<path
					d="M50181 30055v212844h70936v40342c1097-1045 1713-1605 2301-2193 11962-11932 23955-23835 35845-35841 1698-1713 3391-2406 5800-2398 24790 81 49581 97 74371-47 1821-11 4084-952 5381-2231 15454-15243 30736-30661 46152-45943 1728-1713 2354-3421 2351-5806-59-51678-44-103356-44-155034v-3694H50182zm191912 151394h-29441V91364h29441v90085zm-80646-90079v89960h-29976V91370h29976zM80940 333064v-39857H206c-81-1669-198-2962-198-4257l-7-59760v-45701c7-39837 20-79676 43-119520 1-2169 386-4428 1063-6489C7056 39376 13162 21324 19079 3209 19847 863 20812 22 23315-2h120c98799 77 197597 66 296396 66 968-2 1937 0 3313 0v4184c0 64632-17 129265 58 193897v126c-23 2629-823 4462-2695 6326-28665 28550-57271 57158-85821 85822-1894 1902-3751 2696-6450 2678-17390-123-34782 19-52174-135-3332-30-5711 841-8083 3265-11472 11725-23114 23286-34787 34812-1109 1096-2853 2180-4313 2193-7285 72-14569 96-21854 100h-4373c-6800-4-13599-18-20398-26-343 0-685-123-1316-244z"
				>
				</path>
			</svg>
			Watch on twitch
		</a>
		<a href="https://twitter.com/ladyofcode">
			<svg width="20" height="20" viewBox="0 0 640 640" id="twitter">
				<path
					d="M640.012 121.513c-23.528 10.524-48.875 17.516-75.343 20.634 27.118-16.24 47.858-41.977 57.756-72.615-25.347 14.988-53.516 25.985-83.363 31.866-24-25.5-58.087-41.35-95.848-41.35-72.508 0-131.21 58.736-131.21 131.198 0 10.228 1.134 20.232 3.355 29.882-109.1-5.528-205.821-57.757-270.57-137.222a131.423 131.423 0 0 0-17.764 66c0 45.497 23.102 85.738 58.347 109.207-21.508-.638-41.74-6.638-59.505-16.359v1.642c0 63.627 45.225 116.718 105.32 128.718-11.008 2.988-22.63 4.642-34.606 4.642-8.48 0-16.654-.874-24.78-2.35 16.783 52.11 65.233 90.095 122.612 91.205-44.989 35.245-101.493 56.233-163.09 56.233-10.63 0-20.988-.65-31.334-1.89 58.229 37.359 127.206 58.997 201.31 58.997 241.42 0 373.552-200.069 373.552-373.54 0-5.764-.13-11.35-.366-16.996 25.642-18.343 47.87-41.493 65.469-67.844l.059-.059z"
				/>
			</svg>
			Follow on Xwitter
		</a>
	</div>
</section>

<section class="center">
	<div class="portal">
		<div>
			<img id="doorLeft" class="doors" src={doorLeftLight} alt="" />
			<img id="doorRight" class="doors" src={doorRightLight} alt="" />
		</div>
		<img id="frame" src={frameLight} alt="" />
		<img id="lab" src={lab} alt="" />
	</div>
</section>

<svg width="20px" height="20px" id="discord-icon" display="none"> </svg>

<section>
	<div class="container center">
		<h2>Join in the antics</h2>
	
		<div class="card">
			<h3>Dev, design, 3D: Tabs <a href="https://twitch.tv/ladyofcode">@ladyofcode</a></h3>
			<p>Unreal Engine, Blender, Figma, Svelte, JavaScript</p>
			<div id="tabsPlayer"></div>
		</div>
	
		<div class="card">
			<h3>3D modelling and 2D art: Natalie <a href="https://twitch.tv/dotterine_">@dotterine_</a></h3>
			<p>Blender</p>
			<div id="nataliePlayer"></div>
		</div>
	</div>
</section>

<style>
	.header {
		max-width: 800px;
		max-height: 200px;
		text-align: center;
		margin: 0 auto;
		margin-top: 32vh;
		padding: 1.6rem;
	}

	h1 {
		font-size: 4.8rem;
		color: var(--text-headings-color);
	}

	.header > div {
		display: flex;
		align-items: center;
		justify-content: center;
	}

	a,
	svg {
		width: fit-content;
	}

	.header div a {
		display: flex;
		width: fit-content;
		height: 20px;
		align-items: center;
		text-decoration: none;
		padding: 0.8rem 1.2rem;
		border-radius: var(--corner-radius);
	}

	.header div a:first-of-type {
		margin-right: 1.2rem;
	}

	.center {
		display: flex;
		align-items: center;
		justify-content: center;
	}

	.portal {
		max-width: 1200px;
		/* min-height: 100vw; */
		margin: 2.4rem;
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

	#frame,
	.doors {
		position: absolute;
		top: 0;
	}

	#doorLeft {
		left: 0;
	}

	#doorRight {
		right: 0;
	}

	.card {
		width: 100%;
		border: 2px solid grey;
		padding: 1.6rem;
		border-radius: var(--corner-radius);
		margin-bottom: 1.6rem;
	}

	@media (min-width: 800px) {
		h1 {
			font-size: 6rem;
		}
	}
</style>
