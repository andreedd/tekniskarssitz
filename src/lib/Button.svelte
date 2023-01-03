<script>
    export let buttonUrl;
    export let buttonText;
    export let useModal;
    import Modal from './Modal.svelte';

    let showModal = false;
</script>

{#if useModal}
<a class="fancy" on:click="{() => showModal = true}">
    <span class="top-key"></span>
    <span class="text">{buttonText}</span>
    <span class="bottom-key-1"></span>
    <span class="bottom-key-2"></span>
</a>
{:else}
<a class="fancy" href={buttonUrl}>
    <span class="top-key"></span>
    <span class="text">{buttonText}</span>
    <span class="bottom-key-1"></span>
    <span class="bottom-key-2"></span>
</a>
{/if}

{#if showModal}
	<Modal on:close="{() => showModal = false}">
		<h2 slot="header">
			Teknisk Årssitz
		</h2>
        <p>Den Tekniska årssitzen är en finare sitz som årligen ordnas av TFiFs studerandeutskott De yngres råd (DYR).</p>
        <p>Sitzen ordnas vartannat år i Helsingfors och vartannat år i Åbo.</p>
        <p>Bland deltagarna hittas bl.a. medlemmar från Teknologföreningen, Kemistklubben, Datateknologerna, Spektrum, Entech, Quantum, Sigma och Infå.</p>
        <p>Sitzen är ämnad för de som är i slutskedet av studierna och de som nyligen blivit utexaminerade, men alla TFiF-medlemmar är ändå välkomna!</p>
	</Modal>
{/if}


<style>
    /* From uiverse.io */
    .fancy {
    margin-top: 10px !important;
    border-radius: 5px !important;
    background-color: transparent;
    border: 2px solid #dfaf5d;
    border-radius: 0;
    box-sizing: border-box;
    color: red;
    cursor: pointer;
    display: inline-block;
    float: right;
    font-weight: 700;
    letter-spacing: 0.05em;
    margin: 0;
    outline: none;
    overflow: visible;
    padding: 1.25em 2em;
    position: relative;
    text-align: center;
    text-decoration: none;
    text-transform: none;
    transition: all 0.3s ease-in-out;
    user-select: none;
    font-size: 13px;
    }

    .fancy::before {
    content: " ";
    width: 1.5625rem;
    height: 2px;
    background: #dfaf5d;
    top: 50%;
    left: 1.5em;
    position: absolute;
    transform: translateY(-50%);
    transform-origin: center;
    transition: background 0.3s linear, width 0.3s linear;
    }

    .fancy .text {
    font-size: 1.125em;
    line-height: 1.33333em;
    padding-left: 2em;
    display: block;
    text-align: left;
    transition: all 0.3s ease-in-out;
    text-transform: uppercase;
    text-decoration: none;
    color: #dfaf5d;
    }

    .fancy .top-key {
    height: 2px;
    width: 1.5625rem;
    top: -2px;
    left: 0.625rem;
    position: absolute;
    background: white;
    transition: width 0.5s ease-out, left 0.3s ease-out;
    }

    .fancy .bottom-key-1 {
    height: 2px;
    width: 1.5625rem;
    right: 1.875rem;
    bottom: -2px;
    position: absolute;
    background: #dfaf5d;
    transition: width 0.5s ease-out, right 0.3s ease-out;
    }

    .fancy .bottom-key-2 {
    height: 2px;
    width: 0.625rem;
    right: 0.625rem;
    bottom: -2px;
    position: absolute;
    background: #dfaf5d;
    transition: width 0.5s ease-out, right 0.3s ease-out;
    }

    .fancy:hover {
    color: white;
    background: #dfaf5d;
    }

    .fancy:hover::before {
    width: 0.9375rem;
    background: white;
    }

    .fancy:hover .text {
    color: white;
    padding-left: 1.5em;
    }

    .fancy:hover .top-key {
    left: 2px;
    width: 0px;
    }

    .fancy:hover .bottom-key-1,
    .fancy:hover .bottom-key-2 {
    right: 0;
    width: 0;
    }
</style>
  