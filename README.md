# roast.404909.xyz

Public-only GitHub Pages source for the daily roast archive.

The repository intentionally contains only the static site, its archived
reports, and the Pages workflow. The wider `404909.xyz` application repository
remains private.

## Publishing

`.github/workflows/deploy-roast.yml` archives `roast/index.html`, prepares the
static Pages artifact, and deploys it to `https://roast.404909.xyz`.

## Access from another device

Repository URL:

```text
git@github.com:getitcheappro/roast-404909-xyz.git
```

Clone and inspect:

```bash
git clone git@github.com:getitcheappro/roast-404909-xyz.git
cd roast-404909-xyz
python3 -m http.server 8000
```

Then open `http://127.0.0.1:8000/`.

No environment variables, API keys, database, package installation, or
external service credentials are required. GitHub Pages is deployed by GitHub
Actions from the `main` branch. The custom domain is declared in `CNAME`; DNS
must keep `roast.404909.xyz` pointed at `getitcheappro.github.io`.

Troubleshooting:

- A Pages deployment returning HTTP 422 usually means Pages is disabled or the
  repository is private on a plan that does not support private Pages.
- A certificate-name mismatch means the custom domain is missing from the
  repository's Pages settings or GitHub is still issuing the certificate.
- Check Pages state with
  `gh api repos/getitcheappro/roast-404909-xyz/pages`.
