# EchoKey (Magic AI Keyboard) — V1 Agent Instructions

## Goal (V1)
Build an Android keyboard that helps users understand copied incoming messages and generate vibe-appropriate replies, with clean UX and zero typing lag.

## V1 Locked UX Requirements (DO NOT CHANGE)
### Core flows
1) **Same-language “Boost” flow (no clipboard needed)**
- Smart bar shows: `✨ Need help replying?  [🧠 Boost]`
- On Boost: show 3 reply style chips.

2) **Clipboard flow (game changer)**
- When user copies text, keyboard detects clipboard change.
- If settings “Auto Translate After Copy” is ON and filter passes, show:
  - `📋 <detected language> detected`
  - `🌍 View in: EN | తెలుగు | TE (Roman)` (manual user choice)
  - Reply chips (max 3)

3) **Before-send clarity**
- Keyboard never auto-modifies what user typed.
- Show small indicator: `✍️ <reply language> → <detected language>`
- Translation (when implemented) happens only at SEND time to avoid lag.

### Reply styles (V1 max 3)
- 💙 Comfort
- 😜 Tease
- 💼 Professional
(Keep max 3 visible to avoid clutter; future styles can be added later.)

### Settings (V1)
- Toggle: **Auto Translate After Copy** (default ON)
- Manual mode when OFF: show buttons `[Translate] [🧠 Mood/Boost]` only.
- Language mode is user-controlled (no auto switching):
  - EN / తెలుగు / TE (Roman)

### Clipboard smart filter (V1)
Ignore clipboard events if text is:
- URL
- numeric-only / OTP-like
- too short (e.g., < 4 words)

## Engineering constraints (V1)
- No network/AI calls on every keystroke.
- Optimize for responsiveness; keyboard must feel like Gboard.
- Build UI states first; backend/AI integration later.

## Output discipline for Codex changes
- Small, incremental commits.
- Prefer adding docs/specs before major implementation.
- Do not introduce extra features beyond V1 requirements unless requested.
