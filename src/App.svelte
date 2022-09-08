<script>
  import Card from './ui/Card.svelte';
  import Tooltip from './ui/Tooltip.svelte';
  import Salescard from './ui/Salescard.svelte';
  import Rangeslider from './ui/Rangeslider.svelte';
  import Progress from './ui/Progress.svelte';
  import Input from './ui/Input.svelte';
  import Range from './ui/Range.svelte';
  import Carousel from './ui/Carousel.svelte';
  import Tabs from './ui/Tabs.svelte';
  

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
    <p>Ce composant est une card permettant d'afficher les informations d'un compte bancaire de façon dynamique !</p>
    <br>
    <p>Différents props sont disponibles : </p>
    <ul>
      <li>title</li>
      <li>subtitle</li>
      <li>subtitle</li>
      <li>currency</li>
      <li>price</li>
      <li>progressValue : à quelle valeur commence l'animation</li>
      <li>progressEndValue : à quelle valeur doit on finir l'animation</li>
      <li>animationSpeed : à quelle vitesse exécuter l'animation</li>
      <li>slot = icon</li>
    </ul>
  </div>
  <Salescard 
    animationSpeed = { 60 }
    progressValue = { 0 }
    progressEndValue = { 60 }>
</Salescard>
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
  <div class="container_item">
  <h2>Composant Cards</h2>
  </div>

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

<div class="component_container carousel_container">
  <div class="container_item carousel_item">
  <h2>Component Carousel</h2>
  <p>Ce composant permet de mettre en avant vos images.</p>
  <p>Props utilisés : <br> images : tableau d'images </p>
  </div>
  
  <Carousel {images}>

  </Carousel>

</div>  

<div class="component_container tabs_container">
  <div class="container_item tabs_item">
    <h2>Component Tabs</h2>
    <p>Ce composant permet de créer une tab de navigation afin de naviguer entre différents contenus.</p>
    <p>Props utilisés : <br> titles: liste des titres de tabs <br> contents: liste des contenus à afficher selon chaque tab</p>
  </div>
  
  <Tabs titles={titles} contents={contents}></Tabs>
</div>  
