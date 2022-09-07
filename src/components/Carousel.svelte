<script>
import { flip } from "svelte/animate";
// @ts-ignore
import { FontAwesomeIcon, FontAwesomeLayers, FontAwesomeLayersText } from 'fontawesome-svelte';
// @ts-ignore
import Fa from 'svelte-fa'
// @ts-ignore
import { faChevronRight } from '@fortawesome/free-solid-svg-icons'
// @ts-ignore
import { faChevronLeft } from '@fortawesome/free-solid-svg-icons'



    export let images;
    export let speed = 500;

    const suivant = e => {
        const transition = images[0]
        // @ts-ignore
        document.getElementById(transition.id).style.opacity = 0 ; 
        images= [images[images.length -1],...images.slice(0,images.length -1)]
        // @ts-ignore
        setTimeout(() =>{ document.getElementById(transition.id).style.opacity = 1}, speed ) ;
    }

    const precedent = e => {
        const transition = images[images.length -1]
        // @ts-ignore
        document.getElementById(transition.id).style.opacity = 0 ;
        images= [...images.slice(1,images.length),images[0]]
        // @ts-ignore
        setTimeout(() =>{ document.getElementById(transition.id).style.opacity = 1}, speed ) ;
    }
</script>

<div id="Carousel-container">

    <div id="Carousel-img">
        {#each images as image (image.id)} 
            <img src={image.path} alt={image.id} id={image.id} 	animate:flip="{{duration: speed}}" >
        {/each}
    </div>
    <button id="left" on:click={suivant}>  <Fa icon={faChevronLeft} />     </button>
     
    <button id="rigth" on:click={precedent}>    <Fa icon={faChevronRight} />     </button>
    
</div>

<style>

#Carousel-container{
    width: 70%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    overflow: hidden;
    margin: auto;
}

#Carousel-img img{
    width: 450px;
    margin: 0 20pX;
}

#Carousel-img{
    display: flex;
    justify-content: center;
    align-items: center;
    flex-wrap: nowrap;
    -webkit-mask: linear-gradient(to right,transparent,black 40%,black 60%,transparent);
    mask:linear-gradient(to right,transparent,black 40%,black 60%,transparent) ;
}

#left,#rigth{
    position: absolute;
    WIDTH: 30px;
    height: 50px;
}
#left{
    margin-left: -50px;
}

#rigth{
    margin-left: 900px;
}


</style>

