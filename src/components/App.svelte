<script>
  import Card from './components/Card.svelte';
  import Carousel from './components/Carousel.svelte';
  import Tooltip from './components/Tooltip.svelte';

  import TabA from './components/TabA.svelte';
  import TabB from './components/TabB.svelte';
  import TabC from './components/TabC.svelte';

  let activeTab= TabA  

  const images=[
    {path: 'src/images/1.jpg', id: 'image1'},
    {path: 'src/images/2.jpg', id: 'image2'},
    {path: 'src/images/3.png', id: 'image3'},
    {path: 'src/images/4.jpg', id: 'image4'},
    {path: 'src/images/5.jpg', id: 'image5'},
    {path: 'src/images/6.jpg', id: 'image6'},
    {path: 'src/images/7.jpg', id: 'image7'}
  ]

</script>

<main>

  <h1>Cards</h1>

  <div>
    <Card
      title="Thomas"
      content="https://storage.googleapis.com/mustsee-earth.appspot.com/places/matterhorn-sam-ferrara-large%402x.jpg"
      color="red"
    />
    
    <Card
      title="Thomfffas"
      content="-sam-ferrara-large%402x.jpg"
      color="green"
    />
    
    <Card
      title="Thomfffas"
      content="-sam-ferrara-large%402x.jpg"
      color="orange"
    />
  </div>
  
  
  <h1>Tooltip</h1>
  
  <div style="text-align: center;">
    <Tooltip
      title="Top"
      texte="Rigth"
      position="Top"
    />
    
    <Tooltip
      title="Rigth"
      texte="Rigth"
      position="Rigth"
    />
  
    <Tooltip
      title="Bottom"
      texte="Rigth"
      position="Bottom"
    />
  
    <Tooltip
      title="Left"
      texte="Rigth"
      position="Left"
    />
    
  </div>
  <div>
    <Carousel {images}>

    </Carousel>
  </div>
  
  
<div class="warpper">
  <nav class="tabs">
    <button class="tab" on:click={() => (activeTab= TabA)}>Tab A</button>
    <button class="tab" on:click={() => (activeTab= TabB)}>Tab B</button>
    <button class="tab" on:click={() => (activeTab= TabC)}>Tab C</button>
  </nav>

</div>

<div class="panels">
  <div class="panel">
  <svelte:component this={activeTab} />
  </div>
</div>

</main>


<style>

.warpper{
    display:flex;
    flex-direction: column;
    align-items: center;
  }
  .tab{
  cursor: pointer;
  padding:10px 20px;
  margin:0px 2px;
  background:#000;
  display:inline-block;
  color:#fff;
  border-radius:3px 3px 0px 0px;
  box-shadow: 0 0.5rem 0.8rem #00000080;
  }
  .panels{
  background:#fffffff6;
  box-shadow: 0 1rem 2rem #00000080;
  min-height:200px;
  width:100%;
  max-width:500px;
  display: flex;
  align-items: center ;
  border-radius:3px;
  overflow:hidden;
  padding:20px;  
  margin-left: auto;
  margin-right: auto;
}
.panel{
  animation: fadein .8s;
}

</style>