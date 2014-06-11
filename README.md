#HipHop [![Dependency Status](https://david-dm.org/hiphopapp/hiphop.svg?theme=shields.io)](https://david-dm.org/hiphopapp/hiphop)

![screenshot](http://gethiphop.net/images/github_screenshot.png)

## How does it work?

When searching, the app will use iTunes and Last.fm to display song results (with cover, title, artist). It will then try to find the best match for this song on Youtube and stream the **highest quality audio stream**.

No torrents, completely decentralized.

## HipHop on the Web

I've listed the top 20 articles talking about HipHop here:
https://github.com/hiphopapp/hiphop/wiki/HipHop-on-the-Web

## Contribute

Join us on IRC at `#hiphopapp` on freenode ([web access](http://webchat.freenode.net/?channels=hiphopapp)).

# Build

### Requirements
    
You will Grunt:

    $ npm install -g grunt-cli

And Compass to build the stylesheets:

	$ gem install compass

### Running HipHop

Run at least once to install dependencies all the node modules:

    $ npm install

Then you can launch HipHop with:

    $ grunt run

_Note that `grunt build` has to be done at least once before this._
