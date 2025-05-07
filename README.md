<p align="center">
    <img src="https://repository-images.githubusercontent.com/315327563/b5f04180-2f76-11eb-8c6a-ce5276b842e6" height="300">
</p>

# Homebridge XGimiTv Plugin

[![npm](https://img.shields.io/npm/v/homebridge-xgimi-tv.svg)](https://www.npmjs.com/package/homebridge-xgimi-tv)
[![github](https://img.shields.io/github/package-json/v/fantasytu/homebridge-xgimi-tv.svg)](http://github.com/fantasytu/homebridge-xgimi-tv)
[![license](https://img.shields.io/github/license/fantasytu/homebridge-xgimi-tv.svg)](http://github.com/fantasytu/homebridge-xgimi-tv)
[![donate](https://img.shields.io/badge/Donate-Paypal-blue.svg)](https://paypal.me/fantasytu)
[![donate-alipay](https://img.shields.io/badge/捐赠-支付宝-blue.svg)](https://qr.alipay.com/fkx16957oe24tjvvxtdmfa4)

A plugin on [Homebridge](https://github.com/nfarina/homebridge) to bring **XGimi Smart Projector** to HomeKit.

**If you like this plugin, don't hesitate to "Star".**

## Installation

```
homebridge ui console:
cd node_modules/
root@dockerhome:/var/lib/homebridge/node_modules $ git clone https://github.com/iamglobe/homebridge-xgimi-tv.git
root@dockerhome:/var/lib/homebridge/node_modules $ cd homebridge-xgimi-tv/
root@dockerhome:/var/lib/homebridge/node_modules/homebridge-xgimi-tv $ npm install
root@dockerhome:/var/lib/homebridge/node_modules/homebridge-xgimi-tv $ npm run build
```

## Configuration

Configuration on Config UI X is *NOT YET* supported.

Please subscribe for future updates.

That being said, be sure to edit ```config.json``` before add TV into Home app.

### Example BASIC config
```javascript
{
    "bridge": {
        "name": "Homebridge ED57",
        "username": "0E:C6:1D:3E:ED:57",
        "port": 51995,
        "pin": "193-78-630"
    },
    "accessories": [],
    "platforms": [
        {
            "name": "Config",
            "port": 8581,
            "platform": "config"
        },
        {
            "platform" : "XGimiTeleVisionPlatform",
            "devices": [
                {
                  "name": "XGimi TV",
                  "host": "10.0.1.227",
                  "inputs": [
                    {
                      "name"    : "iQiyi",
                      "type"    : "APPLICATION",
                      "package" : "com.gitvjimi.video"
                    },
                    {
                      "name"    : "YouTube",
                      "type"    : "APPLICATION",
                      "package" : "com.liskovsoft.videomanager"
                    }
                  ],
                  "manufacturer": "XGimi",
                  "model": "H2",
                  "serialNumber": "DSXXXXXXXXXX",
                  "firmwareRevision": "1.0.0"
                }
            ]
        }
    ]
}
```

To get the **package** attribute, you can visit:
```
http://{{you_tv_ip}}:16741/data/data/com.xgimi.vcontrol/app_appDatas/list
```

## Tested On

* iOS 14
* Apple Home
* Homebridge 1.1.6

## Troubleshooting

If you have any issue, contact me(**f.tu@me.com**) or just submit an [issues](https://github.com/fantasytu/homebridge-xgimi-tv/issues).
