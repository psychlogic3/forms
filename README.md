# forms.psychlogic.in: PsychLogic Forms hub

```
index.html              → forms.psychlogic.in             (list of all forms)
support-group/          → forms.psychlogic.in/support-group/
CNAME                   → tells GitHub Pages to use forms.psychlogic.in
```

## Publish (one time)
1. On GitHub, create a new repository called `forms`.
2. Upload everything in this folder: `index.html`, `CNAME`, `README.md` and the `support-group` folder, including its `assets`.
3. Go to **Settings → Pages**. Set Source to "Deploy from a branch", choose `main` and `/ (root)`, then click **Save**. Make sure Custom domain shows `forms.psychlogic.in`, and tick **Enforce HTTPS** once it becomes available.
4. Where you manage psychlogic.in's DNS, add this record (the same type you used for `notes`):
   - Type: **CNAME** · Name: **forms** · Value: **psychlogic3.github.io**
5. Wait 10–60 minutes, then open https://forms.psychlogic.in

**Before going live:** paste your Apps Script URL into `support-group/index.html` (`JOIN_ENDPOINT_URL`). The steps are in `support-group/README.md`.

## Opening or closing a form later
In `index.html`, each form is one `<article class="card ...">` block.

**To open a closed form:**
1. Change `is-closed` to `is-open`.
2. Change `status closed` / `dot closed` / `Closed` to `status open` / `dot open` / `Open`.
3. Replace the `<span class="btn off" ...>🔒 Registration closed</span>` with:
   ```html
   <a class="btn go" href="LINK-TO-FORM">Register now <span class="arrow">→</span></a>
   ```
4. Move the card into the "Open now" grid.

The "2 open / 3 closed" counts at the top update automatically.
