# cryptotrackerlovelace

Using the awesome work shared below to get crypto prices and a cracking example of a lovelace view of this data a slighly modified version:

https://community.home-assistant.io/t/displaying-values-as-currency/188544

![Crypto Tracker](/lovelace.png)

There is a load of custom cards here which you'll need to be able to use this:

- [custom:vertical-stack-in-card](https://github.com/ofekashery/vertical-stack-in-card)
- [custom:template-entity-row](https://github.com/thomasloven/lovelace-template-entity-row)
- [custom:config-template-card](https://github.com/iantrich/config-template-card)
- [custom:apexcharts-card](https://github.com/RomRider/apexcharts-card)
- [custom:button-card](https://github.com/custom-cards/button-card)

Changes I've attempted over the original post are:
- swap out mini graph for Apex charts
- selectable periods for the graph (see note about Helpers below)
- better display of currency amounts to fix 2 decimal places and add thousand commas  (set to GBP but can be easily changed)
- jiggled around with the change data

Helpers are needed to drive the selectable period for the graphs. I called mine `input_select.crypto_graph_period`. So for an easy drop in the same name would work. More info on helpers can be found [here](https://www.home-assistant.io/integrations/input_select/).

These are basically the input to Apex charts with expects `duration` followed by `measurement`, such as `1d` for one day or `5h` for 5 hours. You can populate your helper with any values that you require and it should just work!
