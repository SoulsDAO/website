<script>
    import "../app.postcss";
    import PageTransition from '$lib/components/PageTransition.svelte';
	import { page } from '$app/stores';

    export let key;

    const pages = [
        {
            label: 'Home',
            link: '/'
        }, {
            label: 'About',
            link: '/about'
        }, {
            label: 'FAQ',
            link: '/faq'
        }
    ]

    let hideMenu = true;
    function toggle() {
        hideMenu = !hideMenu;
    }
    function hide() {
        hideMenu = true;
    }
</script>

<script context="module">
    export const load = async ({ page }) => ({
        props: {
            key: page.path
        }
    });
</script>

<nav class="backdrop-filter backdrop-blur-sm bg-opacity-80 bg-gray-800 fixed w-full p-3 z-10 top-0">
    <div class="flex items-center justify-between flex-wrap">
        <div class="flex items-center flex-shrink-0 text-white mr-6">
            <a class="text-white no-underline hover:text-white hover:no-underline" href="/">
                <img class="h-10" src="dao_soul_bw.png" alt="logo"/>
            </a>
        </div>

        <div class="block md:hidden">
            <button on:click={toggle} class="flex items-center px-3 py-2 border rounded text-gray-300 border-gray-400 hover:text-white hover:border-white">
                <svg class="fill-current h-3 w-3" viewBox="0 0 20 20" xmlns="http://www.w3.org/2000/svg"><title>Menu</title><path d="M0 3h20v2H0V3zm0 6h20v2H0V9zm0 6h20v2H0v-2z"/></svg>
            </button>
        </div>

        <div class:hidden={hideMenu} class="w-full flex-grow md:flex md:items-center md:w-auto md:block pt-6 md:pt-0" id="nav-content">
            <ul class="list-reset md:flex justify-end flex-1 items-center">
                {#each pages as route}
                    <li class="mr-3">
                        {#if route.link == $page.path}
                            <a on:click={hide()} class="inline-block py-2 px-4 text-white no-underline" href={route.link}>{route.label}</a>
                        {:else}
                            <a class="inline-block py-2 px-4 text-gray-400 no-underline hover:text-gray-200 hover:text-underline" href={route.link}>{route.label}</a>
                        {/if}
                    </li>
                {/each}
            </ul>
        </div>
    </div>
</nav>

<div class="pt-14">
    <PageTransition refresh={key}>
        <slot />
    </PageTransition>
</div>