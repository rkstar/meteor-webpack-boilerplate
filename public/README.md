# OG:IMAGE / FAVICON
in order to get the `<meta property='og:image' content='http://localhost/og.jpg' />` image to show up, it has to be placed into
the `/public` directory of your meteor app.  this is the only way that the meteor app will be able to serve it via a URL.

the same goes for your `favicon.ico` file.  you will also need to place that somewhere in this `/public` directory in order for it
to get displayed properly
