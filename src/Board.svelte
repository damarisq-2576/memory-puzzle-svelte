<script>
  import Flex from "svelte-flex";
  import ClickCard from './ClickCard.svelte';
    let generatedCards = shuffleCards();
  function shuffleCards() {
    let list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 9, 8, 7, 6, 5, 4, 3, 2, 1];
    let ctr = list.length,temp,index;
    while (ctr > 0) {
      index = Math.floor(Math.random() * ctr);
      ctr--;
      temp = list[ctr];
      list[ctr] = list[index];
      list[index] = temp;
    }
    return list;
  }


  
</script>


<ClickCard cards={generatedCards} />

