<script>
    let count = 0
    export let posts;

</script>

<section>
    <h2>مقاله های پیشنهادی</h2>
    <aside>
        
    {#each  posts as {path, metadata: {title}} }
        <a href={`/${path.replace(".md","").replace("/data","")}`} class="border_bg article">
            <p>{title}</p>
            <div class="box__icon">
                <div class="icon">
                    <img src="/images/comment.svg" alt="" width="24" height="24">
                <span class="count"> {count.toLocaleString("fa-IR")}</span>
                </div>
               
            </div>
        </a>
   {/each}
  
    </aside>
    <a href="/blog" class="all__posts"> تمام مقالات <span class="larr">&larr</span></a>
</section>



<style>
    h2 {
        font-size: 28px;
        font-weight: 900;
        
    }
    section {
        margin-top: 3rem;

    }
    aside {
        display: flex;
        gap: 2rem;
        margin-top: 1rem;
        
    }

    .border_bg {
        border: 5px solid transparent;
        border-radius: 1rem;
        padding: 16px 12px;
        height: 216px;
        flex: 1 1 100px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        cursor: pointer;
        text-align: start;
        
        

    }

    .border_bg:hover {
        transform: scale(1.015);
        transition: .2s all ;
    }
    :global(body.dark-mode) .article:nth-child(1) {
        background: 
            linear-gradient(to right, #131516, #131516), 
            linear-gradient(to right,#818cf8 , #d8b4fe ); 
            background-clip: padding-box, border-box;
        background-origin: padding-box, border-box; 

        flex: 1 1 100px;

           
    }
    :global(body.dark-mode)  .article:nth-child(2)  {
        background:    
         linear-gradient(to right, #131516, #131516),
        linear-gradient(to right, #3b82fe , #6ee7b7);
        background-clip: padding-box, border-box;
        background-origin: padding-box, border-box;   
    }
    :global(body.dark-mode)  .article:nth-child(3)   {
        background:    
            linear-gradient(to right, #131516, #131516),
            linear-gradient(to right, #fca5a5 , #fde68a);
        background-clip: padding-box, border-box;
        background-origin: padding-box, border-box;  
    }

    .article:nth-child(1)  {

        background: 
            linear-gradient(to right, white, white), 
            linear-gradient(to right,#818cf8 , #d8b4fe );     
        background-clip: padding-box, border-box;
        background-origin: padding-box, border-box;
        
    }

    

    .article:nth-child(2)  {
        background:    
         linear-gradient(to right, white, white),
        linear-gradient(to right, #3b82fe , #6ee7b7);
        background-clip: padding-box, border-box;
        background-origin: padding-box, border-box;
    }

    .article:nth-child(3) {
        background:    
            linear-gradient(to right, white, white),
            linear-gradient(to right, #fca5a5 , #fde68a);
        background-clip: padding-box, border-box;
        background-origin: padding-box, border-box;
    }

    p {
        font-size: 1.25rem;
        line-height: 2rem;
        font-weight: 500;
    }

    .box__icon {
        display: flex;
        justify-content:flex-start;
        align-items: center;
        gap: 1rem;
        
    }

    .count {
        font-size: 20px;
        font-weight: 300;
        text-align: center;
        max-height: 24px;
    }

    .icon {
        display: flex;
        align-items: center;
        gap: 4px;
    }
    :global(body.dark-mode) img {
            filter: invert(98%) sepia(38%) saturate(85%) hue-rotate(06deg) brightness(83%) contrast(100%);
    }
    .all__posts {
        color: #666;
        margin-top: 1.5rem;
        font-size: 1.15rem;
        cursor: pointer;
    }

    .larr {
        font-size: 2rem;
        font-weight: bold;
    }
    .all__posts:hover {
        color: inherit;
        opacity: .8;
    }

    @media (max-width:700px) {
        .border_bg {
            height: 100%;
        }
        aside {
            flex-direction: column;
        }

      
    }
</style>