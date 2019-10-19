<script>
  export let member = {};

  const avatarUrl = `https://github.com/${member.github}.png`
</script>
<article class="flex items-center my-3">
  <div class="w-16 h-16">
    <img src={avatarUrl} alt={member.name} class="rounded-full"/>
  </div>
  <div class="ml-2">
    <h3>{member.name}</h3>
  </div>
</article>