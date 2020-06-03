<script>
    import Linkcard from '../components/Linkcard.svelte';

    let links = [];
    let search = '';
    let teams = ['The Junction'];
</script>

<style>
    .link-search {
      background: url(/img/SearchIcon2x.png) no-repeat scroll 2px 2px;
      background-color:#4a5568;
      padding-left: 40px;
    }

</style>  

<div class="bg-gray-800 h-screen p-5 w-screen overflow-y-scroll">
    <img class="h-16 md:h-20 mx-auto md:mx-0" src="https://www.oiml.org/en/ressources/icons/link-icon.png/image_preview" alt="The Junction Logo">
    <div class="p-5 w-full">
      <div class="sm:flex w-full justify-between">
        <div class="text-xl font-bold text-white">
            <ul class="flex space-x-2 border-separate">
                <li>Personal</li>
                {#each teams as team}
                    <li class="border-gray-700 border-l pl-2">{team}</li>
                {/each}
            </ul>
        </div>
        <div class="pb-2">
            <input class='link-search text-white font-bold h-10 w-full sm:w-auto rounded-md border-none' type="search" name="search" placeholder="Search" bind:value={search}>
        </div>
      </div>
      <hr class="border-gray-700">
      <div class="grid grid-flow-row grid-col-1 md:grid-cols-2 lg:grid-cols-3 xl:grid-cols-4 grid-rows-1 gap-4 max-w-full">
        {#each links as link}
          {#if link.name.toLowerCase().includes(search.toLowerCase())}
            <Linkcard {...link} />
          {/if}
        {/each}
      </div>
    </div>
</div>
  