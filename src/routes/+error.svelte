<script>
    import { page } from '$app/state';
</script>


<div class="w-screen h-[calc(100vh-200px)] flex flex-col items-center justify-center gap-4">
    <h1 class="font-black text-8xl">
        {#if page.status === 404}
            404
        {:else}
            ERROR!
        {/if}
    </h1>
    <span>{page.error?.message}</span>
</div>
