# Nakatha as an installable web app

This is the same game as the single HTML file, plus the three files a browser needs before
it will offer to install it properly: a manifest, an icon set and a service worker.

Chrome will only install a web app from a secure origin, so this needs to sit on some
https host. Any static host works and none of them need a server process:

  - GitHub Pages: make a repo, drop these files in, enable Pages, open the URL on the phone.
  - Netlify Drop, Cloudflare Pages, or any web space you already have.

On the phone, open the URL in Chrome and choose "Install app" from the menu. After that it
has its own icon, opens without browser chrome, and the service worker keeps it working
with no signal at all.

Files:
  index.html            the game, with the manifest and service worker wired in
  manifest.webmanifest  name, icons, colours, standalone display
  sw.js                 caches everything on first load, then serves from cache
  icon-192.png, icon-512.png

If you would rather not host anything, use the Android Studio project instead
(nakatha-android.zip), which installs as a real APK with no network involved.
