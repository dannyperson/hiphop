
## Build

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
