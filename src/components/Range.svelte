<script>
  export let range = "1700";
  export let minValue = "600";
  export let maxValue = "3000";
  
  </script>



    <div class="slide_item">
      <div class="slide_title">
        <p>Modifier mon plafond de paiement</p>
      </div>
      <div class="slide_range">
        <input type="range" min={ minValue } max={ maxValue } bind:value={ range } class="slider" id="myRange">
        <span>{range}</span>
      </div>
    </div>
    
 

  <style>
    
    .slide_item:first-child {
      margin-bottom: 40px;
    }
    .slide_range {
      display: flex;
      align-items: center;
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
  </style>