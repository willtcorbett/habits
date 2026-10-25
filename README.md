# Notepad Habits

A habit tracker that looks like a page in a notepad. Each day is a fresh page with your habits written down it as bullet points, and you tick them off as you go. It runs in Safari on iPhone and can sit on your Home Screen like a normal app.

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole app |
| `manifest.webmanifest` | Tells the phone the app's name, icon and that it should open full-screen |
| `sw.js` | Lets the app open without an internet connection |
| `icon-180.png`, `icon-512.png` | The Home Screen icon |
| `README.md` | This guide |

Keep all of these together in the same folder.

---

## Getting it on your iPhone

There are two ways. The quick one is good for trying it out. The proper one gives you a real full-screen app that works offline.

### Option A: quick try (no setup)

1. Open the artifact link Claude gave you in **Safari** on your iPhone.
2. Use it straight away, or add it to your Home Screen with the steps in "Adding to your Home Screen" below.

Things to know about this route: it opens inside the Claude page rather than as its own full-screen app, you need to be signed in to Claude, and it needs an internet connection.

### Option B: your own copy (recommended)

The app needs to be hosted at a web address so Safari can load it. GitHub Pages does this for free, and you only need to set it up once.

**1. Put the files online**

1. Create a free account at [github.com](https://github.com) (you can do this on your phone, but a computer is easier).
2. Tap **New repository**. Name it something like `habits`, set it to **Public**, and tap **Create repository**.
3. On the new repository's page, choose **uploading an existing file**.
4. Drag in **the files inside this folder** (not the folder itself), then tap **Commit changes**.
5. Go to **Settings → Pages**. Under "Build and deployment", set **Source** to *Deploy from a branch*, choose the **main** branch and the **/ (root)** folder, and tap **Save**.
6. Wait a minute or two, then refresh the page. It will show your app's address, which looks like:
   `https://YOUR-USERNAME.github.io/habits/`

The repository being public only means the app's code is visible. Your habits and ticks are never uploaded anywhere; they stay on your phone.

**Alternatives:** Netlify and Cloudflare Pages also host simple sites for free. With Netlify you can drag this folder onto its "Deploy manually" page; sign up for a free account so the site doesn't expire.

**2. Open it in Safari**

Open your app's address in **Safari** on your iPhone. It needs to be Safari: other browsers on iPhone can't always add proper Home Screen apps.

Then follow the steps below.

---

## Adding to your Home Screen

1. With the app open in Safari, tap the **Share** button (the square with an arrow pointing up). On newer versions of iOS this may be inside the **⋯** menu at the bottom of the screen.
2. Scroll down and tap **Add to Home Screen**.
3. If you see an **Open as Web App** switch, make sure it's turned on.
4. Check the name (it defaults to "Habits") and tap **Add**.

The notepad icon now appears on your Home Screen. Open it from there from now on, not from Safari. It opens full-screen like any other app, and with Option B it keeps working with no internet connection.

If it opens in a normal Safari window instead of full-screen, delete the icon, then repeat the steps and make sure **Open as Web App** is on.

---

## Using the app

**Ticking things off.** Tap a habit to tick it. The bullet turns into a tick and the line gets crossed out. Tap again to undo. When everything on the page is done, you get a stamp in the corner.

**Moving between days.** Swipe left or right on the page, or use the arrows at the bottom. **Today** brings you back to the current day. You can tick off past days if you forgot, but not future ones.

**Adding a habit.** Tap the blue **+** button. Give it a name and choose when it goes on the page:

- **Every day**: on every page.
- **Some days**: only on the days you pick (for example Mon, Wed, Fri).
- **Weekly**: set how many times a week (1 to 7). It shows up every day until you've done it that many times, then disappears until the following Monday. The small note on the right shows how you're getting on, for example "1 of 3 this week".

**Counting habits (sliders).** Some habits are about doing something several times, like 8 glasses of water or 10 sets of push-ups. When adding or editing a habit, set **How many to tick off each day?** to more than 1. That habit then gets a slider on the line below it:

- Drag the slider to set how many you've done, or use **−** and **+** to change it one at a time.
- Tapping the habit's name also adds one, which is handy for quick "had another glass" moments.
- The small ring around the bullet fills up as you go, and the note on the right shows your count (for example "3/8").
- It's only ticked off and crossed out when it reaches the target. Partly done days show as circled in the habit's calendar.

Leave it at 1 for a normal single tick. Counting works with any schedule: for a weekly habit, the number is how many you need each time you do it.

If you add a habit while looking at a past day, it starts from that day, so you can fill in ticks you've already earned.

**Details and history.** Press and hold a habit (or open **Habits** and tap its name) to see your current streak, your best run, how often you've hit it recently, and a calendar of ticked days. Tap any date in the calendar to jump to that page. From here you can **Edit** or **Pause** a habit. Paused habits stay saved but stop appearing on your pages.

Streaks are fair to each schedule: a "Mon, Wed, Fri" habit isn't broken by skipping Tuesday, and weekly habits count weeks in a row where you hit your target. Today never breaks a streak while it's still in progress.

**Habits page.** Tap **Habits** at the bottom to see every habit, reorder them with the arrows, switch between paper and night appearance, and back up your data.

---

## Your data and backups

Everything is saved on your phone only. There's no account and nothing is sent anywhere. That also means:

- **Safari and the Home Screen app keep separate data.** Ticks made in a Safari tab won't show up in the Home Screen app, and the other way round. Pick the Home Screen app and stick with it.
- **Deleting the Home Screen icon deletes its data** too.
- **Clearing Safari's history and website data** can also erase it.

So back up now and then:

1. Tap **Habits → Back up or restore**.
2. Tap **Copy backup**, then paste it into a note or email it to yourself.

To restore (for example on a new phone, or moving from Option A to Option B), open the same screen, paste the backup into the **Restore** box, and tap **Restore backup**. This replaces everything currently in the app.

---

## Updating the app

If you get a new version of `index.html`, upload it to your GitHub repository the same way (it replaces the old file). Next time you open the app with an internet connection, it picks up the new version, and your habits are kept. If it still looks old, close the app fully and open it again.

If you change the icons or `manifest.webmanifest`, also increase the version number in `notepad-habits-v2` near the top of `sw.js` (to `v3`, and so on) so phones fetch the new files. Icon changes usually need you to remove and re-add the app to your Home Screen.

## Troubleshooting

- **The handwriting fonts don't show.** They download the first time you open the app online. Open it once with a connection and they'll be saved for offline use.
- **My habits have disappeared.** Check you're opening the Home Screen icon, not a Safari tab (they have separate data). If they're really gone, restore from your latest backup.
- **The page shows yesterday.** Swipe or tap **Today**. The app also jumps to the new day when you reopen it after midnight.
