# BPH Tracker — Setup & Use

A self-contained web app (PWA) for capturing everything your urologist needs: 72-hour voiding diary, fluid intake, medications with templates, nighttime tracking, sleep-apnea clues, leg swelling, bowel habits, daytime symptoms, IPSS, and sexual-function priorities. It computes nocturnal polyuria index, max/avg voided volume, and day/night volume splits, and produces a PDF report and CSV exports.

All data stays on your device (browser localStorage). Nothing is sent anywhere.

## Files

- `app/index.html` — the entire app
- `app/manifest.json`, `app/sw.js`, `app/icon-192.png`, `app/icon-512.png` — PWA support (home-screen icon, offline)

## Get it on your iPhone/iPad (one-time, ~10 min)

The app must be served over HTTPS for home-screen/offline support. GitHub Pages is free and simplest:

1. Create a GitHub account (or sign in) at github.com.
2. New repository → name it `bph-tracker` → set it to **Public** (GitHub Pages requires a paid plan for private repos; this is fine — the files contain no personal data, and your health data never leaves your device).
3. Upload the four files from the `app/` folder (drag and drop on the repo page → Commit).
4. Repo → Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, folder `/ (root)` → Save.
5. After a minute, your app is live at `https://<your-username>.github.io/bph-tracker/`.
6. On your iPhone/iPad, open that URL in **Safari** → tap the Share button → **Add to Home Screen**.

It now behaves like a native app: full screen, offline, icon on your home screen.

Alternative hosts if you prefer: Netlify Drop (drag the app folder onto netlify.com/drop) or Cloudflare Pages.

## Important: data lives per device

- Data entered on the iPhone stays on the iPhone; the iPad copy is separate. Pick one device for the 72-hour diary.
- Before deleting the app from your home screen or clearing Safari data, use **More → Backup (JSON)**. Restore on any device via **More → Restore**.
- Back up after completing the 72-hour diary.

## Suggested workflow for the 72-hour diary

1. **More tab**: set units (mL recommended), create your medication template(s), fill in sexual-function priorities, take the IPSS.
2. **Every void**: Log tab → Void. Use a marked collection container; enter volume. At night, the moon toggle sets automatically after 10 pm / before 7 am.
3. **Every drink**: Log tab → Fluid. Type presets caffeine/alcohol flags.
4. **Meds**: Log tab → Meds → apply your template each day; remove anything you skipped, adjust times.
5. **Each evening**: Daily tab — dinner, salt, legs, bowel, daytime symptom scores.
6. **Each morning**: Night tab — bedtime, final wake, sleep-apnea questions. Night voids you logged appear automatically with the total.
7. **Before the visit**: Report tab → set range to Last 72 hours → **Generate PDF report** → in the print preview, tap Share → Save to Files or email it. Also export CSVs if your urologist wants raw data.

## PDF on iOS

The PDF button opens the iOS print sheet. Pinch outward on the preview page to open it as a document, then use the Share icon to save or send the PDF.

## What the report includes

Summary metrics (total/night voids, max and average voided volume, nocturnal polyuria index, fluid totals, average urgency/stream), a nightly breakdown table (awakenings, nocturnal volume, 24-h volume, NPI, snoring/gasping), the full voiding, fluid, and medication logs, daily check-ins, sleep screening, IPSS score with severity, and your stated treatment priorities — organized for a HoLEP vs Aquablation discussion.

Nocturnal volume is computed the standard way: all voids during the sleep window plus the first morning void. NPI above ~33% suggests nocturnal polyuria.

## Red flags

The app lists them under More, but as a reminder: inability to urinate, fever/chills with urinary symptoms, visible blood clots, severe pain, new flank pain with fever, confusion/weakness, or new leakage with numbness — contact a doctor promptly rather than continuing routine tracking.
