<script>
    import { Text } from '@threlte/extras'
    import { T } from '@threlte/core';
    import {Pane} from 'tweakpane'; 
    let value = "Paulo Liedtke"
    let fontSize = 1
    let fontColor = "white"
/*     const pane = new Pane()
    pane.addBlade({
		view: 'text',
		label: "Use the 'wasd' keys to move around",
	}) */

    function setFontSize() {
        fontSize = fontSize == 1 ? 1.5 : 1
    }
</script>

<Text text={value}
color={fontColor}
on:click={() => setFontSize()}
{fontSize}
anchorX="50%"
anchorY="100%"
></Text>



<T.GridHelper args={[50, 50]} />