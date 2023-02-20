<script>
    import * as PIXI from "pixi.js"
    import { Application, Text, Sprite, Ticker } from "svelte-pixi"

    let x = 250
    let y = 250

    let delta;
    let count = 0

    const handleOnTick = (ev) => {
        delta = ev.detail
        count += delta * 0.05
        x = 250 + Math.cos(count) * 150
        y = 250 + Math.sin(count) * 150
    }
</script>

<Application 
    width={500}
    height={500}
    antialias={true}
>
    <Ticker on:tick={handleOnTick}>
        <Text 
            text={delta}
            anchor={0.5}
            x={250}
            y={250}
            style={{
                fill: "white"
            }}
        />
        <Sprite 
            texture={PIXI.Texture.from("images/sample.png")}
            anchor={0.5}
            {x}
            {y}
            scale={0.5}
        />
    </Ticker>
</Application>