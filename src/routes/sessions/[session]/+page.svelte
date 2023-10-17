<script lang="ts">
    import { browser } from '$app/environment';
    import { enhance } from '$app/forms';
    import { invalidateAll } from '$app/navigation';
    import { fade } from 'svelte/transition';
    import type { ActionData } from './$types.js';


    export let data;
    export let form: ActionData

    $: messages = data.message!.reverse()

    browser ? setInterval(invalidateAll, 1000) : null;

</script>


<h2><a href="http://localhost:5173/sessions">Go back to sessions</a></h2>

<h1>Välkommen till session: {data.session}</h1>

<form action="?/message" method="post" use:enhance>
    <input type="text" name="message" />
    <button>SEND</button>
    {#if form?.message}
        <span>{form.message}</span>
    {/if}
</form>

{#each messages as message}
<div transition:fade|local>
    {message}
</div>
{/each}
