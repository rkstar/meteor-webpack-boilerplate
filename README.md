# meteor/webpack boilerplate
this should get you started quickly with the basic meteor/webpack setup for a basic app

all of the directory structure is what i've worked out over a number of projects and i find it keeps things fairly well organized overall.

## settings
in the `.gitignore` file you'll see `settings` and `deploy`.  generally, i keep my meteor `settings.json` files and my [mup](https://github.com/arunoda/meteor-up/tree/mupx) `mup.json` files in these directories respectively.

using directories instead of files allows me to easily have multiple versions of each for different setups.
eg.
```
/settings/local.json
/settings/development.json
/settings/production.json
```

and 

```
/deploy/local.json
/deploy/development.json
/deploy/production.json
```

this makes running in, and deploying to, different environments really easy and keeps my directory structure clean.

## how to use this repo
```
%> git clone https://github.com/rkstar/meteor-webpack-boilerplate myproject
%> cd myproject
%> meteor 
```