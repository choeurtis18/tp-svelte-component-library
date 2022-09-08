<script>

export let title = ''; 
export let content = ''; 
export let color = ''; 
let state = true;

const close_card = () => {
    state = false;
}

</script>

{#if state}
<div class="card card-{color}">
    <h2>
        <span>{ title } </span>
        <span class="close" on:click={ close_card }>×</span>
    </h2>
    <p>{ content }</p>
</div>
{/if}

<style>
.card {
    flex: 100%;
    display: flex;
    flex-direction: column;
    background-color: #f5f5f5;
    border-radius: 4px;
}
.card.hide {
    display: none;
}
.card h2 .close{
    cursor: pointer;
}
.card h2 {
    display: flex;
    justify-content: space-between;
    height: 30%;

    background-color: #4a4a4a;
    color: #fff;

    border-radius: 4px 4px 0 0;
    margin: 0;
    padding: 14px;
}
.card p {
    text-align: center;
}


/* Red */
.card-red {
    background-color: #feecf0;
}
.card-red h2 {
    background-color: #f14668;
    color: #fff;
}
.card-red p {
    color: #cc0f35;
}
/* Green */
.card-green {
    background-color: #effaf5;
}
.card-green h2 {
    background-color: #48c78e;
    color: #fff;
}
.card-green p {
    color: #257953;
}
/* Orange */
.card-orange {
    background-color: #fffaeb;
}
.card-orange h2 {
    background-color: #ffe08a;
    color: #fff;
}
.card-orange p {
    color: #946c00;
}

</style>