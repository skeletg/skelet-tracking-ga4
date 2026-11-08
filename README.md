# tracking-ga4

A [Skelet](https://github.com/skeletg/skelet) tracking destination that sends shop events to Google Analytics 4
through the Measurement Protocol. It runs server to server, so no Google script loads on the storefront.

It sends page views, product views, cart changes, checkouts and orders. Events go only for shoppers who granted
analytics consent.

## Install

```bash
skelet cli plugin add github.com/skeletg/tracking-ga4@<version>
```

Then rebuild the backend and add the destination under **Marketing → Tracking** in the dashboard.

## Settings

| Setting | What |
|---|---|
| Measurement ID | `G-XXXXXXXXXX`, from the web data stream |
| Measurement Protocol API secret | Admin → Data streams → the stream → Measurement Protocol API secrets |
| Endpoint | Empty for Google. `https://region1.google-analytics.com` keeps collection in the EU, and a server-side Google Tag Manager container's URL sends through that container |
| Validate only | `true` sends to Google's validation server, which checks each event and records nothing. Use it while setting up |

## Develop

```bash
go test ./...
```

## License

GPL-3.0, see [LICENSE](LICENSE).
