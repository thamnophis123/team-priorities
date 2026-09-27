# TEAM 2027 Iowa education priorities

Static site for Iowa legislators and legislative staff. It maps [TEAM](index.html)’s eight education priorities for the 2027 Iowa legislative session onto existing Iowa Code and Iowa Administrative Code sections, so a change can be drafted as an amendment rather than a new chapter.

The organization’s name is **TEAM**.

There is no build step and no `package.json`. The site is HTML and one shared stylesheet. It works when the files are served as-is, including by opening `index.html` in a browser. [Vercel](https://vercel.com/) can host this repository from `main` with the framework preset set to “Other” and no install or build command. `vercel.json` turns on `cleanUrls`, so a deployed page is also available without the `.html` suffix. In-page links still use `.html` so the same files work locally.

## Files

| Path | Purpose |
| --- | --- |
| `index.html` | Short introduction, links to all eight priorities, and a summary table |
| `css/styles.css` | Shared layout, including a print stylesheet for letter paper |
| `priorities/required-training.html` | Priority 1. Required training and age-appropriate elementary instruction |
| `priorities/political-messaging.html` | Priority 2. Political and ideological symbols |
| `priorities/school-discipline.html` | Priority 3. Reporting potential crimes and school discipline |
| `priorities/transparency.html` | Priority 4. Open records, open meetings, and posted curriculum |
| `priorities/boee-reform.html` | Priority 5. Board of Educational Examiners |
| `priorities/public-funds.html` | Priority 6. Public funds for political or ideological uses |
| `priorities/screen-time.html` | Priority 7. Screen time and personal devices |
| `priorities/obscenity-exemption.html` | Priority 8. Obscenity-law exemptions for schools and libraries |
| `vercel.json` | `cleanUrls` only |

The header, navigation, and footer are repeated in each HTML file. There is no template engine. If you change a nav label, change it in every file.

## Update a page

1. Edit the HTML file for that priority, or `index.html` if the summary table also changes.
2. Change the visible date on each page you edited. It is the line that reads:

   ```html
   <p class="updated">Last updated: <time datetime="2026-09-27">September 27, 2026</time></p>
   ```

   Update both the `datetime` value (`YYYY-MM-DD`) and the visible text. If the update applies to the whole site, change that line on every page.
3. Keep the page to sourced public law, bills, and documents. Do not add TEAM member names, or the names of legislators TEAM plans to contact.
4. When draft amendment text is ready, replace the paragraph in the section headed **Model legislation**. Leave the heading, and keep the words “Model legislation” easy to find. The placeholder now says “Model legislation: coming soon.”

Print each page from the browser to check letter-paper layout. Navigation is hidden in print. Web addresses are printed after external links.

## Check links locally

From the repository root:

```bash
python3 -m http.server 8080
```

Open `http://localhost:8080/`. Relative links also work if you open `index.html` directly as a file.
