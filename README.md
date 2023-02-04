# mqtt

## Project setup

```
yarn install
```

### Compiles and hot-reloads for development

```
yarn serve
```

### Compiles and minifies for production

```
yarn build
```

### Lints and fixes files

```
yarn lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

## MQTT

Open a mqtt client and after a connection send message to topic "mqttx_77b06fefjuni"

This code will work in a web browser, as long as the browser supports WebSockets. Most modern browsers do support WebSockets, but some older browsers may not. If you need to support older browsers, you may need to use a polyfill or fallback to another communication method such as long polling.

It's important to note that MQTT is a machine-to-machine communication protocol, so it is typically used for communication between devices rather than between a browser and a server. If you need to send data from a browser to a server, you may want to consider using a different communication protocol, such as WebSockets or HTTP.


---


Yes, it is possible to use MQTT protocol in a browser with Vue.js. You can use MQTT.js, a client library that implements the MQTT protocol in JavaScript, to connect to an MQTT broker from a browser-based Vue.js application. MQTT.js can run in a web worker, which allows it to communicate with an MQTT broker without blocking the main thread of the Vue.js application.

But this will use websockets protocol or mqtt protocol?

MQTT.js uses WebSockets protocol to establish a connection between the browser-based Vue.js application and an MQTT broker. MQTT is a publish/subscribe messaging protocol, while WebSockets is a full-duplex communication protocol that runs over a single TCP connection. By using WebSockets, MQTT.js can efficiently send and receive MQTT messages in real-time between the browser and the broker.

It's possible to use mqtt to mqtt in browser an not ws to mqtt?

No, it is not possible to use MQTT directly in the browser without a WebSockets connection or another communication protocol that allows the browser to communicate with the MQTT broker. This is because MQTT is a low-level binary protocol that is designed to run on top of a reliable transport layer such as TCP or WebSockets. Browsers have restrictions on which protocols they can use for network communication, and MQTT is not one of them. To use MQTT in a browser, it must be implemented over a protocol that is supported by the browser, such as WebSockets.
