<script>

export let title = ''; 
export let texte = ''; 
export let position = 'Top'; 

</script>
  <div class="tooltip { position }"> { title }
      <span class="tooltiptext">{ texte }</span>
  </div>


<style>
.tooltip {
  position: relative;
  display: inline-block;
  background-color: #737fec9d;
  color: #fff;
  padding: 5px 20px;
  border-radius: 5px;
  box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 1px 3px 1px;
  font-size: 0.9em;
}

.tooltip:hover {
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  background-color: #737fec;
}

.tooltip .tooltiptext {
  visibility: hidden;
  width: 220px;
  height: 50px;
  background-color: #fff;
  color: #394756;
  border-radius: 6px;
  padding: 10px;
  box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 1px 3px 1px;
}
/* Top tooltip */
.Top .tooltiptext {
    /* Position the tooltip */
    position: absolute;
    z-index: 1;
    bottom: 120%;
    left: 50%;
    margin-left: -120px;
}
.Top .tooltiptext::after {
  content: " ";
  position: absolute;
  top: 100%; /* At the bottom of the tooltip */
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: #fff transparent transparent transparent;
}
/* Right tooltip */
.Right .tooltiptext {
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: -58px;
  left: 57%;
}
.Right .tooltiptext::after {
  content: "";
  position: absolute;
  top: 50%;
  right: 100%;
  margin-top: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent #fff transparent transparent;
}
/* Left tooltip */
.Left .tooltiptext {
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: -58px;
  right: 57%;
}
.Left .tooltiptext::after {
  content: "";
  position: absolute;
  top: 50%;
  left: 100%;
  margin-top: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent transparent transparent #fff;
}
/* Bottom tooltip */
.Bottom .tooltiptext {
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: 120%;
  left: 50%;
  margin-left: -120px;
}
.Bottom .tooltiptext::after {
  content: "";
  position: absolute;
  bottom: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent transparent #fff transparent;
}

.tooltip:hover .tooltiptext {
    visibility: visible;
}
</style>