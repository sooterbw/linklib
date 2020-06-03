<script>
    export let name, link, description, img, alt;
</script>

<style>
    a {
        text-decoration: none;
    }
</style>

<a target="_blank" href="{link}">
    <div class="flex bg-gray-700 cursor-pointer hover:bg-gray-600 p-5 rounded-md">
        <img class="w-20 h-20 rounded-lg" src="{img}" alt="{alt}">
        <div class="flex flex-col pl-5">
        <p class="text-white text-lg font-bold">{name}</p>
        <p class="text-white opacity-50">{description}</p>
        </div>
    </div>
</a>
