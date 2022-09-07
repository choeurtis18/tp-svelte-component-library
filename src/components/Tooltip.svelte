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
  background-color: #6083A9;
  color: #fff;
  padding: 5px 20px;
  border-radius: 5px;
  box-shadow: rgba(60, 64, 67, 0.3) 0px 1px 2px 0px, rgba(60, 64, 67, 0.15) 0px 1px 3px 1px;
  border: 1px solid transparent;
}

.tooltip:hover {
  box-shadow: rgba(0, 0, 0, 0.24) 0px 3px 8px;
  background-color: #fff;
  color: #323031;
  border: 1px solid #323031;
}

.tooltip .tooltiptext {
  visibility: hidden;
  width: 120px;
  background-color: #323031;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;
}
/* Top tooltip */
.Top .tooltiptext {
    /* Position the tooltip */
    position: absolute;
    z-index: 1;
    bottom: 120%;
    left: 50%;
    margin-left: -60px;
}
.Top .tooltiptext::after {
  content: " ";
  position: absolute;
  top: 100%; /* At the bottom of the tooltip */
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: black transparent transparent transparent;
}
/* Right tooltip */
.Right .tooltiptext {
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: -38px;
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
  border-color: transparent black transparent transparent;
}
/* Left tooltip */
.Left .tooltiptext {
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: -38px;
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
  border-color: transparent transparent transparent black;
}
/* Bottom tooltip */
.Bottom .tooltiptext {
  /* Position the tooltip */
  position: absolute;
  z-index: 1;
  top: 120%;
  left: 50%;
  margin-left: -60px;
}
.Bottom .tooltiptext::after {
  content: "";
  position: absolute;
  bottom: 100%;
  left: 50%;
  margin-left: -5px;
  border-width: 5px;
  border-style: solid;
  border-color: transparent transparent black transparent;
}

.tooltip:hover .tooltiptext {
    visibility: visible;
}
</style>