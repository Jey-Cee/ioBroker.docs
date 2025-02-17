---
translatedFrom: en
translatedWarning: Wenn Sie dieses Dokument bearbeiten möchten, löschen Sie bitte das Feld "translationsFrom". Andernfalls wird dieses Dokument automatisch erneut übersetzt
editLink: https://github.com/ioBroker/ioBroker.docs/edit/master/docs/de/adapterref/iobroker.spotify-premium/README.md
title: ioBroker.spotify-premium
hash: ifHAXl5vYXt+VIoW5JF7b9Wm4koyBktRSwPHcor1phM=
---
![Logo](../../../en/adapterref/iobroker.spotify-premium/admin/spotify-premium.png)

![Anzahl der Installationen](http://iobroker.live/badges/spotify-premium-stable.svg)
![NPM-Version](http://img.shields.io/npm/v/iobroker.spotify-premium.svg)
![Downloads](https://img.shields.io/npm/dm/iobroker.spotify-premium.svg)

# IoBroker.spotify-premium
![Test und Freigabe](https://github.com/iobroker-community-adapters/iobroker.spotify-premium/workflows/Test%20and%20Release/badge.svg) [![Übersetzungsstatus](https://weblate.iobroker.net/widgets/adapters/-/spotify-premium/svg-badge.svg)](https://weblate.iobroker.net/engage/adapters/?utm_source=widget)

**Dieser Adapter verwendet Sentry-Bibliotheken, um Ausnahmen und Codefehler automatisch an die Entwickler zu melden.** Weitere Details und Informationen zum Deaktivieren der Fehlerberichterstattung finden Sie unter [Sentry-Plugin-Dokumentation](https://github.com/ioBroker/plugin-sentry#plugin-sentry)! Sentry Reporting wird ab js-controller 3.0 verwendet.

Adapter für den Zugriff auf Spotify-Wiedergabesteuerungen. Aufgrund der Spotify-API ist ein Premium-Konto erforderlich.

Verbindung zu [Spotify Premium-API](https://www.spotify.com/).

## Dokumentation
Siehe auch die [Dokumentation zur Spotify-Entwickler-API](https://developer.spotify.com/).

### Einrichtung / Autorisierung
1. Melden Sie sich unter https://developer.spotify.com/dashboard/ an.
2. Erstellen Sie eine Anwendung. Sie erhalten eine Client-ID und ein Client-Geheimnis
3. Legen Sie die Umleitungs-URIs in Ihren App-Einstellungen in Ihrer erstellten Spotify-Anwendung auf „http://localhost“ fest
4. Geben Sie die Client-ID und das Client-Geheimnis in die Felder unten ein
5. Starten Sie die Instanz
6. Wechseln Sie zur Registerkarte „Objekte“ und klicken Sie bei „spotify-premium.0.authorization“ auf die Schaltfläche getAuthorization
7. Kopieren Sie die angezeigte URL von „spotify-premium.0.authorization.authorizationUrl“ in Ihren Webbrowser und rufen Sie sie auf
8. Möglicherweise müssen Sie sich bei Spotify anmelden und Zugriff gewähren
9. Der Browser wird auf eine ungültige URL umgeleitet. Wenn der Fehler „Ungültige Weiterleitungs-URI“ auftritt, überprüfen Sie bitte Schritt 3
10. Kopieren Sie diese URL und fügen Sie sie in „spotify-premium.0.authorization.authorizationReturnUri“ ein
11. Der Wert in „spotify-premium.0.authorization.authorized“ wird zu „true“, wenn alles erfolgreich war

#### [Videoanleitung](https://www.youtube.com/watch?v=n0m9201qABU)
[![So autorisieren Sie](https://img.youtube.com/vi/n0m9201qABU/0.jpg "https://www.youtube.com/watch?v=n0m9201qABU")](https://www.youtube.com/watch?v=n0m9201qABU)

### Zustände
Alle Zustände sind im Admin beschrieben.

### VIS-Nutzungsbeispiele
Klicken Sie hier, um die Widget-Quelle anzuzeigen.<details><summary> Starten Sie eine bestimmte Playlist<br/><img src="docs/en/img/choose_playlist.png"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplJquiButtonState&quot;,&quot;data&quot;:{&quot;oid&quot;:&quot;spotify-premium.0.playlists.YourPlaylistName.playThisList&quot;,&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;buttontext&quot;:&quot;Choose Playlist&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0,&quot;value&quot;:&quot;true&quot;,&quot;no_style&quot;:false},&quot;style&quot;:{&quot;left&quot;:&quot;549px&quot;,&quot;top&quot;:&quot;364px&quot;},&quot;widgetSet&quot;:&quot;jqui&quot;}]</code></pre></details><details><summary> Starten Sie ein bestimmtes Gerät<br/><img src="docs/en/img/choose_device.png"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplJquiButtonState&quot;,&quot;data&quot;:{&quot;oid&quot;:&quot;spotify-premium.0.devices.YourDeviceName.useForPlayback&quot;,&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;buttontext&quot;:&quot;Choose Device&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0,&quot;value&quot;:&quot;true&quot;,&quot;no_style&quot;:false},&quot;style&quot;:{&quot;left&quot;:&quot;549px&quot;,&quot;top&quot;:&quot;364px&quot;},&quot;widgetSet&quot;:&quot;jqui&quot;}]</code></pre></details><details><summary> Jetzt Spielen<br/><img src="docs/en/img/play_pause.gif"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplSpotifyPlayButton&quot;,&quot;data&quot;:{&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;oidplay&quot;:&quot;spotify-premium.0.player.play&quot;,&quot;oidpause&quot;:&quot;spotify-premium.0.player.pause&quot;,&quot;oidstate&quot;:&quot;spotify-premium.0.player.isPlaying&quot;,&quot;colorplay&quot;:&quot;green&quot;,&quot;colorpause&quot;:&quot;green&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;487px&quot;,&quot;top&quot;:&quot;604px&quot;},&quot;widgetSet&quot;:&quot;spotify-premium&quot;}]</code></pre></details><details><summary> Spielen Sie den vorherigen Titel ab<br/><img src="docs/en/img/previous.png"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplSpotifyPreviousButton&quot;,&quot;data&quot;:{&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;oid&quot;:&quot;spotify-premium.0.player.skipMinus&quot;,&quot;colorbox&quot;:&quot;green&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;386px&quot;,&quot;top&quot;:&quot;604px&quot;},&quot;widgetSet&quot;:&quot;spotify-premium&quot;}]</code></pre></details><details><summary> Spielen Sie den nächsten Titel ab<br/><img src="docs/en/img/next.png"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplSpotifyNextButton&quot;,&quot;data&quot;:{&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;oid&quot;:&quot;spotify-premium.0.player.skipPlus&quot;,&quot;colorbox&quot;:&quot;green&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;588px&quot;,&quot;top&quot;:&quot;604px&quot;},&quot;widgetSet&quot;:&quot;spotify-premium&quot;}]</code></pre></details><details><summary> Kontrollwiederholung<br/><img src="docs/en/img/repeat.gif"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplSpotifyRepeatButton&quot;,&quot;data&quot;:{&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;oidall&quot;:&quot;spotify-premium.0.player.repeatContext&quot;,&quot;oidoff&quot;:&quot;spotify-premium.0.player.repeatOff&quot;,&quot;oidone&quot;:&quot;spotify-premium.0.player.repeatTrack&quot;,&quot;oidstate&quot;:&quot;spotify-premium.0.player.repeat&quot;,&quot;coloroff&quot;:&quot;white&quot;,&quot;colorall&quot;:&quot;green&quot;,&quot;colorone&quot;:&quot;green&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;689px&quot;,&quot;top&quot;:&quot;614px&quot;,&quot;width&quot;:&quot;48px&quot;,&quot;height&quot;:&quot;56px&quot;},&quot;widgetSet&quot;:&quot;spotify-premium&quot;}]</code></pre></details><details><summary> Kontrollieren Sie das Mischen<br/><img src="docs/en/img/shuffle.gif"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplSpotifyShuffleButton&quot;,&quot;data&quot;:{&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;oidon&quot;:&quot;spotify-premium.0.player.shuffleOn&quot;,&quot;oidoff&quot;:&quot;spotify-premium.0.player.shuffleOff&quot;,&quot;oidstate&quot;:&quot;spotify-premium.0.player.shuffle&quot;,&quot;coloroff&quot;:&quot;white&quot;,&quot;coloron&quot;:&quot;green&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;319px&quot;,&quot;top&quot;:&quot;622px&quot;,&quot;width&quot;:&quot;38px&quot;,&quot;height&quot;:&quot;40px&quot;},&quot;widgetSet&quot;:&quot;spotify-premium&quot;}]</code></pre></details><details><summary> Kontextbild<br/><img src="docs/en/img/context_image.png"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplValueStringImg&quot;,&quot;data&quot;:{&quot;oid&quot;:&quot;spotify-premium.0.player.contextImageUrl&quot;,&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;refreshInterval&quot;:&quot;0&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;338px&quot;,&quot;top&quot;:&quot;131px&quot;,&quot;width&quot;:&quot;122px&quot;,&quot;height&quot;:&quot;122px&quot;},&quot;widgetSet&quot;:&quot;basic&quot;}]</code></pre></details><details><summary> Wählen Sie den Titel der aktuellen Playlist<br/><img src="docs/en/img/choose_track.gif"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplJquiSelectList&quot;,&quot;data&quot;:{&quot;oid&quot;:&quot;spotify-premium.0.player.playlist.trackList&quot;,&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;values&quot;:&quot;{spotify-premium.0.player.playlist.trackListNumber}&quot;,&quot;texts&quot;:&quot;{spotify-premium.0.player.playlist.trackListString}&quot;,&quot;height&quot;:&quot;100&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;505px&quot;,&quot;top&quot;:&quot;369px&quot;},&quot;widgetSet&quot;:&quot;jqui&quot;}]</code></pre></details><details><summary> Gerät wechseln<br/><img src="docs/en/img/choose_device.gif"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplJquiSelectList&quot;,&quot;data&quot;:{&quot;oid&quot;:&quot;spotify-premium.0.devices.deviceList&quot;,&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;values&quot;:&quot;{spotify-premium.0.devices.availableDeviceListIds}&quot;,&quot;texts&quot;:&quot;{spotify-premium.0.devices.availableDeviceListString}&quot;,&quot;height&quot;:&quot;100&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;578px&quot;,&quot;top&quot;:&quot;378px&quot;},&quot;widgetSet&quot;:&quot;jqui&quot;}]</code></pre></details><details><summary> Playlist wechseln<br/><img src="docs/en/img/choose_playlist.gif"></summary><pre> <code>[{&quot;tpl&quot;:&quot;tplJquiSelectList&quot;,&quot;data&quot;:{&quot;oid&quot;:&quot;spotify-premium.0.playlists.playlistList&quot;,&quot;g_fixed&quot;:false,&quot;g_visibility&quot;:false,&quot;g_css_font_text&quot;:false,&quot;g_css_background&quot;:false,&quot;g_css_shadow_padding&quot;:false,&quot;g_css_border&quot;:false,&quot;g_gestures&quot;:false,&quot;g_signals&quot;:false,&quot;g_last_change&quot;:false,&quot;visibility-cond&quot;:&quot;==&quot;,&quot;visibility-val&quot;:1,&quot;visibility-groups-action&quot;:&quot;hide&quot;,&quot;values&quot;:&quot;{spotify-premium.0.playlists.playlistListIds}&quot;,&quot;texts&quot;:&quot;{spotify-premium.0.playlists.playlistListString}&quot;,&quot;height&quot;:&quot;100&quot;,&quot;signals-cond-0&quot;:&quot;==&quot;,&quot;signals-val-0&quot;:true,&quot;signals-icon-0&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-0&quot;:0,&quot;signals-blink-0&quot;:false,&quot;signals-horz-0&quot;:0,&quot;signals-vert-0&quot;:0,&quot;signals-hide-edit-0&quot;:false,&quot;signals-cond-1&quot;:&quot;==&quot;,&quot;signals-val-1&quot;:true,&quot;signals-icon-1&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-1&quot;:0,&quot;signals-blink-1&quot;:false,&quot;signals-horz-1&quot;:0,&quot;signals-vert-1&quot;:0,&quot;signals-hide-edit-1&quot;:false,&quot;signals-cond-2&quot;:&quot;==&quot;,&quot;signals-val-2&quot;:true,&quot;signals-icon-2&quot;:&quot;/vis/signals/lowbattery.png&quot;,&quot;signals-icon-size-2&quot;:0,&quot;signals-blink-2&quot;:false,&quot;signals-horz-2&quot;:0,&quot;signals-vert-2&quot;:0,&quot;signals-hide-edit-2&quot;:false,&quot;lc-type&quot;:&quot;last-change&quot;,&quot;lc-is-interval&quot;:true,&quot;lc-is-moment&quot;:false,&quot;lc-format&quot;:&quot;&quot;,&quot;lc-position-vert&quot;:&quot;top&quot;,&quot;lc-position-horz&quot;:&quot;right&quot;,&quot;lc-offset-vert&quot;:0,&quot;lc-offset-horz&quot;:0,&quot;lc-font-size&quot;:&quot;12px&quot;,&quot;lc-font-family&quot;:&quot;&quot;,&quot;lc-font-style&quot;:&quot;&quot;,&quot;lc-bkg-color&quot;:&quot;&quot;,&quot;lc-color&quot;:&quot;&quot;,&quot;lc-border-width&quot;:&quot;0&quot;,&quot;lc-border-style&quot;:&quot;&quot;,&quot;lc-border-color&quot;:&quot;&quot;,&quot;lc-border-radius&quot;:10,&quot;lc-zindex&quot;:0},&quot;style&quot;:{&quot;left&quot;:&quot;571px&quot;,&quot;top&quot;:&quot;509px&quot;},&quot;widgetSet&quot;:&quot;jqui&quot;}]</code></pre></details>

