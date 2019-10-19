<script>
  import Member from "../components/Member.svelte";
  const members = [{
    name: "Maya Shavin",
    github: "mayashavin"
  }, {
    name: "Tamas Piros",
    github: "tpiros"
  }];
</script>
<svelte:head>
	<title>About</title>
</svelte:head>
<div class="flex flex-col items-center mt-10">
  <h1 class="text-2xl text-center pb-2 border-b-2">About the project</h1>
  <p class="pt-2">This project is currently maintained by:</p>
  <div class="my-3 mx-2">
   {#each members as member}
    <Member member={member}/>
    {/each}
  </div>
</div> 