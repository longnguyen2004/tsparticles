[![banner](https://particles.js.org/images/banner3.png)](https://particles.js.org)

# tsParticles Bubbles Preset

[![jsDelivr](https://data.jsdelivr.com/v1/package/npm/tsparticles-preset-bubbles/badge)](https://www.jsdelivr.com/package/npm/tsparticles-preset-bubbles) [![npmjs](https://badge.fury.io/js/tsparticles-preset-bubbles.svg)](https://www.npmjs.com/package/tsparticles-preset-bubbles) [![npmjs](https://img.shields.io/npm/dt/tsparticles-preset-bubbles)](https://www.npmjs.com/package/tsparticles-preset-bubbles)

[tsParticles](https://github.com/matteobruni/tsparticles) preset for colored bubbles coming from the bottom of the
screen on a white background.

[![Slack](https://particles.js.org/images/slack.png)](https://join.slack.com/t/tsparticles/shared_invite/enQtOTcxNTQxNjQ4NzkxLWE2MTZhZWExMWRmOWI5MTMxNjczOGE1Yjk0MjViYjdkYTUzODM3OTc5MGQ5MjFlODc4MzE0N2Q1OWQxZDc1YzI) [![Discord](https://particles.js.org/images/discord.png)](https://discord.gg/hACwv45Hme) [![Telegram](https://particles.js.org/images/telegram.png)](https://t.me/tsparticles)

[![tsParticles Product Hunt](https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=186113&theme=light)](https://www.producthunt.com/posts/tsparticles?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-tsparticles") <a href="https://www.buymeacoffee.com/matteobruni"><img src="https://img.buymeacoffee.com/button-api/?text=Buy me a beer&emoji=🍺&slug=matteobruni&button_colour=5F7FFF&font_colour=ffffff&font_family=Arial&outline_colour=000000&coffee_colour=FFDD00"></a>

## Sample

[![demo](https://raw.githubusercontent.com/matteobruni/tsparticles/main/presets/bubbles/images/sample.png)](https://particles.js.org/samples/presets/bubbles)

## How to use it

### CDN / Vanilla JS / jQuery

The first step is installing [tsParticles](https://github.com/matteobruni/tsparticles) following the instructions for
vanilla javascript in the main project [here](https://github.com/matteobruni/tsparticles)

Once installed you need one more script to be included in your page (or you can download that
from [jsDelivr](https://www.jsdelivr.com/package/npm/tsparticles-preset-bubbles):

```html

<script src="https://cdn.jsdelivr.net/npm/tsparticles-engine@2/tsparticles.engine.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-move-base@2/tsparticles.move.base.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-plugin-emitters@2/tsparticles.plugin.emitters.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-shape-circle@2/tsparticles.shape.circle.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-updater-color@2/tsparticles.updater.color.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-updater-opacity@2/tsparticles.updater.opacity.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-updater-out-modes@2/tsparticles.updater.out-modes.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-updater-size@2/tsparticles.updater.size.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/tsparticles-preset-bubbles@2/tsparticles.preset.bubbles.min.js"></script>
```

#### Bundle

A bundled script can also be used, this will include every needed plugin needed by the preset.

```html

<script src="https://cdn.jsdelivr.net/npm/tsparticles-preset-bubbles@2/tsparticles.preset.bubbles.bundle.min.js"></script>
```

### Usage

Once the scripts are loaded you can set up `tsParticles` like this:

```javascript
(async () => {
    await loadBubblesPreset(tsParticles); // this is required only if you are not using the bundle script

    await tsParticles.load("tsparticles", {
        preset: "bubbles",
    });
})();
```

#### Customization

**Important ⚠️**
You can override all the options defining the properties like in any standard `tsParticles` installation.

```javascript
tsParticles.load("tsparticles", {
    particles: {
        shape: {
            type: "square", // starting from v2, this require the square shape script
        },
    },
    preset: "bubbles",
});
```

Like in the sample above, the circles will be replaced by squares.

### React.js / Preact / Inferno

_The syntax for `React.js`, `Preact` and `Inferno` is the same_.

This sample uses the class component syntax, but you can use hooks as well (if the library supports it).

```typescript jsx
import Particles from "react-tsparticles";
import type { Engine } from "tsparticles-engine";
import { loadBubblesPreset } from "tsparticles-preset-bubbles";

export class ParticlesContainer extends React.PureComponent<IProps> {
    // this customizes the component tsParticles installation
    async customInit(engine: Engine): Promise<void> {
        // this adds the preset to tsParticles, you can safely use the
        await loadBubblesPreset(engine);
    }

    render() {
        const options = {
            preset: "bubbles",
        };

        return <Particles options={options} init={this.customInit}/>;
    }
}
```

### Vue (2.x and 3.x)

_The syntax for `Vue.js 2.x` and `3.x` is the same_

```vue

<Particles id="tsparticles" :particlesInit="particlesInit" :options="particlesOptions" />
```

```ts
const particlesOptions = {
    preset: "bubbles",
};

async function particlesInit(engine: Engine): Promise<void> {
    await loadBubblesPreset(engine);
}
```

### Angular

```html

<ng-particles
        [id]="id"
        [options]="particlesOptions"
        [particlesInit]="particlesInit"
></ng-particles>
```

```ts
const particlesOptions = {
    preset: "bubbles",
};

async function particlesInit(engine: Engine): Promise<void> {
    await loadBubblesPreset(engine);
}
```

### Svelte

```sveltehtml

<Particles
        id="tsparticles"
        options={particlesOptions}
        particlesInit={particlesInit}
/>
```

```js
let particlesOptions = {
    preset: "bubbles",
};

let particlesInit = async (engine) => {
    await loadBubblesPreset(engine);
};
```
