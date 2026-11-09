# Updating your website

Every change you push to the `main` branch rebuilds and publishes the site in about two minutes. You can make all of these edits directly on GitHub in the browser: open the file, click the pencil icon, edit, and click **Commit changes**.

## Update your bio
Edit `content/_index.md`. Text wrapped in `**double asterisks**` shows in bold.
Your tagline, title, email, and LinkedIn link live in `hugo.yaml` under `params`.

## Add a paper
1. (Optional) Upload the PDF to `static/files/` (GitHub: **Add file → Upload files**), e.g. `static/files/my-paper.pdf`.
2. Add an entry to `data/papers.yaml`:
   ```yaml
   - title: "My New Paper"
     authors: ["Yifan (Linda) Wang", "Coauthor Name"]
     year: 2027
     status: "working paper"     # published, accepted, revise and resubmit, under review, working paper, work in progress, thesis
     badge: "Working paper"      # small label shown next to the title (optional)
     venue: ""                   # journal or conference, if any
     pdf: "files/my-paper.pdf"   # or leave empty
     link: ""                    # DOI/SSRN link, if no PDF
     description: "One sentence about the paper."
     job_market_paper: false
   ```
   Current work appears under **Current research**; `published`/`accepted` items appear under **Publications**.

## Mark a paper as published
Change its `status` to `"published"`, fill in `venue`, and update `badge`.

## Add your job market paper
Set `job_market_paper: true` on that entry and add an `abstract:` line. It will appear as a highlighted card at the top of the Research page.

## Add a presentation
Add an entry to `data/presentations.yaml` (title, venue, year).

## Add research experience or teaching
Research positions are in `data/experience.yaml`. To add teaching, ask your assistant to add a Teaching section backed by `data/teaching.yaml`.

## Update your CV
Replace `static/files/cv.pdf` with the new version, keeping the same filename.

## Change your photo
Replace `static/images/photo.jpg`, keeping the same filename. It is shown uncropped, so any shape works. If the new photo has different proportions, update the `width`/`height` numbers on the `<img>` tag in `layouts/partials/profile.html` to match its pixel size.

## Change the look of the site
Colors are the `--color-*` values at the top of `assets/css/style.css`. To redesign more broadly, ask your assistant to run the design quest at https://gking.harvard.edu/mysite/files/QUEST_DESIGN.md; the current design is recorded in `hugo.yaml` under `params.mysite.design`.

## Preview locally (optional)
Install Hugo (extended), then run `hugo server` in this folder and open http://localhost:1313.
