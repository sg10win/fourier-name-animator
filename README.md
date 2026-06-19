# Fourier Name Animator

A single-file interactive tool that draws any name using spinning circles — a visual demonstration of the Discrete Fourier Transform. Built for [Bros Animators](https://youtube.com/@bros_animators).

Sold on Gumroad. Download buttons are locked until purchase.

---

## Live demo

`https://USERNAME.github.io/fourier-name-animator/`

After purchase, Gumroad redirects to:

`https://USERNAME.github.io/fourier-name-animator/?unlocked=true`

This URL parameter removes the lock icons and enables the **Download HTML** and **Download GIF** buttons.

---

## How to update the Gumroad product URL

1. Create your product on [Gumroad](https://gumroad.com).
2. Copy the product link (looks like `https://yourname.gumroad.com/l/xxxxxx`).
3. Open `name-animator.html` and find the buy button near the top:
   ```html
   <a class="btn-buy" href="https://YOUR_GUMROAD_LINK_HERE" ...>
   ```
4. Replace `https://YOUR_GUMROAD_LINK_HERE` with your actual Gumroad link.
5. Commit and push to `main` — GitHub Actions will redeploy automatically.

---

## How to configure the Gumroad success redirect

1. In Gumroad, go to your product → **Edit** → **Customize** tab.
2. Find the **Redirect URL** (or "Thank You page URL") field.
3. Set it to:
   ```
   https://USERNAME.github.io/fourier-name-animator/?unlocked=true
   ```
   Replace `USERNAME` with your GitHub username and `fourier-name-animator` with your repo name if different.
4. Save the product.

Buyers will be redirected to this URL after checkout, where downloads are automatically unlocked.

---

## Adding custom fields in Gumroad checkout

You can collect buyer info (e.g. to personalise the animation) using Gumroad's custom fields:

1. In Gumroad, go to your product → **Edit** → **Checkout** tab (or **Custom fields** section).
2. Click **Add a field** and create:

   | Field label        | Type   | Required |
   |--------------------|--------|----------|
   | Recipient Name     | Text   | Yes      |
   | Color Preference   | Text   | Yes      |

3. **Recipient Name** — the name the buyer wants animated (e.g. "Sophie").
4. **Color Preference** — their preferred trace color (e.g. "blue", "#dc2626", "purple").
5. Save the product. These fields appear at checkout; responses are included in the sale receipt email sent to you.

---

## Deploying (GitHub Actions)

The workflow in `.github/workflows/deploy.yml` triggers on every push to `main` and deploys the repo root to GitHub Pages.

**One-time setup:**

1. Push this repo to GitHub.
2. Go to **Settings → Pages** in your repo.
3. Under **Source**, select **GitHub Actions**.
4. Push any commit to `main` to trigger the first deploy.

No build step needed — it's a single HTML file.
