# Semester Timetable

A timetable app that runs in your browser and installs on your phone or laptop like a normal app. It sends a notification before each class. Your classes are stored on your own device, not on a server.

**Files in this folder**

- `index.html`: the whole app
- `sw.js`: lets the app work offline and show notifications
- `manifest.webmanifest`: the app's name and icon, used when you install it
- `icon-*.png`, `apple-touch-icon.png`: app icons

---

## 1. Put it online (free, about 5 minutes)

Your phone needs the app at an `https://` address before it can install it or send notifications. GitHub Pages hosts it for free.

1. Sign in at [github.com](https://github.com). Create a free account if you don't have one.
2. Click **+** (top right), then **New repository**. Name it `timetable`, choose **Public**, and click **Create repository**.
3. On the new repository page, click **uploading an existing file**. Drag in **all the files inside this folder** (the files, not the folder itself), then click **Commit changes**.
4. Open the repository's **Settings**, then **Pages**. Under *Build and deployment*, set **Source** to *Deploy from a branch* and **Branch** to `main` with `/ (root)`. Click **Save**.
5. Wait a minute and refresh the page. Your app's address appears at the top, like `https://your-username.github.io/timetable/`.

The repository is public, so anyone can see the app's code. Your timetable is **not** uploaded; it stays on your devices.

## 2. Install it

| Device | How |
|---|---|
| Laptop (Chrome or Edge) | Open your address and click **Install app** in the app's top bar, or the install icon at the right of the address bar. |
| Android (Chrome) | Open your address, tap **⋮**, then **Add to Home screen** and **Install**. |
| iPhone (Safari, iOS 16.4 or later) | Open your address, tap **Share**, then **Add to Home Screen**. Always open the app from the Home Screen icon; iPhone only allows notifications there. |

## 3. Turn on reminders

1. Open the app and tap the **bell** at the top.
2. Tap **Turn on reminders**, then **Allow** when the browser asks.
3. Choose how early you want the notice (5 minutes to 1 hour). **Send a test** shows you what it looks like.

**When the notifications arrive**

- **Laptop:** whenever the app is open. It can be minimized or behind other windows. On Windows, check that notifications for Chrome or Edge are on in *Settings, System, Notifications*, and that Do not disturb is off.
- **Phone:** Android and iPhone pause web apps soon after you leave them. For alerts that arrive while the app is closed, add your timetable to your phone's calendar as well: open **Settings**, then **Add to your calendar**.
  - **Calendar file (.ics):** every class in every teaching week, each with a reminder set to your chosen time. On iPhone, open the file and tap **Add All**. On Android, import it at [calendar.google.com](https://calendar.google.com) under *Settings, Import & export*.
  - **Google Calendar (.csv):** the same events in Google's own import format.
  - If imported events arrive without reminders, turn on notifications for the calendar you imported them into.

## 4. Use it on your laptop and your phone

Each device keeps its own copy of your classes.

- **Copy link with my timetable** (in Settings) makes a link that carries all your classes. Open it on the other device and tap **Use this timetable**.
- **Download backup** saves a `.json` file. **Restore backup** loads it on any device.

## Using it

- **Add a class:** click an empty slot on the week grid, or use **Add class**. If you type a course name you already have (the BT session of a lecture, say), the app reuses its color, code and lecturer.
- **Teaching weeks:** put ranges like `2-9, 11-18` on a class. In **Settings, Semester**, set the Monday of week 1. The header then shows the current week, and each week only shows the classes taught in it.
- **Week and Day views:** Week shows the whole grid. Day lists one day's classes with the breaks between them.
- **Overlaps:** classes that clash are drawn with a red dashed border, and the week summary counts them.
- Use the **←** and **→** keys to change week on a laptop.

## Trying it without putting it online

Double-click `index.html` to open it straight from your computer. The timetable and the in-app alert bar work. Installing, offline use and system notifications need a web address. On your laptop you can also run it locally: if you have Python, open a terminal in this folder, run `python -m http.server 8000`, and visit `http://localhost:8000`. Notifications work there too.

## Changing the app later

Upload a new `index.html` to the repository; installed copies pick it up the next time they open online. If you change `sw.js` or the icons, also change `timetable-v1` near the top of `sw.js` to `timetable-v2` so devices replace their saved copies.
