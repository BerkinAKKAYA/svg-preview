<script>
    let svg = "<svg></svg>";

    $: svg = svg.trim();
    $: color = svg.startsWith("<svg") && svg.endsWith("</svg>") ? "black" : "red";
    $: html = color == "black" ? svg : "Invalid SVG";
</script>

<main>
    <textarea id="input" bind:value={svg} spellcheck="false" style="color: {color}"></textarea>
    <div id="output">{@html html}</div>
</main>

<style>
    main { width: 100%; height: 100%; display: grid; grid-template-columns: 1fr 1fr; gap: 20px; padding: 20px }
    #input, #output { width: 100%; height: 100%; padding: 20px; border: 1px solid #ccc }
    #input { transition: border-color .2s ease }
    #input:hover { border-color: #999 }
    #input:focus { border-color: #000 }
</style>