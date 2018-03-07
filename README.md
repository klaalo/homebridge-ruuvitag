# homebridge-ruuvitag

With this [Homebridge](https://github.com/nfarina/homebridge) plugin you can use [RuuviTags](https://tag.ruuvi.com/) with [Apple Home](https://www.apple.com/ios/home/).

## Installation
First, install [Avahi](https://www.avahi.org/) (Homebridge needs this), [Homebridge](https://github.com/nfarina/homebridge) and this plugin
_(you also need Node.js installed)_:
```bash
sudo apt-get install libavahi-compat-libdnssd-dev
sudo npm i -g homebridge
sudo npm i -g homebridge-ruuvitag
```

Then create a [`~/.homebridge/config.json`](https://github.com/nfarina/homebridge/blob/master/config-sample.json) file
(change ID's and add/remove tags as necessary):

```json
{
  "bridge": {
    "name": "Ruuvi",
    "username": "CC:22:3D:E3:CE:30",
    "port": 51826,
    "pin": "031-45-154"
  },

  "description": "RuuviTag bridge",

  "accessories": [
    {
      "accessory": "Ruuvitag",
      "name": "Ruuvi 1",
      "id": "ca67bf52ca12"
    },
    {
      "accessory": "Ruuvitag",
      "name": "Ruuvi 2",
      "id": "fa81b4c6a891"
    },
    {
      "accessory": "Ruuvitag",
      "name": "Ruuvi 3",
      "id": "ac67df12bb34"
    }
  ]
}
```

Now you can run Homebridge:
```bash
homebridge
```

## Supported features
For now the bridge only supports temperature, humidity, battery level and warning for low battery.
