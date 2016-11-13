# qairoe-app-layout

`<qairoe-app-layout>` allows the automatic laying out of header, drawers, and content.
It notifies other components of the scroll progress of the viewport (not the scroll position).

## Installation

To include this, type:

```
$ bower install littleqairoes/qairoe-app-layout
```

## Usage

It is usually used in your entry shell like my-app or core-app.

```html
<qairoe-app-layout>
  <project-header main-header></project-header>
  <project-drawer main-drawer></project-drawer>
  <project-content main-content></project-content>
</qairoe-app-layout>
```

### Setting Elements to be Content, Header, or Drawer

To do that, you just have to set attributes `main-content`, `main-header`, and
`main-drawer` to elements that is the main-content, header, and drawer, respectively
(See above example).

### Opening the Drawers

It listens for an event `toggle-drawer` to open any custom element with
an attribute `main-drawer` in it if and only if the custom element with an
attribute `main-drawer` has a function `toggle` (like `app-drawer`) or `toggleDrawer`.

### Having Several different Drawers

You can have several different drawers and can differentiate them by adding a value
in the `main-drawer` attribute

```html
<qairoe-app-layout>
  <project-header main-header></project-header>
  <project-drawer-one main-drawer="drawer-one"></project-drawer-one>
  <project-drawer-one main-drawer="drawer-two"></project-drawer-one>
  <project-content main-content></project-content>
</qairoe-app-layout>
```

This way, you can add the `drawer-id` in the data payload of the event by calling
this:

```js
this.fire('toggle-drawer', 'drawer-one');
```

The above code will open `<project-drawer-one>`.

## Roadmap

See [ROADMAP](/ROADMAP.md)

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

- v0.0.3: Updated Documentation

- v0.0.2: Made a minor fix to main-header according to [Polymer Styling guide for Children](https://www.polymer-project.org/1.0/docs/devguide/styling#styling-distributed-children-content)

- v0.0.1: Made appropriate changes for publication

- v0.0.0: Creation of repository and copying of reach-core-layout element

## Credits

Toni-Jan Keith Monserrat created this for his projects.

## License

See [LICENSE](/LICENSE)