[README.md](https://github.com/user-attachments/files/32796696/README.md)
# 🏀 EuroLeague Final Standings Simulator

An interactive web tool for exploring how the **2025–26 EuroLeague regular season** could end.
Built after Round 37, it covers the final round (Round 38) plus one postponed fixture: 10 games and 1,024 possible outcome combinations.

**▶ Live demo:** https://euroleaguesimulator-firatyondem.netlify.app/

## Features
- **Pick the winners** of each remaining game and see the projected final standings update instantly
- **EuroLeague tiebreaker logic** for two-team and multi-team ties: head-to-head wins, then head-to-head point difference (regulation scores for overtime games), with further fallbacks
- **Play-In simulator** for places 7–10 (7 vs 8, 9 vs 10, and the qualification game)
- **Playoff quarterfinal bracket** that fills in from the standings and Play-In results
- **Transparency notices** that explain how each tie was resolved and flag ties the available data cannot decide
- Responsive layout that works on mobile

Used by basketball media and by an assistant coach of Panathinaikos BC in his own analysis.

## How it works
- `BASE_WINS` holds each team's record after Round 37.
- `H2H` stores the head-to-head results for every pair of teams that could still finish level.
- When results are picked, `calcStandings()` adds the wins, groups teams with equal records, and resolves each group with `resolve2()` (two teams) or `resolveMulti()` (three or more).

## Tech
A single HTML file with plain HTML, CSS and JavaScript. No frameworks, no build step.
Developed with AI-assisted tooling (Claude Code).

## Run locally
Download `index.html` and open it in any browser.

## Limitations
- The overall season point differential (last tiebreaker fallback) was not entered, so ties that reach that criterion are flagged instead of resolved.
- Head-to-head point difference cannot be calculated for games that are only simulated (no score), so those cases are also flagged.

## Author
**Fırat Yöndem** · Informatics student at TUM · [LinkedIn](https://www.linkedin.com/in/firat-yondem-ab0141286)
