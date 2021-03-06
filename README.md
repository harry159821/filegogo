# filegogo

A file transfer tool that can be used in the browser webrtc p2p

[![Demo.gif](https://i.postimg.cc/wTyzyHMc/Peek-2020-10-24-11-29.gif)](https://postimg.cc/8jS992hj)

## Build && Install

```sh
npm install
make
sudo make install
sudo systemctl start filegogo
```

## Run Development

```sh
cp conf/config.json .

npm install

# server
make run

# frontend
npm run dev
```

## Config

```json
{
  "wsUrl": "ws://localhost:8033/topic/",
  "iceServers": [
    {
      "urls": "stun:stun.services.mozilla.com",
      "username": "louis@mozilla.com",
      "credential": "webrtcdemo"
    }, {
      "urls": ["stun:stun.example.com", "stun:stun-1.example.com"]
    }
  ]
}
```

[Reference iceServer config](https://developer.mozilla.org/en-US/docs/Web/API/RTCIceServer)

iceServer Use Other

For example [coturn](https://github.com/coturn/coturn) Or [gortcd](https://github.com/gortc/gortcd)

### coturn

```sh
apt install coturn
```

```ini
# /etc/turnserver.conf

listening-ip={YOUR_IP_ADDRESS}
relay-ip={YOUR_IP_ADDRESS}

# Public ip
# if aws, aliyun
external-ip={YOUR_IP_ADDRESS}

fingerprint
lt-cred-mech
user=filegogo:filegogo
realm=filegogo

```
