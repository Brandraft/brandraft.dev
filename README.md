# brandraft.dev

The landing page at https://brandraft.dev: one static HTML file plus a favicon,
served from Cloudflare's edge as a Worker with static assets.

## Deploy

The Worker is named `brandraft`. Deploy from a terminal with a scoped API token
(keep the token and account id in an env file with mode 600, outside the repo):

```sh
CLOUDFLARE_API_TOKEN=... CLOUDFLARE_ACCOUNT_ID=... npx wrangler deploy
```

or connect this repository once in the Cloudflare dashboard: Workers & Pages,
Create, Import a repository, pick `Brandraft/brandraft.dev`. Cloudflare reads
`wrangler.jsonc`, binds the custom domain `brandraft.dev`, and redeploys on every
push to `main`. No build step: the site is the `public/` directory.


## Edit

`public/index.html` is the whole page. Add a project as one more `<li>` in the list.
