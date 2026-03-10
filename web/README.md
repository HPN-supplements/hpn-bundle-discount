# HPN Bundle Discount Web Server

Minimal Express server that handles Shopify OAuth and auto-creates
the Bundle Builder automatic discount when installed.

## Deploy to Railway (free)

1. Go to https://railway.app → New Project → Deploy from GitHub repo
2. Set root directory to `web/`
3. Add environment variables:
   - `SHOPIFY_API_KEY` = c77962b9da62ce623c46b24b8c97f2b1
   - `SHOPIFY_API_SECRET` = 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
   - `HOST` = https://your-app.railway.app (the URL Railway gives you)
4. Deploy → copy the URL

## After deploy

Update `shopify.app.toml`:
```toml
application_url = "https://your-app.railway.app"

[auth]
redirect_urls = [ "https://your-app.railway.app/auth/callback" ]
```

Then run:
```
shopify app deploy
```

And reinstall the app on hpnsupplements.myshopify.com — it will
auto-create the discount on install.
