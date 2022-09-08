<script>
  import Card from './components/Card.svelte';
  import Tooltip from './components/Tooltip.svelte';
  import Salescard from './components/Salescard.svelte';
  import Rangeslider from './components/Rangeslider.svelte';
  import Progress from './components/Progress.svelte';
  import Input from './components/Input.svelte';
  import Range from './components/Range.svelte';
  import Carousel from './components/Carousel.svelte';
  import Tabs from './components/Tabs.svelte';
  

  const images=[
    {path: 'src/images/1.jpg', id: 'image1'},
    {path: 'src/images/2.jpg', id: 'image2'},
    {path: 'src/images/3.png', id: 'image3'},
    {path: 'src/images/4.jpg', id: 'image4'},
    {path: 'src/images/5.jpg', id: 'image5'},
    {path: 'src/images/6.jpg', id: 'image6'},
    {path: 'src/images/7.jpg', id: 'image7'}
  ]

  var titles = ['Svelte ?', 'React ?', 'Vue.js ?'];
  var contents = ["Svelte est un framework JavaScript libre et à code ouvert écrit par Rich Harris. Le framework est écrit en TypeScript. Son code source utilise la licence MIT et est hébergé sur GitHub.", "React est une bibliothèque JavaScript libre développée par Facebook depuis 2013. Le but principal de cette bibliothèque est de faciliter la création d'application web monopage, via la création de composants dépendant d'un état et générant une page HTML à chaque changement d'état.", "Vue.js, est un framework JavaScript open-source utilisé pour construire des interfaces utilisateur et des applications web monopages. Vue a été créé par Evan You et est maintenu par lui et le reste des membres actifs de l'équipe principale travaillant sur le projet et son écosystème."];
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
  count = { 38 }
/>
</div>

<div class="component_container">
  <h2>Component Carousel</h2>

  <Carousel {images}>

  </Carousel>

</div>  

<div class="component_container" style="display: block;">
  <h2>Component Tabs</h2>

  <Tabs titles={titles} contents={contents}></Tabs>
</div>  