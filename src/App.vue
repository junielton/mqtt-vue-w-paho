<template>
  <div>
    <h1>MQTT Messages</h1>
    <ul>
      <li v-for="message in messages" :key="message.timestamp">
        {{ message.payload }}
      </li>
    </ul>
  </div>
</template>

<script>
import paho from "paho-mqtt";

export default {
  name: "App",
  data() {
    return {
      messages: [],
    };
  },
  mounted() {
    // Create a client instance
    "localhost", 9001, "clientId";

    const client = new paho.Client(
      "broker.emqx.io",
      8083,
      "clientmqttx_77b06fefqweq3fId"
    );

    client.connect({
      onSuccess: () => {
        console.log("Connected");
        client.subscribe("mqttx_77b06fefjuni");
      },
      onFailure: (message) => {
        console.log("Connection failed: " + message.errorMessage);
      },
    });

    client.onMessageArrived = (message) => {
      this.messages.push({
        payload: message.payloadString,
        timestamp: new Date().getTime(),
      });
    };

    client.onConnectionLost = (responseObject) => {
      if (responseObject.errorCode !== 0) {
        console.log("onConnectionLost:" + responseObject.errorMessage);
      }
    };

    client.onMessageDelivered = (message) => {
      console.log("onMessageDelivered:" + message.payloadString);
    };

    client.onMessageLost = (message) => {
      console.log("onMessageLost:" + message.payloadString);
    };

    client.onTokenRefresh = (message) => {
      console.log("onTokenRefresh:" + message.payloadString);
    };

    client.onConnectionLost = (message) => {
      console.log("onConnectionLost:" + message.payloadString);
    };

    client.onConnectionFailed = (message) => {
      console.log("onConnectionFailed:" + message.payloadString);
    };

    client.onConnectionResumed = (message) => {
      console.log("onConnectionResumed:" + message.payloadString);
    };

    client.onConnected = (message) => {
      console.log("onConnected:" + message.payloadString);
    };

    client.onDisconnected = (message) => {
      console.log("onDisconnected:" + message.payloadString);
    };

    client.onReconnected = (message) => {
      console.log("onReconnected:" + message.payloadString);
    };

    client.onReconnecting = (message) => {
      console.log("onReconnecting:" + message.payloadString);
    };

    client.onSubscribe = (message) => {
      console.log("onSubscribe:" + message.payloadString);
    };

    client.onUnsubscribe = (message) => {
      console.log("onUnsubscribe:" + message.payloadString);
    };
  },
  methods: {},
};
</script>
