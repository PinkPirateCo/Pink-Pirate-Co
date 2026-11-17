# Pink Pirate Co. website

This is the full pinkpirateco.com site as plain HTML, so GitHub Pages can host it for free.
Every page from the Squarespace site is here, at the same web address as before. All images
are copied into `images/`, so nothing depends on Squarespace any more.

```
index.html               Home
about/                   About
portfolio/               Portfolio grid
home/<project>/          The 7 case studies (same URLs as before)
shop/                    Shop + shop/p/thick-pickle-font, shop/p/sandwiches
blog/                    Blog + the "Why your Brand Identity matters" post
contact/                 Contact form
ppq/                     Design request form
404.html                 "Page not found" page
css/style.css            All styling (brand colours are at the top)
```

---

## Before going live: 3 things to fill in

### 1. Forms (Contact + Design Request) with Formspree (free)
1. Sign up at formspree.io and create **two** forms: "Contact" and "Design request".
2. Each form gets an ID that looks like `xpzvqkab`.
3. In `contact/index.html`, replace `YOUR_CONTACT_FORM_ID` with the first ID.
4. In `ppq/index.html`, replace `YOUR_REQUEST_FORM_ID` with the second ID.

Submissions arrive in your email inbox. The free plan covers 50 submissions a month.

### 2. Font sales with Gumroad, Lemon Squeezy or Stripe
GitHub can't take payments, so each "Buy now" button links to a checkout page somewhere else.
**Gumroad** or **Lemon Squeezy** are the easiest choices. You upload the font file, they handle
payment, and the buyer gets the download automatically. There's no monthly fee, just a cut
of each sale.

1. Create a product for each font ($13) and upload the font files.
2. Copy each product's link.
3. In `shop/p/thick-pickle-font/index.html`, replace `#buy-link-thick-pickle` with the Thick Pickle link.
4. In `shop/p/sandwiches/index.html`, replace `#buy-link-sandwiches` with the Sandwiches link.

### 3. (Optional) Newsletter
The old blog's newsletter form was never connected ("needs a storage option"), so it never
collected emails. That spot now links to your Instagram instead. If you want a real
newsletter later, a free Mailchimp or Kit form can go there.

---

## Putting it online

**Use GitHub Desktop, not the website uploader.** The site has about 180 files, and GitHub's
browser upload only takes 100 at a time.

1. Create a free account at github.com.
2. Install **GitHub Desktop** (desktop.github.com) and sign in.
3. In GitHub Desktop: **File → Add local repository** → choose this folder.
   When it says it isn't a repository yet, click **create a repository**.
4. Click **Publish repository**. Untick "Keep this code private" (free GitHub Pages needs a
   public repo).
5. On github.com, open the repo → **Settings → Pages**.
   Under "Build and deployment", pick **Deploy from a branch**, branch **main**, folder **/ (root)**, then **Save**.
6. A minute later the site is live at `https://pinkpirateco.github.io/Pink-Pirate-Co/`.
   Check it there first.

## Pointing pinkpirateco.com at GitHub

Do this in the place that manages your domain (probably **Squarespace → Domains → DNS settings**).

| Type  | Host / Name | Value                       |
|-------|-------------|-----------------------------|
| A     | @           | 185.199.108.153             |
| A     | @           | 185.199.109.153             |
| A     | @           | 185.199.110.153             |
| A     | @           | 185.199.111.153             |
| CNAME | www         | `pinkpirateco.github.io` |

- Remove the old Squarespace A/CNAME records for `@` and `www` (the "Squarespace Defaults").
- **Leave any MX or TXT records alone.** Those keep your email working.
- Back in GitHub → Settings → Pages, type `www.pinkpirateco.com` under "Custom domain".
  After the check passes (anywhere from a few minutes to 24 hours), tick **Enforce HTTPS**.

## Cancelling Squarespace (last step)

Only cancel the **website plan** after the new site loads at www.pinkpirateco.com.
If your domain is registered through Squarespace, cancelling the website does **not** cancel
the domain. You can keep it there (about $20–30/yr) or move it to a cheaper registrar such
as Cloudflare (about $10/yr). Download any orders, customer emails or form submissions you want
to keep before you cancel.

## Editing later

Every page is a plain HTML file. Open one in any text editor, change the words, and save.
In GitHub Desktop, click **Commit**, then **Push**. The live site updates within about a minute.
To add a new portfolio project, copy one of the `home/<project>/` folders and edit it.
