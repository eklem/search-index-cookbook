# Get it running on system [x]

## OSX
Go to Nodejs.org and download and install your favoured version.

## Ubuntu 16.04

First, get node.js and npm, and also get a symlink from nodejs to node on the command line

```console
$ sudo aptitude install nodejs-legacy
```

Then, you need to [give npm the right permission](https://docs.npmjs.com/getting-started/fixing-npm-permissions):

```console
npm config get prefix
```

If you get back */usr/local*, then do:
```console
sudo chown -R $(whoami) $(npm config get prefix)/{lib/node_modules,bin,share}
```



## Check that you're ready to go
```console
$ node -v
```
... and ...
```console
$ npm  -v
```

Version seems to be fine? Ready to go!

## Get `git` for GitHub going on the commandline - OSX and Ubuntu

You need to [generate a SSH key](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/) and [add it to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/).

