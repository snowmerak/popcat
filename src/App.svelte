<script>
	const open = 'images/open.png'
	const close = 'images/close.png'
	const sound = 'sounds/pop.mp3'

	let imgSrc = close
	let isPopping = false
	let pop = new Audio(sound)
	pop.volume = 1

	function click() {
		if (isPopping == true) {
			return;
		}
		pop.play()
		imgSrc = open
		isPopping = true
		window.setTimeout(() => {
			imgSrc = close
			isPopping = false
		}, 100)
	}
</script>

<main>
	<img src={imgSrc} alt="popcat" on:click={click} />
</main>

<style>
	img {
		background-color: black;
		width: 100%;
	}
</style>