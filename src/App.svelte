<script>
  import Card from './components/Card.svelte';
  import Tooltip from './components/Tooltip.svelte';
  import Input from './components/Input.svelte';
  import Range from './components/Range.svelte';

</script>

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
  <h2>Tooltip</h2>
  <div class="component tooltip_container">
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
  <h2>Input</h2>
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

<div class="component_container">
  <h2>Range Slider</h2>
  <div class="component range_container">
    <div class="cadre"></div>
      <div class="slide_container">
        <Range 
          range="1500" 
          minValue="600"
          maxValue="3000"
        />
        <Range 
          range="500" 
          minValue="200"
          maxValue="1500"
        />
      </div> 
    </div> 
</div>
