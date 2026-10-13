# Cadence — personal learning tracker

A static, dependency-free tracker for Srikanth's DSA, system design, web development, E-commerce build, and daily Tamil learning. No installation or build step is needed for GitHub Pages.

## Use it

Open the website through GitHub Pages or a local HTTP server. Directly opening index.html works in many browsers, but browser storage on file URLs is not consistently specified. Use an HTTP server for dependable local use.

If Python is installed, open a terminal in this directory and run:

```powershell
python -m http.server 8000 --bind 127.0.0.1
```

Then visit http://127.0.0.1:8000. Keep the terminal open while using the local website. Stop with Ctrl+C. Keep the same port on later visits to use the same storage origin.

## Publish on GitHub Pages

1. Create a repository in your GitHub account, or use a suitable existing repository.
2. Upload `index.html`, `style.css`, `app.js`, `seed.js`, and `.nojekyll` to its root. This README is optional. Upload these files themselves, rather than placing them inside another directory.
3. Open repository **Settings → Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Choose the branch containing your files (usually `main`) and **/(root)**, then Save.
6. Wait for the Pages deployment and open the URL GitHub displays.

The relative asset paths work on repository Pages URLs. No API keys, cloud database, CDN scripts, fonts, or runtime packages are used.

Source and the supplied plan in `seed.js` are visible to visitors if you publish the site publicly. Your later notes and logs are not in those files. Never commit exported backups to the site repository. Hosting is not configured by this package; publishing requires your GitHub account/repository.

## A useful daily workflow

- Select today's date. Default sessions are suggestions, and source learning topics are aligned to their original dates, 23 September–21 November 2026.
- Use **Notes & log** to change a goal, start time, duration, actual minutes, status, or notes. All sessions accept notes and links as text.
- Use **▶** for a count-up focus timer. Pause for breaks; **Finish & log** adds rounded minutes and opens the session so you can choose its final status. An active timer runs only in the open page and is not restored after closing/reloading. Unsaved timer time triggers a leave-page warning.
- A completion tick does not invent actual time. Record minutes separately. Partial or skipped sessions remain visible.
- Add extra sessions for revision, exercise, chores, or any other activity. You can add multiple tasks per area per day.
- Write a daily reflection. Review the week and leave one practical adjustment.
- Export a JSON backup weekly and before changing browser, device, hostname, or port.

## Schedule and source interpretation

Weekdays start with 90 min DSA at 20:00, 90 min build at 21:40, and 45 min system design at 23:20, using the supplied templates. Web development is a suggested 30 min slot at 19:00. Tamil is 30 min daily at 12:30. Adjust these to your availability; the default weekday total is 4h 45m.

Saturday uses a 180 min DSA block starting 09:30 (the workbook's two sessions are combined in one task), a 90 min system design block at 13:45, web at 16:00, build at 19:30, and Tamil at 12:30. Technical sessions rest on Sundays by default. You can disable Sunday rest, change individual days, and disable an area from defaults. Schedule settings apply only to days without saved entries. Existing days retain their original tasks.

Times after midnight belong to the chosen study day: a 00:05 task means the next calendar morning. The date selection and display use the browser's local calendar/timezone. Set your computer to Asia/Kolkata for India-local tracking.

Imported source content:

- `Ecom_Build_Plan_Shared.xlsx`: 52 project sessions with Srikanth's role/task, Saroj's role/task (originally labelled Partner), together work, completion criteria, and workbook AI policy.
- `60-Day-Prep-Planner.xlsx`: 60 dated days of DSA/system design, 60 DSA library topics, and 51 system design library sessions.
- The provided YouTube link is available on Tamil tasks and in the learning library. Playlist lesson titles were not retrieved. Store lesson numbers, vocabulary and pronunciation doubts in task notes.

The originals remain unchanged. Workbook instructions are displayed as reference content, not commands to this app. CAT is not included because it was outside the requested tracking areas. Web development has no supplied standalone syllabus, so its tasks are editable placeholders.

The tracker does not re-read Excel after publication, update Excel, or synchronize with Saroj. Saroj completion is only a personal local record. Keep the shared workbook as your project's shared source of truth.

## Data storage and recovery

Data is saved under `cadence-personal-v1` in browser localStorage. It persists across normal reloads and browser restarts, but can be lost when site data is cleared, storage is blocked, or private browsing ends. It does not automatically sync between devices or browser profiles. It is browser-managed storage on your machine, rather than an ordinary editable file on disk.

GitHub Pages serves static files. Browser logs/notes are not uploaded to GitHub. Local preview, GitHub Pages and a custom domain have different origins and therefore separate storage. Export a JSON backup from the old location, open the new location, and restore it under Schedule & backup. Paths on the same origin share storage, so use one Cadence installation per origin. Use only one editing tab at a time to avoid conflicting edits.

**JSON export** includes all saved daily sessions, notes, settings, reflections and project notes. **Restore** validates the backup and asks before replacing current data. Export current data first to keep both versions. **CSV export** includes saved session rows for analysis; it cannot fully restore the tracker. Downloaded backups must be kept outside the public website repository.

Completion percentage is completed sessions divided by all planned sessions, including skipped ones. The 60-day heatmap shows saved activity only. Complete-day streak requires every planned task completed, looking backward from the selected date; days with no tasks are ignored. Actual time can be logged without a completion tick.

No automatic file access, Excel upload, user accounts, cloud syncing, analytics or service worker is included. Internet is needed to load the hosted site and open YouTube. Once loaded, logging does not require any network requests.

## Verification

JavaScript syntax was checked with Node. Browser checks covered daily rendering, logging and persistence after reload, weekly totals, consistency, project and library views, and settings. Test minutes/notes were reverted after verification. The source package is ready for GitHub Pages; deployment needs a selected repository.

References: [MDN localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) · [GitHub Pages documentation](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages).
