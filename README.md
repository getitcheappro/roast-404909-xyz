# roast.404909.xyz archive mirror

Public archive mirror for the daily roast site.

The canonical source for `https://roast.404909.xyz` is now
`getitcheappro/404909.xyz`. That repository owns the custom domain and receives
the daily `roast/index.html` updates.

## Publishing

`.github/workflows/deploy-roast.yml` can still archive `roast/index.html` and
deploy this repository to its default GitHub Pages URL, but it no longer owns
the `roast.404909.xyz` custom domain.

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

No environment variables, API keys, database, package installation, or external
service credentials are required. GitHub Pages is deployed by GitHub Actions
from the `main` branch. The custom domain is intentionally not declared here;
`roast.404909.xyz` belongs to `getitcheappro/404909.xyz`.

Troubleshooting:

- A Pages deployment returning HTTP 422 usually means Pages is disabled or the
  repository is private on a plan that does not support private Pages.
- A certificate-name mismatch for `roast.404909.xyz` should be checked in
  `getitcheappro/404909.xyz`, not this mirror repository.
- Check Pages state with
  `gh api repos/getitcheappro/roast-404909-xyz/pages`.
