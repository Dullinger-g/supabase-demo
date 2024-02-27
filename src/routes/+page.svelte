<script>
    import {supabase} from '$lib/supabase';

    let promise = supabase.from("countries").select();
</script>

{#await promise}
<div><span class="loading loading-dots loading-sm"></span></div>
{:then result}
<div>{JSON.stringify(result)}</div>
{/await}
