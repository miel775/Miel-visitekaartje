<script>
    export let size = 1;
    export let className = "card";
</script>

<div class="card">
    <div class="card-front">
        <h2>Front Side</h2>
    </div>
    <div class="card-back">
        <h2>Back Side</h2>
        <p>Extra info or contact details here.</p>
    </div>
</div>

<style>
.card {
    position: relative;
    width: 400px;
    height: 300px;
    perspective: 1000px;

    @media (max-width: 600px) {
        border-radius: var(--border-radius-mobile);
        width: 300px;
        height: 400px;
    }
}

.card-front, .card-back {
    position: absolute;
    width: 100%;
    height: 100%;
    backface-visibility: hidden;
    display: flex;
    justify-content: center;
    align-items: center;
    border-radius: var(--border-radius-dekstop);
    background: var(--secondary-color);
}

.card-back {
    background: var(--primary-color);
    color: var(--secondary-color);
    transform: rotateY(180deg);
}
</style>