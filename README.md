# Goal-on CV Site (GitHub Pages)

This folder is a small standalone git repo that publishes Danish Hussain's
interactive HTML CV to GitHub Pages. It deliberately stays separate from the
main project (which lives on OneDrive and is not a git repo).

The CV is generated from `profile.yaml` by `agents\cv_builder.py` in the
project root and copied here as `index.html` by
`scripts\deploy_ghpages.ps1`. Do not edit `index.html` by hand — regenerate
it.

## One-time setup

1. Create an empty public repository on GitHub, e.g. `danishhussain-cv`
   (do NOT add a README — this folder already provides one).
2. Run the deploy script with your repo URL:

   ```powershell
   powershell -ExecutionPolicy Bypass -File scripts\deploy_ghpages.ps1 `
     -RepoUrl https://github.com/<you>/danishhussain-cv.git
   ```

3. In the repo's **Settings → Pages**, set Source to **Deploy from a branch**,
   branch `main`, folder `/ (root)`.
4. Your CV will be live at
   `https://<you>.github.io/danishhussain-cv/`.
5. Put that URL into `agents\config.py` as `CV_URL` and rebuild outreach
   drafts so the link lands in the email signature.

## Re-deploy after a CV change

```powershell
powershell -ExecutionPolicy Bypass -File scripts\deploy_ghpages.ps1
```

(Repo URL is remembered in the git remote of this folder.)
