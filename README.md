# Class Jobs Maker

A free website where teachers make beautiful, printable class job cards in three steps: pick the jobs you want, choose a look, then print, save a PDF, or present as a slideshow. Works on full sheets (1 per page), half sheets (2 per page), or quarter sheets (4 per page).

No sign-in, no account, nothing to install. Everything a teacher does is saved in their own browser.

Live site: https://mrpiercey.github.io/edutopiaclassjobs/

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole site. Everything is in this one file. |
| `lucide.min.js` | The free icon library (bundled here so the site still works on school Wi-Fi that blocks outside scripts). |
| `pptxgen.bundle.js` | [PptxGenJS](https://gitbrucecampbell.github.io/PptxGenJS/), bundled locally so the PowerPoint export works without outside scripts. Loaded only when someone exports. |
| `edu_bug.png` | The Edutopia "edu" bug, used in the header and as the browser tab icon. |
| `openmoji/` | 150 color SVG pictures from [OpenMoji](https://openmoji.org), one for every job plus extras for the picker. See `openmoji/LICENSE.txt`. |
| `README.md` | This file. |

## Brand

The site follows the Edutopia brand guidelines and shares its design system with the [Authentic or AI?](https://mrpiercey.github.io/aiedutopia/) game: cream background, flat corner circles, slab headlines in Pacific Blue, pill buttons, white cards with soft shadows, and the seven-color palette ribbon under the app bar.

- **Fonts.** Poppins is the Google-safe stand-in for Gotham and is used for all interface text. Zilla Slab stands in for Museo Slab for headlines and for the titles on most card looks, and Caveat stands in for Helping Hand on the Handwritten look.
- **Colors.** Every card look is built only from the Edutopia palette (Electric Orange, Dark Orange, Tangerine, Sunshine, Midnight Blue, Space Blue, Pacific Blue, Tech Blue, Purple, Light Purple, Pink, Salmon, Teal, Light Teal, Green, Light Green, Dark Grey, Light Grey, Cream, White). The full palette is defined as CSS variables at the top of `index.html`.
- **Electric Orange (#FF4C00)** is used sparingly: the edu bug, the word "Maker" in the title, one primary action button per screen, and the Edutopia Orange card look.

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

1. **Welcome screen.** Explains the three steps. Click **Pick Your Jobs**. A returning teacher sees a **Continue** button instead, plus **Start Over**.
2. **Pick your jobs.** Tap the colorful job cards you want. Use **Pick the classics** for a quick set, search for something specific, or add a **Custom job**. Tap the pencil on any card to change its words. Click **Design My Cards** when you have at least one.
3. **Design.** Type the class name and year, click a look (14 to choose from, all built from the Edutopia palette and designed to print cleanly), and pick a size. Half sheet (2 per page) is the default.
4. The **Your jobs** list on the left shows your picks in order. Click a picture to swap it, the pencil to edit the words, the arrows to reorder, or **Add or remove** to go back to the job cards.
5. Edit right on the cards too: click any words to retype them, click the picture to swap it, and hover a card for the buttons to reorder or remove it. Changing the class name or the "Job Description" label on one card changes it on all of them.
6. Click **Print or Present** and choose:
   - **PDF.** Opens the print window. Choose **Save as PDF** as the printer (or an actual printer). Make sure "Background graphics" is turned on and margins are set to **None** or **Default** so the colors and borders print.
   - **Slideshow.** Downloads a PowerPoint file (`.pptx`) with a title slide and one job per slide, styled to match the chosen look. Open it in PowerPoint, or upload it to Google Drive and open it with Google Slides (right-click the file, **Open with**, **Google Slides**). Google Slides has Poppins, Zilla Slab and Caveat built in, so the fonts carry over.
   - **Present now.** Shows one job per slide full screen in the browser, for a projector or smartboard. Use the arrow keys or the on-screen buttons to move between jobs, **Full screen** for class, and **Esc** to exit. Opening the site with `#slideshow` on the end of the address jumps straight into it.

## Pictures

Every job comes with an [OpenMoji](https://openmoji.org) picture already. Teachers can swap in:

- **Pictures** from OpenMoji (150 are bundled in the `openmoji/` folder, so they work offline and print the same everywhere)
- **Icons** from [Lucide](https://lucide.dev) (about 230 kid-friendly ones are built into the picker, all free and open source)
- **Emoji** (about 260 of them, searchable)
- **Their own image** uploaded from their computer. The picture never leaves their browser.

Good places to find free pictures to upload: [OpenMoji](https://openmoji.org), [SVG Repo](https://www.svgrepo.com), [unDraw](https://undraw.co/illustrations), [Openclipart](https://openclipart.org), and [Flaticon](https://www.flaticon.com) (check each site's license before using).

## Changing the job list or the looks

Everything lives near the top of the `<script>` section in `index.html`:

- **Jobs** are in the `JOBS` list. Each line is `['id', 'Title', 'Description', 'openmoji-hexcode', featured]`. The hexcode is the file name in `openmoji/` (for example `1F331` is the seedling). Set the last number to `1` to put it in "The classics" group or `0` for "More ideas."
- **Looks** are in the `THEMES` list plus a matching block of CSS (search for `/* ============ THEMES`) and a matching entry in `PPT_THEMES` and `pptDecos` for the PowerPoint export. Copy an existing one, rename it, and change the colors. Stick to the `--edu-*` palette variables to stay on brand.
- **Picker pictures** are in `OPENMOJI` (hexcode plus search words). To add one, download `color/svg/<hexcode>.svg` from the [OpenMoji repository](https://github.com/hfg-gmuend/openmoji) into `openmoji/` and add a line.
- **Picker icons** are in `ICON_NAMES`. Any name from [lucide.dev/icons](https://lucide.dev/icons) works.

## Credits

PowerPoint export by [PptxGenJS](https://github.com/gitbrucecampbell/PptxGenJS) (MIT). Pictures by [OpenMoji](https://openmoji.org), the open-source emoji and icon project (CC BY-SA 4.0). Icons by [Lucide](https://lucide.dev) (ISC license). Fonts (Poppins, Zilla Slab, Caveat) from [Google Fonts](https://fonts.google.com). Brand colors and the edu bug are Edutopia's. Built for teachers by a teacher.
