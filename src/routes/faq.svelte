<script>
    let faqs = [
        {
            q: "Is the Souls DAO run by the Solana Souls owners?",
            a: "No, we are a group of friends who were excited by the good soul vibes around the community and decided to share some of our love and respect for this growing family!"
        }, {
            q: "How can I be a part of the Soul DAO community?",
            a: "Anyone that is verified to be a current Solana Souls holder is welcome to participate and also be a part of the Soul DAO."
        }, {
            q: "What are the plans for the future?",
            a: "As DAO decisions will be driven by you, the community! A polling system will help us to decide how to drive the DAO community."
        }, {
            q: "How is the DAO going to be governed?",
            a: "A perk of being a soul holder is having a voice in a community! Our DAO is going to be self-governed by the vote of every Solana Souls holder."
        }
    ];
</script>

<div class="container mx-auto flex flex-col items-center my-12 mt-24 max-w-screen-lg">
    <div class="mb-5 font-thin xl:text-8xl text-5xl text-white">FAQ</div>
</div>
<div class="container mx-auto flex flex-col items-left mb-24 max-w-screen-lg">
    {#each faqs as faq}
        <div class="xl:m-10 m-5 px-5">
            <div class="xl:mb-5 mb-2 font-medium xl:text-3xl text-2xl text-white">{faq.q}</div>
            <div class="pl-5 xl:text-xl font-light text-white">{faq.a}</div>
        </div>
    {/each}
</div>