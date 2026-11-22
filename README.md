# TideNav for OpenCPN

TideNav helps you plan a passage using surface current forecasts. It compares
25 departure times over 12 hours and estimates arrival time, true heading
and speed over ground along an existing OpenCPN route. You can inspect the
selected departure's steering plan and preview currents, wind and waves on
the chart.

## Download and install

**0.12.0-beta.3** is available for **OpenCPN Flatpak on Linux x86_64**, using
Freedesktop runtime **25.08**. [Download the beta installer](https://github.com/SteileBank/tidenav-releases/releases/download/0.12.0-beta.3/TideNav-0.12.0-beta.3_flatpak-x86_64-25.08-x86_64.tar.gz) · [Release notes](https://github.com/SteileBank/tidenav-releases/releases/tag/0.12.0-beta.3)

1. Open OpenCPN's plugin manager and select **Import plugin**.
2. Select the downloaded installer `.tar.gz` and enable TideNav.
3. Open TideNav from the OpenCPN toolbar.

Use the same import process when upgrading. [All releases](https://github.com/SteileBank/tidenav-releases/releases)

## Plan your first passage

1. Create or open a route in OpenCPN, then select it in TideNav. Use
   **Refresh routes** after editing the route in OpenCPN.
2. Enter your earliest departure in UTC and your speed through water in
   knots. Select **Update forecasts** to fetch current data for the route.
3. Select a departure in the comparison to inspect its ETA, leg details and
   **Steering plan**. Use **Forecast coverage** to locate gaps along the route.
4. For wind and waves, select **Enable marine weather (information only)**,
   then **Update wind / weather**. The weather table shows conditions at
   estimated waypoint arrival times. The chart overlays follow the chart's
   UTC slider.

Forecast downloads start when you select an update button. TideNav can reuse
saved forecasts offline while they cover the selected area and time.

## Forecast coverage and estimates

| Data | Sources |
| --- | --- |
| Surface currents | DMI DKSS, MET Norway Norkyst and Copernicus NWS in their coverage areas, with Copernicus SMOC as the global open-water fallback. |
| Wind and waves | DMI WAM NSB for the North Sea and Baltic Sea, with NOAA GFS-Wave as the offshore fallback. |

When current data is missing, TideNav assumes zero current for those sections
and marks the ETA as conditional. Only departures with full current coverage
qualify for the fastest-departure recommendation. Wind and waves are shown
for planning. The heading and ETA estimates use surface currents and speed
through water.

Use local data for harbours and narrow passages. Automatic current downloads
support routes that avoid crossing the 180° meridian.

## Source code and licence

Each release includes the corresponding source archive and `SHA256SUMS`.
The source archive contains `BUILD-FROM-SOURCE.md` and the licence notices
for the bundled components. [Beta 3 source archive](https://github.com/SteileBank/tidenav-releases/releases/download/0.12.0-beta.3/TideNav-0.12.0-beta.3-source.tar.gz) · [Beta 3 checksums](https://github.com/SteileBank/tidenav-releases/releases/download/0.12.0-beta.3/SHA256SUMS)

TideNav is licensed under GPL-3.0-or-later and builds on Mike Rossiter's
ShipDriver plugin. OpenAI Codex helped write TideNav's code, tests and
documentation under human direction.