## Changelog
<!--
    Placeholder for the next version (at the beginning of the line):
    ### **WORK IN PROGRESS**
-->
### **WORK IN PROGRESS**
-   (mcm1957) changed: Testing has been changed to support node 16, 18 and 20
-   (mcm1957) changed: Dependencies have been updated

### 1.2.2 (2022-06-17)
* (Apollon77) Fix potential crash cases reported by Sentry
* (Apollon77) Optimize adapter stop behaviour

### 1.2.1 (2022-05-12)
* (Apollon77) Prevent js-controller warnings

### 1.2.0 (2022-05-11)
* (duczz) Fix tracklist request issues
* (Apollon77) Fix several potential crash cases and object warnings
* (Apollon77) Add Sentry for crash reporting

### 1.1.9 (2021-11-21)
* (bluefox) Tried to catch 403 error

### 1.1.8 (2021-11-18)
* (ohle64) Fixed the shuffle behaviour 
* (bluefox) Allowed to set the default shuffle value
* (bluefox) The type of trackNo corrected

### 1.1.4 (2021-11-17)
* (bluefox) Fix errors

### 1.1.3 (2021-07-22)
* (bluefox) Improved authorization process

### 1.1.1 (2021-07-22)
* (bluefox) removed warnings for js-controller 3.x

