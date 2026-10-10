# Avenue Vision template library

Templates for Avenue Vision, an AI website generator for local trade contractors. Each template is one Claude Design page (`.dc.html`): a homepage for a fictional contractor, built in one visual direction.

## What is here

- `project/canvas.json` is the index. It lists each page, the board for each template, and the order they appear in.
- `project/*.dc.html` are the templates. `T01` to `T10` are the first ten site templates. `PA`, `PB` and `PC` are three packs of four pages each. `V01` to `V20` are twenty franchise-style variations. `D01` to `D16` and `E01` to `E12` are art directions. `H01` to `H05` are five HVAC-style templates. `PalmettoSite.dc.html` is a sample pool-service template.
- `project/ds/` holds the design-system files.
- `brief/` holds the build briefs used to make the templates.

## Not included

- **Photos.** `project/img/` is not in this repo. Templates point to `img/<trade>/NN.jpg`, so those images show as empty boxes until the photos are added back.
- **Builder screens and drafts.** The Avenue Vision builder app screens, earlier drafts, render images and backup copies are left out.
- **Third-party brand names.** Names of the franchises and brands we studied have been removed from the text and footers. Some layouts and structures are modelled on those sites.

## Notes

- The templates load `./support.js`, which is not in this repo.
- No licence has been chosen yet, so default copyright applies.
