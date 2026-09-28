# v1.0.1-edge-resolume-fix

Confirmed compatibility build for Edge, WebView2, OBS, Chrome, and Resolume browser sources.

## Fixed

- Added a direct local-WebSocket fallback when Caffeinated does not inject `Koi`, `Widget`, or `App` into its child iframe.
- Preserved the normal injected-API path for OBS and browsers where it already works.
- Added safe reconnection, widget settings updates, ping/pong handling, and duplicate-listener protection.

## Security

The release JAR was checked for widget authorization values, passwords, API keys, local user paths, and private LAN addresses before publication. None are embedded.

SHA-256:

```text
E1EAFF1F0EA2E6BCD9753A94FD302C109EB591D0F69F39BFCA7B4603C91B9099
```
