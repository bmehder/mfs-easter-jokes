<svelte:options tag="mfs-easter-jokes" />

<script>
  import { jokeData } from "./jokeData.js";
  import { onMount } from "svelte";
  console.log(jokeData.length);
  let randomNumber = 0;

  const getRandomNumber = () =>
    (randomNumber = Math.floor(Math.random() * jokeData.length));

  onMount(() => getRandomNumber());
</script>

<article>
  <h4>Easter Bunny Jokes 🐣</h4>
  <button on:click={getRandomNumber}>Get Another Joke</button>
  <div>
    <p>{jokeData[randomNumber]}</p>
  </div>
</article>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  article {
    width: 600px;
    margin: auto;
    padding: 2em 3em;
    display: flex;
    flex-direction: column;
    align-items: center;
    background: url("bg.jpg") no-repeat center center/cover;
    font-family: Arial, Helvetica, sans-serif;
    font-size: 1em;
    border-radius: 16px;
  }
  h4 {
    margin: 1em 0;
    color: white;
    font-size: 2em;
    text-align: center;
    text-shadow: 0 0 8px rgba(0, 0, 0, 0.5);
  }
  button {
    width: 100%;
    padding: 1em;
    background: #9386e6;
    outline: none;
    border: none;
    border-radius: 4px;
    font-weight: bold;
    font-size: 1em;
    line-height: 1.5;
    color: white;
    /* box-shadow: 0 2px 4px rgba(255, 255, 255, 0.32); */
    transition: all 400ms;
    text-shadow: 0 0 2px rgba(0, 0, 0, 0.5);
    text-transform: uppercase;
  }
  button:hover {
    background-image: linear-gradient(
      to bottom,
      transparent,
      rgba(0, 0, 0, 0.05)
    );
    box-shadow: none;
  }
  button:focus {
    outline: none;
  }
  div {
    width: 100%;
    min-height: 150px;
    margin: 1em 0;
    padding: 2em;
    background: white;
    background-image: linear-gradient(
      to bottom,
      transparent,
      rgba(0, 0, 0, 0.1)
    );
    color: #333;
    font-size: 20px;
    line-height: 1.5;
    text-align: center;
    border-radius: 4px;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.32);
  }
  p {
    margin-bottom: 0.5em;
  }
</style>
