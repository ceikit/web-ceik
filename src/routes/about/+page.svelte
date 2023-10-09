<script lang="ts">
    import { RangeSlider } from "@skeletonlabs/skeleton";
    import type { PageData } from "./$types";

    export let data: PageData;
    let value = 15;

    import Device from "svelte-device-info";

    console.log(Device.isMobile);
</script>

<h1 class="h1">About Us</h1>
<h2 class="h2">About Us</h2>
<p >Ciao patatella baby amore mio grande</p>


{#if Device.isMobile}
    <div class="option-bar">ASDADA</div>
{/if}
