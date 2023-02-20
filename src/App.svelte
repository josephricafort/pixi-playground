<script>
    import TailwindCss from "./TailwindCss.svelte";
    import PixiSvelteDemo from "./components/PixiSvelteDemo.svelte";
    import { Ticker } from "svelte-pixi"
</script>

<TailwindCss />

<main>
    <Ticker>
        <PixiSvelteDemo />
    </Ticker>
</main>

<style>

</style>