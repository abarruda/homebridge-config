# homebridge-config

A Helm chart for a Kubernetes ConfigMap representing Homebridge configuration

### Included Plugins

`homebridge-camera-ffmpeg` - Remote streams appear as cameras in Homekit

`homebridge-http-garage` - Garage door control

`homebridge-vizio` - Vizio TV control

### Prerequisites

`homebridge-camera-ffmpeg` requires a file called `cam-config.json` that represents the streams to appear as cameras.

*Sample `cam-config.json`:* 

```
"cameras": [
  {
    "name": "Living Room",
    "videoConfig": {
      "source": "-rtsp_transport tcp -re -i rtsp://user:pass@1.1.1.1/stream",
      "stillImageSource": "-i rtsp://user:pass@1.1.1.1/stream",
      "maxStreams": 2,
      "maxBitrate": 50,
      "maxFPS": 10,
      "vcodec": "copy",
      "videoFilter": "none",
      "debug": true
    }
  },
  {
    "name": "Backyard",
    "videoConfig": {
      "source": "-rtsp_transport tcp -re -i rtsp://user:pass@1.1.1.2/stream",
      "stillImageSource": "-i rtsp://user:pass@1.1.1.2/stream",
      "maxStreams": 2,
      "maxBitrate": 50,
      "maxFPS": 10,
      "vcodec": "copy",
      "videoFilter": "none",
      "debug": true
    }
  }
]
```
