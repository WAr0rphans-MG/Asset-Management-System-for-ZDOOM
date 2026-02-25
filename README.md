# Asset-Management-System-for-ZDOOM
Real-time asset customization system for GZDoom. Swap health/armor pickup sprites instantly via in-game menus with preset and custom modes. Showcases architectural evolution from ACS/DECORATE with Legacy files to ZScript incorporation across iterations from 2022-2023, then resumed and refined in late 2025-2026.

## Note on Assets

This repository contains only the code and logic (ACS, DECORATE, ZScript, menu definitions). 
Sprite assets are not included but will be available when a playable mod release is published.

To use this code in your own projects, you'll need to provide your own sprites or substitute 
the sprite names in the DECORATE files.


# Asset Management System for ZDOOM

Real-time asset customization system for GZDoom. Swap health/armor pickup sprites instantly via in-game menus with preset and custom modes. Showcases architectural evolution from ACS/DECORATE to ZScript across iterations from 2022-2023, then resumed and refined in late 2025-2026.

---

## The Journey

**v0 (September 2022)** was functionally complete - everything worked perfectly. What followed wasn't building new features, but **chasing elegance:**

- **v1-v3a (October 2022):** Replacing working buttons with cleaner dropdown menus
- **v4-v5 (2025-2026):** Refactoring working code into scalable architecture

**This repository documents the iterative process of making something that works *look good* and *be maintainable* - a real-world learning journey through code quality, UX design, and architectural thinking.**

The system worked on day one. Everything after was polish.

---

## Project Origins

**Mid-August 2022:** This project began as an effort to merge two GZDoom mods:
- **RVDoomVox** (voxel model support)
- **Delashin's Smooth Doom Remake** (enhanced gameplay and visuals)

The initial goal was customization: replace included DOOM 64 sprites with higher-quality versions from DOOM 64 Community Edition, add missing weapons (fists, plasma rifle, BFG), and ensure voxel compatibility.

**The Spark:** While working on sprite replacements, I discovered real-time routing patterns in DSD Remake's weapon states - weapons that checked CVars every frame and switched attachments/modes instantly. I realized this pattern could be adapted for health pickups.

**What started as "I want to merge two mods"** became a deep dive into:
- ACS scripting (from zero programming knowledge)
- DECORATE actor logic and state management
- Voxel creation (majority self-made)
- Menu system integration
- HUD customization
- Modern ZScript architecture

**The medical symbol customization system emerged as a standalone feature** - a way to apply these discovered patterns to create something new.

---

## What This Repository Contains

**Code-only documentation** of the preset system's evolution:
- ACS scripting progression (getter functions → preset logic → unified architecture)
- DECORATE routing patterns (stop-based → real-time → refactored)
- ZScript integration (menu preview, armor tracking, HUD replacement)
- Supporting files (MENUDEF, CVARINFO, LOADACS, SBARINFO)

**Sprites, voxels, and other assets are not included** - this focuses purely on the code and logic. Full mod release with assets will come later.

**The larger mod work** (weapon ports, voxel integration, complete sprite replacements) is out of scope for this repository. This extracts and documents the medical symbol routing system as an educational reference.

---

## Development Timeline

**August 22, 2022:** Pre-v0 file (mod merging work, no medical symbol system yet)

**August 22 - September 18, 2022:** v0 development (~4 weeks)
- Complete working system with button-based presets
- Real-time routing discovered and implemented
- All DOOM 64 CE sprites integrated
- Custom voxels created (majority self-made)
- ArmorID tracking system
- SBARINFO HUD integration

**October 17-20, 2022:** v1 attempts (UI redesign)
- Goal: Replace buttons with dropdowns for visual consistency
- Multiple failed attempts at preset/custom mode logic
- v1-successful achieved separation but lacked overlap

**October 24, 2022:** Intense experimentation day
- Parallel attempts: v2a, v3, v3b, v3b1, multiple v3a iterations
- Trying everything to crack the preset/custom overlap problem

**October 25-26, 2022:** Continued v2 refinements

**October 27, 2022:** v3-alpha BREAKTHROUGH ✨
- Router + worker pattern finally achieves overlap
- Dropdown presets work like v0 buttons (override in both modes)
- 10 days of iteration (Oct 17-27) complete

**October 2022 - October 2023:** Continued work on larger mod
- Medical symbol system functionally complete
- Focus shifted to broader integration (weapons, voxels, etc.)

**December 30, 2025:** Return to project after 3 years
- v4: Consolidated worker logic (minutes before v5)
- v5: Unified worker architecture with Microsoft Copilot assistance
- Both completed in under 1 hour

**January 28, 2026:** v5 refinements
- DECORATE architectural refactors (factory + variants pattern)
- ZScript integration (menu preview, armor handler, HUD)

**February 2026:** Documentation and GitHub preparation
- Breaking 15-year pattern of unfinished projects
- Code commenting and README creation with Claude AI assistance

---

## Active Development Time

**Total: ~6 weeks** across two intensive periods:
- **4 weeks:** August-September 2022 (v0 foundation)
- **10 days:** October 17-27, 2022 (v1 → v3-alpha iteration)
- **~3 hours:** December 30, 2025 (v4-v5 refactoring)
- **1 day:** January 28, 2026 (v5 DECORATE + ZScript)

The 3-year gap (October 2022 - December 2025) was dormancy - no code work on this system.

---

## What I Learned

**From zero programming knowledge to working systems:**

**2022 (Self-Taught):**
- Reverse-engineering existing code (decompiled ACS from DSD Remake)
- Pattern-matching across mods (weapon routing → pickup routing)
- Trial and error iteration (v1 → v3a in 10 days)
- Flow control fundamentals (nested conditions, loops, state management)
- DECORATE actor logic and real-time routing
- Voxel creation and sprite editing

