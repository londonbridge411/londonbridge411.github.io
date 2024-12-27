<script lang="ts">
    import "$lib/index";

	import Customimage from "$lib/components/customimage.svelte";

    // Images
    import Me from "$lib/assets/images/me/london.jpg";
    import Nier1 from "$lib/assets/images/me/nier.jpeg";
    import Nier2 from "$lib/assets/images/me/yokotaro.jpeg";
    import Friends from "$lib/assets/images/me/friends.jpeg";
    import Books from "$lib/assets/images/me/books.jpeg";
    import Ramen from "$lib/assets/images/me/ramen.jpeg";
    import Anime from "$lib/assets/images/me/anime.jpeg";
    import NYC from "$lib/assets/images/me/timessq.jpeg";


</script>
<h1>About</h1>
<Customimage src={Me} width=275 text="ME!!!"/>
<p>Hi, nice to meet you! My name is London Bowen and I graduated from West Virginia University in May 2023 with a Bachelor's in Computer Science. I have a love for programming and learning like no other. Rarely will a day pass where I am not working on a project or trying to expand my knowledge.</p>

<p>While at WVU, I was an active member and president of the WVU Game Developers Club. The club focused on introducing aspiring game developers the basics of the development cycle and many of the tools used. As an officer for 3 years, I shifted the club to foster an engaging environment where members could meet and learn.

<p>I am highly interested in software, web, and game development as well as database architecture. My strengths are in game development, Java, C#, Python, JavaScript, TypeScript, CSS, React, and relational databases.</p>

<p>When I'm not programming, you can typically find me playing piano or a new video game. I also volunteer at my former high school as a JV wrestling coach and will do one-on-ones with those who ask. I LOVE eating barbeque (it's really a problem) and tasting different cuisine.</p>

<div class="media-holder">
    <Customimage src={Friends} width=350 text="My friends and I on Halloween! (Yes, I am Frodo)" />
    <Customimage src={NYC} width=350 text="Times Square!" />
    <Customimage src={Anime} width=350 text="Anime NYC 2024" />
    <Customimage src={Books} width=200 text="Part of my book collection" />
    <Customimage src={Ramen} width=200 text="Amazing ramen!" />
    <Customimage src={Nier1} width=200 text="NieR Concert in Orlanda, FL" />
    <Customimage src={Nier2} width=200 text="YOKO TARO AND KEIICHI OKABE!!!!!" />
</div>