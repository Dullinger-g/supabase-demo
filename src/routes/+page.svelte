<script>
    import {supabase} from '$lib/supabase';

    let promise = supabase.from("countries").select();
    let countries = [];
    promise.then(result => {
        countries = result.data;
    });
</script>

{#await promise}
<div><span class="loading loading-dots loading-sm"></span></div>
{:then}
<ul>
    {#each countries as country}
        <li>{country.name}</li>
    {/each}
</ul>
{/await}
