# One More Can

Website for One More Can, a youth-run nonprofit can drive founded by Sierra
Kimmer. The idea: whatever cans of food you were going to donate, bring one
more. Drop them off at a meetup, hang out with friends, and the cans get
delivered to the local food bank.

**Slogan:** One more can. One more meal.

**Mascot:** Tinny, a smiling tin can with its lid tipped like a cap, always
holding up one finger for "one more."

## Files

- `index.html` – the whole site (HTML, CSS, and a little JavaScript in one file)
- `images/can.svg` – Tinny the mascot, also used as the favicon

## Running it

Open `index.html` in a browser. There is no build step.

## Putting it on onemorecan.com

The site is hosted free with GitHub Pages. The `CNAME` file in this repo
tells GitHub the site lives at `onemorecan.com`.

1. **Turn on GitHub Pages.** In this repo go to Settings → Pages. Under
   "Build and deployment," pick "Deploy from a branch," then `main` and
   `/ (root)`, and save.
2. **Add DNS records** where the domain was bought (GoDaddy, Namecheap,
   Squarespace, Cloudflare, etc.). Delete any existing A or AAAA records for
   the bare domain (`@`) first, then add:

   | Type  | Name  | Value                          |
   |-------|-------|--------------------------------|
   | A     | @     | 185.199.108.153                |
   | A     | @     | 185.199.109.153                |
   | A     | @     | 185.199.110.153                |
   | A     | @     | 185.199.111.153                |
   | AAAA  | @     | 2606:50c0:8000::153            |
   | AAAA  | @     | 2606:50c0:8001::153            |
   | AAAA  | @     | 2606:50c0:8002::153            |
   | AAAA  | @     | 2606:50c0:8003::153            |
   | CNAME | www   | stephanie-444-faith.github.io  |

3. **Check the domain in GitHub.** Back in Settings → Pages, the custom
   domain box should show `onemorecan.com`. Wait for the DNS check to pass.
   This can take anywhere from a few minutes to a day.
4. **Turn on "Enforce HTTPS"** on the same page once it becomes clickable.

`www.onemorecan.com` will redirect to `onemorecan.com` automatically.

Optional but recommended: verify the domain under your GitHub account
(Settings → Pages → "Add a domain") so nobody else can claim it for their
own Pages site.

## Connecting the Google Form

The "Start a meetup" form on the site sends each sign-up into a Google Form,
so answers land in the form's Responses tab (and a Google Sheet if you link
one). Until the link below is filled in, the form tells visitors sign-ups
aren't open yet.

1. **Make the Google Form.** Go to forms.google.com and create a blank form
   called "One More Can hosts." Add four **Short answer** or **Paragraph**
   questions, in any order:
   - Your name (required)
   - Email (required)
   - Town or school (required)
   - Your idea (optional, Paragraph)
2. **Check two settings** under the Settings tab, or submissions from the
   website will be silently dropped:
   - Responses → **Collect email addresses: Do not collect**. The Email
     question above collects it instead.
   - Responses → **Limit to 1 response: off**, and "Restrict to users in
     your organization" off if you see it.
3. **Get the pre-filled link.** Click the ⋮ menu at the top right → **Get
   pre-filled link**. Type these exact words into the matching questions:

   | Question        | Type this |
   |-----------------|-----------|
   | Your name       | NAME      |
   | Email           | EMAIL     |
   | Town or school  | TOWN      |
   | Your idea       | IDEA      |

   Click **Get link**, then **Copy link**.
4. **Paste it into the site.** In `index.html`, near the bottom, find this
   line and paste the link between the quotes:

   ```js
   var GOOGLE_FORM_PREFILLED_LINK = '';
   ```

   Commit the change. You can do this right on github.com: open
   `index.html`, click the pencil icon, edit, and commit.
5. **Test it.** Open the live site, send a test sign-up, and make sure it
   shows up in the Google Form's Responses tab. Then delete the test response.

Tip: in the Responses tab, click the green Sheets icon to send sign-ups to a
spreadsheet, and turn on email notifications from the ⋮ menu there.

## Things to fill in

- **Meetups**: the three events on the page are samples. Replace them with real
  dates, times, and places in the `#meetups` section.
- **Contact**: add an email or social handle to the footer once One More Can
  has one.
- **Repo name**: the GitHub repo is still called TwoCan. Rename it under
  Settings → General if you want it to match.
