# bLazem Caffeinated Giant Emote

A Casterlabs Caffeinated widget that displays the latest chat emote at a configurable size and position.

This build includes a compatibility fallback for Microsoft Edge, WebView2, and embedded browser hosts such as Resolume. Some browser engines load Caffeinated's child iframe without receiving the injected `Koi`, `Widget`, and `App` globals. When that happens, Giant Emote now connects directly to the widget's local Caffeinated WebSocket and continues receiving `RICH_MESSAGE` events.

## Download and install

1. Download `bLazem-Giant-Emote-Caffeinated-v1.0.1-edge-resolume-fix.jar` from the latest GitHub release.
2. Close Caffeinated.
3. Open **Caffeinated > Settings > Plugins > Open plugins folder**.
4. Remove older copies of the Giant Emote JAR so only one version remains.
5. Copy the downloaded JAR into the plugins folder and restart Caffeinated.
6. Create or reopen the **bLazem Giant Emote** widget and copy its newly generated URL.

## Using the widget on another computer

`127.0.0.1` always refers to the computer opening the URL. For an overlay host on another computer, replace both of these values with the LAN address of the computer running Caffeinated:

- The hostname at the beginning of the URL.
- The `validAddress` query parameter.

For example, if Caffeinated runs at `192.168.1.50`, both values must be `192.168.1.50`. They must match exactly or the browser can block Caffeinated's iframe injection as cross-origin.

Allow Caffeinated through the Windows firewall on the private network. The default local server port is TCP `8092`.

## Important URL note

Caffeinated widget URLs contain a widget ID and an authorization value. Do not post a live widget URL publicly. If a saved URL opens as a blank page after recreating or reloading the plugin, copy a fresh URL from Caffeinated; obsolete widget IDs fail with `WIDGET_NOT_FOUND`, which the current Caffeinated loader does not display.

## Compatibility fix

Normal operation is unchanged when Caffeinated successfully injects its APIs. The fallback starts only when those globals remain unavailable, then:

- Opens the same local widget WebSocket used by Caffeinated's loader.
- Handles `INIT`, `UPDATE`, `PING`, and `KOI` messages.
- Applies saved widget settings.
- Displays `RICH_MESSAGE` emotes.
- Reconnects if the local socket closes.

The relevant browser-side source is available at [`giant-emote.html`](giant-emote.html).

## Verified environments

- OBS Browser Source
- Google Chrome
- Microsoft Edge
- Resolume through a WebView/embedded-browser source

## Integrity

SHA-256 for the release JAR:

```text
E1EAFF1F0EA2E6BCD9753A94FD302C109EB591D0F69F39BFCA7B4603C91B9099
```

## Version

Compatibility build based on bLazem Giant Emote `1.0.1`.
