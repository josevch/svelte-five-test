<script lang="ts">
    import Header from "./Header.svelte";
    
    let name = $state('Scott');

    let status: 'OPEN' | 'CLOSED' = $state('OPEN');

    function onclick() {
        status = status === "OPEN" ? 'CLOSED' : 'OPEN'
    }

    let full_name = $derived(name + " " + 'Tolinski')

</script>
<div class="m-3">
    <Header {name} fake_name="wes" />

     <h2>{full_name}</h2>

    <input class="border-2" type="text" bind:value={name} />
    
    <p>The store is now {status}</p>
    <button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded" {onclick}>Toggle Status</button>
    <button class="bg-blue-800 hover:bg-slate-600 text-white font-bold py-2 px-4 rounded" onclick="{() =>
         status = status === "OPEN" ? 'CLOSED' : 'OPEN'
        }" >Toggle Status FUNCTION INLINE</button>
</div>
