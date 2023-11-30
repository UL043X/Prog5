<script>
  let hufAmount = 1;
  let euroAmount = 0;
  let usdAmount = 0;

  const convertCurrency = () => {
    const euroRate = 0.0026;
    const usdRate = 0.0029;

    euroAmount = hufAmount * euroRate;
    usdAmount = hufAmount * usdRate;
  };
</script>

<style>
  main {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  }

  h1 {
    font-size: 36px; 
    margin-bottom: 20px;
    color: #008080; 
    font-weight: bold; 
    text-transform: uppercase; 
  }

  label {
    font-size: 16px;
    margin-bottom: 8px;
  }

  input {
    width: 200px;
    padding: 8px;
    font-size: 16px;
    border: 1px solid #ddd;
    border-radius: 4px;
    margin-bottom: 16px;
  }

  button {
    background-color: #4CAF50;
    color: white;
    border: none;
    padding: 10px 20px;
    text-align: center;
    text-decoration: none;
    display: inline-block;
    font-size: 16px;
    border-radius: 4px;
    cursor: pointer;
    transition: background-color 0.3s ease;
  }

  button:hover {
    background-color: #45a049;
  }

  .conversion-results {
    margin-top: 20px;
    text-align: center;
  }

  p {
    font-size: 18px;
    margin: 8px 0;
  }
</style>

<main>
  <h1>HUF Currency Converter</h1>

  <label for="hufAmount">HUF Amount:</label>
  <input type="number" id="hufAmount" bind:value={hufAmount} />

  <button on:click={convertCurrency}>Convert</button>

  <div class="conversion-results">
    <h2>Converted Amounts:</h2>

    <p>EUR: {euroAmount.toFixed(2)} Euro</p>
    <p>USD: {usdAmount.toFixed(2)} US Dollar</p>
  </div>
</main>
