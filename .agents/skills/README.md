# Exemple de skill-uri · Cursul 3 (AI-2)

Cele șase skill-uri de la laboratorul 3, scrise pentru repo-ul cu pagina de login de la laboratorul 2. Sunt exemple: la laborator, skill-urile le face agentul tău din prompturile tale, iar ale tale vor arăta altfel.

| Skill | Ce face | Pornește |
|---|---|---|
| `write-spec` | specificația după `docs/specs/TEMPLATE.md`, cu întrebările întâi | automat |
| `plan-feature` | planul înainte de cod; fără cod până îl aprobi | automat |
| `browser-tests` | testele Playwright, câte unul pe linie din specificație | automat |
| `unit-tests` | teste unitare pentru funcțiile din `js/`, cu `node --test` | automat |
| `deploy-pages` | publică pe GitHub Pages și verifică pagina | doar la `/deploy-pages` |
| `ai-log-draft` | ciorna intrării din `docs/ai-log.md`, în chat | automat |

## Cum le folosești

- Le compari cu ale tale: descrierea (ce face, „Use when …”, ce se strică fără el), primul rând, lista de bifat.
- Dacă iei unul, îl pui în repo la `.agents/skills/<nume>/SKILL.md`, la exact un nivel; numele folderului e același cu `name`.
- În `AGENTS.md`, la „Where to look”, trebuie să existe rândul pentru Claude Code: `- .agents/skills/: procedures, one folder each; read the description at the top of each SKILL.md and follow the one that matches the task`
- Îl testezi într-o sesiune nouă, fără să-l pomenești: pornește când trebuie și nu pornește când nu trebuie?
- Un skill luat de aici nu e scris de tine: în `docs/ai-log.md` scrii de unde l-ai luat și ce ai schimbat.

`deploy-pages` cere GitHub Pages pornit în repo: Settings › Pages › Deploy from a branch › `main`, `/ (root)`.
