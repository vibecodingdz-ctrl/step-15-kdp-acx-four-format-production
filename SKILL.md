---
name: step-15-kdp-acx-four-format-production
description: Convert an approved manuscript into a controlled four-format production package for Kindle EPUB, paperback PDF, hardcover PDF, and ACX narration-ready files/scripts. Use after manuscript quality approval and before publishing-package assembly; verify current KDP and ACX requirements and never submit files.
---

# KDP and ACX four-format production

Use an approved manuscript only. Create local production files and QA reports; never log in, upload, publish, submit to KDP/ACX, order proofs, or claim platform acceptance. The human author performs all final uploads and account actions.

## Current policy safeguards

Recheck official KDP and ACX sources before each production run because technical rules can change. The current official KDP pages state that paperback interiors with bleed must be PDF, fonts/images should be embedded, images should be at least 300 DPI, paperback page count is calculated from the manuscript and rounded up to an even number, and paperback minimum page count is 24 [VERIFIED: https://kdp.amazon.com/help/topic/G201857950, 2026-11-21]. KDP states that case-laminate hardcover page count is 75–550 pages [VERIFIED: https://kdp.amazon.com/help/topic/GAVW3FZZAKA2KY3B, 2026-11-21].

ACX currently requires one chapter/section per file, separate opening and closing credits, human narration unless specifically authorized, 192 kbps or higher CBR 44.1 kHz MP3, RMS between -23 dB and -18 dB, peaks no higher than -3 dB, noise floor below -60 dB RMS, and room tone no longer than 5 seconds [VERIFIED: https://help.acx.com/s/article/what-are-the-acx-audio-submission-requirements, 2026-11-21].

Do not label AI-generated speech as ACX-ready. If TTS is used for internal proofreading or a demo, label every file `NOT FOR ACX SUBMISSION — AI/TTS DEMO` unless current written authorization is documented. Human narration or documented authorization remains a hard gate.

## Required inputs

Require the final manuscript file, title/author/narrator metadata, language, chosen trim size, paperback/hardcover formats, bleed decision, ISBN/edition data, image/font rights, and human approval for production. If the manuscript is missing or not quality-approved, return `BLOCKED — Error / Tried / Next`.

Default print trim may be 6 x 9 inches, but do not assume it is correct. Confirm trim, paper/ink, bleed, and format from the project brief and current KDP rules. Hardcover must pass the current 75–550 page range; do not force a 75-page minimum with empty pages.

## Required output folders

Create exactly:

- `1_Kindle_eBook/`
- `2_Paperback/`
- `3_Hardcover/`
- `4_Audiobook/`

Keep source manuscript and rejected/superseded files outside the submission-ready folders.

## Production procedure

### 1. Freeze identity and source

Create a manifest with project ID, title, subtitle, author, edition, language, source filename/hash, date, trim size, formats, and approval status. Preserve the original manuscript. Record all transformations.

### 2. Kindle EPUB

Create a clean, reflowable EPUB with semantic headings, chapter breaks, a clickable table of contents, valid navigation, accessible reading order, and no print-only running headers, footers, or page numbers. Embed fonts only when legally licensed and technically appropriate; do not promise that custom fonts will render identically across Kindle devices. Validate EPUB structure with an EPUB checker and inspect in a Kindle-compatible previewer. Output the EPUB, validation report, metadata, and known limitations in `1_Kindle_eBook/`.

### 3. Paperback PDF

Create a single-page print interior at the approved trim size, with mirrored margins/gutter, safe text placement, running headers and bottom page numbers only when appropriate, embedded fonts, and no crop marks, comments, annotations, placeholder text, or unsupported metadata. Add bleed only when the design requires it and follow current KDP dimensions. Render and inspect every page or a complete contact sheet, then run a PDF preflight.

Record the exact final PDF page count from the generated file. Do not estimate it from word count. Note that KDP may round to an even count. Output the PDF, page-count record, preflight report, and cover-calculation input record in `2_Paperback/`.

### 4. Hardcover PDF

Create a separate hardcover interior unless the approved specifications prove the paperback interior is compatible. Use the approved trim, mirrored margins, gutter, embedded fonts, and correct front/body/back matter. Confirm the final generated PDF page count is between 75 and 550 pages under current KDP rules. Never add empty padding solely to reach 75 pages; return a human blocker if the manuscript is too short. Output the PDF, exact page-count record, preflight report, and cover-calculation input record in `3_Hardcover/`.

### 5. Audiobook script and audio preparation

Create a narration-ready TXT/script per chapter. Remove page numbers, headers/footers, image-only captions, layout artifacts, tables that do not make sense aloud, and visual instructions. Preserve meaning, chapter titles, pronunciation notes, and rights-sensitive text. Create separate Opening Credits and Closing Credits scripts. The opening must identify title, author(s), and narrator(s); the closing must clearly signal finality and include title, author(s), and narrator(s) as required by current ACX guidance.

Prepare one audio file per chapter/section plus separate credits files. Each file must be one section and no longer than 120 minutes. If no authorized human narration is supplied, produce scripts and an audio-production specification only. Do not produce an ACX-submission-ready TTS audiobook. If authorized human narration files are supplied, inspect them for format, CBR, 44.1 kHz, RMS, peak, noise, room tone, channel consistency, file naming, and chapter length. Output TXT/scripts, audio QA reports, and authorized MP3 files in `4_Audiobook/`.

## Final QA and handoff

Create a manifest and QA report listing every output, exact page count for both PDFs, EPUB validation result, font/image checks, audio metrics, missing items, and status `PASS`, `CONDITIONAL`, or `BLOCKED`. State clearly that local preflight is not proof of KDP or ACX acceptance. Stop before any upload or submission control.

## Official references

- KDP paperback submission guidelines: https://kdp.amazon.com/help/topic/G201857950
- KDP hardcover requirements: https://kdp.amazon.com/help/topic/GAVW3FZZAKA2KY3B
- KDP hardcover formatting: https://kdp.amazon.com/help/topic/GKYZRXFBZH2LDXAK
- ACX audio submission requirements: https://help.acx.com/s/article/what-are-the-acx-audio-submission-requirements
## Workflow position

**Step 15** — this card is part of the numbered KDP workflow. Use the previous step outputs before starting it and pass its required outputs to the next step.

