A small application I built to learn how Quasar framework works 

Some commands for deployment

## Server side rendering
quasar dev -m ssr

## Build PWA
quasar dev -m pwa

## building it for Mobile
First install cordova:
npm install cordova

Then,
quasar build -m cordova -T [ios|android]

For android, it will generate apk file(you will first need to sign the app)

# Quasar App (quasar-example)

A Quasar Framework app

## Install the dependencies
```bash
npm install
```

### Start the app in development mode (hot-code reloading, error reporting, etc.)
```bash
quasar dev
```

### Lint the files
```bash
npm run lint
```

### Build the app for production
```bash
quasar build
```

### Customize the configuration
See [Configuring quasar.conf.js](https://quasar.dev/quasar-cli/quasar-conf-js).
