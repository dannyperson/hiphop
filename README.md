#HipHop [![Dependency Status](https://david-dm.org/hiphopapp/hiphop.svg?theme=shields.io)](https://david-dm.org/hiphopapp/hiphop)

![](http://gethiphop.net/images/github_screenshot.png)

## How does it work?

When searching, HipHop will use iTunes and Last.fm to display song results (with cover, title, artist). It will then try to find the best match for this song on Youtube and stream the **highest quality audio stream**.

HipHop **DOES NOT** use torrents and is entirely safe and untraceable, wherever you live.

## Roadmap

- **Angular.js refactor - *In progress***
- Android & iOS apps (with Cordova)
- Easy proxy setup (Youtube is blocked at work for many users)
- Media keys support on desktop (https://github.com/rogerwang/node-webkit/issues/200)
- Internationalization (everyone will be able to help on translations)
- Auto-update
- Sync Playlists & History between all your devices (tough one)
- Offline mode for both desktop & mobile apps
- Kick-ass homescreen (with Top tracks in your country, ranking by genres, ...)

And we should keep focusing on:

- Keeping the app simple
- Improving performance (especially search and playback)
- Fixing bugs
- Providing a clean & attractive design
- Staying decentralized and impossible to take down

What's NOT a priority and why:

- Adding more metadata services: HipHop already provides an enormous library of tracks (iTunes and Last.fm, combined)
- Playing local files (most of them are available for streaming anyway)
- Working on anything that would require HipHop to have a backend or some sort of centralized system that could easily be taken down
- Too advanced features (ex: showing the kbps for the current track)

## HipHop on the Web

Here is a list of some of the articles talking about us:

https://github.com/hiphopapp/hiphop/wiki/HipHop-on-the-Web

# Contribute

We need you! Join us on IRC at `#hiphopapp` on freenode ([web access](http://webchat.freenode.net/?channels=hiphopapp)).

# Build

### Requirements
    
You will need Grunt:

	$ npm install -g grunt-cli

And Compass to build the stylesheets:

	$ gem install compass

You will also need to install all the node dependencies:

	$ npm install

### Running HipHop

You can easily launch HipHop with:

	$ grunt run

_Note that `grunt build` has to be done at least once before this._
Build with:

    $ grunt build

By default it will build for your current platform however you can control that
by specifying a comma separated list of platforms in the `platforms` option to
grunt:

    $ grunt build --platforms=linux32,linux64,mac,win

You can also build for all platforms with:

    $ grunt build --platforms=all

## Release

_Note: should add some grunt automation here_

1. Update `version` in `/package.json`

2. `$ grunt build --platforms=mac` or just `$ grunt build` if you're on a Mac (the generated `HipHop.app` will be available in `/build/releases/HipHop/mac/`)

3. Download latest Windows version of [rogerwang/node-webkit#downloads](https://github.com/rogerwang/node-webkit#downloads) and put all files in `/node-webkit/win/*`

4. Open and Build `/dist/windows/windows-installer.iss` in a Windows environment (requires [Inno Setup](http://www.jrsoftware.org/isdl.php#stable) installed), this will generate `/dist/windows/Install HipHop x.x.x.exe`. You have your Windows installer!

5. Upload both files to `http://download.gethiphop.net/releases/x.x.x/[mac|win]/`

6. Update `/misc/update.json` accordingly and upload to `http://gethiphop.net/update.json` (*ONLY* when both releases are available for download)


# Known problems

### Error about missing libudev.so.0

Search for libudev.so.0 on your distribution. Most of the time it can be easily fixed by creating a symbolic link from libudev.so to libudev.so.0

See: https://github.com/rogerwang/node-webkit/wiki/The-solution-of-lacking-libudev.so.0
