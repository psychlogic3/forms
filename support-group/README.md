# PsychLogic Support Group website

One-page website: "A Safe Space for You 💙". It includes the registration form, the ₹199 UPI payment (same QR as the notes website), the screenshot upload, and an email to you on every registration.

## Files in this repo (public)
- `index.html`: the whole website
- `assets/payment-qr.png`: the UPI QR (amang9290@ybl), same as the notes site

**Never upload `Support-Group-Script.txt` to GitHub.** It stays private in Google Apps Script.

## One-time setup (about 10 minutes)

### 1. Create the backend (sends you an email on every registration)
1. Open https://script.google.com and sign in as **kavyauuy@gmail.com**. Click **New project**.
2. Delete the sample code. Paste everything from `Support-Group-Script.txt`, then save (Ctrl+S). Name the project "PsychLogic Support Group".
3. In the toolbar, choose **setupSupportGroup** and click **Run**. Allow the permissions it asks for.
   - This creates a Google Sheet called "PsychLogic - Support Group Registrations".
   - It also creates a Drive folder called "Support Group Payments" inside your existing payments folder.
4. Optional: choose **testEmail** and click **Run**. You should get a test email.
5. Click **Deploy → New deployment → ⚙ → Web app**:
   - Execute as: **Me**
   - Who has access: **Anyone**
   - Click **Deploy** and copy the **Web app URL** (it ends in `/exec`).

### 2. Connect the website
Open `index.html` and find this line near the bottom:
```
const JOIN_ENDPOINT_URL = '';
```
Paste your URL between the quotes, then save.

Until a URL is added, the form shows a friendly "message us on WhatsApp" note, so nobody loses a registration.

### 3. Publish on GitHub Pages
1. On GitHub, create a new repository, for example `support-group`.
2. Upload `index.html`, `README.md` and the `assets` folder.
3. Go to **Settings → Pages**. Set Source to "Deploy from a branch", choose `main` and `/ (root)`, then click **Save**.
4. The site goes live at `https://psychlogic3.github.io/support-group/`.

To use a subdomain such as `support.psychlogic.in`:
- Add a file named `CNAME` that contains just that domain.
- In your domain DNS, add a CNAME record that points `support` to `psychlogic3.github.io`.

## What happens on each registration
1. The screenshot is saved in Drive, in the "Support Group Payments" folder.
2. A row is added to the Sheet. These columns are for you to update: Payment status, Added to group?, Refund status.
3. You get an email with all the details, a link to the screenshot, and a one-tap WhatsApp chat link for the member.
4. The member is redirected to your WhatsApp (917987623467) with a ready-made message that includes their reference number.

**Always check the ₹199 in your bank or UPI app before adding someone.** A screenshot can be faked.

## Editing later
- Fee, UPI ID and WhatsApp number: find "OWNER SETTINGS" at the bottom of `index.html`. If you change the fee, also change `FEE_INR` in the script and redeploy.
- After any script change: **Deploy → Manage deployments → ✏ → Version: New version → Deploy**. The URL stays the same.
- Tiny tasks shown on the page: edit the `TINY_TASKS` list in `index.html`.
