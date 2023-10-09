<script lang="ts">
    import { RangeSlider } from '@skeletonlabs/skeleton';
    import type { PageData } from './$types';
    
    export let data: PageData;
    let value = 15;

</script>

<h1>About Us</h1>
<p>Ciao patatella baby amore mio grande</p>
<RangeSlider name="range-slider" bind:value={value} max={25} step={1} ticked>Label</RangeSlider>
