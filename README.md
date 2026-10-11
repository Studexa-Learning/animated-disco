# UALN — Usher American Live News

A local-first election night *simulation*, not a real news or forecasting service.

## Start

Place all five root-level files together (no folders): `index.html`, `control.html`, `app.js`, `style.css`, `README.md`. Open `index.html` for broadcast and `control.html` for the control room. For reliable synchronisation use a simple local HTTP server (e.g. `python -m http.server 8000`), visit `http://localhost:8000/index.html` and `http://localhost:8000/control.html` in the **same browser**. File URLs often have restricted storage behavior. Alternatively upload the five files to the root of a GitHub Pages repo, enable Pages from main branch / root, and open both URLs.

## Features

- 2026 midterm election studio with House/Senate composition tally and threshold displays.
- Fictional *2028 JD Vance v Kamala Harris* presidential matchup; not actual declared nominees.
- 51 clickable state/DC tiles, state EV allocations with 2024 apportionment, partisan controls and 2016/2020/2024 historical winner presets.
- 12 broadcast slide scenes; comparison, swing/balance visualisation, battleground, road to 270, legislative results, explainers, breaking, countdown, archive.
- Remote cueing for three full-screen control projection graphics, each with Democratic/Republican (and congressional too-close) variants.
- Red/blue animated star wipe and broadcast-style screen graphic.
- Control room with 51 state editors, 32 presidential year selectors, 12 slide cues, ~30 graphic/overlay switches and labels, projection calls and result counters, back-up tools; over 100 on-screen controls.
- Browser-origin sync between tabs through `BroadcastChannel` and localStorage. No credentials, SQL or dependencies.
- Export/import show JSON and import historical map winner data.

## Historical accuracy & limitations

The historical comparison dropdown lists presidential elections 1900–2024. Only 2016, 2020 and 2024 state-winner maps are included. Earlier years require imported data and explicitly show a missing-data notice, not fabricated results. This application does not preload 1900–2024 midterm seat-by-seat maps. Current interactive state EV values use the 2024 and 2028 apportionment (total 538) even for old comparative maps; historic elections had different EV allocations and not all modern states existed. Maine/Nebraska district-level EV splitting isn't modeled (whole-state demo assignment). Some elections featured meaningful third-party allocations/faithless electors that aren't captured by the R/D winner map.

For validated historical data see [The American Vote](https://theamericanvote.com/data), [The American Presidency Project](https://www.presidency.ucsb.edu/statistics/elections/1900), and [US Election Map](https://github.com/jacksonjude/USA-Election-Map). Import a map as `{"1900":{"CA":"R","NY":"R",...}}` into Control Room > Historical data.

House majority = 218 out of 435 voting seats; presidential Electoral College majority = 270 out of 538; Senate 51 seats generally controls, but 50–50 ties depend on vice-presidential tie-breaking. The midterms decide all House seats and normally a third of Senate seats, not the presidency.

**Storage note:** GitHub Pages is static. Local sync works within the same origin/browser, not across separate devices. For shared remote producers you'd need a backend or realtime database.
