<script>
    export let titles = []; 
    export let contents = []; 
    let currentTab = 0;
</script>

<div class="warpper">
<nav>
    {#each titles as title, i}
        <button class="tab" on:click={ () => { currentTab = i; } }>
            { title }
        </button>
    {/each}
</nav>
</div>

{#if titles.length > 0 && contents.length > 0 && titles.length == contents.length}
    <div class="panels">
        <div class="panel">
            <div class="panel-title"> { titles[currentTab] } </div>
            <p> { contents[currentTab] } </p>
        </div>
    </div>
{:else if titles.length == 0 }
    <p> Le tableau Titre est vide !!!</p>
{:else if contents.length == 0 }
    <p> Le tableau Contenu est vide !!!</p>
{:else if titles.length != contents.length}
    <p> Vos tableaux n'ont pas la même taille !!! </p>
{:else}
    <p> Il y a un probleme avec vos tableau là !!!</p>
{/if}


<style>  
.warpper{
    display:flex;
    flex-direction: column;
    align-items: center;
}
.tab {
    cursor: pointer;
    padding:10px 20px;
    margin:0px 2px;
    background:#7380ec;
    display:inline-block;
    color:#fff;
    border: none;
    border-radius:3px 3px 0px 0px;
    box-shadow:0 0.2rem 0.9rem #00000080;
}
.panels{
    border-radius: 15px;
    flex-direction: column;
    background:#fffffff6;
    box-shadow: 0 1rem 2rem #00000080;
    min-height:200px;
    width:100%;
    max-width:500px;
    display: flex;
    align-items: center ;
    overflow:hidden;
    padding:20px;  
    margin-left: auto;
    margin-right: auto;
}
.panel{
    animation: fadein .8s;
}
</style>