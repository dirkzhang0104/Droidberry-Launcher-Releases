<h1>
  <span aria-hidden="true">🫐</span>
  Droidberry Launcher
  Home on Reddit: https://www.reddit.com/r/DroidberryLauncher/
</h1>

A feature-rich **Android home-screen launcher** built for **phones, tablets, and foldable devices**, featuring a **BlackBerry-style Hub** — a single, unified inbox that brings every notification on the device into one easy-to-browse, chronological stream.

Built with **Kotlin**, **Jetpack Compose**, **Material 3**, and **Jetpack WindowManager** for
fold-aware layouts.

## ✨ Features

### 📬 BlackBerry-style Hub
- `NotificationListenerService` funnels all notifications into one unified inbox with
  account/category filter chips (Messages, Email, Social, Calls, etc.), just like BlackBerry OS 10.
- Chronological stream with live unread badge on the home screen shortcut.
- Tap any item to fire its original `contentIntent`; dismiss items individually or in bulk.
- **Inline reply** — compose and send a reply directly from the Hub using `Notification.Action`
  remote inputs without leaving the launcher.
- Swipe down from anywhere in the hub to close it.

### 📱 Foldable & Adaptive UI
- `rememberFoldState()` observes the hinge via `WindowInfoTracker` and swaps between a bottom
  `NavigationBar` (folded / flat) and a side `NavigationRail` (unfolded / dual-pane).
- Detects `FLAT`, `BOOK`, and `TABLETOP` postures.
- App-drawer grid column count adapts to screen width automatically.
- Outer screen supports up to 5 apps in the dock while inner supports up to 12.

### 🏠 Home Screen
- Live clock showing day of week, time, and date in one glance.
- **Live weather chip** — pulls current temperature and conditions from the free, keyless
  [Open-Meteo](https://open-meteo.com) API using the device's last-known coarse location.
  Automatically switches between °F and °C by locale.
- Battery indicator always visible next to the clock.
- Quick-access shortcuts to the Hub (with live unread badge) and the app drawer.
- **Home-screen widgets** — long-press empty space to add any Android app widget; drag to reposition,
  resize with a handle, and remove with a tap. Widget state persists across relaunches.
- **Layout edit lock** — widget and dock edits are locked automatically when the screen turns off,
  preventing accidental changes. Unlock explicitly from the home screen to edit again.
- **Google Feed / "-1 page"** — swipe the home surface to the right to open the Google app as a
  side panel (optional; toggle in Settings). This is not a true google feed but the Google app you have installed because Google has restricted the implementation of AIDLBridge so it is not possible to have native solutions anymore.

### 🔎 App Drawer & Search
- Searchable, adaptive grid of every launchable app on the device.
- **Work profile support** — apps from a managed/work profile are shown with their work badge,
  launched in the correct profile context.
- **Tag filter chips** — filter the drawer by user-created tags.
- Dedicated **App Search** screen accessible via gesture or shortcut.
- Long-press any app icon to pin it to the dock, change its icon, or access app info.

### 🧰 Customisable Dock
- Optional persistent dock at the bottom of every screen.
- Pin up to 5 apps (outter screen or slab phone) or 12 apps (inner screen); reorder by drag-and-drop.
- Enable or disable from Settings.

### 👆 Gesture Customisation
- Bind **swipe up**, **swipe down**, and **double-tap** on the home surface to any of:
  - Open App Drawer
  - Open Hub
  - Open Search
  - Expand Notification Shade
  - Lock Screen
  - None (disable)
- Defaults: swipe-up → App Drawer, swipe-down → Notification Shade, double-tap → Lock Screen.

### 🎨 Icon Pack Support
- Compatible with any icon pack that uses the standard **icon pack protocol** (Nova, ADW, GO, Apex,
  Lawnchair, and others that advertise via a theme intent).
- **Per-app icon override** — long-press any app in the drawer to pick a specific icon drawable
  from any installed icon pack, independent of the global pack.
- Revert any override back to the default with one tap.

### 🖼️ Look & Feel
- Global app icon size selector: 100 %, 120 %, or 150 % of the base tile size.

### 💾 Backup & Restore (Experimental but works most of the time)
- Launcher setting is located separately as a standalone icon in your app drawer, search for "setting" or "droidberry"
- Export all launcher settings (tags, gestures, dock, icon pack, widgets, overrides, …) to a
  single JSON file and save it anywhere on the device or cloud storage.
- Restore from any previously exported JSON file.

### ℹ️ Other
- Runs edge-to-edge over the wallpaper with fully transparent system bars.
- Registered as a `HOME` app — can be set as the system default launcher.
- `AccessibilityService` used for the swipe-down notification-shade gesture and the lock-screen
  gesture; completely opt-in.
- Pressing the hardware/software Home button while already inside Droidberry snaps back to the
  home surface from any tab.
