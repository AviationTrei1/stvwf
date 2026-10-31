# Stevens Virtual — WorldFlight 2026

The Stevens Virtual WorldFlight dashboard, published with GitHub Pages.

## Live dashboard

After enabling GitHub Pages with **GitHub Actions** as the build and deployment source, the site will be available at:

https://aviationtrei1.github.io/stvwf/

## Connect the live flight feed

The dashboard currently starts in demo mode. It accepts a Cloudflare Worker endpoint through the `api` query parameter:

```
https://aviationtrei1.github.io/stvwf/?api=https://YOUR-WORKER.workers.dev/flight-map
```

Replace the example Worker URL with your deployed HTTPS `/flight-map` endpoint. The Worker must allow browser requests from the Pages site (CORS) and return JSON in the format accepted by the dashboard.

**Never put a vAMSYS client secret, OAuth token, or other private credential in `index.html` or any public GitHub file.** Keep credentials in Cloudflare Worker environment secrets.

## Deploy the site

1. Open this repository's **Settings → Pages**.
2. Under **Build and deployment**, choose **GitHub Actions** as the source.
3. The workflow in `.github/workflows/pages.yml` will publish the root of the repository.
4. Check the **Actions** tab for the deployment result.

## Project status

- [x] Existing Stevens Virtual HTML dashboard added as `index.html`
- [x] GitHub Pages deployment workflow
- [ ] Enable GitHub Pages in repository settings
- [ ] Deploy and verify the Cloudflare Worker
- [ ] Add the live Worker URL to the site

The frontend and Worker are separate deployments. Publishing this repository does not itself deploy the Cloudflare Worker.
