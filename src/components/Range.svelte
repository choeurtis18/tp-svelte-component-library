<script>
  let paiement_range = 1700;
  let retrait_range = 500;
  
  </script>

<div class="cadre"></div>

  <div class="slide_container">

    <div class="slide_item">
      <div class="slide_title">
        <p>Modifier mon plafond de paiement</p>
      </div>
      <div class="slide_range">
        <input type="range" min="600" max="3000" bind:value={ paiement_range } class="slider" id="myRange">
        <span>{paiement_range}</span>
      </div>
    </div>

    <div class="slide_item">
      <div class="slide_title">
        <p>Modifier mon plafond de retrait</p>
      </div>
      <div class="slide_range">
        <input type="range" min="200" max="1500" bind:value={ retrait_range } class="slider" id="myRange">
        <span>{retrait_range}</span>
      </div>
    </div>
    
  </div>

  <style>
    .slide_container {
      padding: 2em 4em;
      background: #fff;
      border-radius: 10px;
      box-shadow: rgba(50, 50, 93, 0.25) 0px 6px 12px -2px, rgba(0, 0, 0, 0.3) 0px 3px 7px -3px;
      position: absolute;
      text-transform: capitalize;
    }
    .slide_container p {
      font-size: 1em;
      font-weight: 600;
      color: #323031;
      margin: 0 0 15px 0 ;
      padding-bottom: 10px;
    }
    .slide_item:first-child {
      margin-bottom: 40px;
    }
    .slide_range {
      display: flex;
      align-items: center;
    }
    .slide_container span {
      font-size: 0.8em;
      color: #394756;
      width: 20%;
      text-align: right;
    }
    .slide_range input {
      -webkit-appearance: none;
      width: 80%;
      height: 2px;
      border-radius: 2px;
      background: #000;
      outline: none;
      box-shadow: rgba(99, 99, 99, 0.2) 0px 2px 8px 0px;
    }
    .slide_range input::-webkit-slider-thumb {
      -webkit-appearance: none;
      appearance: none;
      width: 17px;
      height: 17px;
      border-radius: 50%;
      background: #6083A9;
      cursor: pointer;
      box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
    }
    .slide_range input::-webkit-slider-thumb:hover {
      box-shadow: rgba(0, 0, 0, 0.35) 0px 5px 15px;
    }
    .cadre {
      border: 1px solid #fff;
      width: 365px;
      height: 222px;
      border-radius: 10px;
      margin-top: -15px;
      margin-left: -30px;
      position: relative;
    }
  </style>