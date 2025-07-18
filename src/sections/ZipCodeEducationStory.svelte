<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import { Chart } from "@highcharts/svelte";

    // Median household income data (2023, from Black Wealth Data Center and census sources)
    const chartOptions = {
        chart: {
            type: "column",
        },
        title: {
            text: "Median Household Income by Chicago Zip Code (2023)",
        },
        xAxis: {
            categories: ["60654 (River North)", "60620 (Auburn Gresham)"]
        },
        yAxis: {
            min: 0,
            title: {
                text: "Median Household Income (USD)"
            }
        },
        series: [{
            type: 'column',
            name: "Median Income",
            data: [144831, 48805],
            colorByPoint: true
        }],
        legend: {
            enabled: false
        },
        tooltip: {
            pointFormat: '<b>${point.y:,.0f}</b>'
        }
    };

    // Graduation rates data for the two zip codes
    const gradChartOptions = {
        chart: {
            type: 'column',
        },
        title: {
            text: 'High School Graduation Rate by Zip Code',
        },
        xAxis: {
            categories: ['60654 (Ogden International)', '60620 (Harlan Community Academy)']
        },
        yAxis: {
            min: 0,
            max: 100,
            title: {
                text: 'Graduation Rate (%)'
            }
        },
        series: [{
            type: 'column',
            name: 'Graduation Rate',
            data: [95, 65],
            colorByPoint: true
        }],
        legend: {
            enabled: false
        },
        tooltip: {
            pointFormat: '<b>{point.y}%</b>'
        }
    };
</script>

<div>
    <Scroller layout="right">
        {#snippet sticky()}
            <h2>How does a student's zip code in Chicago impact the quality of education?</h2>
        {/snippet}

        {#snippet scrolly()}
            <ArticleText>
                <strong>Introduction</strong><br/>
                In Chicago, where a student lives can shape their educational journey. The city is divided into many neighborhoods, each with its own zip code—and each zip code can mean a very different school experience.
            </ArticleText>

            <ArticleText>
                <strong>Observation</strong><br/>
                Schools in wealthier zip codes often have more resources: newer textbooks, advanced classes, and extracurriculars. Meanwhile, schools in less affluent areas may struggle with outdated materials and fewer opportunities. This difference is largely due to how schools are funded—often by local property taxes, which vary greatly from one zip code to another.
            </ArticleText>

            <div style="width: 80%; margin: 2rem auto;">
                <Chart options={chartOptions} />
                <div style="text-align: center; font-size: 0.95em; color: #555; margin-top: 0.5rem;">
                    <em>Median household income in 2023: $144,831 (60654, River North) vs $48,805 (60620, Auburn Gresham).<br/>Source: Black Wealth Data Center, US Census Bureau</em>
                </div>
            </div>

            <div style="width: 80%; margin: 2rem auto;">
                <Chart options={gradChartOptions} />
                <div style="text-align: center; font-size: 0.95em; color: #555; margin-top: 0.5rem;">
                    <em>Graduation rates: 95% (Ogden International, 60654) vs 65% (Harlan Community Academy, 60620).<br/>Source: Chicago Public Schools, Illinois Report Card</em>
                </div>
            </div>

            <ArticleText>
                <strong>Conclusion</strong><br/>
                Where you grow up, your zip code, can reveal a lot about your family's financial background. In Chicago, neighborhoods with higher household incomes often have better-funded schools, thanks to local property taxes. This means students in wealthier zip codes benefit from more resources, advanced classes, and extracurriculars, while those in less affluent areas may face greater challenges. Your zip code, shaped by income and tax base, can make a big difference in the quality of education you receive and in the opportunities available to you.
            </ArticleText>
        {/snippet}
    </Scroller>
</div> 