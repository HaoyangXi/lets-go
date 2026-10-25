# Let's Go

A trip planner in a single HTML file. Plan each day, keep a wishlist of places, track where you're staying, and tick things off as you go.

## Features
- Trips shown as tickets with a countdown to departure
- Day-by-day timeline with places and transport, plus drag and drop from the wishlist
- Stays shown on each night
- Progress tracking, with a check-off for each stop
- Map and route links through Google Maps
- Light and dark themes, with a choice of accent colours

## Run it
Open `index.html` in a browser. No build step.

With no configuration it runs in **test mode**: trips are saved in that browser only.

## Plan with friends (cloud mode)
Open `index.html` and fill in the `CONFIG` block at the top of the script:

```js
const CONFIG = {
  appName: "Let's Go",
  env: '',             // Tencent CloudBase environment ID
  publishableKey: '',  // Tencent CloudBase Publishable Key
  region: 'ap-shanghai',
  collection: 'trip_planner',
};
```

Then in CloudBase:
1. Create a document database collection named `trip_planner`.
2. Set its security rules to `{"read": true, "write": true}`.
3. Add your site's domain under environment settings → security origins.

Each trip has its own code. Anyone you send the code to can view and edit that trip, and none of your other trips.

## Hosting
Turn on GitHub Pages (Settings → Pages → deploy from the `main` branch) to get a public URL you can share.
