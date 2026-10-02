# OSINT Workstation

**A single-file, open-source investigation workspace that puts hundreds of OSINT resources one click away, so you never have to remember a link again.**

![License](https://img.shields.io/badge/license-MIT-blue)
![Type](https://img.shields.io/badge/type-single--file%20HTML%20app-informational)
![Dependencies](https://img.shields.io/badge/build%20step-none-brightgreen)
![Data](https://img.shields.io/badge/data-stored%20locally%20in%20your%20browser-lightgrey)

> **Created by:** `LINDUNDA KALALUKA` — `https://github.com/kalalukalindunda`
> **Original repository:** `https://github.com/kalalukalindunda/OSINT-Workstation`

---

## Table of Contents

1. [Purpose and Philosophy](#1-purpose-and-philosophy)
2. [Features at a Glance](#2-features-at-a-glance)
3. [Quick Start](#3-quick-start)
4. [Interface Tour](#4-interface-tour)
5. [The Application Viewer](#5-the-application-viewer)
6. [Resource Categories](#6-resource-categories)
7. [Case Management](#7-case-management)
8. [Reports, Timeline and Audit Log](#8-reports-timeline-and-audit-log)
9. [Settings and Local Storage](#9-settings-and-local-storage)
10. [Privacy and Security Model](#10-privacy-and-security-model)
11. [Responsible and Legal Use](#11-responsible-and-legal-use)
12. [Architecture and Code Structure](#12-architecture-and-code-structure)
13. [Customising and Extending](#13-customising-and-extending)
14. [Known Limitations](#14-known-limitations)
15. [Troubleshooting and FAQ](#15-troubleshooting-and-faq)
16. [Contributing](#16-contributing)
17. [Attribution and Credit Policy](#17-attribution-and-credit-policy)
18. [Acknowledgements](#18-acknowledgements)
19. [License](#19-license)
20. [Disclaimer](#20-disclaimer)

---

## 1. Purpose and Philosophy

OSINT (Open Source Intelligence) work depends on a very large number of websites: flight and ship trackers, map and imagery services, webcam directories, news agencies, archive tools, leak monitors and more. Experienced investigators carry long lists of bookmarks in their heads, and newcomers lose hours hunting for the right link.

**OSINT Workstation exists to cut that time.** It is a ready-made, organised launchpad where:

- Every resource is a **card** with a short description. You click **Open** instead of remembering a URL.
- Resources open **inside the application** (embedded viewer) or in a **dedicated app window / new tab**, whichever the site allows.
- Anything you find can be **recorded to a case file** with a timestamp, a confidence rating and provenance notes.
- Everything runs **in your browser**. There is no server, no account and no telemetry.

It is **free and open source**. Anyone who understands OSINT tradecraft and the legal and ethical limits of the work is welcome to use it, fork it and improve it, provided the original creator is credited (see [Attribution and Credit Policy](#17-attribution-and-credit-policy)).

**Design principles**

| Principle | What it means in practice |
|---|---|
| Zero memorisation | Categories, search, filters and one-click launch replace bookmark lists |
| Zero setup | One `.html` file. Double-click to run |
| Local first | Cases, evidence and audit data never leave your device |
| Honest tooling | The app does not bypass website security, disguise traffic or scrape sites |
| Provenance matters | Every recorded item carries a source, time and confidence level |
| Risk awareness | High-risk resources require an explicit authorisation confirmation |

---

## 2. Features at a Glance

- **Resource launchpad** across six source categories: OSINT, Dark & Deep Web, Transport & Maritime, CCTV & Public Webcams, Locations & Maps, and News & Open Sources
- **Embedded application viewer** with reload, maximise, address bar, "open in app window" and "open in browser tab"
- **Smart handling of sites that block embedding**: detects them and offers a dedicated app window instead of showing a blank frame
- **Global query bar**: type a domain, IP, handle, place or coordinates and get a launcher of relevant sources
- **Location-aware tools**: set an active location once and 16 map, aviation, maritime, rail and infrastructure tools open centred on it
- **Location Summary** powered by OpenStreetMap (Nominatim + Overpass): counts of schools, clinics, hospitals, hotels, lodges, recreation, shops, banks, police, fuel stations, transport hubs, utilities and more, with named lists and CSV export
- **News directory** of 176 sources (wire agencies, broadcasters, international organisations) filterable by region, country and type, with editable links
- **Case management**: subjects and entities, evidence registry with confidence flags, analytical notes
- **Reporting**: downloadable HTML executive summary and print-friendly view
- **Timeline** combining evidence and activity
- **Audit log** of resource access and case actions, exportable as CSV
- **Risk gating** for High Risk and Sensitive resources
- **Screen density control** (Compact / Comfortable / Large), full-screen mode and a responsive layout
- **Keyboard and accessibility support**: focus outlines, ARIA labels, Escape closes dialogs

---

## 3. Quick Start

### Option A: Run locally (recommended)

1. Download `osint_workstation_professional_updated.html` (or clone the repository).
2. Open the file in a modern browser (Chrome, Edge, Firefox or Safari).
3. Start using it. No installation, build step or server is needed.

```bash
git clone [YOUR REPOSITORY URL]
cd osint-workstation
# then simply open the file in your browser
```

### Option B: Host it on GitHub Pages

1. Rename the file to `index.html` (or keep the name and link to it directly).
2. In your repository go to **Settings → Pages**, choose the branch and root folder, and save.
3. Your workstation is served at `https://<username>.github.io/<repository>/`.

> Hosting is optional. Because all data is stored in each visitor's own browser, hosting it publicly does not expose anyone's cases.

### Requirements

| Requirement | Detail |
|---|---|
| Browser | Any current evergreen browser |
| Internet | Needed to load the embedded sites, icons (Font Awesome CDN) and the Location Summary |
| Pop-ups | Allow pop-ups for the page, otherwise "Open in App Window" is blocked |
| Tor Browser | Needed separately for any `.onion` address (see [section 6.2](#62-dark--deep-web)) |

---

## 4. Interface Tour

The screen has three areas.

### 4.1 Left sidebar (navigation)

| Section | Item | What it does |
|---|---|---|
| **Investigation Workspace** | Dashboard | Case counts, evidence count, resources opened, high-risk confirmations, quick launch buttons and recent activity |
| | Cases | Opens the case workspace (the badge shows the active case's evidence count) |
| | Subjects & Entities | Table of targets, associates and other persons of interest with linked evidence counts |
| | Evidence | Jumps straight to the Evidence tab of the active case |
| **Intelligence Sources** | OSINT Resources | General OSINT tools |
| | Dark & Deep Web | Dark web search engines, directories, leak monitors, file sharing |
| | Transport & Maritime | Aviation, maritime, road and rail tracking |
| | CCTV & Public Webcams | Public webcam directories |
| | Locations & Maps | Maps, imagery, sun/shadow tools, infrastructure maps and the Location Summary |
| | News & Open Sources | Global news agency and organisation directory |
| **Administration** | Timeline | Chronological view of evidence and activity |
| | Reports | Generate and download the case report |
| | Audit Log | View and export the activity log |
| | Settings | Screen density and workspace reset |

On narrow screens (under 720 px) the sidebar collapses to icons only.

### 4.2 Top control bar

| Control | Function |
|---|---|
| **Global query box** | Type a domain, IP, handle or coordinates and press **Enter** |
| **Add to Case** | Records the resource currently open in the viewer as evidence |
| **Density selector** | Compact, Comfortable or Large spacing and font sizes |
| **Toggle Viewer** | Show or hide the right-hand viewer pane |
| **Full Screen** | Enter or leave browser full-screen |

### 4.3 Main content and viewer

The left part of the content area shows resource cards or the case workspace. The right part is the **Application Viewer** (section 5).

---

## 5. The Application Viewer

The viewer is the heart of the "no need to remember links" idea. Click **Open** on any card and the site loads in the right-hand pane.

### 5.1 Viewer controls

| Button | Action |
|---|---|
| Reload | Reloads the current page, or re-runs the current query launcher |
| Maximise | Expands the viewer to fill the content area |
| Address bar | Type a full URL, a bare domain (e.g. `example.org`), an IP address, coordinates or a search term, then press **Enter** |
| Add to Case | Records the current page as an evidence item |
| Open in App Window | Opens the page in a separate pop-up window sized to your screen |
| Open in browser tab | Opens the page in a new tab (with `noopener, noreferrer`) |
| Close | Clears the viewer |

### 5.2 How the address bar interprets input

| You type | The workstation does |
|---|---|
| `https://…` | Loads it in the viewer |
| `example.org/path` | Adds `https://` and loads it |
| An IP such as `8.8.8.8` | Opens the Global Query launcher with IP-specific sources |
| `-15.77, 28.18` | Opens a Google Maps view at those coordinates |
| Anything else | Opens the Global Query launcher with that text |

### 5.3 Sites that refuse to be embedded

Many major sites (Google Search, X/Twitter, Facebook, FlightRadar24, MarineTraffic, GitHub, Reddit, YouTube watch pages and others) send `X-Frame-Options` or `frame-ancestors` headers that forbid display inside another page. **OSINT Workstation does not try to bypass this**; that is a security policy of the website.

Instead, the viewer:

1. Recognises these domains from a built-in `BLOCKED` list.
2. Shows an explanatory card with buttons: **Open in App Window**, **Add to Case**, **Browser Tab**, **Copy URL** and **Try Embedded Anyway**.
3. For Standard-risk resources, automatically opens the App Window so you keep working with no extra clicks.

Some sites are rewritten to their embeddable form where the provider supports it, for example Google Maps (`output=embed`) and YouTube watch links (`/embed/`).

If a site that is *not* on the list still shows a blank frame, a notice appears after loading (or after a 12-second timeout) explaining that the site probably blocks embedding.

### 5.4 Global Query launcher

Entering a query in the top bar (or an unrecognised value in the viewer address bar) opens a launcher with the right sources for that input:

| Always offered | Offered for IP addresses | Offered for domains |
|---|---|---|
| Map search, Wayback Machine, Wikipedia, Google, Bing, DuckDuckGo, Yandex | Shodan, ARIN / RDAP | RDAP Domain, VirusTotal |

Each row is tagged **Embedded** (opens in the viewer) or **App Window** (opens in a separate window because that site forbids embedding).

---

## 6. Resource Categories

Each resource card shows a name, description, a **risk badge** (Standard, Sensitive or High Risk) and action buttons: **Open**, **App Window**, **Copy URL**, **Add to Case** (the exact set depends on the category).

### 6.1 OSINT Resources

General-purpose starting points: **Google Advanced Search**, **Wayback Machine** and **Google Maps / Earth**.

### 6.2 Dark & Deep Web

> **Warning:** these resources may contain illegal, harmful, disturbing or unverified material. A warning banner is shown at the top of the category.

| Sub-section | Contents |
|---|---|
| Search Engines | Ahmia, Tor66, Torch, Kilos, Google.onion, Phobos, TORMAX, GDARK |
| Service & Site Directories | The Hidden Wiki, OnionLinks, Onion.Live, tor.taxi, dark.fail |
| Breach & Leak Monitoring | BreachForums, Ransomware Live, Ransomlook |
| Chat & File Sharing | OnionShare |

How these cards behave:

- **Risk gating.** Opening any High Risk or Sensitive card shows a confirmation dialog: *"I Confirm Authorization."* The confirmation is written to the audit log.
- **`.onion` addresses cannot load in a normal browser.** The viewer shows a Tor card with **Copy Address** and **Record Observation**. Open the address in **Tor Browser** under your own authorised setup.
- **Cards with no stored destination** (marked `#` in the code) show a "Set a destination" prompt. Enter the official, verified URL once; it is remembered for that card in your browser (`osint_workstation_custom_urls`).
- **Leak monitors** deliberately say *"DO NOT automatically download or ingest stolen credentials."* The workstation never downloads, scrapes or ingests leaked data.
- Onion addresses change often and are frequently impersonated. **Verify every address against an authoritative source** before relying on it.

### 6.3 Transport & Maritime (16 tools)

| Group | Tools |
|---|---|
| Aviation & Aircraft Intelligence | FlightRadar24, FlightAware, PlaneFinder, ADS-B Exchange, OpenSky Network, Aviationstack, FAA Resources, EUROCONTROL |
| Maritime & Vessel Intelligence | MarineTraffic, VesselFinder, MyShipTracking, Global Fishing Watch, FleetMon |
| Road & Rail Transport Intelligence | Open Railway Map, TomTom Traffic Index, Waze Live Map |

### 6.4 CCTV & Public Webcams (5 tools)

EarthCam, Skyline Webcam, World Cam, WebcamTaxi and the Global Public Cam Map (Windy webcams).

Only **explicitly public** cameras and livestreams belong here. Accessing private or unsecured camera systems is illegal in most jurisdictions and is **strictly prohibited** (see [section 11](#11-responsible-and-legal-use)).

### 6.5 Locations & Maps (9 tools plus Location Summary)

| Group | Tools |
|---|---|
| Maps & Imagery | Google Earth, Google Maps, Street View (Mapillary), Yandex Maps |
| Sun & Shadow Analysis | SunCalc, ShadowMap, ShadeMap (useful for chronolocation: testing whether a photo's shadows match its claimed time and place) |
| Terrain, Infrastructure & Specialised Maps | OpenStreetMap, Open Infrastructure Map |

#### The Active Location

When you run a Location Summary, the place becomes the **Active Location**, shown as a chip at the top of the Transport, CCTV and Locations pages. Any tool tagged **"follows active location"** (16 in total) opens centred on those coordinates. Clear the chip to return to default views. The active location is remembered in your browser (`osint_workstation_location`).

#### Location Summary

Type a place name (e.g. `Kafue, Zambia`) or coordinates (e.g. `-15.77, 28.18`), choose a scope, and press **Summarise**.

| Scope option | Meaning |
|---|---|
| Administrative area boundary | The OpenStreetMap boundary of the place (falls back to a 5 km radius for point results) |
| Radius 2 / 5 / 10 / 25 km | A circle around the point |

The summary counts mapped features across **24 categories in 6 groups**:

| Group | Categories |
|---|---|
| Education | Schools, colleges & universities, kindergartens |
| Health | Hospitals, clinics, pharmacies |
| Accommodation | Hotels, lodges & guest houses, campsites & caravan sites |
| Recreation & Tourism | Recreation & sport, attractions & viewpoints |
| Commerce & Finance | Restaurants/cafes/bars, shops, markets, banks & ATMs |
| Public Services | Police, fire stations, government offices, places of worship |
| Transport & Utilities | Fuel stations, bus stations & stops, railway stations, airfields & airports, water & power facilities |

Click any tile to list the individual named features (first 300 shown) with a **Map** button for each. Use **Copy**, **CSV**, **Add to Case** and **Map** on the summary header. Adding to a case stores the counts, scope, source and retrieval time as a provenance note.

> **Data caveat:** figures come from **OpenStreetMap contributors**. They show what volunteers have mapped, not an official census. Rural coverage is often incomplete, so treat counts as a **minimum**, and corroborate with official sources.

### 6.6 News & Open Sources (176 sources)

A directory of national news agencies, public broadcasters and international organisations.

| Region | Entries |
|---|---|
| International (organisations and global wires) | 24 |
| Africa | 44 |
| Asia & Middle East | 47 |
| Europe | 42 |
| Americas | 15 |
| Oceania | 4 |

- **Filters:** free-text search (accent-insensitive), region, country and source type (Wire/state agency, Broadcaster/newspaper, International organisation, Global wire).
- **Cards** show the agency, country, source type and one or more website chips. Some sources are flagged **"May be blocked"** because they are often restricted from certain regions (e.g. KCNA, SANA, WAFA).
- **Edit** lets you correct any link; the change is saved locally and can be reset to default.
- **Coverage notes** explain which countries are not listed and why (for example agencies that have closed).

> **Note:** the news links were compiled from general knowledge and have **not all been live-tested**. Please use the Edit button for corrections and consider submitting a pull request with fixes.

---

## 7. Case Management

Open **Cases** in the sidebar. The case workspace has four tabs.

### 7.1 Overview & Subjects

| Field | Purpose |
|---|---|
| Primary Target Name / Alias | The main subject of the investigation |
| Associated Entities | Comma-separated organisations or people linked to the target |
| Other Subjects / POIs | Comma-separated further persons of interest |
| Master Investigation Objectives & Notes | Authorised scope, objectives and high-level summary |

Press **Save Workspace** to store the details. These fields feed the **Subjects & Entities** table and the report.

### 7.2 Evidence File

Record any source observation:

| Field | Purpose |
|---|---|
| Source Link / URL | Where the information was found |
| Observation Title / Label | A short descriptive name |
| Provenance Confidence | The reliability rating (see table below) |
| Associate to Entity | Primary Target, Associated Entity or General Lead |
| Investigator Provenance Notes | Collection date, hash, corroborating sources and so on |

**Confidence ratings**

| Flag | Label | Meaning |
|---|---|---|
| Red | Verified | Confirmed evidence |
| Orange | Corroborated | Probable |
| Yellow | Unverified | Raw observation (default) |
| Purple | Inferred | Analytical assessment |

Evidence is shown in the **Evidence Registry** table with timestamp. Click a recorded link to reopen it in the viewer.

**Fast capture.** Every card has an **Add to Case** button, and the viewer header has one too. A small dialog lets you add observation notes before recording. Location summaries and news sources can be added the same way.

### 7.3 Intelligence & Findings

A free-text area for hypotheses, corroborations and contradictions. It carries the guidance: *"Do not automatically convert an OSINT claim into a confirmed fact."* Keep verified evidence and analytical judgement separate.

### 7.4 Reports & Audit

Shortcut to the Reports module.

---

## 8. Reports, Timeline and Audit Log

### 8.1 Reports

Generate an **Executive Summary** of the active case containing case ID, generation time, subjects, objectives and notes, and the full evidence registry with confidence, source, entity, notes and time. Use **Download (HTML)** to save `osint-report-<CASE-ID>.html`, or print it from the browser.

### 8.2 Timeline

Evidence entries and audit events combined in reverse chronological order.

### 8.3 Audit Log

A local record of what you did, including: resources opened, high-risk access confirmations, apps windows opened, global queries, evidence recorded, workspace saved, reports generated and location summaries produced. **Export CSV** produces `osint-audit-log.csv` with columns `time, case, action, detail`.

> The audit log lives in your browser's local storage and is **not tamper-proof**. For evidential or compliance use, export it regularly and keep the exports under your organisation's controls.

---

## 9. Settings and Local Storage

**Settings** offers screen density and **Reset all local workspace data** (cases, evidence, audit history and custom URLs, after a confirmation prompt).

All data is stored with the browser's `localStorage` on the current device and browser profile:

| Key | Contents |
|---|---|
| `osint_workstation_cases` | Cases and their evidence |
| `osint_workstation_audit` | Audit log |
| `osint_workstation_density` | Chosen screen density |
| `osint_workstation_custom_urls` | Destinations you entered for cards with no preset link |
| `osint_workstation_news_links` | Your edits to news source links |
| `osint_workstation_location` | The active location |

Consequences worth knowing:

- Data does **not** sync between browsers or devices.
- Clearing site data, using private/incognito mode, or switching browser profiles will remove or hide it.
- Opening the file from a different path or origin (for example `file://` versus a hosted URL) can use a different storage area.
- **Back up** important work by downloading reports and CSV exports.

---

## 10. Privacy and Security Model

**What stays local:** your cases, evidence, notes, audit log, preferences and custom links.

**What the app contacts**

| Service | Why | When |
|---|---|---|
| `cdnjs.cloudflare.com` | Font Awesome icons | On page load |
| `nominatim.openstreetmap.org` | Geocoding place names | Only when you run a Location Summary |
| `overpass-api.de`, `overpass.kumi.systems`, `overpass.private.coffee` | Feature counts (tried in order) | Only when you run a Location Summary |
| The websites you choose to open | Showing the resource | Only when you open them |

There is no analytics, tracking, account system or backend belonging to this project.

**Built-in safeguards**

- All user-supplied text is HTML-escaped before display.
- The viewer only loads `http:` and `https:` addresses.
- The embedded frame is sandboxed, and browser-tab opens use `noopener, noreferrer`.
- High Risk and Sensitive resources require explicit confirmation.
- The application does **not** proxy, disguise, rewrite or bypass the security policy of external websites.

**Things to be aware of**

- Websites you open (embedded or in a window) can see your IP address and browser details as with any normal visit. If your work requires anonymity, use appropriate and authorised tooling (such as a VPN, a managed investigation machine or Tor Browser) **before** you start.
- Location lookups send the place name or coordinates you type to OpenStreetMap services.
- Because the app runs in a normal browser tab, treat the device itself as the security boundary. Case data is stored **unencrypted** in browser storage.

---

## 11. Responsible and Legal Use

OSINT Workstation is for **lawful, authorised and ethical** investigation. By using it you accept that:

- You will comply with all applicable laws, your organisation's policies, your investigative authority and each platform's terms of service.
- You will **not** access private systems, private cameras or accounts, or any resource you are not authorised to access.
- You will **not** download, ingest, trade or redistribute stolen credentials, personal data from breaches, or illegal material.
- You will treat High Risk resources as potentially harmful and disturbing, and take appropriate operational-security and welfare precautions.
- You will verify claims before treating them as fact, record provenance (what, where, when) and distinguish verified evidence from assessment.
- You will respect privacy, avoid harassment, stalking and doxxing, and consider the impact on the people you research.

The tool provides links and a note-keeping workspace. **You are responsible for how you use it.**

---

## 12. Architecture and Code Structure

The whole project is **one self-contained HTML file** with three layers, using no frameworks or build tools.

| Layer | Location in file | Notes |
|---|---|---|
| Styles | `<style>` block | CSS variables for theme, density and flag colours; responsive breakpoints at 980 px and 720 px |
| Markup | `<body>` | Sidebar, top bar, resource sections, case studio, viewer pane, modals |
| Logic | Main `<script>` (an IIFE in strict mode) | All application behaviour |

### 12.1 Key data structures

| Name | Purpose |
|---|---|
| `REG` | Registry mapping card names to real destination URLs (used by cards that carry only a placeholder) |
| `BLOCKED` | Domains known to forbid iframe embedding |
| `TRUSTED` | Domains known to embed well (suppresses the "may be blocked" banner) |
| `TOOLS` | Catalogue of the Transport, CCTV and Locations tools (`cat`, `group`, `name`, `icon`, `desc`, `url`, optional `loc(l)` that builds a location-centred URL) |
| `TOOL_GROUPS` | Which groups appear under each category |
| `NEWS_RAW` | Pipe-delimited news directory: `Region\|Country\|Agency\|Type\|domain[,domain]\|R?` |
| `CATS` | The 24 location summary categories and their OpenStreetMap filters |
| `MODULES` | Render functions for Dashboard, Subjects & Entities, Timeline, Reports, Audit Log and Settings |

### 12.2 Main functions

| Area | Functions |
|---|---|
| Viewer | `openResource`, `loadInApp`, `toEmbedUrl`, `isBlocked`, `openAppWindow`, `openInTab`, `viewerGo`, `showBrief`, `showLauncher` |
| Risk | `confirmRiskAccess` |
| Cases | `addEvidenceItem`, `renderEvidence`, `saveCaseDetails`, `addResourceToCase`, `confirmAddToCase`, `quickClipToCase` |
| Reporting | `reportHtml`, `downloadReport`, `exportAudit`, `logAudit` |
| News | `initNews`, `renderNews`, `openEditLink` |
| Tools | `initTools`, `renderTools`, `toolUrl`, `setLocation` |
| Location | `geocode`, `overpass`, `runSummary`, `renderSummary`, `showNames`, `summaryCsv` |

### 12.3 Risk levels

| Badge | Behaviour |
|---|---|
| Standard | Opens directly |
| Sensitive | Requires authorisation confirmation |
| High Risk | Requires authorisation confirmation; never auto-opens an App Window |

---

## 13. Customising and Extending

### 13.1 Add a tool to Transport, CCTV or Locations

Add an object to the `TOOLS` array:

```js
{
  cat: 'transport',                 // 'transport' | 'cctv' | 'locations'
  group: G_AV,                      // an existing group constant, or add a new one
  name: 'My New Tracker',
  icon: 'fa-plane',                 // any Font Awesome 6 solid icon
  desc: 'One-sentence description of what it is for.',
  url: 'https://example.org/',
  // optional: make it follow the active location
  loc: l => `https://example.org/map?lat=${r5(l.lat)}&lon=${r5(l.lon)}`
}
```

To create a new group, define a constant such as `const G_NEW = 'My Group';` and list it in `TOOL_GROUPS` under the right category.

### 13.2 Add a news source

Add a line to `NEWS_RAW`:

```
Region|Country|Agency name|Type|domain.tld
```

- **Region:** `International`, `Africa`, `Asia & Middle East`, `Europe`, `Americas` or `Oceania`
- **Type:** `A` wire/state agency, `P` broadcaster/newspaper, `O` organisation, `G` global wire
- **Domain:** without `https://`; separate several with commas
- Append `|R` to flag a source as often blocked or restricted

### 13.3 Mark a site as non-embeddable

Add its domain to `BLOCKED`. If it embeds fine, add it to `TRUSTED`.

### 13.4 Give a card a real destination

Add the card's title and URL to `REG`.

### 13.5 Add a location summary category

Add an entry to `CATS` with a label, icon, group and one or more Overpass filters. The counting query is generated from this list automatically.

### 13.6 Change the look

Edit the CSS variables in `:root` (backgrounds, accent colours, flag colours, risk colours, sidebar width). Density presets live in `body.density-compact` and `body.density-large`.

---

## 14. Known Limitations

Being upfront helps contributors know where the best opportunities are:

- **Single active case in the interface.** The data model stores a list of cases, but the current interface works with one active case. A case switcher and "new case" control would be a valuable contribution.
- **"Intelligence & Findings" text is not saved.** That text area has no persistence yet.
- **Dark web search engine addresses need verification.** Some `.onion` entries are short placeholder-style addresses, not full verified hidden-service addresses. The Tor card guides you to verify before use, but the list should be reviewed and replaced with confirmed addresses. Directory and leak-monitor cards without a destination ask you to enter one.
- **"Last Verified: Today" is a static label** on dark web search cards. It does not reflect live checking.
- **Not all links are live-tested**, especially the news directory. Websites change; expect some dead or moved links.
- **Embedding depends on each website.** The `BLOCKED` list is maintained by hand and will drift over time.
- **Location data is only as complete as OpenStreetMap.** Public Overpass servers can be slow or busy, and very large areas may time out (use a radius).
- **Browser-only storage.** No sync, no encryption, no tamper-proof audit trail.
- **Pop-up blockers** can stop "Open in App Window".
- **Optional dashboard/report polish.** Reports are plain HTML; PDF output relies on the browser's print dialog.

---

## 15. Troubleshooting and FAQ

**The viewer is blank or says "refused to connect."**
That site forbids embedding. Use **Open in App Window** or **Browser Tab**.

**"Open in App Window" does nothing.**
Allow pop-ups for the page in your browser's site settings.

**Icons are missing.**
The Font Awesome CDN could not load. Check your connection or any content blocker.

**Location Summary fails or times out.**
Try a smaller radius, retry after a short wait (public servers get busy), or add the country to the place name (e.g. `Kafue, Zambia`).

**My cases disappeared.**
Browser data was cleared, you changed browser or profile, or you opened the file from a different location. Restore from your exports.

**An `.onion` link won't open.**
That is expected. Copy the address and open it in Tor Browser.

**A news link is wrong.**
Click **Edit** on its card, correct it and save. Please also send a pull request.

**Can several people share one case?**
Not currently. Data is local to one browser. Share by exporting the HTML report.

**Does it work offline?**
The interface loads offline (apart from icons), but the resources it opens, and the Location Summary, need internet access.

---

## 16. Contributing

Contributions are very welcome, from fixing a dead link to building a new module.

1. **Fork** the repository and create a branch (`feature/short-description`).
2. Make focused changes. Keep it a **single self-contained HTML file** unless discussed first.
3. **Test** in at least two browsers, including: opening cards, the blocked-site flow, adding evidence, generating a report and the Location Summary.
4. Keep the safety model intact: do not add features that bypass website protections, scrape, proxy, or auto-ingest leaked data.
5. Open a **pull request** describing the change and why.

**Good first contributions**

- Verify and fix links (especially the news directory and dark web entries)
- Add new, genuinely useful public OSINT resources
- Case switcher, "new case" and case export/import (JSON)
- Persist the Intelligence & Findings notes
- Encrypted local storage option
- Translations and accessibility improvements

---

## 17. Attribution and Credit Policy

This project is open source, and **recognising the original creator is a condition of using, modifying and redistributing it.**

If you use, fork, modify, improve, rebrand or redistribute OSINT Workstation (in whole or in part, including as part of a larger tool or training material), you **must**:

1. **Keep the original copyright and licence notice** in the source file and in the repository.
2. **Credit the original creator by name** in your README and in the application's About/footer/header comment, using wording such as:

   > Based on **OSINT Workstation** by `[YOUR NAME / HANDLE]` — `[YOUR REPOSITORY URL]`

3. **Link back to the original repository.**
4. **State clearly that your version is modified** and describe what you changed. Do not present your version as the original.
5. **Keep this attribution section** (or an equivalent) in any derivative documentation.
6. Add your own name as an additional contributor for your improvements. Adding credit for yourself never replaces credit to the original creator.

**Suggested header comment for the HTML file:**

```html
<!--
  OSINT Workstation
  Original creator: [YOUR NAME / HANDLE]
  Original repository: [YOUR REPOSITORY URL]
  Licence: MIT (see LICENSE). Modified versions must retain this notice
  and credit the original creator.
-->
```

Please do not remove the creator's credit to make a version look original. Respecting credit keeps the open-source community healthy and encourages people to keep sharing.

### Contributors

| Name | Role | Contribution |
|---|---|---|
| `[YOUR NAME / HANDLE]` | Original creator | Concept, design and initial implementation |
| *You?* | Contributor | Open a pull request and add yourself here |

---

## 18. Acknowledgements

OSINT Workstation stands on the shoulders of the open-source and open-data community. Heartfelt thanks to everyone who builds, maintains and shares tools and data openly.

**Open data and open-source projects used directly**

- **[OpenStreetMap](https://www.openstreetmap.org/) and its volunteer mappers.** The foundation of the Location Summary and several map tools. Data © OpenStreetMap contributors, available under the [ODbL](https://www.openstreetmap.org/copyright).
- **[Overpass API](https://overpass-api.de/)** and the community mirrors (`overpass.kumi.systems`, `overpass.private.coffee`) for making OpenStreetMap queryable.
- **[Nominatim](https://nominatim.org/)** for geocoding.
- **[Font Awesome](https://fontawesome.com/)** (Free) for the icon set, delivered via cdnjs / Cloudflare.
- **[Open Railway Map](https://www.openrailwaymap.org/)** and **[Open Infrastructure Map](https://openinframap.org/)** for open rail and infrastructure mapping.
- **[Mapillary](https://www.mapillary.com/)** for crowd-sourced street-level imagery.
- **[OpenSky Network](https://opensky-network.org/)** and **[ADS-B Exchange](https://www.adsbexchange.com/)** and the volunteer feeders who power open aircraft tracking.
- **[Internet Archive / Wayback Machine](https://archive.org/)** for preserving the web.
- **[Wikipedia](https://www.wikipedia.org/)** and the Wikimedia community.
- **[Global Fishing Watch](https://globalfishingwatch.org/)** for open maritime transparency data.
- **[SunCalc](https://www.suncalc.org/)**, **[ShadowMap](https://shadowmap.org/)** and **[ShadeMap](https://shademap.app/)** for sun and shadow analysis.
- **[Windy](https://www.windy.com/)** for its public webcam map.
- **[Ahmia](https://ahmia.fi/)**, **[dark.fail](https://dark.fail/)**, **[Ransomware.live](https://www.ransomware.live/)**, **[RansomLook](https://www.ransomlook.io/)**, **[OnionShare](https://onionshare.org/)** and **[The Tor Project](https://www.torproject.org/)** for transparency and privacy research tooling.

**The wider OSINT community**

Thank you to the researchers, journalists, analysts, educators and hobbyists who publish their methods, curate resource lists and teach others, including every open-source project and curated link collection whose ideas shaped this workstation. This tool exists to make that shared knowledge easier to reach.

**Third-party services**

All other services linked from this workstation (flight and ship trackers, map providers, webcam directories, news agencies and so on) are independent third parties. Their names and marks belong to their owners. Listing a service does not imply endorsement or affiliation, and each service's own terms of use apply.

*If you maintain a project listed here and would like the wording changed or a link updated, please open an issue.*

---

## 19. License

This project is released under the **MIT License** (recommended; replace with your chosen licence if different), with the attribution expectations described in [section 17](#17-attribution-and-credit-policy).

```
MIT License

Copyright (c) [YEAR] [YOUR NAME / HANDLE]

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

> The MIT licence already requires that the copyright notice travel with the software. Add a `LICENSE` file to the repository root containing the text above.

---

## 20. Disclaimer

- OSINT Workstation is provided **"as is"**, without warranty of any kind.
- It is a **link launcher and note-keeping aid**. It does not verify information, guarantee that any link is safe, current or accurate, or provide legal advice.
- Third-party sites, including High Risk resources, may contain illegal, harmful or misleading material. Open them only if you are authorised, prepared and acting lawfully.
- The creator and contributors accept **no liability** for misuse, for decisions made from information gathered with the tool, or for the content of any external website.
- Location counts and directory entries may be incomplete or out of date. **Always corroborate** before relying on them.

---

<p align="center">
  <b>OSINT Workstation</b> — created by <code>[Lindunda Kalaluka]</code><br>
  Built for the OSINT community, with thanks to every open-source project that made it possible.
</p>
