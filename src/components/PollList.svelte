<script>
  import PollStore from "../stores/PollStore";
  import PollDetails from "./PollDetails.svelte";
</script>

<div class="poll-list">
  {#each $PollStore as poll (poll.id)}
    <div>
      <PollDetails {poll} />
    </div>
  {:else}
    <div class="no-polls">No Polls Found...</div>
  {/each}
</div>

<style>
  .poll-list {
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-gap: 20px;
  }

  .no-polls {
    text-align: center;
    grid-column: span 2;
    font-size: 18px;
  }
</style>
