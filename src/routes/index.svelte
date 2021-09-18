<script> 
    import { fade } from 'svelte/transition';
    import { onMount } from 'svelte';

    let ready = false;
    onMount(() => ready = true);
    const taglines = [
        "There's no wrong way to slurp a soul.",
        "The coolest souls on ice.",
        "Be young, have fun, slurp souls.",
        "Probably the best souls in the world.",
        "Souls? You bet.",
        "The best souls under one roof.",
        "Wouldn't you like to own a soul too?",
        "Strong and beautiful, just like souls.",
        "Discover the world of souls.",
        "One goal, one passion - souls.",
        "Promise her anything, but giver her souls.",
        "Grab life by the souls.",
        "The passionate pursuit of souls.",
        "What would you do for a soul?",
        "Happiness is soul-shaped.",
        "You can't stop souls.",
        "You don't want souls as your enemy.",
        "Make the world a better place... with souls."
    ];
    const tagline = taglines[Math.floor(Math.random()*taglines.length)];
</script>


{#if ready}
    <div in:fade={{delay: 100}} class="container mx-auto flex flex-col md:flex-row items-center my-12 md:my-24 max-w-screen-lg">
        <!--Left Col-->
        <div class="flex flex-col w-full lg:w-1/2 justify-center items-start pt-12 pb-10 px-14">
            <div>
                <span class="xl:text-8xl text-5xl font-thin text-white">Souls</span><span class="xl:text-8xl text-5xl font-normal text-white">DAO</span>
            </div>
            <h2 class="xl:mt-6 m-4 pl-4 xl:text-xl font-medium text-white">{tagline}</h2>
            <div class="flex pl-10 xl:text-xl">
                <a href="https://discord.com/invite/WMnhjUge"><i class="mx-2 fab fa-discord text-white hover:text-gray-300"></i></a>
                <a href="https://twitter.com/SoulsDAO"><i class="mx-2 fab fa-twitter text-white hover:text-gray-300"></i></a>
            </div>
        </div>
        <!--Right Col-->
        <div class="w-full lg:w-1/2 lg:py-5 text-center">
            <div class="flex justify-center bg-no-repeat bg-center mx-10" style="background-image: url(dao_soul_rb.png);">
                <img width="400" height="400" class="spin" src="circle-soul.png" alt="Soul Circle"/>
            </div>
        </div>
    </div>
{/if}

<style>
    .spin {
    max-width: 400px;
    max-height: 400px;
    width: auto;
    height: auto;
    animation-name: spin;
    animation-duration: 50000ms;
    animation-iteration-count: infinite;
    animation-timing-function: linear;
    }

    @keyframes spin {
        from {
            transform:rotate(0deg);
        }
        to {
            transform:rotate(360deg);
        }
    }
</style>