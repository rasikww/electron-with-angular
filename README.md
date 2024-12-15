# Electron App with Angular

This is a simple Electron app built with Angular to practice electron with Angular.

## Installation

Install the dependencies with `npm install` and run `ng serve` to start the Angular app.

Run `npm run electron` to start the Electron app.

## Process of creating the Electron app with Angular

1. Install Angular CLI: `npm install -g @angular/cli`
2. Create a new Angular app: `ng new demo-app`
3. Install Electron: `npm install electron@latest --save-dev`
4. Add `main.js` file from the [Electron Angular Tutorial](https://www.digitalocean.com/community/tutorials/angular-electron#installation) to `src` directory
5. Add following to `package.json`

```json
{
  "main": "src/main.js",
  "scripts": {
    "electron": "ng build --base-href ./ && electron ."
  }
}
```

6. Change `main.js` file and add the proper `pathname`:

```js
win.loadURL(
  url.format({
    pathname: path.join(__dirname, "../dist/demo-app/browser/index.html"),
    protocol: "file:",
    slashes: true,
  })
);
```

7. Run `npm run electron` to run the electron app

8. Run `ng serve` to run the Angular app while making changes to the Electron app.
