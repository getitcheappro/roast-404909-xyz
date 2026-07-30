# roast.404909.xyz

Public GitHub Pages host for the daily roast archive.

The daily source report is maintained in the private `getitcheappro/404909.xyz`
repository at `roast/index.html`. This repository owns the public custom domain
and deploys the static archive at `https://roast.404909.xyz`.

## Publishing

`.github/workflows/deploy-roast.yml` fetches `roast/index.html` from
`getitcheappro/404909.xyz`, archives it into `reports/YYYY-MM-DD/index.html`,
updates `reports.json`, and deploys the Pages artifact.

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

No package installation, database, API keys, or local `.env` file are required
for local static inspection. Public deployment uses GitHub Actions from `main`.

Required GitHub Actions secret:

```text
ROAST_SOURCE_TOKEN=<token with read access to getitcheappro/404909.xyz>
```

Do not commit the token. Set or rotate it with GitHub Actions secrets.

The custom domain is declared in `CNAME`; DNS must keep `roast.404909.xyz`
pointed at `getitcheappro.github.io`. GitHub Pages source must remain set to
GitHub Actions.

Troubleshooting:

- If `/today/` does not update, check the latest `Deploy Roast` workflow run and
  confirm `ROAST_SOURCE_TOKEN` can read `getitcheappro/404909.xyz`.
- If the workflow archives an old report, confirm the private
  `getitcheappro/404909.xyz:roast/index.html` file was actually updated.
- A Pages deployment returning HTTP 422 usually means Pages is disabled or the
  custom domain is already assigned to another repository.
- A certificate-name mismatch means the custom domain is missing from this
  repository's Pages settings or GitHub is still issuing the certificate.
- Check Pages state with
  `gh api repos/getitcheappro/roast-404909-xyz/pages`.
