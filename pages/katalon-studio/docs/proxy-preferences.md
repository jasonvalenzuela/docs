---
title: "Proxy Preferences" 
sidebar: katalon_studio_docs_sidebar
permalink: katalon-studio/docs/proxy-preferences.html 
redirect_from:
    - "/display/KD/Proxy+Preferences/"
    - "/display/KD/Proxy%20Preferences/"
    - "/x/hw1O/"
    - "/katalon-studio/docs/proxy-preferences/"
description: 
---

Proxy can be configured at: **Katalon Studio> Preferences > Katalon > Proxy**. This setting affects both WebUI and WebService testings.

In the Proxy Settings, you can select one of three options below.

* **No proxy**: there's no proxy.
* **Use system proxy configuration**: Katalon Studio tries to guess which proxy server your system is behind and sync with this setting.
* **Manual proxy configuration**: you can manually set up your proxy.

<img src="https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/proxy-preferences/proxy.png" width="671" height="532">

> If you're behind a Proxy Server, you'll need to configure the proxy settings before activating Katalon Studio. Click Config Proxy at the bottom of the Activation dialog box.
>
> ![Config Proxy](https://github.com/katalon-studio/docs-images/raw/master/katalon-studio/docs/proxy-preferences/image2017-7-2-213A403A23.png)

## Pass proxy details through the script

Starting from **version 7.0.0**, Katalon Studio supports an option to pass proxy details via a request object in Web Service testing. Below is an example:

```groovy
RequestObject requestObject = findTestObject("google")
ProxyInformation proxyInfo = new ProxyInformation();
proxyInfo.setProxyServerAddress("localhost")
proxyInfo.setProxyServerPort(8001)
proxyInfo.setProxyOption(ProxyOption.MANUAL_CONFIG.toString())
proxyInfo.setProxyServerType(ProxyServerType.HTTP.toString())
requestObject.setProxy(proxyInfo)
```

>**Note**: The proxy information passed in the request object takes precedence over the proxy information set in **Preferences**.
