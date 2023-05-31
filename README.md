# SAS Rap

## TL;DR
Run the code below (SAS9 or Viya), and open the link in a browser to hear a SAS streamed [SAS Rap](https://www.youtube.com/watch?v=FtTAoYV9HS8&feature=youtu.be) by [Thiago De Souza](https://www.linkedin.com/in/thiago-de-souza/) 

```
filename playme url "https://sasjs.io/rap.sas";
%inc playme;
```

## WTF?

Ok, lemme break it down for ya.  The ability to base64 encode binary files inside SAS programs makes it possible to stream images / excel files / mp3 and other exotic types as web services.

This does not make it a good technique!  In fact it's highly inefficient, and should only be used if there are no better options (such as serving directly from the static content area of the SAS Web Server, or from a database that supports binary file types).

The point of the repo is to demonstrate the utility of the "streaming" functionality of [SASjs](https://sasjs.io) for building web apps.  For simple apps, for sites where getting access to the SAS Web Server is time consuming or problematic, streaming web content is sometimes the only available option.  SASjs supports (but does not usually recommend) this approach.  It's worth noting however that such assets are cached on the browser side, so there is usually just one request needed per user/browser combination.

## Prerequisites

* NPM
* SASjs CLI

Once you have installed NPM, run `npm i -g @sasjs/cli` to get the CLI tool

## Build Process

Clone the repo and `cd` into it.  Then run `sasjs cb -t sas9` or `sasjs cb -t viya` depending on your preferred SAS target.  This will compile the assets from the `src` folder and build a deployment program under `sasjsbuild`.  Run this program in SAS (must be StudioV in Viya) to create the service in your home directory.  The link will be at the bottom of the log.

## Credits

Thanks to [Michael Dixon](https://www.linkedin.com/in/seleritymd/) of [Selerity](https://seleritysas.com/) for this informative base64 [article](https://support.selerity.com.au/hc/en-us/articles/223345708-Tip-SAS-and-Base64)

And most especially thanks to [Thiago De Souza](https://www.linkedin.com/in/thiago-de-souza/) for giving permission to reproduce the musical rendition!

Full video is here:  [https://www.youtube.com/watch?v=FtTAoYV9HS8&feature=youtu.be](https://www.youtube.com/watch?v=FtTAoYV9HS8&feature=youtu.be)
