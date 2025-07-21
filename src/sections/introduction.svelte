<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <h2 style="text-align: center;">How does a student's zip code in Chicago impact the quality of education?</h2>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <div style="text-align: center;">
                    <strong>Introduction</strong><br/>
                    In Chicago, where a student lives can shape their educational journey. The city is divided into many neighborhoods, each with its own zip code, and each zip code can mean a very different school experience. This section introduces the idea that a student's zip code can have a big impact on the quality of education they receive.
                </div>
            </ArticleText>
        {/snippet}
    </Scroller>
</div> 