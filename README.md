# Elvia for HomeAssistant

![GitHub release (latest by date)](https://img.shields.io/github/v/release/sindrebroch/ha-elvia?style=flat-square)
[![hacs_badge](https://img.shields.io/badge/HACS-Custom-41BDF5.svg)](https://github.com/hacs/integration)

[!["Buy Me A Coffee"](https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png)](https://www.buymeacoffee.com/sindrebroch)

HomeAssistant-integration for Elvia

## Requirements

- **Metering point id.** (*Målepunkt-ID*, not *Målernummer*) Log into [Elvia](https://www.elvia.no/logg-inn/) and find your ID, or see it printed on your invoice.
- **API-key.** Sign up at [Elvia developer portal](https://developers.elvia.no/), open `Products`, select `Grid Tariff`, enter a subscription name and press `Subscribe`. Your keys are available on `Profile`. See [API-doc](https://assets.ctfassets.net/jbub5thfds15/1mF3J3xVf9400SDuwkChUC/a069a61a0257ba8c950432000bdefef3/Elvia_GridTariffAPI_for_smart_house_purposes_v1_1_20210212.doc.pdf) for more info.
- **Token.** [Read how](https://www.elvia.no/smart-forbruk/api-er-for-smartere-hjem-og-bedrifter/slik-kan-du-ta-i-bruk-metervalue-api/)

## Installation

<details>
   <summary>HACS (Recommended)</summary>

   1. Ensure that [HACS](https://hacs.xyz/) is installed.
   2. Add this repository as a custom repository
   3. Search for and install the "Elvia" integration.
   4. Restart Home Assistant.
   5. Add the `Elvia` integration to HA from the integration-page
</details>

<details>
   <summary>Manual installation</summary>

   1. Download the `Source code (zip)` file from the
      [latest release](https://github.com/sindrebroch/ha-elvia/releases/latest).
   2. Unpack the release and copy the `custom_components/elvia` directory
      into the `custom_components` directory of your Home Assistant
      installation.
   3. Restart Home Assistant.
   4. Add the `Elvia` integration to HA from the integration-page
</details>


## Sensors
- Energy price
   - Daily tariff (array of hourly values for the day)

- Fixed price hourly
- Fixed price level
- Fixed price monthly

- Average max
   - Current month
   - Previous month

- Max hours [1, 2, 3]
   - Current month
      - StartTime (attribute)
      - EndTime (attribute)
   - Previous month
      - StartTime (attribute)
      - EndTime (attribute)

## Debugging
If something is not working properly, logs might help with debugging. To turn on debug-logging add this to your `configuration.yaml`
```
logger:
  default: info
  logs:
    custom_components.elvia: debug
```

## API limitations
Limited to 200 calls/hour/user. The integration normally polls once every hour.

## Inspiration
https://github.com/uphillbattle/NettleieElvia
