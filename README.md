# Arman Tunnel — public configs repo

This repository is the **public** delivery target for the SnapDark/Arman Tunnel app.

The admin panel (Cloudflare Worker at `admin.cloudv2roy.xyz`) commits three
**AES-GCM encrypted** files here on every publish:

| File | Contents |
|---|---|
| `arman_configs_2026_v2.enc` | JSON array of active server configs (v2/v3 envelope) |
| `arman_app_settings.enc` | app settings bundle (branding, lock, force-update, categories) |
| `sensei_backup.enc` | encrypted full-panel snapshot (off-site backup) |

The app downloads them from the GitHub Pages CDN:
`https://armanmiah2026.github.io/arman-tunnel-configs/<file>`

These files are ciphertext — publishing them publicly is safe. The plaintext
never leaves the Worker.
