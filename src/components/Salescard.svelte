<script>
let progressBar = document.querySelector(".circular-progress");

export let progressValue = 0;
export let progressEndValue = 100;
export let animationSpeed = 50;
export let price = '503.40';
export let currency = '€';
export let title = 'Compte principal';
export let subtitle = 'Solde de votre compte';
export let svgPath = 'm8 0 6.61 3h.89a.5.5 0 0 1 .5.5v2a.5.5 0 0 1-.5.5H15v7a.5.5 0 0 1 .485.38l.5 2a.498.498 0 0 1-.485.62H.5a.498.498 0 0 1-.485-.62l.5-2A.501.501 0 0 1 1 13V6H.5a.5.5 0 0 1-.5-.5v-2A.5.5 0 0 1 .5 3h.89L8 0ZM3.777 3h8.447L8 1 3.777 3ZM2 6v7h1V6H2Zm2 0v7h2.5V6H4Zm3.5 0v7h1V6h-1Zm2 0v7H12V6H9.5ZM13 6v7h1V6h-1Zm2-1V4H1v1h14Zm-.39 9H1.39l-.25 1h13.72l-.25-1Z'

let progress = setInterval(() => {
    if (progressValue === progressEndValue - 1) {
      clearInterval(progress);
    }
    progressValue = progressValue + 1;
}, animationSpeed);

</script>
<div class="container">
    <div class="card">
        <div class="icon">
            <svg width="30" height="30" fill="currentColor" viewBox="0 0 16 16">
                <path d={ svgPath } />
            </svg>
        </div>
        <div class="middle">
            <div class="left-side">
                <h2>{ title }</h2>
                <h3>{ price }{ currency }</h3>
            </div>
            <div class="circular-progress" style="background:conic-gradient(
                #7380ec { progressValue * 3.6}deg,
                #cadcff {progressValue * 3.6}deg;">
                <div class="value-container">{ progressValue }%</div>
            </div>
        </div>
        <small class="text-muted">{ subtitle }</small>
    </div>
</div>


<style>
    @font-face {
    font-family: 'Ranade-Variable';
    src: url('../fonts/Ranade-Variable.woff2') format('woff2'),
       url('../fonts/Ranade-Variable.woff') format('woff'),
       url('../fonts/Ranade-Variable.ttf') format('truetype');
       font-weight: 100 700;
       font-display: swap;
       font-style: normal;
    }


    .card{
        margin-top: 1.4rem;
        font-family: 'Ranade-Variable'; 
        padding: 1.5rem 2rem;
        border-radius: 2rem;
        background-color: white;
        box-shadow: 0 2rem 3rem rgba(132, 139, 200, 0.18);
        width: 350px;
        transition: all 300ms ease;
        font-family: 'Ranade-Variable';
        position: relative;
        border: 2px solid rgba(132, 139, 200, 0.18);
    }

    .card:hover{
        box-shadow: none;
    }
    .icon
    {
        background-color: #7380ec;
        padding: 1rem;
        border-radius: 30%;
        width: 35px ;
        height: 35px;
        display: flex;
        justify-content: center;
        align-items: center;
    }
    .icon svg{
        fill: white;
    }
    .left-side h2
    {
        font-size: 1rem;
        margin: 1rem 0 0.6rem;
        font-weight:400;
        color: #394756;
    }
    .left-side h3
    {
        font-size: 2rem;
        margin: 0;
    }

    .middle
    {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
        
    .circular-progress {
    position: relative;
    height: 90px;
    width: 90px;
    border-radius: 50%;
    display: grid;
    place-items: center;
    padding: 1rem;
    }
    .circular-progress:before {
    content: "";
    position: absolute;
    height: 84%;
    width: 84%;
    background-color: #ffffff;
    border-radius: 50%;
    }
    .value-container {
    position: relative;
    font-family: "Poppins", sans-serif;
    font-size: 2rem;
    color: #231c3d;
    }

    .text-muted
    {
        color: #394756;
    }
</style>