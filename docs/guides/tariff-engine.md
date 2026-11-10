# JTS Tariff Engine — Human Operations Manual

For JTS Tariff Engine v1.2.1.

## Mission Directive

Track verified 15-minute electricity prices for DK1 or DK2 through Home
Assistant sensors, diagnostics, a read-only dashboard and stored price history.

## Commissioning

Use Home Assistant 2026.10 or later and the official Nord Pool integration
configured for DK1 or DK2 in DKK. Install through HACS as a custom integration
or use the manual Home Assistant ZIP. [Installation and updates](../HACS_DISTRIBUTION.md).

Add a site, select the Nord Pool source, enter verified grid and supplier rates
and confirm the VAT display preference. Use **Configure** to resume or edit
setup. Configure shows a short English overview of what the integration does.
The link on **Service info** opens the README commissioning guide.
[Dashboard and display units](../PRICE_DASHBOARD.md).

## Verification

Open the site's service under **Settings → Devices & services**. Check the
configured site name, JTS Tariff Engine model, Jefferies Tube Solutions
manufacturer and installed version. Compare a verified quarter's components
with the configured rates. Missing or stale prices should show as unavailable.
[Native diagnostics](../DIAGNOSTICS.md).

CI covers HA 2026.10.3 and 2026.10.4, both ZIP layouts and desktop/mobile
dashboard scenarios. Verify private rates and live source access at the
installation. [Test evidence](../DEVELOPMENT_STATUS.md).

## Fault Isolation and Recovery

Check Nord Pool availability and the effective dates of the grid and supplier
rates. Use **Check prices now** to retry verification. Delete the site's SQLite files to recover from an incomplete price history.
The integration restores the full history and its prior revisions from Nord Pool
on the next update. A backup is unnecessary. [Data retention and rollback](../HACS_DISTRIBUTION.md#data-retention-and-rollback).
