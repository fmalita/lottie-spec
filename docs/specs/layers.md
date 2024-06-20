# Layers

## Common Properties

<h3 id="layer">Layer</h3>

{schema_string:layers/layer/description}

{schema_object:layers/layer}

The `ty` property defines the specific layer type based on the following values:

{schema_subtype_table:layers/all-layers:ty}

<h3 id="visual-layer">Visual Layer</h3>

{schema_string:layers/visual-layer/description}

{schema_object:layers/visual-layer}

## Layer types


<h3 id="shape-layer">Shape Layer</h3>

{schema_string:layers/shape-layer/description}

{schema_object:layers/shape-layer}

<h3 id="image-layer">Image Layer</h3>

{schema_string:layers/image-layer/description}

{schema_object:layers/image-layer}

<h3 id="null-layer">Null Layer</h3>

{schema_string:layers/null-layer/description}

{schema_object:layers/null-layer}

<h3 id="solid-layer">Solid Layer</h3>

{schema_string:layers/solid-layer/description}

{schema_object:layers/solid-layer}

<h3 id="precomposition-layer">Precomposition Layer</h3>

{schema_string:layers/precomposition-layer/description}

{schema_object:layers/precomposition-layer}

The `st` property specifies a start time offset, while `sr` defines a time stretch factor,
to be applied when evaluating animated properties pertaining to the layer:

$$t\prime = \dfrac{t}{stretch} - start$$

`sr` values less than $1$ increase the layer playback speed, while values greater than $1$
decrease it ("stretching" the layer timeline).

<lottie-playground example="time_stretch.json">
    <title>Example</title>
    <form>
        <input type="range" min="0.5" max="2" value="1" step="0.01" title="Time Stretch"/>
    </form>
    <json>lottie.layers[0]</json>
    <script>
        var layer = lottie.layers[0];
        layer.sr =  Number(data["Time Stretch"]);
    </script>
</lottie-playground>

