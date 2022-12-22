<script lang="ts">
	import '../routes/styles.css';
	import Ukiran from '$lib/images/ukiran.svg';
	import Omswatiastu from '$lib/images/omswatiastu.svg';
	import Images_home from '$lib/images/home_pages.jpg';
	import Cik from '$lib/images/cik.svg';
	import Atik from '$lib/images/atik.svg';
	import Line from '$lib/images/line.svg';
	import Slide1 from '$lib/images/slide1.jpg';
	import Slide2 from '$lib/images/slide2.jpg';
	import Slide3 from '$lib/images/slide3.jpg';
	import Gallery_1 from '$lib/images/gallery_1.jpg';
	import Gallery_2 from '$lib/images/gallery_2.jpg';
	import Gallery_3 from '$lib/images/gallery_3.jpg';
	import Gallery_4 from '$lib/images/gallery_4.jpg';
	import Gallery_5 from '$lib/images/gallery_5.jpg';
	import Gallery_6 from '$lib/images/gallery_6.jpg';
	import Gallery_7 from '$lib/images/gallery_7.jpg';
	import Musik from '$lib/images/tetaman.mp3';
	// import Carousel from 'svelte-carousel';
	import { fly } from 'svelte/transition';
	import { queryParam } from 'sveltekit-search-params';
	import { onMount } from 'svelte';

	const to = queryParam('to');
	const slideShow = [
		{
			url: `${Slide1}`,
			description: 'image1'
		},
		{
			url: `${Slide2}`,
			description: 'image1'
		},
		{
			url: `${Slide3}`,
			description: 'image1'
		}
	];
	const Gallery = [
		{
			url: `${Gallery_1}`,
			description: 'image1'
		},
		{
			url: `${Gallery_2}`,
			description: 'image1'
		},
		{
			url: `${Gallery_3}`,
			description: 'image1'
		},
		{
			url: `${Gallery_4}`,
			description: 'image1'
		},
		{
			url: `${Gallery_5}`,
			description: 'image1'
		},
		{
			url: `${Gallery_6}`,
			description: 'image1'
		},
		{
			url: `${Gallery_7}`,
			description: 'image1'
		}
	];
	let isOpen = true;
	// let carousel;
	let celebration: HTMLAudioElement;

	onMount(() => {
		celebration.play();

		setTimeout(() => {
			celebration.pause();
			celebration.currentTime = 0;
		}, 1000);
	});
</script>

