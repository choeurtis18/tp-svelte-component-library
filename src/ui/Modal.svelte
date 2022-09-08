<script>
	import { createEventDispatcher } from 'svelte';

	export let closeIcon = "M11.2614 22.5747L16.9698 16.9699M16.9698 16.9699L22.6782 11.365M16.9698 16.9699L22.5747 22.6782M16.9698 16.9699L11.365 11.2615"

	const dispatch = createEventDispatcher();
	const close = () => dispatch('close');

	let modal;

</script>

<div class="modal-background" on:click={close}></div>

<div class="modal" role="dialog" aria-modal="true" bind:this={modal}>
	<div style="display: inline-flex; align-items: center;">
		<slot class="header-modal" name="header"></slot>
		<button class="close-modal" on:click={close}>
			<svg class="icon" width="20" height="20" stroke="white" stroke-width="2" stroke-linecap="round" fill="none" viewBox="0 0 34 34">
				<path d={ closeIcon } fill="white" />
			</svg>
		</button>
	</div>
	<hr>

	<div class="content-modal">
		<slot name="content"></slot>
	</div>
</div>

<style>
	.modal-background {
		position: fixed !important;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: rgba(0,0,0,0.3);
	}

	.modal {
		background-color: #F6DFD5 !important;
		border: 1px solid #323031;
		position: fixed !important;
		left: 50%;
		top: 50%;
		width: calc(100vw - 4em);
		max-width: 32em;
		max-height: calc(100vh - 4em);
		overflow: auto;
		transform: translate(-50%,-50%);
		padding: 2em;
		border-radius: 1em;
		background: white;
	}

    .content-modal {
		padding-inline-end: 15px;
		font-family: "Avenir", sans-serif;
    	font-size: 18px;
    	color: #394756;
    }

	.close-modal {
		background-color: #7380ec;
        padding: 10px;
        border-radius: 60%;
        border: none !important;
        display: flex;
		height: 40px;
		margin-left: 85px;
        justify-content: center;
        align-items: center;
	}
</style>