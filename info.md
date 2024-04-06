# Lovelace animated weather card

Maintained fork of [animated weather card](https://github.com/bramkragten/weather-card) by @bramkragten

Originally created for the [old UI](https://community.home-assistant.io/t/custom-ui-weather-state-card-with-a-question/23008) converted by @arsaboo and @ciotlosm to [Lovelace](https://community.home-assistant.io/t/custom-ui-weather-state-card-with-a-question/23008/291) and now converted to Lit to make it even better.

This card uses the awesome [animated SVG weather icons by amCharts](https://www.amcharts.com/free-animated-svg-weather-icons/).

![Weather Card](https://raw.githubusercontent.com/avee87/weather-card/master/weather-card.gif?raw=true)

Thanks for all picking this card up.

## Installation:

Add the following to resources in your lovelace config:

```yaml
resources:
  - url: /local/custom-lovelace/weather-card/weather-card.js
    type: module
```

## Configuration:

And add a card with type `custom:weather-card`:

```yaml
type: custom:weather-card
entity: weather.yourweatherentity
name: Optional name
```

If you want to use your local icons add the location to the icons:

```yaml
type: custom:weather-card
entity: weather.yourweatherentity
icons: '/local/custom-lovelace/weather-card/icons/'
```

You can choose wich elements of the weather card you want to show:

The 3 different rows, being:

- The current weather icon, the current temperature and title
- The details about the current weather
- The X day forecast or hourly forecast

```yaml
type: custom:weather-card
entity: weather.yourweatherentity
current: true
details: false
forecast: true
forecast_type: daily
number_of_forecasts: 5
```

If you want to show the sunrise and sunset times, make sure the `sun` component is enabled:

```yaml
# Example configuration.yaml entry
sun:
```

### Dark Sky:

When using Dark Sky you should put the mode to `daily` if you want a daily forecast with highs and lows.

```yaml
# Example configuration.yaml entry
weather:
  - platform: darksky
    api_key: YOUR_API_KEY
    mode: daily
```

### OpenWeather Map:

When using OpenWeather map you can select hourly(default) or daily forecast to show.

```yaml
# Example configuration.yaml entry
weather:
  - platform: openweathermap
    api_key: YOUR_API_KEY
```
