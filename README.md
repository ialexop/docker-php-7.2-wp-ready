# What is this Dockerfile?
A stripped down version of the official WP (v4.9.4) Dockerfile.

# Why this Dockerfile?
The official Dockerfile for WP (v4.9.4) works well for most cases but for my use case, there were some items that I could only address with a custom image:
- Enable `headers` module for Apache. This is to be able to configure `CORS` (e.g. to serve files fron a CDN, etc.).
- Change the contents of the `/var/www/html` directory: In my case, WP was on a subdirectory and I needed to also have `Gulp` installed to run some tasks. The `VOLUME` directive on the official image, doesn't allow this, see https://goo.gl/DqzWbx .
- Last but not least, I just wanted to be able to use my WP project source code, I didn't really need to have WP downloaded and installed by the image for me.
