<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
    import { Chart } from "@highcharts/svelte";

    // Median household income data (2023, from Black Wealth Data Center and census sources)
    const chartOptions = {
        chart: {
            type: 'column',
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
                <strong>Income Comparison</strong><br/>
                The median household income in River North (60654) is $144,831, while in Auburn Gresham (60620) it is $48,805. This large gap in income can translate to significant differences in school funding and resources.
            </ArticleText>

            <div style="width: 80%; margin: 2rem auto;">
                <Chart options={chartOptions} />
                <div style="text-align: center; font-size: 0.95em; color: #555; margin-top: 0.5rem;">
                    <em>Median household income in 2023: $144,831 (60654, River North) vs $48,805 (60620, Auburn Gresham).<br/>Source: Black Wealth Data Center, US Census Bureau</em>
                </div>
            </div>

            <ArticleText>
                <strong>School Report Card: 60654 (River North)</strong><br/>
                <u>Ogden International School of Chicago (East Campus)</u><br/>
                <ul>
                  <li><b>Address:</b> 24 W Walton St, Chicago, IL 60610</li>
                  <li><b>Grades:</b> K-5 (East Campus), 6-12 (West Campus)</li>
                  <li><b>GreatSchools Rating (2023):</b> 7/10 (Elementary), 7/10 (Middle), 8/10 (High School)</li>
                  <li><b>CPS SQRP:</b> Level 1+ (highest rating, last published 2020)</li>
                </ul>
                Ogden International is a well-rated public school, with above-average test scores and a diverse student body. It is considered one of the stronger public schools in central Chicago.
            </ArticleText>

            <ArticleText>
                <strong>School Report Card: 60620 (Auburn Gresham)</strong><br/>
                <u>Harlan Community Academy High School</u><br/>
                <ul>
                  <li><b>Address:</b> 9652 S. Michigan Ave, Chicago, IL 60628 (serves 60620)</li>
                  <li><b>Grades:</b> 9-12</li>
                  <li><b>Graduation Rate (2023):</b> 65%</li>
                  <li><b>CPS SQRP:</b> Level 2 (last published 2020)</li>
                </ul>
                Harlan Community Academy is a neighborhood public high school in Auburn Gresham. Its graduation rate is significantly lower than schools in wealthier areas, reflecting the challenges faced by schools in under-resourced communities.
            </ArticleText>

            <div style="width: 80%; margin: 2rem auto;">
                <Chart options={gradChartOptions} />
                <div style="text-align: center; font-size: 0.95em; color: #555; margin-top: 0.5rem;">
                    <em>Graduation rates: 95% (Ogden International, 60654) vs 65% (Harlan Community Academy, 60620).<br/>Source: Chicago Public Schools, Illinois Report Card</em>
                </div>
            </div>
        {/snippet}
    </Scroller>
</div> 