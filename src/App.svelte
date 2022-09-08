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
    <h2>Composant Salescard</h2>
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
    <h2>Composant Tooltip</h2>
    <p>Ce composant permet d'afficher une information liée au bloc survolé. Il peut être affiché sous différentes formes : au dessus, en dessous, à droite et à gauche.</p>
    <p>Props utilisées : <br> title : le texte à survoler<br> texte : le texte affiché en survol<br> position : l'emplacement du texte à afficher</p>
  </div>
  <div class="component tooltip_component">
    <Tooltip
      title="Mes Dépenses"
      texte="Retrouvez vos dépenses du mois ici... "
      position="Top"
    />
    <div class="tooltip_middleItems">
      <Tooltip
        title="Mon Epargne"
        texte="Retrouvez le montant de votre Epargne ici..."
        position="Left"
      />
      <Tooltip
        title="Mes Virements"
        texte="Retrouvez vos virements du mois ici..."
        position="Right"
      />
    </div>
    <Tooltip
      title="Mes Informations"
      texte="Consultez vos informations bancaires ici..."
      position="Bottom"
    />
    
  </div>
</div>

<div class="component_container">
  <div class="container_item input_item">
    <h2>Composant Input</h2>
    <p>Ce composant permet à l'utilisateur d'entrer des informations. Il est souvent utiliser dans les formulaires.</p>
    <p>Props utilisés : <br> type : le type d'input <br> texte : le label de l'input <br> placeholder : le contenu du placeholder</p>
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
    <h2>Composant Range Slider</h2>
    <p>Ce composant permet de choisir une valeur entre une valeur minimum et une valeur maximum.</p>
    <p>Props utilisés : <br> range : la valeur par défaut <br> minValue : la valeur minimale <br> maxValue : la valeur maximale </p>
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
  <h2>Composant Cards</h2>
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
<div class="component_container progress_container">
  <div class="container_item">
    <h2>Composant Progress Bar</h2>
    <p>Ce composant permet d'afficher une bar de progrès avec une valeur située entre 0 et 100.</p>
    <p>Props utilisés : <br> count : la valeur souhaitée</p>
  </div>
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
