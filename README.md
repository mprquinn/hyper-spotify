# hyper-spotify [![npm](https://img.shields.io/npm/v/hyper-spotify.svg)](https://www.npmjs.com/package/hyper-spotify)

[![License](https://img.shields.io/github/license/panz3r/hyper-spotify.svg)](LICENSE.md)
[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com)
[![hyper](https://img.shields.io/badge/Hyper-v1.3.3-brightgreen.svg)](https://github.com/zeit/hyper/releases/tag/1.3.3)
[![npm](https://img.shields.io/npm/dm/hyper-spotify.svg)](https://www.npmjs.com/package/hyper-spotify)

[![Build Status](https://travis-ci.org/panz3r/hyper-spotify.svg)](https://travis-ci.org/panz3r/hyper-spotify)
[![GitHub issues](https://img.shields.io/github/issues/panz3r/hyper-spotify.svg)](https://github.com/panz3r/hyper-spotify/issues)

> Spotify plugin for [Hyper](https://hyper.is). <br>
Display currently playing song on [Spotify](https://www.spotify.com) at the bottom of the terminal and allows you to control your favourite music

![hyper-spotify](art/preview.png)

## Installation
Simply add this plugin inside `~/.hyper.js` and enjoy your music :musical_note:
```js
module.exports = {
  ...
  plugins: ['hyper-spotify']
  ...
}
```

<br />

## Configuration
In your `~/.hyper.js` you can define the following parameters to customize `hyper-spotify` appearance
```js
modules.exports = {
  config: {
    ...
    hyperSpotify: {
      position: 'top', // or 'bottom'
      margin: 'default', // or 'double' or custom value
      controlsPosition: 'default', // or 'left' or 'right'
    },
    ...
  },
  ... 
};
```

### Position
`hyper-spotify bar` supports 2 different positioning: 
- `top`
- `bottom` (default)

### Margin
`hyper-spotify bar` supports 3 margin options:
- `default`, should work most of the times
- `double`, when using other bar plugins (such as `hyper-statusline` or `hyperline`)
- custom value, specify a custom margin value as an interger (e.g. 30)

### Controls position
`hyper-spotify controls` support 3 different positioning: 
- `default`, controls appears just before the song details
- `left`, controls are fixed to the left side of Hyper window
- `right`, controls are fixed to the right side of Hyper window

### Theme
`hyper-spotify` support different themes:
- `default`, A light theme with a `Spotify Green` (`#1ED760`) Spotify icon
- `light`, An white theme suitable for dark `hyper` themes
- `dark`, A deep-black theme suitable for light `hyper` themes
- special event themes (look for them if you really want to :stuck_out_tongue_winking_eye:)
- `custom`, A customizable theme (see below for more options)

#### Custom Theme
If you'd like to give a personal touch to `hyper-spotify`, you can use a custom `theme` and specify one or more of the theme colors
- `overlayColor`, the color to apply to `hyper-spotify` bar background, defaults to `white` (`#FFF`)
- `iconColor`, the color for every actionable icon, defaults to `white` (`#FFF`)
- `spotifyIconColor`, the color for the Spotify icon (visible when `Spotify` app is not running), defaults to `iconColor` (if specified) or to `Spotify Green` (`#1ED760`)
- `textColor`, track info color, defaults to `white` (`#FFF`)

<br />

Custom theme sample configuration, edit your `~/.hyper.js`
```js
modules.exports = {
  config: {
    ...
    hyperSpotify: {
      ...
      theme: 'custom', // important!
      overlayColor: '#000',
      iconColor: '#D75C1B',
      spotifyIconColor: '#1ED760',
      textColor: '#FFF'
    },
    ...
  },
  ... 
};
```

<br />

## Limitations
Currently works only on `macOS`, `Linux` (Tested on Ubuntu 17.04).

## Troubleshooting

### Can't load `hyper-spotify`
Unfortunately this seems to be a common issue with `Hyper` plugins (see here [zeit/hyper#191](https://github.com/zeit/hyper/issues/191))

After installing `hyper-spotify` if `Hyper` complains about an error while enabling the plugin:
- do a full restart of `Hyper` app

if even after restaring the issue persists try running the following command
```bash
$ cd ~/.hyper_plugins && npm install
```

<br />

## Related Projects

If you found this plugin of your interest or if you need to control other media players be sure to check out
[`hyper-media-control`](https://github.com/OrionNebula/hyper-media-control) by [@OrionNebula](https://github.com/OrionNebula)

## Credits

This plugin is inspired by [`atom-spotify2`](https://github.com/albertorestifo/atom-spotify2) and relies on 
- [`spotify-node-applescript`](https://github.com/andrehaveman/spotify-node-applescript) on macOS
- [`node-dbus`](https://github.com/sidorares/node-dbus) on Linux

to interact with [Spotify](https://www.spotify.com) client

## Special Thanks

- [@OrionNebula](https://github.com/OrionNebula) for `Windows` support initial implementation.