<section>
	{#if isOpen}
		<div class="relative z-10" transition:fly={{ y: 200, duration: 2000 }}>
			<div class="overflow-visible">
				<img src={Images_home} alt="home" class="h-screen w-full object-cover" />
				<div class=" grid gap-2 absolute bottom-[60px] w-full">
					<div class=" text-center text-white">
						<span> We Are Getting Married </span>
						<h1 class="text-[#DAA520]">Cikawana & Atik Karnila</h1>
					</div>
					<div class="text-center text-white">
						<span> Kepada Bapak/Ibu/Saudara/i </span>
						<h2 class="text-2xl">{$to}</h2>
						<span> Gianyar | 26 Desember 2022 </span>
					</div>
					<div class="text-center text-white mt-5">
						<button class="border border-[#676565] p-3 w-52" on:click={() => (isOpen = !isOpen)}
							>Buka Undangan</button
						>
					</div>
				</div>
			</div>
		</div>
	{/if}

	{#if !isOpen}
		<audio controls autoplay>
			<source src={Musik} type="audio/mpeg" />
		</audio>
		<div class="absolute top-0 w-full">
			<div class="bg-black">
				<div class="relative">
					<img src={Ukiran} alt="ukiran" class="w-full" />
					<div class=" text-center text-white absolute bottom-[49px] w-full">
						<span> We Are Getting Married </span>
						<h1 class="text-[#DAA520]">Cikawana & Atik Karnila</h1>
						<span> Gianyar | 26 Desember 2022 </span>
					</div>
				</div>
				<div class="relative">
					<img src={Slide1} alt="slide 1" />
					<div class="absolute bottom-0 p-5 text-center text-white">
						" Ya Tuhan, anugerahkanlah kepada pasangan pengantin ini kebahagiaan, keduanya tiada
						terpisahkan dan panjang umur. Semoga pengantin ini dianugerahkan putra dan cucu yang
						memberikan penghiburan, tinggal di rumah yang penuh kegembiraan.
						<br />
						" - Rg Veda X.85.42 -
					</div>
				</div>
			</div>
			<div class=" bg-[#D9D9D9] h-auto py-5">
				<div class=" flex items-center justify-center py-10 px-5">
					<img src={Omswatiastu} alt="omswatiastu" />
				</div>
				<div class="text-center px-5">
					Atas Asung Kertha Wara Nugraha Ida Sang Hyang Widhi Wasa/ Tuhan Yang Maha Esa, kami
					bermaksud mengundang Bapak/ Ibu/ Saudara/ i pada Upacara Manusa Yadnya Pawiwahan lan
					Mepandes putra dan putri kami.
				</div>
				<h1 class="text-center pt-5">Mempelai</h1>
				<div class="flex items-center justify-center">
					<img src={Line} alt="line" />
				</div>
				<div class="bg-white rounded-md mx-5 h-auto py-5">
					<div class="flex items-center justify-center ">
						<img src={Cik} alt="cik" />
					</div>
					<h1 class="text-[B57D30] text-center">Pande Kadek Cik Suarsa</h1>
					<div class="text-center">
						Putra Kedua dari pasangan <br />
						Pande Made Lasia <br />&<br />Ni Made warni <br />Br. Juga Desa Mas, Kec. Ubud, Gianyar
					</div>
				</div>
				<h1 class="text-center py-5">&</h1>
				<div class="bg-white rounded-md mx-5 h-auto py-5">
					<div class="flex items-center justify-center pt-8">
						<img src={Atik} alt="cik" />
					</div>
					<h1 class="text-[B57D30] text-center">Ni Made Yatik Karnilasari</h1>
					<div class="text-center">
						Putri Kedua dari pasangan <br />
						I Made Dogil <br />
						& <br />Ni Wayan Gandri <br />
						Br. Juga Desa Mas, Kec. Ubud, Gianyar
					</div>
				</div>
			</div>
			<div class="my-5">
				<div class="text-center pt-5 px-5">
					Merupakan suatu kehormatan & kebahagian kami apabila Bapak/Ibu/Saudara/i berkenan hadir
					memberi doa restu pada :
				</div>
				<h1 class="text-center pt-5">Mempelai</h1>
				<div class="flex items-center justify-center">
					<img src={Line} alt="line" />
				</div>
				<div class="text-center pt-5 font-bold">
					Senin, 26 Desember 2022 <br /> 13.00 WITA s/d Selesai <br /> Br. Juga Desa Mas, Kec. Ubud,
					Gianyar.
				</div>
				<div class=" w-full py-5 flex items-center justify-center">
					<a href="https://goo.gl/maps/oQobKMsJ9fpeJ18SA">
						<button class="bg-blue-500 text-white w-32 h-10 rounded-md"> lokasi </button>
					</a>
				</div>
			</div>
			<div class=" bg-[#D9D9D9] h-auto py-5">
				<h1 class="text-center pt-5">Photo Gallery​</h1>
				<div class="flex items-center justify-center">
					<img src={Line} alt="line" />
				</div>
				<div class="grid gap-5 py-5">
					{#each Gallery as items}
						<img src={items.url} alt={items.description} class=" w-full h-auto px-5 gap-5" />
					{/each}
				</div>
			</div>
			<div>
				<h1 class="text-center pt-5">Om Shanti Shanti Shanti Om​</h1>
				<div class="flex items-center justify-center">
					<img src={Line} alt="line" />
				</div>
			</div>
		</div>
	{/if}
</section>
