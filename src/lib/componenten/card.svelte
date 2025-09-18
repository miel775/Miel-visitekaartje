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
            <h1>Miel van Sleeuwen</h1>
            <Logo />
            <Drawing />
            <Miel />
        </div>

        <div class="card-back">
            <h2 class="miel-text">Miel van Sleeuwen</h2>   
            <p class="job-title">Webdeveloper & Designer</p>

            <div class="line"></div>

            <div class="socials">
                <a href="https:/www.mielvansleeuwen.com" class="ico fa-solid fa-globe"></a>
                <a href="https:/www.github.com/miel775" class="ico fa-brands fa-github"></a>
                <a href="https:/www.linkedin.com/in/mielvansleeuwen" class="ico fa-brands fa-linkedin"></a>
            </div>

            <TreeGreen />
            <Mill id="mill-overall"/>
            <TreeDarkgreen />
        </div>
    </div>
</div>

<style>
:root {
    /* colors */
    --primary-color: #0A1252;
    --secondary-color: #C7CCEF;

    /* text-color */
    --text-color: #FFFFFF;

    /* border-radius */
    --border-radius-desktop: 70px;
    --border-radius-mobile: 45px;
}

h1 {
    display: none;
}

h2 {
    font-family: 'Garet', sans-serif;
    font-size: 32px;
    color: var(--primary-color);
    margin: 0;
    padding: 0;
    margin-bottom: 0.5rem;
}

p {
    font-family: 'Jersey 20', serif;
    font-size: 24px;
    color: var(--primary-color);
    margin: 0;
    padding: 0;
    margin-bottom: 1rem;
}

#mill-overall {
    position: relative;
    top: -200px;
}



.card {
    position: relative;
    width: 400px;
    height: 250px;
    perspective: 1000px;

    @media (max-width: 600px) {
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
    padding: 1em;
    display: grid;
    justify-content: center;
    align-items: center;
    overflow: hidden;
    border-radius: var(--border-radius-desktop);


    @media (max-width: 600px) {
        grid-template-columns: 100%;
        grid-template-rows: 33% 33% 33%;
    }
}

.card-front {
    background: var(--secondary-color);
    grid-template-columns: 60% 40%;
    grid-template-rows: 50% 50%;
}

.card-front :global(svg:nth-of-type(1)) {
    @media (max-width: 600px) {
        margin-bottom: 50px;
    }
}

.card-front :global(svg:nth-of-type(2)) {
    grid-column-start: 1;
    grid-row-start: 2;

        @media (max-width: 600px) {
        margin-bottom: 200px;
        margin-right: 150px;
        height: 50px;
        grid-column-start: 1;
        grid-row-start: 2;

    }
}

.card-front :global(svg:nth-of-type(3)) {
    grid-column-start: 2;
    margin-top: 180px;
    margin-right: 250px;

    @media (max-width: 600px) {
        margin-top: 0px;
        margin-left: 500px;
        grid-column-start: 1;
        grid-row-start: 2;
        justify-self: center;
        align-self: center;
    }
}


.card-back {
    background: var(--secondary-color);
    color: var(--primary-color);
    transform: rotateY(180deg);
}

.miel-text {
    margin-top: 50px;

    @media (max-width: 600px) {
        margin-top: 0px;
        font-size: 24px;
    }
}

.job-title {
    margin-bottom: 0px;

    @media (max-width: 600px) {
        margin-bottom: 225px;
        font-size: 16px;
    }
}

.line {
    display: block;
    width: 90%;
    height: 2px;
    background-color: var(--primary-color);

    @media (max-width: 600px) {
        margin-bottom: 450px;
    }
}


.socials {
    display: flex;
    flex-direction: row;
    justify-content: flex-start;
    align-items: center;
    margin-top: 15px;

    @media (max-width: 600px) {
        margin-top: -500px;
        justify-content: center;
    }
}

a {
    display: block;
    background-color: var(--primary-color);
    height: 32px;
    width: 32px;
    display: flex;
    justify-content: center;
    align-items: center;
}

.ico {
    color: var(--secondary-color);
    font-size: 24px;
    margin-right: 1rem;
    text-decoration: none;
}

</style>
