# Dart ClickStack

## ClickStacks and CloudBees

ClickStarts are used by specifying the application type when you deploy an app. 
You can specify the stack to use either by name, or <name> and 
-RPLUGIN.SRC.<name>=<url> - this is called a "remote" plugin and is useful for 
getting the latest version of things.

This stack uses npm to install any required packages, and expects applications 
to be packaged up as a zip. 

## Usage

Get a sample app (eg sampleapp from this repo).
The [Cloudbees SDK](http://wiki.cloudbees.com/bin/view/RUN/BeesSDK) must be installed.

```
cd sampleapp
zip -r ../app.zip *
bees app:deploy -a playground/node -t node -RPLUGIN.SRC.node=https://s3.amazonaws.com/clickstacks/nicofrancois/dart-plugin.zip ../app.zip
```

## Dart SDK build

By default, this clickstack use the last Dart SDK version. 
If you want a specific one, just define the DART_BUILD environment variable :

```
bees config:set -a playground/node DART_BUILD=version
```
