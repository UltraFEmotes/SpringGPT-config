# SpringGPT service configuration

`config.json` controls the temporary model service behind SpringGPT. It is public: **never put API keys, credentials or private data here.**

1. Run the SpringGPT Kaggle notebook with Internet and a GPU enabled. Keep the final cell running while you want the service online.
2. Copy the `https://...trycloudflare.com` URL printed by the notebook.
3. Edit `config.json`, put that URL in `backend_url`, and set `enabled` to `true`. Save the change to `main`. The gateway checks for changes roughly every 15 seconds.
4. When the notebook stops or the URL changes, update the file. Set `enabled` to `false` when the service is unavailable.

The gateway accepts only HTTPS Quick Tunnel URLs ending in `.trycloudflare.com` and never follows redirects. The temporary tunnel has no authentication; conversations pass through the configured service. This setup is a prototype with no uptime, performance, or privacy guarantees. The 0.6B model is small and may be inaccurate; longer thinking can make responses slower. Kaggle's quotas, notebook session time limits and Cloudflare service limits still apply.
