# OSINT Workstation

**A single-file, open-source workspace that brings a hand-picked selection of OSINT resources together in one place, so investigators and learners have a solid starting point and never have to remember a link again.**

![License](https://img.shields.io/badge/license-MIT-blue)
![Type](https://img.shields.io/badge/type-single--file%20HTML%20app-informational)
![Dependencies](https://img.shields.io/badge/build%20step-none-brightgreen)
![Data](https://img.shields.io/badge/data-stored%20locally%20in%20your%20browser-lightgrey)

> **Created by:** Lindunda Kalaluka · [github.com/kalalukalindunda](https://github.com/kalalukalindunda)
> **Original repository:** [github.com/kalalukalindunda/OSINT-Workstation](https://github.com/kalalukalindunda/OSINT-Workstation)

> **Important, please read:** OSINT Workstation is a **launchpad**. It does not own, operate, host or control any of the websites, tools, datasets or services it links to. Every one of them was built and is maintained by other people and organisations, and their work deserves recognition (see [Acknowledgements](#20-acknowledgements)). **Free access to this workstation does not give you the same rights on the linked sites.** Each site has its own terms, licences, usage limits and legal requirements, and you must follow them (see [Section 13](#13-third-party-sites-terms-and-your-responsibilities)).

---

## Table of Contents

1. [Purpose and Philosophy](#1-purpose-and-philosophy)
2. [What This Project Is (and Is Not)](#2-what-this-project-is-and-is-not)
3. [Features at a Glance](#3-features-at-a-glance)
4. [Quick Start](#4-quick-start)
5. [Interface Tour](#5-interface-tour)
6. [The Application Viewer](#6-the-application-viewer)
7. [Resource Categories](#7-resource-categories)
8. [Case Management](#8-case-management)
9. [Reports, Timeline and Audit Log](#9-reports-timeline-and-audit-log)
10. [Settings and Local Storage](#10-settings-and-local-storage)
11. [Privacy and Security Model](#11-privacy-and-security-model)
12. [Responsible and Legal Use](#12-responsible-and-legal-use)
13. [Third-Party Sites, Terms and Your Responsibilities](#13-third-party-sites-terms-and-your-responsibilities)
14. [Architecture and Code Structure](#14-architecture-and-code-structure)
15. [Customising and Extending](#15-customising-and-extending)
16. [Known Limitations](#16-known-limitations)
17. [Troubleshooting and FAQ](#17-troubleshooting-and-faq)
18. [Contributing](#18-contributing)
19. [Attribution and Credit Policy](#19-attribution-and-credit-policy)
20. [Acknowledgements](#20-acknowledgements)
21. [License](#21-license)
22. [Disclaimer](#22-disclaimer)

---

## 1. Purpose and Philosophy

OSINT (Open Source Intelligence) work depends on a very large number of websites: flight and ship trackers, map and imagery services, webcam directories, news agencies, archive tools, leak monitors and more. Experienced investigators carry long lists of bookmarks in their heads, and newcomers lose hours hunting for the right link.

**OSINT Workstation exists to cut that time.** It is a ready-made, organised launchpad where:

- Every resource is a **card** with a short description. You click **Open** instead of remembering a URL.
- Resources open **inside the application** (embedded viewer) or in a **dedicated app window / new tab**, whichever the site allows.
- Anything you find can be **recorded to a case file** with a timestamp, a confidence rating and provenance notes.
- Everything runs **in your browser**. There is no server, no account and no telemetry.

It is **free and open source**. Anyone who understands OSINT tradecraft and the legal and ethical limits of the work is welcome to use it, fork it and improve it, provided the original creator is credited (see [Attribution and Credit Policy](#19-attribution-and-credit-policy)).

**Design principles**

| Principle | What it means in practice |
|---|---|
| Zero memorisation | Categories, search, filters and one-click launch replace bookmark lists |
| Zero setup | One `.html` file. Double-click to run |
| Local first | Cases, evidence and audit data never leave your device |
| Honest tooling | The app does not bypass website security, disguise traffic or scrape sites |
| Provenance matters | Every recorded item carries a source, time and confidence level |
| Risk awareness | High-risk resources require an explicit authorisation confirmation |
| Credit where due | The sites and communities behind every link are acknowledged and respected |

---

## 2. What This Project Is (and Is Not)

**What it is**

OSINT Workstation simply **brings selected, publicly available OSINT sites together in a single workstation** so that users have a solid starting point. The real value lives in the sites and services it points to. This project adds only:

- an organised, searchable layout,
- a viewer and launcher,
- a local note-keeping and case workspace, and
- a few convenience features such as the Location Summary.

**The workstation combines the great work of many people.** Every tracker, map, archive, directory, dataset, agency website and open-source project listed here is the product of other people's effort, expertise, infrastructure and funding. Volunteers who map the world, feed aircraft data, preserve the web, run public cameras, publish research and keep news services running make this kind of work possible. **Their efforts must not go unnoticed**, and this project does not claim any of that work as its own.

**What it is not**

- It is **not** the owner, publisher, operator, mirror or reseller of any linked site.
- It is **not** affiliated with, endorsed by, or sponsored by any linked site or organisation. Listing a site is not an endorsement, and a site's presence here does not mean it endorses this project.
- It is **not** a data provider. It does not store, copy or redistribute third-party content.
- It is **not** a licence to use third-party services. See [Section 13](#13-third-party-sites-terms-and-your-responsibilities).

---

## 3. Features at a Glance

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

## 4. Quick Start

### Option A: Run locally (recommended)

1. Download `osint_workstation_professional_updated.html` (or clone the repository).
2. Open the file in a modern browser (Chrome, Edge, Firefox or Safari).
3. Start using it. No installation, build step or server is needed.

```bash
git clone https://github.com/kalalukalindunda/OSINT-Workstation.git
cd OSINT-Workstation
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
| Tor Browser | Needed separately for any `.onion` address (see [section 7.2](#72-dark--deep-web)) |

---

## 5. Interface Tour

The screen has three areas.

### 5.1 Left sidebar (navigation)

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

### 5.2 Top control bar

| Control | Function |
|---|---|
| **Global query box** | Type a domain, IP, handle or coordinates and press **Enter** |
| **Add to Case** | Records the resource currently open in the viewer as evidence |
| **Density selector** | Compact, Comfortable or Large spacing and font sizes |
| **Toggle Viewer** | Show or hide the right-hand viewer pane |
| **Full Screen** | Enter or leave browser full-screen |

### 5.3 Main content and viewer

The left part of the content area shows resource cards or the case workspace. The right part is the **Application Viewer** (section 6).

---

## 6. The Application Viewer

The viewer is the heart of the "no need to remember links" idea. Click **Open** on any card and the site loads in the right-hand pane.

### 6.1 Viewer controls

| Button | Action |
|---|---|
| Reload | Reloads the current page, or re-runs the current query launcher |
| Maximise | Expands the viewer to fill the content area |
| Address bar | Type a full URL, a bare domain (e.g. `example.org`), an IP address, coordinates or a search term, then press **Enter** |
| Add to Case | Records the current page as an evidence item |
| Open in App Window | Opens the page in a separate pop-up window sized to your screen |
| Open in browser tab | Opens the page in a new tab (with `noopener, noreferrer`) |
| Close | Clears the viewer |

### 6.2 How the address bar interprets input

| You type | The workstation does |
|---|---|
| `https://…` | Loads it in the viewer |
| `example.org/path` | Adds `https://` and loads it |
| An IP such as `8.8.8.8` | Opens the Global Query launcher with IP-specific sources |
| `-15.77, 28.18` | Opens a Google Maps view at those coordinates |
| Anything else | Opens the Global Query launcher with that text |

### 6.3 Sites that refuse to be embedded

Many major sites (Google Search, X/Twitter, Facebook, FlightRadar24, MarineTraffic, GitHub, Reddit, YouTube watch pages and others) send `X-Frame-Options` or `frame-ancestors` headers that forbid display inside another page. **OSINT Workstation does not try to bypass this**; that is a security policy of the website and it must be respected.

Instead, the viewer:

1. Recognises these domains from a built-in `BLOCKED` list.
2. Shows an explanatory card with buttons: **Open in App Window**, **Add to Case**, **Browser Tab**, **Copy URL** and **Try Embedded Anyway**.
3. For Standard-risk resources, automatically opens the App Window so you keep working with no extra clicks.

Some sites are rewritten to their embeddable form where the provider supports it, for example Google Maps (`output=embed`) and YouTube watch links (`/embed/`).

If a site that is *not* on the list still shows a blank frame, a notice appears after loading (or after a 12-second timeout) explaining that the site probably blocks embedding.

### 6.4 Global Query launcher

Entering a query in the top bar (or an unrecognised value in the viewer address bar) opens a launcher with the right sources for that input:

| Always offered | Offered for IP addresses | Offered for domains |
|---|---|---|
| Map search, Wayback Machine, Wikipedia, Google, Bing, DuckDuckGo, Yandex | Shodan, ARIN / RDAP | RDAP Domain, VirusTotal |

Each row is tagged **Embedded** (opens in the viewer) or **App Window** (opens in a separate window because that site forbids embedding).

---

## 7. Resource Categories

Each resource card shows a name, description, a **risk badge** (Standard, Sensitive or High Risk) and action buttons: **Open**, **App Window**, **Copy URL**, **Add to Case** (the exact set depends on the category).

> Every resource below belongs to its respective owner. See [Acknowledgements](#20-acknowledgements) for credit and [Section 13](#13-third-party-sites-terms-and-your-responsibilities) for the rules that apply when you use them.

### 7.1 OSINT Resources

General-purpose starting points: **Google Advanced Search**, **Wayback Machine** and **Google Maps / Earth**.

### 7.2 Dark & Deep Web

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
- A listing here is for awareness and research navigation only. It is not an endorsement of any site's content, community or conduct.

### 7.3 Transport & Maritime (16 tools)

| Group | Tools |
|---|---|
| Aviation & Aircraft Intelligence | FlightRadar24, FlightAware, PlaneFinder, ADS-B Exchange, OpenSky Network, Aviationstack, FAA Resources, EUROCONTROL |
| Maritime & Vessel Intelligence | MarineTraffic, VesselFinder, MyShipTracking, Global Fishing Watch, FleetMon |
| Road & Rail Transport Intelligence | Open Railway Map, TomTom Traffic Index, Waze Live Map |

### 7.4 CCTV & Public Webcams (5 tools)

EarthCam, Skyline Webcam, World Cam, WebcamTaxi and the Global Public Cam Map (Windy webcams).

Only **explicitly public** cameras and livestreams belong here. Accessing private or unsecured camera systems is illegal in most jurisdictions and is **strictly prohibited** (see [section 12](#12-responsible-and-legal-use)).

### 7.5 Locations & Maps (9 tools plus Location Summary)

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
>
> **Attribution reminder:** OpenStreetMap data is © OpenStreetMap contributors and licensed under the [ODbL](https://www.openstreetmap.org/copyright). If you publish or share Location Summary results, credit OpenStreetMap as the licence requires.

### 7.6 News & Open Sources (176 sources)

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
- News content is the copyright of each agency or broadcaster. The workstation only links to it. It does not copy, mirror or republish articles.

> **Note:** the news links were compiled from general knowledge and have **not all been live-tested**. Please use the Edit button for corrections and consider submitting a pull request with fixes.

---

## 8. Case Management

Open **Cases** in the sidebar. The case workspace has four tabs.

### 8.1 Overview & Subjects

| Field | Purpose |
|---|---|
| Primary Target Name / Alias | The main subject of the investigation |
| Associated Entities | Comma-separated organisations or people linked to the target |
| Other Subjects / POIs | Comma-separated further persons of interest |
| Master Investigation Objectives & Notes | Authorised scope, objectives and high-level summary |

Press **Save Workspace** to store the details. These fields feed the **Subjects & Entities** table and the report.

### 8.2 Evidence File

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

### 8.3 Intelligence & Findings

A free-text area for hypotheses, corroborations and contradictions. It carries the guidance: *"Do not automatically convert an OSINT claim into a confirmed fact."* Keep verified evidence and analytical judgement separate.

### 8.4 Reports & Audit

Shortcut to the Reports module.

---

## 9. Reports, Timeline and Audit Log

### 9.1 Reports

Generate an **Executive Summary** of the active case containing case ID, generation time, subjects, objectives and notes, and the full evidence registry with confidence, source, entity, notes and time. Use **Download (HTML)** to save `osint-report-<CASE-ID>.html`, or print it from the browser.

### 9.2 Timeline

Evidence entries and audit events combined in reverse chronological order.

### 9.3 Audit Log

A local record of what you did, including: resources opened, high-risk access confirmations, app windows opened, global queries, evidence recorded, workspace saved, reports generated and location summaries produced. **Export CSV** produces `osint-audit-log.csv` with columns `time, case, action, detail`.

> The audit log lives in your browser's local storage and is **not tamper-proof**. For evidential or compliance use, export it regularly and keep the exports under your organisation's controls.

---

## 10. Settings and Local Storage

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

## 11. Privacy and Security Model

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

## 12. Responsible and Legal Use

OSINT Workstation is for **lawful, authorised and ethical** investigation. By using it you accept that:

- You will comply with all applicable laws, your organisation's policies, your investigative authority and each platform's terms of service.
- You will **not** access private systems, private cameras or accounts, or any resource you are not authorised to access.
- You will **not** download, ingest, trade or redistribute stolen credentials, personal data from breaches, or illegal material.
- You will treat High Risk resources as potentially harmful and disturbing, and take appropriate operational-security and welfare precautions.
- You will verify claims before treating them as fact, record provenance (what, where, when) and distinguish verified evidence from assessment.
- You will respect privacy, avoid harassment, stalking and doxxing, and consider the impact on the people you research.

The tool provides links and a note-keeping workspace. **You are responsible for how you use it.**

---

## 13. Third-Party Sites, Terms and Your Responsibilities

This section is essential. Please read it before using any linked resource.

### 13.1 Free access here does not mean free rights there

OSINT Workstation is released under the MIT licence, so **you may use, copy and modify the workstation's own code** under that licence. **That licence covers only this project's code and documentation.** It does **not** extend to any website, service, dataset, API, brand, logo or content that the workstation links to or opens.

The fact that you can open a site from this workstation, or that the workstation is free, does **not** mean you have the same rights on that site. Each linked site has its own owner, and each sets its own rules.

### 13.2 What you must do

For every site you open through this workstation, you are responsible for:

1. **Reading and following that site's Terms of Service / Terms of Use**, privacy policy, acceptable-use policy and any API or data-licence terms.
2. **Respecting usage limits and access rules**, including rate limits, registration or subscription requirements, paid tiers, and restrictions on commercial, bulk, automated or research use.
3. **Respecting licences and attribution requirements** for any data, imagery, maps or text you reuse. Examples:
   - OpenStreetMap data requires attribution under the ODbL.
   - Wikipedia content is generally licensed with attribution and share-alike conditions.
   - Crowd-sourced imagery (for example on Mapillary) is subject to its own licence.
   - Open-data and aviation or maritime feeds often restrict commercial use, redistribution or bulk collection.
4. **Respecting copyright.** News articles, photographs, video, webcam streams and other content belong to their creators and publishers. Linking to them is not permission to copy, republish or train systems on them.
5. **Not scraping, mass-downloading or automating access** to any site unless its terms explicitly allow it. This workstation does not do this for you, and you should not do it yourself outside the rules.
6. **Respecting security controls.** Do not bypass embedding restrictions, paywalls, logins, geo-blocks or other protections.
7. **Following the law** of your country and the country of the site, including privacy, data-protection, computer-misuse and surveillance laws.
8. **Following any extra conditions** your employer, client, university or investigative authority places on tool use.

### 13.3 Services used directly by the workstation

Two parts of the workstation make requests on your behalf, so their policies apply directly:

- **Nominatim (OpenStreetMap geocoding)** has a usage policy that limits request rates and prohibits heavy or abusive use. Run lookups sparingly and do not script bulk geocoding.
- **Overpass API servers** are shared community infrastructure. Please use small radii, avoid repeated large queries, and be considerate of the volunteers who run them.

### 13.4 Names, logos and trademarks

All site names, product names and marks mentioned in this project belong to their respective owners. They are used only to identify the destination. Their use does not imply any partnership, sponsorship or endorsement in either direction.

### 13.5 Links change

Websites move, close, change their terms or add restrictions without notice. A listing in this project is not a guarantee that a site is available, safe, accurate or still permitted for your use. Always check the current terms at the source.

### 13.6 Removal and corrections

If you own or maintain a listed site and want it renamed, corrected or removed, please [open an issue](https://github.com/kalalukalindunda/OSINT-Workstation/issues). Reasonable requests will be handled promptly.

---

## 14. Architecture and Code Structure

The whole project is **one self-contained HTML file** with three layers, using no frameworks or build tools.

| Layer | Location in file | Notes |
|---|---|---|
| Styles | `<style>` block | CSS variables for theme, density and flag colours; responsive breakpoints at 980 px and 720 px |
| Markup | `<body>` | Sidebar, top bar, resource sections, case studio, viewer pane, modals |
| Logic | Main `<script>` (an IIFE in strict mode) | All application behaviour |

### 14.1 Key data structures

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

### 14.2 Main functions

| Area | Functions |
|---|---|
| Viewer | `openResource`, `loadInApp`, `toEmbedUrl`, `isBlocked`, `openAppWindow`, `openInTab`, `viewerGo`, `showBrief`, `showLauncher` |
| Risk | `confirmRiskAccess` |
| Cases | `addEvidenceItem`, `renderEvidence`, `saveCaseDetails`, `addResourceToCase`, `confirmAddToCase`, `quickClipToCase` |
| Reporting | `reportHtml`, `downloadReport`, `exportAudit`, `logAudit` |
| News | `initNews`, `renderNews`, `openEditLink` |
| Tools | `initTools`, `renderTools`, `toolUrl`, `setLocation` |
| Location | `geocode`, `overpass`, `runSummary`, `renderSummary`, `showNames`, `summaryCsv` |

### 14.3 Risk levels

| Badge | Behaviour |
|---|---|
| Standard | Opens directly |
| Sensitive | Requires authorisation confirmation |
| High Risk | Requires authorisation confirmation; never auto-opens an App Window |

---

## 15. Customising and Extending

### 15.1 Add a tool to Transport, CCTV or Locations

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

> When you add a site, please also add it to the [Acknowledgements](#20-acknowledgements) and check that its terms allow being linked and opened this way.

### 15.2 Add a news source

Add a line to `NEWS_RAW`:

```
Region|Country|Agency name|Type|domain.tld
```

- **Region:** `International`, `Africa`, `Asia & Middle East`, `Europe`, `Americas` or `Oceania`
- **Type:** `A` wire/state agency, `P` broadcaster/newspaper, `O` organisation, `G` global wire
- **Domain:** without `https://`; separate several with commas
- Append `|R` to flag a source as often blocked or restricted

### 15.3 Mark a site as non-embeddable

Add its domain to `BLOCKED`. If it embeds fine, add it to `TRUSTED`.

### 15.4 Give a card a real destination

Add the card's title and URL to `REG`.

### 15.5 Add a location summary category

Add an entry to `CATS` with a label, icon, group and one or more Overpass filters. The counting query is generated from this list automatically.

### 15.6 Change the look

Edit the CSS variables in `:root` (backgrounds, accent colours, flag colours, risk colours, sidebar width). Density presets live in `body.density-compact` and `body.density-large`.

---

## 16. Known Limitations

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
- **Third-party terms are not tracked.** The workstation cannot tell you whether a site's terms have changed. You must check them yourself.

---

## 17. Troubleshooting and FAQ

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

**The workstation is free. Can I use the linked sites for free, commercially or in bulk?**
Not necessarily. The workstation's licence does not transfer to the sites it links to. Each site decides its own rules, so read its terms first (see [Section 13](#13-third-party-sites-terms-and-your-responsibilities)).

**Is this project affiliated with the sites it lists?**
No. It only links to them. All names and marks belong to their owners.

---

## 18. Contributing

Contributions are very welcome, from fixing a dead link to building a new module.

1. **Fork** the repository and create a branch (`feature/short-description`).
2. Make focused changes. Keep it a **single self-contained HTML file** unless discussed first.
3. **Test** in at least two browsers, including: opening cards, the blocked-site flow, adding evidence, generating a report and the Location Summary.
4. Keep the safety model intact: do not add features that bypass website protections, scrape, proxy, or auto-ingest leaked data.
5. When adding a resource, **credit it** in the Acknowledgements and confirm that linking to it is consistent with its terms.
6. Open a **pull request** describing the change and why.

**Good first contributions**

- Verify and fix links (especially the news directory and dark web entries)
- Add new, genuinely useful public OSINT resources
- Case switcher, "new case" and case export/import (JSON)
- Persist the Intelligence & Findings notes
- Encrypted local storage option
- Translations and accessibility improvements

---

## 19. Attribution and Credit Policy

This project is open source, and **recognising the original creator is a condition of using, modifying and redistributing it.**

If you use, fork, modify, improve, rebrand or redistribute OSINT Workstation (in whole or in part, including as part of a larger tool or training material), you **must**:

1. **Keep the original copyright and licence notice** in the source file and in the repository.
2. **Credit the original creator by name** in your README and in the application's About/footer/header comment, using wording such as:

   > Based on **OSINT Workstation** by **Lindunda Kalaluka** — https://github.com/kalalukalindunda/OSINT-Workstation

3. **Link back to the original repository.**
4. **State clearly that your version is modified** and describe what you changed. Do not present your version as the original.
5. **Keep this attribution section** (or an equivalent) in any derivative documentation.
6. **Keep the third-party acknowledgements** ([Section 20](#20-acknowledgements)) and the third-party terms notice ([Section 13](#13-third-party-sites-terms-and-your-responsibilities)) in any derivative. The credit owed to the sites and communities behind the links travels with the project.
7. Add your own name as an additional contributor for your improvements. Adding credit for yourself never replaces credit to the original creator.

**Suggested header comment for the HTML file:**

```html
<!--
  OSINT Workstation
  Original creator: Lindunda Kalaluka (https://github.com/kalalukalindunda)
  Original repository: https://github.com/kalalukalindunda/OSINT-Workstation
  Licence: MIT (see LICENSE). Modified versions must retain this notice
  and credit the original creator.
  Note: The MIT licence covers this project's own code only. All linked sites,
  services, data and marks belong to their owners and are subject to their own terms.
-->
```

Please do not remove the creator's credit to make a version look original. Respecting credit keeps the open-source community healthy and encourages people to keep sharing.

### Contributors

| Name | Role | Contribution |
|---|---|---|
| [Lindunda Kalaluka](https://github.com/kalalukalindunda) | Original creator | Concept, design, curation and initial implementation |
| *You?* | Contributor | Open a pull request and add yourself here |

---

## 20. Acknowledgements

**OSINT Workstation brings selected OSINT sites together in a single workstation so that users have a solid starting point. It does not replace, own or improve on the work of the people behind those sites.** Every tool below was built, funded, hosted and maintained by others, often volunteers, and the workstation only exists because of them. Their efforts must not go unnoticed.

**A reminder:** free access to OSINT Workstation does not mean the same rights apply to the sites listed here. Please follow each site's own guidelines, terms and requirements ([Section 13](#13-third-party-sites-terms-and-your-responsibilities)). Names and marks belong to their respective owners. Listing a site is not an endorsement, and no affiliation is implied.

Heartfelt thanks to everyone who builds, maintains, curates and shares tools and data openly.

### 20.1 Open-data and open-source projects used directly

| Project | How the workstation uses it |
|---|---|
| [OpenStreetMap](https://www.openstreetmap.org/) and its volunteer mappers | Foundation of the Location Summary and several map tools. Data © OpenStreetMap contributors, available under the [ODbL](https://www.openstreetmap.org/copyright) |
| [Overpass API](https://overpass-api.de/) and community mirrors (`overpass.kumi.systems`, `overpass.private.coffee`) | Makes OpenStreetMap queryable for feature counts |
| [Nominatim](https://nominatim.org/) | Geocoding place names |
| [Font Awesome](https://fontawesome.com/) (Free) via cdnjs / Cloudflare | Icon set |

### 20.2 General OSINT and global query sources

| Site | Used for |
|---|---|
| [Google](https://www.google.com/) (Advanced Search) | Search and advanced queries |
| [Bing](https://www.bing.com/) | Search launcher |
| [DuckDuckGo](https://duckduckgo.com/) | Search launcher |
| [Yandex](https://yandex.com/) | Search launcher and reverse search |
| [Internet Archive / Wayback Machine](https://archive.org/) | Preserving and retrieving past versions of web pages |
| [Wikipedia](https://www.wikipedia.org/) and the Wikimedia community | Reference lookups |
| [Shodan](https://www.shodan.io/) | IP and device information launcher |
| [ARIN](https://www.arin.net/) / RDAP | IP address registration lookups |
| RDAP domain services | Domain registration lookups |
| [VirusTotal](https://www.virustotal.com/) | Domain and file reputation launcher |

### 20.3 Dark & Deep Web resources

Listed for research navigation and awareness only. No endorsement of any site's content is implied.

| Site | Category |
|---|---|
| [Ahmia](https://ahmia.fi/) | Search engine |
| Tor66 | Search engine |
| Torch | Search engine |
| Kilos | Search engine |
| Google.onion | Search engine |
| Phobos | Search engine |
| TORMAX | Search engine |
| GDARK | Search engine |
| The Hidden Wiki | Directory |
| OnionLinks | Directory |
| Onion.Live | Directory |
| tor.taxi | Directory |
| [dark.fail](https://dark.fail/) | Directory |
| BreachForums | Breach and leak awareness |
| [Ransomware.live](https://www.ransomware.live/) | Ransomware monitoring |
| [RansomLook](https://www.ransomlook.io/) | Ransomware monitoring |
| [OnionShare](https://onionshare.org/) | File sharing and chat |
| [The Tor Project](https://www.torproject.org/) | Tor Browser and the Tor network |

### 20.4 Transport & Maritime

| Site | Category |
|---|---|
| [FlightRadar24](https://www.flightradar24.com/) | Aviation |
| [FlightAware](https://www.flightaware.com/) | Aviation |
| [PlaneFinder](https://planefinder.net/) | Aviation |
| [ADS-B Exchange](https://www.adsbexchange.com/) and its volunteer feeders | Aviation |
| [OpenSky Network](https://opensky-network.org/) and its volunteer feeders | Aviation |
| [Aviationstack](https://aviationstack.com/) | Aviation |
| [FAA](https://www.faa.gov/) resources | Aviation |
| [EUROCONTROL](https://www.eurocontrol.int/) | Aviation |
| [MarineTraffic](https://www.marinetraffic.com/) | Maritime |
| [VesselFinder](https://www.vesselfinder.com/) | Maritime |
| [MyShipTracking](https://www.myshiptracking.com/) | Maritime |
| [Global Fishing Watch](https://globalfishingwatch.org/) | Maritime transparency |
| [FleetMon](https://www.fleetmon.com/) | Maritime |
| [Open Railway Map](https://www.openrailwaymap.org/) | Rail |
| [TomTom Traffic Index](https://www.tomtom.com/traffic-index/) | Road traffic |
| [Waze](https://www.waze.com/) Live Map | Road traffic |

### 20.5 CCTV & Public Webcams

| Site | Category |
|---|---|
| [EarthCam](https://www.earthcam.com/) | Public webcams |
| [Skyline Webcams](https://www.skylinewebcams.com/) | Public webcams |
| World Cam | Public webcams |
| [WebcamTaxi](https://www.webcamtaxi.com/) | Public webcams |
| [Windy](https://www.windy.com/) webcams | Public webcam map |

### 20.6 Locations & Maps

| Site | Category |
|---|---|
| [Google Earth](https://earth.google.com/) | Imagery |
| [Google Maps](https://www.google.com/maps) | Maps |
| [Mapillary](https://www.mapillary.com/) | Crowd-sourced street-level imagery |
| [Yandex Maps](https://yandex.com/maps) | Maps |
| [SunCalc](https://www.suncalc.org/) | Sun position analysis |
| [ShadowMap](https://shadowmap.org/) | Shadow analysis |
| [ShadeMap](https://shademap.app/) | Shadow analysis |
| [OpenStreetMap](https://www.openstreetmap.org/) | Open map data |
| [Open Infrastructure Map](https://openinframap.org/) | Power, telecoms and infrastructure mapping |

### 20.7 News & Open Sources directory

The News directory links to national news agencies, public broadcasters and international organisations. All articles, photographs and video on those sites belong to the respective agencies and publishers. The agencies and bodies below are acknowledged; the authoritative, current list is the `NEWS_RAW` data in the source file.

**International organisations and global wires**

United Nations (UN News), European Union (Press Corner), African Union, ASEAN, NATO, World Health Organization, International Monetary Fund, World Bank, World Trade Organization, OECD, Council of Europe, OSCE, Organization of American States, League of Arab States, Organisation of Islamic Cooperation, The Commonwealth, SADC, ECOWAS, East African Community, Pacific Islands Forum, ICRC, Reuters, Associated Press, Agence France-Presse (AFP).

**Africa**

APS (Algeria), ANGOP (Angola), ABP (Benin), BOPA (Botswana), AIB (Burkina Faso), ABP (Burundi), Inforpress (Cabo Verde), CRTV (Cameroon), ADIAC (Congo), ACP (DR Congo), AIP (Côte d'Ivoire), ADI (Djibouti), MENA (Egypt), Shabait (Eritrea), ENA (Ethiopia), AGP (Gabon), GRTS (Gambia), GNA (Ghana), KNA (Kenya), LeNA (Lesotho), LINA (Liberia), LANA (Libya), MANA (Malawi), AMAP (Mali), AMI (Mauritania), GIS (Mauritius), MAP (Morocco), AIM (Mozambique), NAMPA (Namibia), ANP (Niger), NAN (Nigeria), The New Times (Rwanda), APS (Senegal), Seychelles Nation, SONNA (Somalia), SAnews (South Africa), SUNA (Sudan), Daily News (Tanzania), ATOP (Togo), TAP (Tunisia), UBC (Uganda), ZANIS (Zambia), ZIANA (Zimbabwe), APA News (pan-African).

**Asia and Middle East**

Bakhtar (Afghanistan), Armenpress (Armenia), AZERTAC (Azerbaijan), BNA (Bahrain), BSS (Bangladesh), Kuensel (Bhutan), Borneo Bulletin (Brunei), AKP (Cambodia), Xinhua (China), CNA (Cyprus), Interpressnews (Georgia), PTI and ANI (India), ANTARA (Indonesia), IRNA (Iran), INA (Iraq), Times of Israel, Kyodo and Jiji (Japan), Petra (Jordan), Kazinform (Kazakhstan), KUNA (Kuwait), Kabar (Kyrgyzstan), KPL (Laos), NNA (Lebanon), Bernama (Malaysia), PSM News (Maldives), Montsame (Mongolia), GNLM (Myanmar), RSS (Nepal), KCNA (North Korea), ONA (Oman), APP (Pakistan), WAFA (Palestine), PNA (Philippines), QNA (Qatar), SPA (Saudi Arabia), The Straits Times (Singapore), Yonhap (South Korea), Daily News (Sri Lanka), SANA (Syria), Khovar (Tajikistan), Thai News Agency (Thailand), Tatoli (Timor-Leste), Anadolu Agency (Turkey), WAM (UAE), UzA (Uzbekistan), VNA (Vietnam), SABA (Yemen).

**Europe**

ATA (Albania), APA (Austria), BelTA (Belarus), Belga (Belgium), FENA (Bosnia and Herzegovina), BTA (Bulgaria), HINA (Croatia), ČTK (Czechia), Ritzau (Denmark), BNS (Estonia and Lithuania), STT (Finland), AFP (France), dpa (Germany), ANA-MPA (Greece), MTI (Hungary), RÚV (Iceland), RTÉ (Ireland), ANSA (Italy), Kosova Press (Kosovo), LETA (Latvia), ELTA (Lithuania), Luxemburger Wort (Luxembourg), Times of Malta, Moldpres (Moldova), MINA (Montenegro), ANP (Netherlands), MIA (North Macedonia), NTB (Norway), PAP (Poland), Lusa (Portugal), Agerpres (Romania), TASS (Russia), Tanjug (Serbia), TASR (Slovakia), STA (Slovenia), EFE (Spain), TT (Sweden), Keystone-SDA (Switzerland), Ukrinform (Ukraine), PA Media (United Kingdom), Vatican News.

**Americas and Oceania**

Noticias Argentinas (Argentina), ABI (Bolivia), Agência Brasil (Brazil), The Canadian Press (Canada), El Tiempo (Colombia), Prensa Latina (Cuba), Andes (Ecuador), AGN (Guatemala), JIS (Jamaica), IP (Paraguay), Andina (Peru), Associated Press (United States), AVN (Venezuela), AAP (Australia), RNZ (New Zealand), FBC News (Fiji), Post-Courier (Papua New Guinea).

### 20.8 The wider OSINT community

Thank you to the researchers, journalists, analysts, educators and hobbyists who publish their methods, curate resource lists and teach others, including every open-source project and curated link collection whose ideas shaped this workstation. This tool exists to make that shared knowledge easier to reach, not to take credit for it.

### 20.9 Third-party services, terms and trademarks

All services linked from this workstation are independent third parties. Their names and marks belong to their owners. Listing a service does not imply endorsement or affiliation, and **each service's own terms of use, licences and guidelines apply to you** whenever you use it.

*If you maintain a project listed here and would like the wording changed, credit improved, a link updated or the listing removed, please [open an issue](https://github.com/kalalukalindunda/OSINT-Workstation/issues).*

---

## 21. License

The **OSINT Workstation source code and documentation** are released under the **MIT License**, with the attribution expectations described in [Section 19](#19-attribution-and-credit-policy).

> **The MIT licence applies only to this project's own code and documentation.** It does not grant any rights over third-party websites, services, data, APIs, content, names or trademarks that are linked from the workstation. Those remain governed by their owners' terms (see [Section 13](#13-third-party-sites-terms-and-your-responsibilities)).

```
MIT License

Copyright (c) 2026 Lindunda Kalaluka

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

## 22. Disclaimer

- OSINT Workstation is provided **"as is"**, without warranty of any kind.
- It is a **link launcher and note-keeping aid** that brings selected third-party resources together as a starting point. It does not verify information, guarantee that any link is safe, current or accurate, or provide legal advice.
- It is **not affiliated with or endorsed by** any listed site or organisation, and it claims no ownership of their work.
- **Your access to this free tool gives you no rights on third-party sites.** You alone are responsible for reading and complying with each site's terms, licences, usage limits and the applicable law.
- Third-party sites, including High Risk resources, may contain illegal, harmful or misleading material. Open them only if you are authorised, prepared and acting lawfully.
- The creator and contributors accept **no liability** for misuse, for breaches of third-party terms by users, for decisions made from information gathered with the tool, or for the content of any external website.
- Location counts and directory entries may be incomplete or out of date. **Always corroborate** before relying on them.

---

<p align="center">
  <b>OSINT Workstation</b> — created by <a href="https://github.com/kalalukalindunda">Lindunda Kalaluka</a><br>
  Built for the OSINT community, with thanks to every person and project whose work it brings together.
</p>
