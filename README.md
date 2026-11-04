Addon WOW
# QuestFlow Forever

> An intelligent quest-routing addon project for **World of Warcraft: Forever**, designed to reduce unnecessary travel and make leveling more efficient.

**Status:** Early development / technical feasibility research.

## Overview

QuestFlow Forever is a free, community-oriented addon project that aims to recommend the next useful quest objective based on the player's current progress, location, and available quest information.

Rather than replacing existing quest databases, the project is designed to **complement Questie** and other compatible data sources with a route-optimization layer.

## Planned features

- **Dynamic quest routing:** group nearby objectives and minimize backtracking.
- **Adaptive recommendations:** reconsider the route when quests are accepted, completed, or discovered.
- **Forever-specific quest support:** investigate custom quests and objectives not yet included in existing addon databases.
- **Multiple data sources:** evaluate client-exposed quest information, QuestieDB, and an authorized offline import of ForeverDB data.
- **Clear navigation:** compact, low-clutter guidance focused on the next action.
- **Character-aware planning:** account for level, class, available travel options, and selected profession or dungeon goals where data is available.
- **Performance-first design:** lightweight processing and event-driven updates whenever possible.

These are development goals, **not a claim that the features are already implemented or supported by the game client**.

## ForeverDB API integration

We would like to request developer access to the **ForeverDB API** to investigate whether its quest, NPC, objective, and related metadata can help build a more complete **offline quest-routing dataset** for WoW Forever.

Our intended approach:

1. Retrieve only data authorized by ForeverDB's API and usage terms.
2. Validate available fields and document missing or uncertain information.
3. Generate a local addon-compatible dataset outside of the game client, subject to the API's redistribution rules.
4. Combine that dataset with information exposed to addons in game, without assuming that the game API provides the entire server-side quest database.
5. Clearly attribute ForeverDB wherever its data is used, as required by its terms.

**No API keys or other secrets will be embedded in the addon or committed to this repository.** Any API-dependent build step would run separately from the in-game addon.

## Proposed architecture

```text
QuestieDB / compatible local datasets ----+
                                          |
WoW Forever client quest information -----+--> QuestFlow data layer
                                          |          |
Authorized ForeverDB offline export ------+          v
                                                Route planner
                                                     |
                                                     v
                                             Minimal in-game UI
```

All integrations are subject to compatibility testing, source licenses, API permissions, and the actual capabilities of the WoW Forever addon environment.

## Development roadmap

- [ ] Audit the WoW Forever addon API and quest data capabilities.
- [ ] Verify QuestieDB compatibility and data access.
- [ ] Evaluate ForeverDB API fields, permissions, and permitted uses.
- [ ] Implement basic quest-state detection and a small navigation prototype.
- [ ] Create a route optimizer accounting for travel and quest dependencies.
- [ ] Add fallback behavior for incomplete or unknown quest data.
- [ ] Test on actual WoW Forever characters and refine recommendations.
- [ ] Publish installation instructions and supported-client details after verification.

## Installation

**Not available yet.** The project is currently in its planning and feasibility stage; no working addon release is included here.

## Fair use and attribution

QuestFlow Forever is an independent fan project, not affiliated with or endorsed by the operators of WoW Forever, Blizzard Entertainment, Questie, or ForeverDB.

Third-party APIs, code, and datasets will only be used as allowed by their respective licenses and terms. Applicable credits will be added as integrations are implemented.

## Contact and contributions

Feedback, ideas, and technical contributions can be shared through the repository's GitHub Issues once enabled.

---

**Project goal:** Spend less time traveling between objectives and more time making meaningful leveling progress.
