# The True Balance Method Companion

An interactive companion to *The True Balance Method: Why the Body Compensates, and How to Restore Balance* by Anthony Anderson (True Balance Therapy).

It follows Part IV of the book, step by step:

1. **Start**: the safety checks and stop rules from Chapter 17. You can't go on until you've read the stop rules, and urgent warning signs stop the process.
2. **Posture**: the photo checks and wall test from Chapter 18.
3. **Movement**: the ten tests from Chapter 19, with sign checkboxes, left/right sides, and automatic flags for balance time (under 30 sec) and knee-to-wall distance (under 4 in).
4. **Results**: the Chapter 20 region tally and priority rules, giving a primary driver, breathing inclusion and an optional second region. The reader can override the result.
5. **My plan**: a 15-minute session built from Chapter 22 and the Appendix D exercise library. It builds up week by week, following Chapter 24: one activation exercise and no integration in week 1, the second activation and integration from week 2, and the second region from week 3. Each exercise can be swapped, comes with instructions, an image and an optional video demo, and shows its doses. The plan can be printed.
6. **30 days**: the Chapter 24 tracker with full, short and easy days, each week's plan, and weekly check-ins.
7. **Re-test**: compares Day 1 with the re-test (flags, knee-to-wall, balance, region counts, symptoms and a real-life activity), using the Chapter 25 reading guide.
8. **Exercises**: all 58 exercises in the library, searchable and filterable.

## Privacy

There is no server, no account, no analytics and no tracking. Answers are stored only in the reader's browser (`localStorage`). Exercise videos use YouTube's privacy-enhanced player (`youtube-nocookie.com`) and load only when the reader taps play. The **Save a backup** and **Load a backup** buttons move data between devices as a JSON file.

## Files

```
index.html     the whole app (HTML, CSS and JS, with the book data built in)
images/        exercise illustrations (JPEG, web-sized)
README.md
```

## Publish on GitHub Pages

1. Create a new public repository, for example `true-balance-companion`.
2. Upload `index.html`, the `images/` folder and this README to the root of the repository.
3. Go to **Settings → Pages → Build and deployment**, set **Source** to *Deploy from a branch*, choose `main` and `/ (root)`, and click **Save**.
4. After a minute or two the site is live at `https://<your-username>.github.io/true-balance-companion/`.
5. Optional: to use your own domain (such as `companion.truebalancetherapy.com`), add it under **Settings → Pages → Custom domain** and create a CNAME DNS record that points to `<your-username>.github.io`.

The same folder also deploys on Vercel or Netlify as a static site, with no build step.

## Updating

The app is generated from the manuscript, so the book and the app don't drift apart. After changing the manuscript, adding exercise images (`assets/exercises/CODE.png`) or adding videos (`content/videos.json`), run:

```
python3 build_supplement.py
```

Then commit the new `index.html` and `images/`.

## Adding exercise videos

1. Upload each demo to YouTube. Public or **Unlisted** both work; Unlisted keeps them off search and off your channel page.
2. Paste the link next to the exercise code in `content/videos.json` (in the book build folder, not in this repo):

   ```json
   "C7": "https://youtu.be/XXXXXXXXXXX",
   "D1": "https://www.youtube.com/watch?v=XXXXXXXXXXX&t=45s",
   ```

   Any normal YouTube link works (watch, youtu.be, Shorts, with or without a start time). Leave the value as `""` for exercises that have no video yet.
3. Run `python3 build_supplement.py` and commit the new `index.html`.

A "▶ Watch the demo" button then appears on that exercise in the plan and the library, and a **Video** tag shows in the library list. A2 shares D1's video automatically.

## Disclaimer

This companion is education, not medical care. It cannot diagnose and does not replace a licensed healthcare provider.

© True Balance Therapy. All rights reserved.