### 1.1.0 (in dev)
* IMPORTANT: js-controller 2.0.0 is now required at least
* (twonky) added control widgets
* (twonky) added compact mode
* (Apollon77) Core Files/Testing Update and introduce adapter-core
* (twonky) added state `player.playUri` to support user defined input
* (Apollon77) Fix js-controller 3.3 warnings
* (Xyolyp) Listen on `player.volume` instead of player.device.volume as the latter is readonly
* (bellerG) fix player.playUri

### 1.0.0 (2018.12.18)
* (twonky) `playbackInfo` and `player` merged together to `player`
* (twonky) `player.volume` moved to `player.device.volume`
* (twonky) The `duration` format of `player.playlist.trackListArray` and `playlists.[playListName].trackListArray` was changed from milliseconds to time (MM:SS) and a new one was created for this `durationMs`.
* (twonky) The `album` of `player.playlist.trackListArray` and `playlists.[playListName].trackListArray` was changed to `artistName` and `artistArray`.
* (twonky) Several data was added to `player.playlist.trackListArray` and `playlists.[playListName].trackListArray`: `album`, `addedAt`, `addedBy`, `discNumber`, `episode`, `explicit` and `popularity`
* (twonky) change `player.playlist.trackNo` to start with 1 (0-based before)
* (twonky) performance optimization (states/objects are only set on change)
* (twonky) html lists added: `html.devices`, `html.playlists` and `html.tracks`
* (twonky) new icons

