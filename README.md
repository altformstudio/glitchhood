# GLITCH allowlist website

## Files
- `index.html`: frontend website.
- `Code.gs`: Google Apps Script backend.

## Google Sheet
The first sheet's row 1 must contain these headers in order:
`Timestamp | X Username | Ethereum Wallet | Reply URL`

## Setup
1. Confirm `SPREADSHEET_ID` in `Code.gs` matches your private Google Sheet.
2. Confirm `SITE_ORIGIN` is your actual GitHub Pages origin. If your Pages URL is `https://NFT-BOY.github.io`, keep the current value. If the site is hosted at a project path, the origin is still the domain origin, not the path.
3. In Apps Script, save the code, run `testSpreadsheetAccess` once and approve the permissions when prompted.
4. Deploy > Manage deployments > Edit > New version > Deploy. Set Execute as: Me. Set access so visitors can submit without signing in, if that is your intended public flow.
5. Keep the deployed `/exec` URL in `index.html` as `APPS_SCRIPT_URL`.
6. Test one entry and verify a row is added. This code checks duplicate X username and wallet and stores reply URL. Social tasks are not automatically verified.

## Important
Do not collect seed phrases or private keys. The public wallet address is not a secret. This starter does not independently verify that a user followed, liked, reposted, or replied.
