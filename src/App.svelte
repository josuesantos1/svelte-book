<script>
	import { marked } from 'marked';

	let source = `
# built with svelte

a simple svelte app
	`;

</script>

<main class="container">
	<header class="header">
		<h1 class="header-title">Svelte book</h1>
	</header>

	<div class="markdown-editor">
		<div class="left-panel">
			<textarea bind:value={source} class="source"></textarea>
		</div>

		<div class="right-panel">
			<div class="output">{@html marked(source)}</div>
		</div>
	</div>
</main>

<style>
    main { 
        background: #001628;
        color: #fff;
    }
    .container{
        padding:10px 30px;
        font-family: 'Roboto', sans-serif;
    }
    .header {
        height: 10vh;
        display: flex;
        align-items: center;
        justify-content: center;

    }
    .markdown-editor {
        width: 100%;
        display: flex;
        align-items:flex-start;
        justify-content: space-evenly;
    }
    .left-panel, .right-panel {
        width: 50%;
        border: solid 1px black;
        height: 85vh;
        background: #ffffff;
        color: #001628;
    }
    .right-panel {
        overflow: auto;
    }
    .source {
        border: none;
        width: 100%;
        height: 100%;
        background: #000;
        color: #15a080;
    }
    .source:focus {
        outline: none;
    }
    .output {
        width: 100%;
        padding: 0 2em;
    }

</style>