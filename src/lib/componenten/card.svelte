<script>
    import Miel from "./miel.svelte";
    import Logo from "./logo.svelte";
    import Drawing from "./drawing.svelte";
    import TreeGreen from "./tree-green.svelte";
    import TreeDarkgreen from "./tree-darkgreen.svelte";
    import Mill from "./mill.svelte";

    export let size = 1;
    export let className = "card";
</script>

<div class="card">
    <div class="card-inner">
        <div class="card-front">
            <Logo />
            <Drawing />
            <Miel />
        </div>

        <div class="card-back">
            <h2>Miel van Sleeuwen</h2>   
            <p>Webdeveloper & Designer</p>

            <TreeGreen />
            <Mill />
            <TreeDarkgreen />
        </div>
    </div>
</div>

<style>
.card {
    position: relative;
    width: 400px;
    height: 250px;
    perspective: 1000px;
    border-radius: var(--border-radius-desktop);

    @media (max-width: 600px) {
        border-radius: var(--border-radius-mobile);
        width: 250px;
        height: 400px;
    }
}

.card-inner {
    position: relative;
    width: 100%;
    height: 100%;
    transform-style: preserve-3d;
    transition: transform 0.8s;
    border-radius: var(--border-radius-desktop);
}

.card:hover .card-inner {
    transform: rotateY(180deg);
}

.card-front,
.card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    border-radius: var(--border-radius-desktop);
    padding: 1em;
    display: grid;
    justify-content: center;
    align-items: center;
    overflow: hidden;

    @media (max-width: 600px) {
        border-radius: var(--border-radius-mobile);
        grid-template-columns: 100%;
        grid-template-rows: 33% 33% 33%;
    }
}

.card-front {
    border-radius: var(--border-radius-desktop);
    background: var(--secondary-color);
    grid-template-columns: 60% 40%;
    grid-template-rows: 50% 50%;
}

.card-front :global(svg:nth-of-type(2)) {
    grid-column: 2;
    grid-row: 1 / span 2;
    align-self: center;
    justify-self: center;
    width: 80%;
    height: auto;
}

.card-back {
    background: var(--secondary-color);
    color: var(--primary-color);
    transform: rotateY(180deg);
}
</style>