**2025-2026 (AI-Assisted):**
- Modern development workflows (Copilot collaboration)
- Mental debugging (analyzing code without execution)
- ZScript architecture (event handlers, HUD rendering)
- Architectural refactoring (scalability, separation of concerns)
- Data-driven vs hardcoded approaches

**The consistent thread:** Learning what's needed, finding resources (code, AI, documentation), iterating until it works.

---

## Repository Structure
├── acs/              # ACS script evolution (v0 → v5)
├── decorate/         # DECORATE routing patterns
├── zscript/          # ZScript integration (v5)
├── misc/             # Supporting files (MENUDEF, CVARINFO, ArmorID, etc.)
└── docs/             # Timeline, architecture, learning journey
**Each component has detailed README** explaining its evolution, key learnings, and development context.

---

## Technical Highlights

**Real-Time Routing Pattern:**
- Discovered from DSD Remake weapon states
- Adapted from weapons to pickups
- Continuous checking + looping for instant updates
- No level reload required

**Router + Worker Architecture (v3-alpha):**
- Separation of concerns (routing vs logic)
- Each worker handles one preset
- Breakthrough after 10 days of iteration

**Unified Worker with State Memory (v5):**
- Single script tracks preset changes over time
- Fully scalable (works for unlimited presets)
- Data-driven architecture

**ZScript Integration (v5):**
- Real-time menu preview (changes apply while menu open)
- Event-driven armor tracking (replaces looping ACS)
- Modern HUD rendering (replaces SBARINFO)

---

## Documentation Philosophy

**This repository shows the messy reality of learning:**

**Preserved:**
- ✅ Failed attempts (v1-v3 broken logic)
- ✅ Dead ends (v3b, v3b1 variants)
- ✅ Iteration process (5+ attempts on Oct 24 alone)
- ✅ AI collaboration (transparent about Copilot/Gemini assistance)
- ✅ Honest commentary (what worked, what didn't, what's still unclear)

**Not sanitized:**
- ❌ No "here's the perfect solution" narrative
- ❌ No hiding the struggle
- ❌ No pretending I knew what I was doing from the start

**The goal:** Help others learning GZDoom modding see that iteration, failure, and confusion are normal parts of the process.

---

## AI Assistance Transparency

**Code:** Written by me (2022-2026)

**v5 ACS/ZScript:** Architectural scaffolding generated by Microsoft Copilot and Google Gemini (December 2025 - January 2026), debugged and refined through iteration

**Documentation:** Created February 2025 in collaboration with Claude (Anthropic)
- I provided code, context, and timeline
- Claude structured documentation, wrote explanatory comments, organized the narrative
- Iterative refinement to ensure accuracy

**This collaborative approach allowed me to:**
- Document years of work in a condensed timeframe (meeting Feb 28 deadline)
- Gain new insights into my own learning process
- Structure the repository for educational value
- Be transparent about modern development workflows

---

## What Makes This Valuable

**Not a tutorial** - doesn't teach GZDoom step-by-step

**Not a showcase** - shows failures alongside successes

**Not just a portfolio** - documents the learning process

**It's all three:**
- **Tutorial value:** Others can learn from my mistakes and iterations
- **Showcase value:** Demonstrates growth from zero to working systems
- **Portfolio value:** Shows ability to learn, iterate, debug, and finish

**The combination is rare** - most repositories show only the final polished result.

---

## Future Work

**Post-Feb 28 refinements:**
- Add detailed comments to all code files
- Document v2-v3 micro-iterations
- Expand docs/ with architecture deep-dives
- Add v5 optimization concepts (indexed getter, DECORATE overhead reduction)

**Potential explorations:**
- v6 concept (ZScript-based engine with data modules)
- Backport v6 patterns to ACS (if possible)
- Apply learned patterns to other GZDoom systems

---

## Credits & Acknowledgments

**Base Mods:**
- **Delashin's Smooth Doom Remake** - Real-time routing pattern learned from weapon states
- **RVDoomVox** - Symbol actor separation pattern adapted from voxel/sprite handling

**AI Assistance:**
- **Microsoft Copilot** - v5 ACS and ZScript generation (December 2025 - January 2026)
- **Google Gemini** - ZScript debugging and refinement (January 2026)
- **Claude (Anthropic)** - Documentation structuring and commentary (February 2025)

**Learning Resources:**
- ZDoom Wiki (limited but essential ACS documentation)
- Single YouTube ACS tutorial series (name forgotten, fundamentals)
- Decompiled scripts from existing mods (primary learning method)

---

## License

GPL-3.0

This matches GZDoom's license and ensures any derivative work remains open source, preserving the educational value for future modders.

---

## A Note on Finishing

**This breaks a 15-year pattern** of unfinished projects.

**Why it worked this time:**
- Clear deadline (February 28, 2026)
- Defined scope (document what exists, don't build new features)
- External accountability (Claude collaboration)
- Honest approach (show failures, not just successes)

**The code was done years ago. The documentation makes it real.**

If you're learning GZDoom modding (or any technical skill) and struggling:
- Your confusion is normal
- Failed attempts are progress
- Finishing is possible
- Documenting helps you understand what you built

**Ship it.** Then refine it.

---

## Contact & Contributions

**Issues and suggestions:** Open an issue on GitHub

**Learning from this:** Feel free to reference, adapt, or build upon these patterns

**Found a bug in my old code:** I'd love to know! These files represent my learning journey - spotting issues helps me learn further

---

*"Interest and purpose are the difference between 'I should learn this' (dies immediately) and 'I need to learn this to do X' (unstoppable)."*

*I wanted to replace a green cross. This is what happened.*