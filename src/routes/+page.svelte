<script lang="ts">
    import type { PageData } from './$types';
    import{enhance} from '$app/forms';
    
    export let data: PageData;
</script>

<h1>home</h1>

<form method="post" action="/login?/logout" use:enhance>
    <button>LOGOUT</button>
</form>

<a href="http://localhost:5173/sessions">Sessions</a>