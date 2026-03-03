<script>
    import { SiGithub, SiSoundcloud } from "@icons-pack/svelte-simple-icons";
    import { Mail } from "lucide-svelte";
</script>


<div class="w-screen h-[calc(100vh-150px)] flex flex-col items-center justify-center gap-4">
    <img class="w-32 h-32 rounded-full object-cover" src="/me.webp" alt="Gabriele Pio Midulla">
    <h1 class="font-bold text-5xl text-center">
        gabriele pio midulla
    </h1>
    <span>software engineer, edm music producer, human</span>
    <div class="flex gap-4 mt-4">
        <a href="mailto:me@gabriele.engineer"><Mail size={32} /></a>
        <a target="_blank" href="https://github.com/gabrielemidulla"><SiGithub size={32} /></a>
        <a target="_blank" href="https://soundcloud.com/gabrielemidulla"><SiSoundcloud size={32} /></a>
    </div>
    <code class="text-xs max-w-xl mt-6 px-4">Love is patient and kind. Love is not jealous or boastful or proud or rude. It does not demand its own way. It is not irritable, and it keeps no record of being wronged. It does not rejoice about injustice but rejoices whenever the truth wins out. Love never gives up, never loses faith, is always hopeful, and endures through every circumstance <b>(1 corinthians 13:4-7)</b></code>
</div>
