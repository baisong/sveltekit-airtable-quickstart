<script>
    import Airtable from 'airtable';
    import { shouldListRecordsParamBePassedAsParameter } from 'airtable/lib/query_params';
import { each } from 'svelte/internal';

    /** @type {import('./$types').PageData} */
	export let data;
</script>

<svelte:head>
	<title>Airtable</title>
	<meta name="description" content="Svelte airtable demo" />
</svelte:head>

<section>
	<h1>Airtable demo: almost there!</h1>

    <h3>Configuration steps:</h3>
	<ol>
        <li>Copy <pre>.env.example</pre> to <pre>.env</pre></li>
		<li>Replace the example values with your actual API Key and Base ID in .env from <a href="https://airtable.com/api" target="_blank" rel="noreferrer">https://airtable.com/api</a></li>
        <li>Try editing <strong>src/routes/airtable/+page.svelte</strong> to get your actual records and fields to display in the list below</li>
    </ol>

    <div>...That's it! You'd probably like to look at <strong>src/routes/airtable/+page.server.js</strong> to see how <pre>data</pre> is loaded.</div>
    
    <h3><pre>data.records</pre> length: {data.records.length}</h3>
    <ol>
        {#each data.records as record}
            <!-- Note: field names are case sensitive-->
            <li>{record["Name"]}</li>
        {/each}
    </ol>
</section>

<style>
    pre {
        display: inline
    }
    li {
        margin: 0.25em;
    }
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 0.6;
	}

	h1 {
		width: 100%;
	}
</style>
