# Cryptowatch Embed

Small library for embedding [Cryptowatch](https://cryptowat.ch) charts on a website.

## Usage

### Vanilla ES5

Include the ES5 build in your page:

```html
<script type="text/javascript" src="https://cdn.cryptowat.ch/assets/build/dist/embed-0.0.1.js"></script>
```

Use the library in the global `cryptowatch` namespace:

```js
var chart = new cryptowatch.Embed('bitfinex', 'btcusd');

chart.mount('#chart-container');
```

### ES6/webpack

Install package:

```
npm install cryptowatch-embed --save
```

Import package:

```js
import CryptowatchEmbed from 'cryptowatch-embed';

let chart = new CryptowatchEmbed('bitfinex', 'btcusd');

chart.mount('#chart-container');
```

## API

At minimum, the library requires an exchange and currency pair.

```js
var chart = new cryptowatch.Embed('bitfinex', 'btcusd');
```

A few options can be provided to configure the chart.

### `timePeriod`

Any of the supported time periods may be chosen.

```js
var chart = new cryptowatch.Embed('bitfinex', 'btcusd', {
  timePeriod: '4H'
});
```

### `presetColorScheme`

Any of the preset color schemes may be chosen.

```js
var chart = new cryptowatch.Embed('bitfinex', 'btcusd', {
  presetColorScheme: 'delek'
});
```

### `customColorScheme`

Alternatively, a custom color scheme may be defined.

```js
var chart = new cryptowatch.Embed('bitfinex', 'btcusd', {
  customColorScheme: {
    bg:           "000000",
    text:         "b2b2b2",
    textStrong:   "e5e5e5", // Emphasized text
    textWeak:     "7f7f7f", // De-emphasized text
    short:        "C60606", // Stroke color of decreasing candlesticks, ask orders, and other "short" related UI
    shortFill:    "C60606", // Fill color of decreasing candlesticks
    long:         "00B909", // Color of increasing candlesticks, bid orders, and other "long" related UI
    longFill:     "000000", // Fill color of increasing candlesticks
    cta:          "363D52", // Color of buttons and other prominent UI elements
    ctaHighlight: "414A67", // Color of buttons and other prominent UI elements when hovered over
    alert:        "FFD506"  // Color associated with price & volume alerts
  }
});
```

Future versions of this library will also enable you to add indicators/overlays.
The current version renders only the candlestick chart with volume underneath.
