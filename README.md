# Muhammad Imam Hussain – job market website

Five static pages, one stylesheet, no build step. Works on GitHub Pages as is.

```
index.html      Home: bio, job market paper, other research, education
research.html   Job market paper, working paper, work in progress, presentations, publications
teaching.html   Instructor and teaching assistant record
experience.html Professional experience at the IMF and Bangladesh Bank
contact.html    Email, phone, mailing address, LinkedIn
cv.html         Forwards muhammadimamhussain.com/cv to the CV PDF (a stable address for the CV's own header line)
CV_of_Muhammad_Imam_Hussain.pdf   The CV. To update it, upload the new PDF under the same name (Add file → Upload files, then Commit)
style.css       Layout, fonts, light and dark themes
assets/         photo.jpg (your portrait, 4:5 crop)
.nojekyll       Tells GitHub Pages to serve the files exactly as they are
```

## 1. Put the site on GitHub Pages (free, about ten minutes)

1. Sign in to github.com (user name mhussai7) and open https://github.com/new.
2. Repository name: exactly `mhussai7.github.io`. Visibility: Public. Leave "Add a README file" unticked. Click Create repository.
3. On the empty repository page click **uploading an existing file**. Unzip this package and drag in everything:
   the five .html pages, cv.html, style.css, README.md, the `assets` folder (with photo.jpg), and .nojekyll if your
   computer shows it (it is a hidden file; skipping it is harmless for these files). Click **Commit changes**.
4. Open **Settings → Pages**. Under *Build and deployment* choose **Deploy from a branch**, branch `main`,
   folder `/ (root)`, and Save.
5. After one or two minutes the page shows "Your site is live at https://mhussai7.github.io". Check every page there.

To change anything later, open the file on GitHub, click the pencil icon, edit, and commit; the site updates itself
within a minute. Or connect GitHub to Claude and ask Claude to make the change.

## 2. Buy the domain and connect it (Cloudflare)

1. Create an account at https://dash.cloudflare.com and verify the email address.
2. In the dashboard open **Domain Registration → Register Domains**, search `muhammadimamhussain.com`, and buy it
   (Cloudflare sells at cost, about US$10 to 11 a year for a .com; contact details are required, and WHOIS privacy is
   included). Leave auto-renew on.
3. Open the domain, then **DNS → Records**. Delete any placeholder records and add these five, each with
   Proxy status set to **DNS only** (grey cloud, not orange):

   | Type  | Name | Content              | Proxy    |
   |-------|------|----------------------|----------|
   | A     | @    | 185.199.108.153      | DNS only |
   | A     | @    | 185.199.109.153      | DNS only |
   | A     | @    | 185.199.110.153      | DNS only |
   | A     | @    | 185.199.111.153      | DNS only |
   | CNAME | www  | mhussai7.github.io   | DNS only |

4. Back on GitHub, in the repository: **Settings → Pages → Custom domain**, type `muhammadimamhussain.com`, Save.
   GitHub adds a file named CNAME to the repository and runs a DNS check. When the check passes (minutes to an hour),
   tick **Enforce HTTPS**. If that box is greyed out, the certificate is still being issued; try again later, up to a day.
5. Test https://muhammadimamhussain.com and https://www.muhammadimamhussain.com (www forwards to the main address).

## 3. After the site is live

- CV header: "Website: https://muhammadimamhussain.com" and "Most recent version of this CV: https://muhammadimamhussain.com/cv".
- Resume: the research-item hyperlinks that point to sites.google.com/view/mdihussain/research become
  https://muhammadimamhussain.com/research.
- LinkedIn (Contact info → Website), JOE and EconJobMarket profiles, Handshake, email signature.
- Old Google Site: add one line to its home page, "This site has moved to muhammadimamhussain.com", and leave it up,
  since PDFs already in circulation link to it.

## 4. Keeping the content current

- The CV is the file CV_of_Muhammad_Imam_Hussain.pdf in the repository; upload a new PDF with the same name to update it.
- The job market paper link points to your Google Drive file. Replacing it on Drive
  (right-click → Manage versions → Upload new version) keeps the link unchanged, so the site needs no edit.
- The job-market label on the home page and the year in the footer are the only dated items.
