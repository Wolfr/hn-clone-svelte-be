# Hacker news - Svelte

Hacker news using Svelte.js and Routify.

Base: starter template for [Routify](https://github.com/sveltech/routify)

### Npm scripts

* `dev`: Development 
* `dev:split`: Development (with code splitting) 
* `build`: Build a bundled app for SSR + prerendering and a dynamic app for code splitting
* `export`: Export static pages (with app fallback) 
* `preview-build`: Run after build to preview app
* `deploy:*`: Deploy to netlify or now

---

### SSR and pre-rendering

SSR and pre-rendering are included in the default build process.

`mpm run deploy:(now|netlify)` will deploy the app with SSR and prerendering included.

To render async data, call the `$ready()` helper whenever your data is ready.

If $ready() is present, rendering will be delayed till the function has been called.

Otherwise it will be rendered instantly.

See [src/pages/example/api/[showId].svelte](https://github.com/sveltech/routify-starter/blob/master/src/pages/example/api/%5BshowId%5D.svelte) for an example.

### Production

* For SPA or SSR apps please make sure that url rewrite is enabled on the server.
* For SPA redirect to `__dynamic.html`.
* For SSR redirect to the lambda function or express server.
