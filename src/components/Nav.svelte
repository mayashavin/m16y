<script>
// import { createEventDispatcher } from 'svelte';
import Logo from './Logo.svelte';
import { stores } from '@sapper/app';

const { page } = stores();
  
const title = "The M16Y Project"; 

const routes = [{
    title: 'about', link: 'about'
  }, {
    title: 'documentation', link: 'documentation'
  }, {
	title: 'github', link: 'https://github.com/mayashavin/m16y',
  }];

let currRoute = page.path || "";
const setRoute = e => {
	const title = e.target.getAttribute('data-link');
	if (currRoute !== title) {
		currRoute = title;
	}
}
</script>
<nav class="shadow-xl w-full p-3 flex justify-between bg-gray-200">
  <a class="flex items-center" href="/" on:click={setRoute} data-link="">
    <Logo width={30} height={30}/>
    <h1 class="ml-2 text-xl">{title}</h1>
  </a>
  <div class="flex items-center">
  {#each routes as {title, link}}
    <a class="uppercase mx-1 py-2 px-3 border-b-2 { currRoute === title ? 'border-blue-200' : 'border-transparent' } hover:border-blue-200 "
		href={link}
		on:click={setRoute}
		rel=prefetch
		data-link={link}>{title}</a>
  {/each}
  </div>
</nav>