### 0.3.1 (2018.06.20)
* (twonky) Fix: state playlists.playlistList doesn't refresh after the playlist changed via app

### 0.3.0 (2018.05.31)
* (twonky) Change playlist and device state names from name to id
* (twonky) New states for device selection: `devices.deviceList`, `devices.deviceListIds`, `devices.deviceListString`, `devices.availableDeviceListIds`, `devices.availableDeviceListString`
* (twonky) New states for playlist selection: `playlists.playlistList`, `playlists.playlistListIds`, `playlists.playlistListString`, `playlists.yourPlaylistListIds`, `playlists.yourPlaylistListString`
* (twonky) Add option to avoid shuffle state reset on some devices after starting a playlist

### 0.2.5 (2018.05.24)
* (twonky) Fix: `playlists.YourPlaylistName.playThisList` starts always with second track

### 0.2.4 (2018.05.17)
* (twonky) remove special character ("'*) from device and playlist state names

### 0.2.3 (2018.05.17)
* (twonky) remove special character (,?[]) from device and playlist state names

### 0.2.2 (2018.05.16)
* (twonky) `playbackInfo.playlist.track*` States are only reset when changed; stop flickering of tracks SelectList (example "Choose track of current playlist")

### 0.2.1 (2018.05.14)
* (twonky) change state `player.shuffle` to string with possible values "on" and "off"

### 0.2.0 (2018.05.13)
* (twonky) removed support for deprecated state `PlaybackInfo.image_url`
* (twonky) all states improved and proper descriptions added

### 0.1.3 (2018.04.28)
* (twonky) fix spotify api change

### 0.1.2 (2018.04.10)
* (twonky) automatic updating of devices and playlists (configurable in the adapter)
* (twonky) new state `Devices.DEVICE.is_available` indicates if a device is available
* (twonky) shows warning message http 202 only as debug and only one time
* (twonky) the States `Player.Shuffle`,` Player.Playlist_ID`, `Player.TrackId` and` Player.Volume` also show the current value
* (twonky) new states `Playlists.PLAYLISTNAME.image_url`,` PlaybackInfo.Playlist_image_url`, `PlaybackInfo.Album_image_url`
* (twonky) marks the state `PlaybackInfo.image_url` as deprecated. Will not be included in a new installation and will not be updated in future versions
* (twonky) changing the State `Playlists.PLAYLISTNAME.Track_ID` now works like in Lucky's script

### 0.1.1 (2018.03.03)
* (twonky) fix several small issues

### 0.1.0 (2018.02.23)
* (twonky) rework api polling mechanism

### 0.0.9 (2018.02.21)
* (twonky) new state `PlaybackInfo.repeat` with possible values: off, context, track
* (twonky) new state `PlaybackInfo.shuffle` with possible values: true, false
* (twonky) states for the playing device will also updated in 5s intervals
* (twonky) states in `PlaybackInfo` are now updated also if no device is active playing
* (twonky) states in `PlaybackInfo` are now cleared if no device is available
* (twonky) loading new playlists if playing the first time

### 0.0.8 (2018.02.20)
* (twonky) new adapter option to delete no longer existing devices and playlists
* (twonky) load complete playlists (limitation of 100 first tracks was removed)

### 0.0.7 (2018.02.16)
* (twonky) fix: auto refresh token

### 0.0.6 (2018.02.16)
* (twonky) fix: playlist loading

### 0.0.5 (2018.02.16)
* (twonky) fix: fatal error if no open player

### 0.0.4 (2018.02.16)
* (twonky) check configuration
* (twonky) fix: adapter configuration in admin2
* (twonky) fix: restart after authorization need

### 0.0.3 (2018.02.15)
* (wendy2702) improved manual

### 0.0.2 (2018.02.11)
* (twonky) merge original script v0.5.3 by [Lucky](http://forum.iobroker.net/viewtopic.php?f=21&t=8173)

### 0.0.1 (2018.02.07)
* (twonky) initial adapter, original script v0.5.1 by [Lucky](http://forum.iobroker.net/viewtopic.php?f=21&t=8173)

## License
The MIT License (MIT)

Copyright (c) 2019-2022 Alexander Kose <twonky4@gmx.de>

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.