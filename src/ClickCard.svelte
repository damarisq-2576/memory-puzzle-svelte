<script>
  import Flex from "svelte-flex";
  export let cards = {};
  var turnos = 2;
  let generatedCards = cards;
  let current = -1, current2 = -1;
  let arr1, arr2, arr3, arr4, cont;
  arr1 = generatedCards.slice(0, 5);
  arr2 = generatedCards.slice(5, 10);
  arr3 = generatedCards.slice(10, 15);
  arr4 = generatedCards.slice(15, 20);

  //split array to draw it
  generatedCards.forEach(function(value, i) {
    // if (i >= 0 && i < 6) {
    //   arr1 = [...value]
    // }
    // if (i >= 6 && i < 11) {
    //   arr2.push(val);
    // }
    // if (i >= 11 && i < 16) {
    //   arr3.push(val);
    // }
    // if (i >= 16 && i < 20) {
    //   arr4.push(val);
    // }
  });
  console.log("InitCards", cards);
  let length = 0;

  function rotateCard(card, id, e) {
    turnos--;
    if (turnos == 1) current = id;
    if (turnos == 0) current2 = id;
   
   // Add validation between cards
 
 
  }
</script>

<style>
  .card {
    background-color: transparent;
    height: 150px;
    width: 120px;
    border: darkblue 3px solid;
    perspective: 1000px; /* Remove this if you don't want the 3D effect */
    margin: 15px 0px;
  }

  .card-body {
    position: relative;
    width: 100%;
    height: 100%;
    text-align: center;
    transition: transform 0.6s;
    transform-style: preserve-3d;
    box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2);
  }

  .flipped {
    transform: rotateY(180deg);
  }
  /* Position the front and back side */
  .card-front,
  .card-reverse {
    position: absolute;
    width: 100%;
    height: 100%;
    -webkit-backface-visibility: hidden; /* Safari */
    backface-visibility: hidden;
    justify-content: center;
    display: flex;
    align-items: center;
  }

  /* Style the card-front side (fallback if image is missing) */
  .card-front {
    background-color: cadetblue;
    z-index: -100;
  }

  /* Style the back side */
  .card-reverse {
    background-color: goldenrod;
    color: white;
    transform: rotateY(180deg);
  }
</style>

<Flex direction="row" justify="">
  {#each arr1 as card, i}
    <div class="card">

      <div
        class="card-body {current === (length + i) ? 'flipped' : current2 === (length + i )? 'flipped' : ''}"
        on:click={event => rotateCard(card, length + i, event)}
        id={length + i}>

        <div class="card-front">Otherside</div>
        <div class="card-reverse">
          <h3 class="card-content">{card}</h3>
        </div>
      </div>

    </div>
  {/each}
</Flex>

<Flex direction="row" justify="">

  {#each arr2 as card, i}
    <div class="card">

      <div
        class="card-body"
        on:click={event => rotateCard(card, length + 5 + i, event)}
        id={length + 5 + i}>

        <div class="card-front">Otherside</div>
        <div class="card-reverse">
          <h3 class="card-content">{card}</h3>
        </div>
      </div>

    </div>
  {/each}

</Flex>
<Flex direction="row" justify="">

  {#each arr3 as card, i}
    <div class="card">

      <div
        class="card-body"
        on:click={event => rotateCard(card, length + 10 + i, event)}
        id={length + 10 + i}>

        <div class="card-front">Otherside</div>
        <div class="card-reverse">
          <h3 class="card-content">{card}</h3>
        </div>
      </div>

    </div>
  {/each}

</Flex>
<Flex direction="row" justify="">

  {#each arr4 as card, i}
    <div class="card">

      <div
        class="card-body"
        on:click={event => rotateCard(card, length + 15 + i, event)}
        id={length + 15 + i}>

        <div class="card-front">Otherside</div>
        <div class="card-reverse">
          <h3 class="card-content">{card}</h3>
        </div>
      </div>

    </div>
  {/each}

</Flex>
