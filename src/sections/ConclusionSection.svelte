<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <h2>Conclusion: Why Zip Code Matters</h2>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>Conclusion</strong><br/>
                Where you grow up, your zip code, can reveal a lot about your family's financial background. In Chicago, neighborhoods with higher household incomes often have better-funded schools, thanks to local property taxes. This means students in wealthier zip codes benefit from more resources, advanced classes, and extracurriculars, while those in less affluent areas may face greater challenges. Your zip code, shaped by income and tax base, can make a big difference in the quality of education you receive and in the opportunities available to you.
            </ArticleText>
        {/snippet}
    </Scroller>
</div> 