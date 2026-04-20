---
layout: default
---

# Frequently Asked Questions

## Overview

### What does the App do?

This is an in-car lyrics display app. After you enable Personal Hotspot on your iPhone, a connected device, such as a Tesla in-car browser, can view the currently playing song information and synced lyrics in real time.

### Which Tesla models are supported?

All Tesla vehicles with a built-in web browser are supported.

### Which music sources are supported?

The App currently supports two music sources:
- **Apple Music** — Requires permission to access your music library
- **Spotify** — Requires connecting your Spotify account

## Connection and Setup

### How do I start using it?

Follow these steps:
1. **Choose a music source** — Select Apple Music or Spotify
2. **Authorize music access** — Allow the App to read your music library for Apple Music, or connect Spotify
3. **Enable the lyrics service** — Tap the enable button, and the App will start the local lyrics service through VPN
4. **Turn on Personal Hotspot** — Enable Personal Hotspot in iPhone Settings
5. **Open the page in the in-car browser** — Connect the Tesla to your iPhone hotspot, then open the displayed address in the browser

### Why does the App need VPN?

The App uses a local VPN tunnel to forward requests from the in-car browser to a local server running on your iPhone. This VPN does **not** send your browsing or network traffic to any remote server. Data between your phone and connected devices is transmitted locally. Separately, if usage analytics are enabled, the App may send limited usage and diagnostic events to Firebase to improve reliability.

### What address should I open in the in-car browser?

After the lyrics service is enabled and the hotspot is connected, the App will display an access address. Enter that address in the in-car browser.

### What should I do if the in-car browser cannot open the page?

1. Make sure the lyrics service is enabled and the VPN is connected
2. Make sure the Tesla is connected to your iPhone hotspot
3. Make sure the address was entered correctly
4. Try refreshing the page in the in-car browser
5. Restart the App and try again

## Lyrics

### Does the App support word-by-word synced lyrics?

Yes. If a song has word-by-word lyrics in TTML format, the in-car browser can display synchronized word highlighting.

### What should I do if the lyrics are out of sync?

You can adjust the "lyrics time offset" in Settings. The range is -5000 ms to +5000 ms. Positive values make lyrics appear earlier, while negative values make lyrics appear later.

### Why do some songs have no lyrics?

Some songs may not be available from the lyrics sources. Instrumental tracks, remixes, and less common songs may not have matching lyrics.

## Personalization

### Can I set different display styles for different devices?

Yes. When multiple devices are connected, the App automatically recognizes each device, and you can configure lyrics display styles separately for each one.

### What is Low Performance Mode?

Because of MCU2 performance limitations, some animations may not run smoothly. If the browser feels sluggish, you can enable Low Performance Mode to reduce visual effects and improve smoothness.

## Trial and Purchase

### Is there a free trial?

Yes. The App provides 10 minutes of free trial time per day, which resets automatically the next day.

### What is the pricing model for the full version?

The full version is a one-time purchase. There is no subscription and no additional in-app purchase.

### How do I restore a previous purchase?

If you purchased the full version on another device, tap the "Restore Purchase" button and use the same Apple ID.

## Privacy and Security

### Does the App collect my data?

The App collects limited usage analytics and crash diagnostics through Firebase Analytics and Firebase Crashlytics to understand feature usage, diagnose errors, and improve the App. The App does not use analytics events or app-provided crash diagnostic fields to collect songs, lyrics, Spotify tokens, Apple Music tokens, IP addresses, or raw browser identifiers.

To fetch lyrics, the App may query specific lyrics service providers, which usually requires sending the necessary information about the currently playing song, such as the song title, artist, album name, or playback progress. Lyrics queries are used only to match and return lyrics content.

### Can I turn off usage analytics?

Yes. You can turn off "Share Usage Analytics" in iOS Settings > RoadLyrics. In regions where consent is required, the App asks before enabling usage analytics. Turning the setting off disables Firebase Analytics collection.

### Is the VPN safe?

The VPN used by the App is a local-only VPN, used only to bridge communication between hotspot-connected devices and your iPhone. The VPN itself does not forward your network traffic to third-party servers. Firebase analytics and crash diagnostics are separate from VPN traffic and are used only for app usage analysis and reliability improvements. When the App queries lyrics, it may send the necessary currently playing song information according to the requirements of the lyrics service provider.

### Who can see my lyrics page?

Only the Tesla in-car browser connected to your iPhone hotspot can access the lyrics page.

## Background Running

### What happens if the App is terminated by the system?

If the App is force-terminated, the lyrics service will stop. Open the App again and enable the lyrics service to resume. If a device is connected, the App will send a notification before being terminated.

## Troubleshooting

### What should I do if the VPN connection fails?

1. Make sure the App has Network Extension permission, which iOS asks for during first use
2. Go to iPhone Settings > General > VPN & Device Management and make sure the VPN configuration exists
3. Try turning the lyrics service off and on again
4. Restart the App and try again

### What should I do if Spotify disconnects?

Spotify authorization tokens are valid for 1 hour. After they expire, Spotify needs to be connected again. The App will automatically try to restore the connection. If that fails, please authorize Spotify manually again.

### Why did the lyrics service suddenly stop?

Possible causes:
- The App was suspended because of limited system resources — reopen the App and keep it in the foreground
- The VPN configuration was removed — enable the lyrics service again
