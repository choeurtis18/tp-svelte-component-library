<script>
export let value = 0;
export let maxValue = 100;
export let minValue = 0;
const slider = (e)=> {
    value = e.target.value;
}
</script>

<input type="range" id="my-slider" style="background = linear-gradient(to right, #3264fe { value }%, #d5d5d5 { value }%" value={ minValue } min={ minValue } max={ maxValue } on:input = { slider }>
{#if value <= 0 }
    <div id="slider-value"> { minValue } </div>
{:else }
    <div id="slider-value"> { value } </div>
{/if}


<style>
    input[type="range"]{
    position: relative;
    -webkit-appearance: none;
    -moz-appearance: none;
    display: block;
    width: 80%;
    height: 8px;
    background-color: #d5d5d5;
    border-radius: 8px;
    outline: none;
}
input[type="range"]::-webkit-slider-runnable-track{
    -webkit-appearance: none;
    height: 8px;
}
input[type="range"]::-moz-track{
    -moz-appearance: none;
    height: 8px;
}
input[type="range"]::-ms-track{
    appearance: none;
    height: 8px;
}
input[type="range"]::-webkit-slider-thumb{
    -webkit-appearance: none;
    height: 20px;
    width: 20px;
    background-color: #7380ec;
    border-radius: 50%;
    cursor: pointer;
    margin-top: -6px;
    border: none;
}
input[type="range"]::-moz-range-thumb{
    -webkit-appearance: none;
    height: 20px;
    width: 20px;
    background-color: #7380ec;
    border-radius: 50%;
    cursor: pointer;
    margin-top: -6px;
    border: none;
}
input[type="range"]::-ms-thumb{
    appearance: none;
    height: 20px;
    width: 20px;
    background-color: #7380ec;
    border-radius: 50%;
    cursor: pointer;
    margin-top: -6px;
    border: none;
}
input[type="range"]:active::-webkit-slider-thumb{
    background-color: #ffffff;
    border: 3px solid #7380ec;
}
#slider-value{
    width: 13%;
    position: relative;
    background-color: #7380ec;
    color: #ffffff;
    text-align: center;
    font-family: "Roboto Mono",monospace;
    padding: 10px 0;
    border-radius: 5px;
}
</style>