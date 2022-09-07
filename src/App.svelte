<script>
  import Card from './components/Card.svelte';
  import Tooltip from './components/Tooltip.svelte';
  import Salescard from './components/Salescard.svelte';
  import Rangeslider from './components/Rangeslider.svelte';
</script>

<h1>Cards</h1>

<div style="display: flex; flex-wrap:wrap">
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

<div style="display: flex; flex-wrap:wrap; text-align: center;" >
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

<Salescard 
animationSpeed = { 60 }
progressValue = { 0 }
progressEndValue = { 60 }
/>

<Rangeslider 
minValue = {100}
maxValue = {700}
/>
