<script>
  import Card from './components/Card.svelte';
  import Tooltip from './components/Tooltip.svelte';
  import Salescard from './components/Salescard.svelte';
  import Rangeslider from './components/Rangeslider.svelte';
  import Progress from './components/Progress.svelte';
  import Input from './components/Input.svelte';
  import Range from './components/Range.svelte';
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
<div>
  <h1>Rangeslider</h1>
  <Rangeslider 
  minValue = {100}
  maxValue = {700}
  />
</div>
<Progress 
  count = { 78 }
/>
