<script>
    import { nonpassive } from "svelte/legacy";
    import Miel from "$lib/componenten/miel.svelte";
    import Logo from "$lib/componenten/logo.svelte";
    import Drawing from "$lib/componenten/drawing.svelte";
    import Card from "$lib/componenten/card.svelte";
    import Mill from "$lib/componenten/mill.svelte";
    import TreeDarkgreen from "$lib/componenten/tree-darkgreen.svelte";
</script>


<Card size={1} className="card-front">

</Card>

<Mill />
<div class="trees">
    <TreeDarkgreen />
</div>

<style>
    :root {
    /* colors */
    --primary-color: #0A1252;
    --secondary-color: #C7CCEF;

    /* text-color */
    --text-color: #FFFFFF;

    /* border-radius */
    --border-radius-dekstop: 70px;
    --border-radius-mobile: 45px;
}


:global(body) {
    background-color: var(--primary-color);
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Garet', sans-serif;
}

.trees {
    width: 50px;
    height: 50px;
    position: absolute;
    top: 22px;
    left: 22px;
    z-index: 10;

    animation: skew 2s infinite alternate;
}

@keyframes skew {
    /* scaleY with the anchorpoint on the bottom */
    0% {
        transform: scale(1) ;
        offset-anchor: bottom;
    }
    50% {
        transform: scale(0.8);
    }
}
</style>