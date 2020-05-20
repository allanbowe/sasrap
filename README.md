# SAS Rap

## TL;DR
Run the code below (SAS9 or Viya), and open the link in a browser to hear a SAS streamed SAS Rap

```
filename playme url "https://sasjs.io/rap.sas";
%inc playme;
```

## WTF?

Ok, lemme break it down for ya.  The ability to base64 encode binary files inside SAS programs makes it possible to stream images / excel files / mp3 and other exotic types as web services.

This does not make it a good technique!  In fact it's highly inefficient, and should only be used if there are no better options (such as serving as static content from your Web Server, or directly from a database that supports binary file types).

The point of the repo is to demonstrate the utility of the "streaming" functionality of [SASjs](https://sasjs.io) for building web apps.  For simple apps, for sites where getting access to the SAS Web Server is time consuming or problematic, streaming web content is sometimes the only available option.  SASjs supports (but does not recommend) this approach.

## Prerequisites

* NPM
* SASjs 

Once you have installed NPM, run `sasjs i -g sasjs-cli` to get the CLI tool

## Build Process

Clone the repo and change into it.  Then run `sasjs cb sas9` or `sasjs cb viya` depending on your target.  This will compile the assets from the `src` folder and create a deployment script under `sasjsbuild`.  Run this in SAS (must be StudioV in Viya) to create the service in your home directory.  The link will be in the log.

