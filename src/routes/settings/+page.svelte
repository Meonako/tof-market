<script lang="ts">
    import { settings } from "$lib/store/settings";
    import { setTheme } from "$lib/utils/theme";
</script>

<svelte:head>
    <title>Settings | ToF Market</title>
</svelte:head>

<div class="flex flex-col w-full h-full mt-2 items-center">
    <h1 class="h1 text-center my-5">Settings</h1>
    <hr class="w-full h-px my-2" />

    <label class="flex items-center space-x-2 mt-2">
        <input class="checkbox" type="checkbox" bind:checked={$settings.enableAnimation} />
        <p>Page Animation</p>
    </label>

    <label class="label mt-2">
        <span>Theme: </span>
        <select
            class="select mr-2 w-auto"
            bind:value={$settings.theme}
            on:change={() => {
                setTheme($settings.theme);
            }}
        >
            <option value="modern">Modern</option>
            <option value="rocket">Rocket</option>
            <option value="gold-nouveau">Gold Nouveau</option>
            <option value="random">Dev's Randomly Generate</option>
        </select>
    </label>
</div>
