# SwarnKosh WhatsApp engine updates

This directory is ready for static HTTPS hosting. Upload **all its contents** to a public repository in one Git commit. Keep the metadata/ and targets/ directories, old numbered metadata and hashed targets. No server, npm install, GitHub Actions secrets or shop credentials are needed by the public repository.

Engine: 1.0.0; metadata version: 3.
Timestamp expires: **2026-10-21T12:02:09.638Z**.
Trust root expires: 2027-10-14T09:56:57.595Z.

## Hosting

If these files are at the root of OWNER/REPO on branch main, the app configuration is:

```json
{
  "metadataUrl": "https://raw.githubusercontent.com/OWNER/REPO/main/metadata/",
  "targetUrl": "https://raw.githubusercontent.com/OWNER/REPO/main/targets/",
  "target": "whatsapp-v1.json"
}
```

If you commit this directory as dist/, add /dist before /metadata/ and /targets/. GitHub Pages or another static host also works with directly served HTTPS URLs. Use the file-serving URL, not a GitHub /blob/ page or a redirecting release-asset URL. The included .nojekyll supports Pages hosting.

Set these URLs in resources/whatsapp/trust.json in the SwarnKosh source project. The release tool has installed the matching **public** root at resources/whatsapp/root.json. Ship these resources in the first OTA-enabled desktop application. The public server alone cannot establish client trust. Repository URLs have deliberately not been guessed.

## Subsequent releases and refreshes

In the original private SwarnKosh project, run:

```powershell
npm run whatsapp:release
npm run whatsapp:verify-release
```

Upload the complete resulting dist contents again in one commit. Refresh every few days, **before the seven-day timestamp expiry**, even without engine changes. The command increments metadata versions and preserves immutable history. Expiry blocks new downloads; cached verified engines can still run unless revoked. No scheduled public publisher is installed: retain one authoritative publishing machine/state to avoid conflicting version numbers.

Back up .whatsapp-release/ securely in the private project. It contains signing keys and canonical repository history and must NEVER be uploaded here. Keep root.pem offline after backing it up; routine releases use the other three keys. Do not regenerate keys, delete history, or reset metadata versions between releases. Root/key rotation must be arranged before the one-year root expiry; it is not automated by these scripts.

## Runtime and notices

The signed target embeds the engine JavaScript, required npm dependencies and WASM. It runs in SwarnKosh's Node/Electron utility process (Node 22 or newer for this build). Shops do not install Node, npm or node_modules separately. This is not a browser script or standalone executable. Optional image/audio/link-preview features are outside the invoice-PDF integration.

See THIRD_PARTY_NOTICES.txt and SOURCES.md for bundled dependency licenses, source inventory and archive limitations. These files do not grant a license to the proprietary SwarnKosh application. Live Meta/Baileys sending and the eventual hosted endpoint require a separate deployment check.
