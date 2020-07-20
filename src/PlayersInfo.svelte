<script>
  import Flex from "svelte-flex";
  let turn = true;
  let whowWin;
  let pts = {
    ptsPlayer1: 0,
    ptsPlayer2: 0
  };
</script>

<Flex direction="row" justify="around">
  <div >
    <h3>Turn:</h3>
    <h4>{turn ? 'Player 1' : 'Player 2'}</h4>
    <div class="alert alert-success">
      <h4>{whowWin}</h4>
    </div>
  </div>
  
  <div >
    <p>Points Player 1:</p>
    <p>{pts.ptsPlayer1}</p>
    <p>Points Player 2:</p>
    <p>{pts.ptsPlayer2}</p>
  </div>
</Flex>
