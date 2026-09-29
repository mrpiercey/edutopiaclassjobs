# Class Jobs Maker

A free website where teachers make simple, printable class job cards. Pick the jobs you want, choose a look, swap in any picture, then export as a PDF or present as a slideshow. Works on full sheets (1 per page), half sheets (2 per page), or quarter sheets (4 per page).

No sign-in, no account, nothing to install. Everything a teacher does is saved in their own browser.

Live site: https://mrpiercey.github.io/edutopiaclassjobs/

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole site. Everything is in this one file. |
| `lucide.min.js` | The free icon library (bundled here so the site still works on school Wi-Fi that blocks outside scripts). |
| `edu_bug.png` | The Edutopia "edu" bug, used in the header and as the browser tab icon. |
| `README.md` | This file. |

## Brand

The site follows the Edutopia brand guidelines.

- **Fonts.** Poppins is the Google-safe stand-in for Gotham and is used for all interface text and most card looks. Zilla Slab stands in for Museo Slab on the Editorial Slab look, and Caveat stands in for Helping Hand on the Handwritten look.
- **Colors.** Every card look is built only from the Edutopia palette (Electric Orange, Dark Orange, Tangerine, Sunshine, Midnight Blue, Space Blue, Pacific Blue, Tech Blue, Purple, Light Purple, Pink, Salmon, Teal, Light Teal, Green, Light Green, Dark Grey, Light Grey, Cream, White). The full palette is defined as CSS variables at the top of `index.html`.
- **Electric Orange (#FF4C00)** is used sparingly: the edu bug, the single primary action button, and the Edutopia Orange card look.

## Publish it on GitHub (about 5 minutes)

1. Go to [github.com/new](https://github.com/new) and create a new repository. Name it something like `class-jobs-maker`. Make it **Public**. Do not add a README (you already have one).
2. On the empty repository page, click **uploading an existing file**.
3. Drag all four files from this folder onto the page, then click **Commit changes**.
4. In the repository, click **Settings** (top tab), then **Pages** in the left sidebar.
5. Under **Build and deployment**, set **Source** to **Deploy from a branch**, set **Branch** to `main` and the folder to `/ (root)`, then click **Save**.
6. Wait about a minute and refresh. GitHub will show your live link. It will look like
   `https://YOUR-USERNAME.github.io/class-jobs-maker/`

That's it. Share the link with any teacher.

To update the site later, open `index.html` in the repository, click the pencil icon, paste in the new version, and commit. GitHub Pages republishes automatically.

## How teachers use it

1. **Start screen.** Tap the jobs you want. Use **Pick the classics** for a quick set, or search for something specific. Click **Make my cards** when you have at least one.
2. Type the class name and year.
3. Click a look. There are 12 to choose from, all built from the Edutopia palette and designed to print cleanly.
4. Pick a print size.
5. Change your mind about jobs any time in the list on the left, or click **Back to the start screen**. Use **+ Custom job** for anything that isn't on the list.
6. Edit right on the cards: click any words to retype them, click the picture to swap it, and hover a card for the buttons to reorder or remove it. Changing the class name or the "Job Description" label on one card changes it on all of them.
7. Click **Export** and choose:
   - **PDF.** Opens the print window. Choose **Save as PDF** as the printer (or an actual printer). Make sure "Background graphics" is turned on and margins are set to **None** or **Default** so the colors and borders print.
   - **Slideshow.** Shows one job per slide for a projector or smartboard. Use the arrow keys or the on-screen buttons to move between jobs, **Full screen** for class, and **Esc** to exit. Opening the site with `#slideshow` on the end of the address jumps straight into the slideshow.

## Pictures

Every job comes with a picture already. Teachers can swap in:

- **Icons** from [Lucide](https://lucide.dev) (about 230 kid-friendly ones are built into the picker, all free and open source)
- **Emoji** (about 260 of them, searchable)
- **Their own image** uploaded from their computer. The picture never leaves their browser.

Good places to find free pictures to upload: [OpenMoji](https://openmoji.org), [SVG Repo](https://www.svgrepo.com), [unDraw](https://undraw.co/illustrations), [Openclipart](https://openclipart.org), and [Flaticon](https://www.flaticon.com) (check each site's license before using).

## Changing the job list or the looks

Everything lives near the top of the `<script>` section in `index.html`:

- **Jobs** are in the `JOBS` list. Each line is `['id', 'Title', 'Description', 'icon-name', featured]`. Set the last number to `1` to put it in "The classics" group or `0` for "More ideas."
- **Looks** are in the `THEMES` list plus a matching block of CSS (search for `/* ============ THEMES`). Copy an existing one, rename it, and change the colors. Stick to the `--edu-*` palette variables to stay on brand.
- **Picker icons** are in `ICON_NAMES`. Any name from [lucide.dev/icons](https://lucide.dev/icons) works.

## Credits

Icons by [Lucide](https://lucide.dev) (ISC license). Fonts (Poppins, Zilla Slab, Caveat) from [Google Fonts](https://fonts.google.com). Brand colors and the edu bug are Edutopia's. Built for teachers by a teacher.
