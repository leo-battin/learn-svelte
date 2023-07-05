<script>
    const emojis = {
		apple: '🍎',
		banana: '🍌',
		carrot: '🥕',
		doughnut: '🍩',
		egg: '🥚'
	};

    export let name;
    const emoji = emojis[name];
</script>

<p>initial: {emoji}; current: {emojis[name]} ; {name}</p>
