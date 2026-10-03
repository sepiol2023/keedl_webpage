# Keedl public website

Dependency-free static website for Keedl, published from the repository root with GitHub Pages. There is no build step or backend.

## URLs

- Canonical homepage: <https://keedl.com/>
- Privacy Policy: <https://keedl.com/privacy/>
- Terms of Service: <https://keedl.com/terms/>
- GitHub Pages project URL: <https://sepiol2023.github.io/keedl_webpage/>
- Repository: <https://github.com/sepiol2023/keedl_webpage>

The custom domain and canonical metadata are prepared in this repository. The GitHub repository and Pages site are not yet available; publish from `main` at `/(root)` and attach `keedl.com` in the repository's Pages settings to activate these URLs.

## Publish with GitHub Pages

1. Push the `main` branch to `https://github.com/sepiol2023/keedl_webpage`.
2. In GitHub, open **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/(root)`, then save. No workflow or build command is needed.
3. Once the first deployment finishes, confirm the project URL and the `/privacy/` and `/terms/` pages work.
4. In **Settings → Pages → Custom domain**, enter `keedl.com` and save. The root `CNAME` file in this repository also declares that hostname.
5. Add the DNS records below in Porkbun. Remove conflicting records for `@` or `www` that point elsewhere.
6. Wait for GitHub's DNS check and certificate provisioning. Then enable **Enforce HTTPS** in **Settings → Pages**. DNS propagation and certificate issuance can take time; leave HTTPS enforcement off until GitHub offers it.

## Porkbun DNS records

GitHub account owner verified for this repository: `sepiol2023`.

Create these records in Porkbun DNS:

| Type | Host | Answer |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `sepiol2023.github.io` |

After `keedl.com` is set as the Pages custom domain and both apex and `www` DNS point to GitHub Pages, GitHub Pages handles the domain variant redirect; no redirect code is included in the site.

## Local preview and updates

From the repository root:

```sh
python -m http.server 8000
```

Open <http://localhost:8000/>. To update the live site after setup:

```text
edit → commit → push to main → GitHub Pages publishes
```

## Site files

- `index.html` — homepage, canonical metadata and Open Graph tags
- `privacy/index.html` — Privacy Policy
- `terms/index.html` — Terms of Service
- `styles.css` — shared responsive styles
- `etc/Logo.png` — supplied logo, header, favicon and social preview image
- `CNAME` — GitHub Pages custom domain (`keedl.com`)

The site contains no application secrets or credentials. The support email is still awaiting an official address; the pages state that no official contact address has been configured.
