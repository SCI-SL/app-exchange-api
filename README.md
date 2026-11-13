# SL COOL API Reference Site

Static reference for the public SL Cool Agent and game APIs. The OpenAPI contract uses `https://open.sl.cool`; it excludes the SLConsole test backend and private service listener.

## Publish with GitHub Pages

1. This site is maintained in https://github.com/SCI-SL/app-exchange-api.
2. The repository root already contains the site, including `.github` and `.nojekyll`.
3. Push the files to the `main` branch.
4. In the repository, open **Settings → Pages** and select **GitHub Actions** as the build and deployment source.
5. Run **Actions → Deploy GitHub Pages → Run workflow**. The workflow is manual
   so uploading source does not attempt to deploy before Pages is configured.
   GitHub will show the published URL in Pages settings after deployment.

The site is plain HTML and JSON. No Node.js build or server-side runtime is required. Redoc and Swagger UI load from their public CDNs, so viewers need an internet connection.

## Local preview

From this directory, run:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000`. Serving over HTTP is required because the documentation viewer fetches the local OpenAPI JSON file.

## Files

- `API.md`: GitHub-readable reference with all endpoint parameters and examples.
- `index.html`: Redoc API reference.
- `swagger.html`: Swagger UI alternative; interactive requests are disabled by default.
- `platform-stock-public.openapi.json`: the public API contract (61 operations).
- `.github/workflows/pages.yml`: deploys this directory's repository root to GitHub Pages.

## Update the API contract

Update the OpenAPI contract and the matching endpoint details/examples in `API.md`, commit both, push to `main`, and run the deployment workflow. Do not publish internal tokens, private service URLs, or test-backend endpoints.

## Related CLI

https://github.com/SCI-SL/app-exchange-cli contains the installable Python CLI
for the same public API contract. Both projects use `https://open.sl.cool` as
the API origin.
