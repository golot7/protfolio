<script context="module">
    const allSnippet = import.meta.glob("./*.md");
    let body = [];
    for (let path in allSnippet) {
     body.push(
      allSnippet[path]().then( ({metadata}) => {
       return { path, metadata}
      })
     );  
    }

    export async function load() {
     const snippets = await Promise.all(body);
   return {
    props: {snippets}
   }
 }
</script>

<script>
    export let snippets;
</script>


<main>
    <h2>
        تکه کدها
    </h2>
    <h3 class="">
        اینها مجموعه ای از کدهایی  که من در گذشته استفاده کرده و ذخیره کرده ام. و ممکنه دوباره نیاز داشته باشم و ممکنه شما هم نیاز داشته باشید
    </h3>
    <section>
        {#each snippets as { metadata: {title,sum,image,url}} }
        <a href="/snippets/{url}" class="snippet">
            <img src="/images/{image}" alt="">
            <p class="title">{title}</p>
            <p class="body">{sum}</p>
        </a>
        {/each}
    </section>
</main>

<style>
    h2 {
        margin: 3rem 0 1rem 0;
        font-size: 28px;
        font-weight: 600;
    }

    h3 {
        font-weight: 300;
        font-size: 1rem;
        opacity: .7;
        margin: 0;
    }

    section{
        display: grid;
        grid-gap: 1.25rem;
        grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
        margin-top: 3rem;
    }
    .snippet {
        border:3px solid rgba(34, 34, 34,.1);
        box-shadow: 0 .5rem 1rem rgba(0, 0, 0, .05);
        padding: 1rem;
        border-radius: .5rem;
        background-color: #fff;
        cursor: pointer;
        transition: .5s all;
    }

    .snippet:hover {
        background-color: rgba(150, 150, 150, .05);
    }

    :global(body.dark-mode) .snippet:hover {
        background-color: rgba(255, 255, 255, .025);

    }

    :global(body.dark-mode) .snippet {
        background-color: inherit;
        border:3px solid rgb(34, 34, 34,.6);

    }

    img {
        background-color: rgba(255, 255, 255,.95);
        padding: .25rem;
        border-radius: 50%;
        width: 2rem;
        background-position: center;
        background-size: contain;
    }

    .title {
        font-size: 20px;
        font-weight: 600;
        margin: .25rem 0;
    }
    .body {
        font-size: 1rem;
        opacity: .7;

    }

</style>