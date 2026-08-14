# Stockify — rebuilt from scratch

This is a completely new build of your app: new design ("Warehouse
Manifest" — dark ink header, warm amber scan accent, cream paper
background, condensed display type + monospace for barcode/SKU
numbers), and it runs **fully offline** with no server at all. All
your data — inventory, categories, stocktake history — lives on the
device itself (local storage), not on Netlify. That also means: no
CORS patches, no cookie settings, no `auth.mjs` — none of that
complexity exists anymore.

## What's included

- **Home dashboard** — item count, stock value, low-stock count, categories
- **Inventory** — add/edit/delete items, search, category filters, pull-to-refresh
- **Barcode scanner** — camera scanning (with flashlight toggle) that
  properly releases the camera when closed, or manual entry
- **Stocktake** — start a count session, scan/tally items, see
  over/under vs. system stock, export results
- **Price labels** — pick items, export a price-label sheet
- **Statistics** — charts on stock value/levels
- **Settings** — PIN lock, dark mode, currency, category management,
  full data export
- Excel export saves through Android's native Save/Share sheet (the
  bug you hit before is fixed from the start this time)

## First-time setup: a PIN, not a login

There's no username/password server anymore — instead, on first
launch you'll set a PIN to lock the app. Simpler, and it works with
zero internet connection.

## Build steps

1. Create a **new, separate** GitHub repo (don't reuse `Myappbuilder`
   — that one's wired to your old site-loading version; a fresh repo
   keeps things clean)
2. Upload everything in this folder (via "Add file → Upload files" on
   GitHub's website, same as before) — make sure the hidden `.github`
   folder and the `resources` folder both come along
3. Go to the **Actions** tab, wait for the green checkmark
4. Download the APK from **Artifacts**
5. **Uninstall the old Stockify app first** (different app internally,
   Android will otherwise refuse to install over it), then install
   the new one

## One thing to know

Because everything is stored locally on the device now, your
inventory data won't automatically appear on a different phone or
sync anywhere. If you need multi-device sync later, that's a bigger
feature (would need a real backend again) — just say so and we can
plan it.
