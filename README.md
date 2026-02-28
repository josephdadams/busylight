# 🚨 Busylight for Node

A Node.js library for controlling Busylight USB devices.

More info about Busylight devices: http://busylight.com/

---

## Maintained fork

This is a maintained fork of the original **porsager/busylight** library.

Additional improvements:

- Support for additional Kuando / Plenom BusyLight models
- Ongoing maintenance and compatibility updates

---

## Install

```bash
npm install @josephdadams/busylight
```

---

## Quick start

### Get a Busylight

```js
const busylight = require('@josephdadams/busylight').get()
```

### Make it dance

```js
busylight.ring().pulse()
```

### Stop

```js
busylight.off()
```

### Hammertime

```js
busylight.ring('Funky').blink(['red', 'yellow', 'blue', 'green'], 150)
```

---

## Usage

### Finding an attached Busylight

Get the first available Busylight:

```js
const busylight = require('@josephdadams/busylight').get()
```

Get a specific Busylight:

```js
const busylight = require('@josephdadams/busylight').get(path)
```

List connected devices:

```js
const busylights = require('@josephdadams/busylight').devices(showAllUSBDevices)
```

Pass `true` to see all USB HID devices if the Busylight is not detected.

---

### Defaults

Configure default behavior:

```js
busylight.defaults({
  keepalive: true,
  color: 'white',
  duration: 30 * 1000,
  rate: 300,
  degamma: true,
  tone: 'OpenOffice',
  volume: 4
})
```

---

### light(color)

```js
busylight.light('orange')
busylight.light(false)
```

---

### ring(tone, volume)

```js
busylight.ring('OpenOffice')
```

Volume range: 0–7

Ringtones:

- OpenOffice
- Quiet
- Funky
- FairyTale
- KuandoTrain
- TelephoneNordic
- TelephoneOriginal
- TelephonePickMeUp
- Buzz

---

### blink(colors, rate)

```js
busylight.blink(['red', 'green', 'blue'], 500)
```

---

### pulse(colors, rate)

```js
busylight.pulse(['#f00', '#0f0', '#00f'])
```

---

### off()

```js
busylight.off()
```

---

### close()

```js
busylight.close()
```

---

### Chaining

```js
busylight.ring().blink()
busylight.ring(false).blink(false)
```

---

## Supported devices

Primarily Kuando / Plenom BusyLight devices.

Additional models supported in this fork.

---

## TypeScript

Type definitions are included.

---

## Electron

Busylight relies on node-hid. node-hid must be rebuilt for each Electron version.

https://github.com/electron/electron-rebuild

---

## Node-webkit

node-hid must be built for each node-webkit version using nw-gyp:

https://github.com/rogerwang/node-webkit/wiki/Build-native-modules-with-nw-gyp

---

## License

MIT — original authors retain copyright.
