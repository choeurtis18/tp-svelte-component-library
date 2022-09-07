<script>
  import Card from './components/Card.svelte';
  import Tooltip from './components/Tooltip.svelte';
  import Salescard from './components/Salescard.svelte';
  import Rangeslider from './components/Rangeslider.svelte';
  import Progress from './components/Progress.svelte';
  import Input from './components/Input.svelte';
  import Range from './components/Range.svelte';
  import Carousel from './components/Carousel.svelte';
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

<h1>Bankable Components</h1>

<div class="component_container">
  <div class="container_item card_item">
    <h2>Component Salescard</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis facilis amet suscipit, a hic odio porro quam voluptatum accusamus voluptas, consectetur soluta placeat atque earum nisi beatae magnam dolorem corrupti?</p>
  </div>
  <Salescard 
  animationSpeed = { 60 }
  progressValue = { 0 }
  progressEndValue = { 60 }
  />
</div>


<div class="component_container tooltip_container">
  <div class="container_item tooltip_item">
    <h2>Component Tooltip</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis facilis amet suscipit, a hic odio porro quam voluptatum accusamus voluptas, consectetur soluta placeat atque earum nisi beatae magnam dolorem corrupti?</p>
  </div>
  <div class="component tooltip_component">
    <Tooltip
      title="Top"
      texte="Top"
      position="Top"
    />
    <div class="tooltip_middleItems">
      <Tooltip
        title="Left"
        texte="Left"
        position="Left"
      />
      <Tooltip
        title="Right"
        texte="Right"
        position="Right"
      />
    </div>
    <Tooltip
      title="Bottom"
      texte="Bottom"
      position="Bottom"
    />
    
  </div>
</div>

<div class="component_container">
  <div class="container_item input_item">
    <h2>Component Input</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis facilis amet suscipit, a hic odio porro quam voluptatum accusamus voluptas, consectetur soluta placeat atque earum nisi beatae magnam dolorem corrupti?</p>
  </div>
  <div class="component input_component">
    <Input
      type="regural"
      texte="Name"
      placeholder="Ex : John, Thomas..."
    />
    <Input
      type="email"
      texte="Enter your email"
      placeholder="Ex : name@mail.com"
    />
    <Input
      type="password"
      texte="Password (8 characters minimum)"
      placeholder="Enter your Password"
    />
    <Input
      type="textarea"
      texte="Message"
    />
  </div>
</div>

<div class="component_container range_container">
  <div class="container_item range_item">
    <h2>Component Range Slider</h2>
    <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quis facilis amet suscipit, a hic odio porro quam voluptatum accusamus voluptas, consectetur soluta placeat atque earum nisi beatae magnam dolorem corrupti?</p>
  </div>
  <div class="component range_component">
    <div class="cadre"></div>
      <div class="slide_container">
        <div class="slide_item">
          <div class="slide_title">
            <p>Modifiez votre plafond de paiement</p>
          </div>
          <Range 
            range="1500" 
            minValue="600"
            maxValue="3000"
          />
        </div>
        <div class="slide_item">
          <div class="slide_title">
            <p>Modifiez votre plafond de retrait</p>
          </div>
          <Range 
            range="500" 
            minValue="200"
            maxValue="1500"
          />
        </div>
      </div> 
    </div> 
</div>

<div class="component_container">
  <h2>Cards</h2>
  <div class="component">
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
</div>
<div class="component_container">
  <h1>Rangeslider</h1>
  <Rangeslider 
  minValue = {100}
  maxValue = {700}
  />
<Progress 
  count = { 78 }
/>
</div>

<div class="component_container">
  <h2>Component Carousel</h2>

  <Carousel {images}>

  </Carousel>

</div>  


<div class="component_container" style="display: block;">
  <h2>Component Tabs</h2>

  <div class="warpper">
    <nav class="tabs">
      <button class="tab" on:click={() => (activeTab= TabA)}>Svelte</button>
      <button class="tab" on:click={() => (activeTab= TabB)}>React</button>
      <button class="tab" on:click={() => (activeTab= TabC)}>Vue.Js</button>
    </nav>
  
  </div>
  
  <div class="panels">
    <div class="panel">
    <svelte:component this={activeTab} />
    </div>
  </div>

</div>  
