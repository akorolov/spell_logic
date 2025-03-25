<script lang="ts">
    import { addToast } from '$lib/Toaster.svelte'

    let spellcraft = false

function craftSpell() {
    spellcraft = true
    addToast({
        data: {
            title: 'Crafting time!',
            description: "Time to craft your first spell."
        }
    });
}

</script>


<div class="flex flex-col gap-2 border rounded-xs border-amber-700 border-3 p-2 w-full justify-center bg-white h-full my-2 items-center">

    <div class="flex flex-row w-full justify-center {(spellcraft) ? 'h-full' : ''} items-center">
        {#if spellcraft}
        <div class="border border-lime-700 border-3 rounded bg-lime-50 flex flex-col gap-2 p-2 w-1/2 h-1/2 items-center ">
            <span>It's time to craft a spell!</span>
            <code class="code">If else</code>

        </div>

        {:else}
        <button class="btn cursor-pointer outline-black border-3 text-lime-900 border-lime-700 bg-lime-50 rounded p-2 hover:bg-lime-700 hover:text-white active:bg-lime-900 hover:animate-pulse" on:click={craftSpell}>Craft a Spell</button>
        {/if}
    </div>
    

</div>