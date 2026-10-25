# Nusi — UI Design PRD

**Version:** 1.2 — multi-task morning setup correction  
**Status:** Design specification only. Nothing is built, deployed, or changed. Work begins only after the owner explicitly approves building.  
**Platform:** Android, phone-first, single user, free  
**Working app name:** Nusi (spelling remains to be confirmed by the owner)

## 1. Product and visual direction

Nusi is a private, personal daily-progress app for one user. Its job is to make the next meaningful action clear, help the owner track what actually happened, and keep Salah and Qur'an revision prominent without making the day feel crowded or judged.

### Visual direction

Use a **dark, frosted-glass dashboard** inspired by the supplied reference screen recording. The reference is inspiration for visual style only; do not copy its text, names, avatars, branding, desktop layout, or exact interface.

The design should feel calm, premium, minimal, readable, and slightly animated. It must feel distinct from Amanah: no reuse of Amanah's visual identity or layout decisions. Use one-column portrait layouts designed for one-handed Android use.

- Near-black charcoal background, approximately `#17181C`.
- Optional subdued wallpaper behind glass cards.
- Glass cards: white at approximately 6% opacity, around 24 px background blur, and a 1 px white border around 10% opacity.
- Card radius: 24 px. Buttons and chips: 16 px. Timer pill and toggles: fully rounded.
- Primary text: near-white. Secondary text: grey at approximately 60% opacity, subject to contrast checks.
- **Default accent: green.** Use the accent consistently for the primary action, selected options, ring progress, ticks, active tab, and meaningful active states. Supported accent choices: blue, purple, pink, orange, green, and grey.
- Rings use thick rounded strokes on dim tracks with a restrained glow. Glow must not reduce readability.
- Screen margin: approximately 16 px. Card gap: 12 px. Card interior padding: 16–20 px.
- Motion is gentle: ring values animate, cards fade or rise in slightly, and presses give soft tactile feedback. No flashing, bouncing celebration, confetti, or showy transitions.
- Keep typography highly legible, with clear title/body/label hierarchy. Use one readable sans-serif family throughout.

The approximate values above are starting tokens, not pixel-perfect laws. Tune them by eye while preserving the overall system.

## 2. Design principles and constraints

1. **Salah comes first.** It is the first content card on Today and remains visible on all three daily paths: Rest, Locked In, and Busy.
2. **Three-step setup, multiple tasks allowed.** Morning setup has three screens: path, primary work area, and task/subject selection. The first two screens use one-tap choices and advance automatically. The third screen supports selecting multiple tasks or subjects for the same day, then one clear “Build my day” action. Do not force the owner to choose only one task, and do not add extra profile questions or a separate confirmation screen.
3. **One clear next action.** Each screen has a clear primary action and no more than one competing visual focal point.
4. **Honest progress.** Show what was completed, partially completed, missed, or not scheduled. Never fabricate activity, streaks, focus time, or emotional evidence.
5. **Rest is quieter.** Reduce visual emphasis and hide optional productivity metrics on Rest days.
6. **Busy is essentials-only.** Show only Salah, Qur'an revision, and the approved love-strengthening message card, except for the global active-focus pill if a focus session is already running or paused.
7. **No social layer.** No feeds, public profiles, likes, comments, messaging, followers, or social comparison.
8. **No unapproved features.** Do not add gamification, new task categories, extra timer modes, streak awards, badges, or unrelated screens beyond this specification.
9. **Private and evidence-based.** The love-strengthening card may display only evidence or wording the owner has supplied or explicitly approved. It must not claim to know another person's thoughts or feelings.
10. **Design only for now.** This document does not authorize coding, database changes, notifications implementation, deployment, or modification of any existing app.

## 3. Global layout and navigation

### Phone layout

- Portrait Android layout, single column, vertically scrollable content where needed.
- Respect status-bar, navigation-bar, keyboard, and device safe areas.
- Use a consistent 16 px side margin and 12 px card gap.
- Avoid horizontal scrolling for core screens.
- No nested menus. Settings sections should be direct and shallow.
- Use large tappable options and controls suitable for one-handed use.

### Bottom navigation

A frosted-glass bottom bar contains exactly four tabs:

- **Today**
- **Progress**
- **Streak**
- **Settings**

Only the selected tab uses the active accent state. The bar remains visually quiet and does not cover the last content card; scrolling content must allow room for it.

### Header

The standard header shows:

- A simple greeting, such as “Good morning”.
- The current date below it.
- The selected path as a small pill where relevant.
- One right-side primary action.

**Header-action rule:** use the Focus shortcut when no timer is running; when a timer is already running or paused, the global Focus pill takes priority and the header must not duplicate it. Do not add an “add task” action unless task creation is separately approved.

### Floating Focus pill

When a focus session is running or paused, show a small pill at the top centre on every screen except the dedicated Focus screen, where the large countdown ring already serves that purpose. The pill includes a small ring/dot, “Focus”, and remaining time; paused state must be visibly distinguishable. Tapping it opens the Focus screen and restores the active session. It must not overlap the status bar, screen title, or primary controls.

### Stat chips

Under the header, use a compact row of glass chips such as:

- `Done today 3/8`
- `Focus today 58m`
- `Missed 0`

Values must be derived from actual saved activity. On narrow devices the row may wrap cleanly into two rows; do not shrink text to force one row. In Rest and Busy paths, omit stat chips if they would undermine the intentionally sparse layout.

## 4. Morning setup — three steps, multiple tasks allowed

Morning setup must be quick, but it must not limit the owner to doing only one task on a busy or productive day. Use three screens with a thin three-step progress indicator. The first two screens each take one tap and advance automatically. The third screen is a **multi-select task/subject picker**; multiple items can be selected before the owner taps one bottom-pinned **Build my day** button. This means three setup steps, not literally three taps. Do not sacrifice the multi-task workflow to preserve a misleading “three-tap” label.

Use large rounded glass cards with a brief accent outline/glow when selected. On the third screen, selected options remain selected while the owner picks more items; each has an unmistakable check/toggle state. Show a small count such as `3 selected` near the bottom action. Disable “Build my day” until at least one task or subject is selected. Include a back arrow so the owner can change path or area without losing task selections unnecessarily. Keep transitions fast and avoid extra confirmation screens.

### Step 1 — daily path

**Question:** “Which path are you taking today?”

Options:

- **Rest**
- **Locked In**
- **Busy**

Tapping an option advances automatically to Step 2.

### Step 2 — primary work area

**Question:** “What is your main work area today?”

Options:

- **Find Niche**
- **Qur'an with Nature**
- **School**

Tapping an option advances automatically to Step 3. This choice identifies the area for the task picker; it must not imply that Salah, Qur'an revision, Gym, School schedule blocks, or other already-planned anchors cease to exist for the day.

### Step 3 — choose today's tasks or subjects

**Question:** “What do you want to work on today?”

The owner may select **one or more** items. The list depends on the selected primary work area.

**If Find Niche:**
- Find product
- Edit video
- Review video
- Post / upload video
- Review your account

**If Qur'an with Nature:**
- Find clip
- Edit video
- Review video
- Post video
- Review your account

**If School:**
- Maths
- English
- Geography
- History
- Accounting
- IT
- Economics

The owner can select several items in one visit. For example, a Find Niche day can include **Find product + Edit video + Review video + Post / upload video** together. Do not make the owner repeat morning setup or choose a different day just to plan multiple tasks.

For School, selecting more than one subject is allowed. Do not invent chapters, assignments, or specific schoolwork that the owner has not supplied.

After one or more items are selected, tapping **Build my day** creates the day's task list and opens the selected path's Today layout. Do not add a fourth question or a separate confirmation screen. If the owner selected the wrong path or area, the back arrow allows edits before finalizing the day.

**Scope note:** this step selects multiple tasks from one primary area. The design does not yet specify an “add any task from any area” editor during the day; do not invent such a feature as part of this correction. Keep the primary area as the setup focus, not as a claim that other daily anchors disappear.

## 5. Today — standard home

The standard Locked In Today screen is a vertically scrolling stack in this order. The header/stat area sits above the first content card; **Salah is always the first content card.**

### 5.1 Header and stat chips

Show greeting, date, selected path pill, and eligible stat chips. Keep this section compact so Salah appears near the top of the screen.

### 5.2 Salah card — always first

Show the five prayers as five tappable circles, labelled Fajr, Dhuhr, Asr, Maghrib, and Isha. Tapping a prayer toggles its completed state; completed circles fill with the selected accent and show a tick. Each prayer's state must be readable without colour alone.

Do not invent prayer times. If the UI displays a time, it must come from a schedule actually configured for the owner. If a prayer-time source or schedule has not been configured, show prayer names and completion states without made-up times.

### 5.3 Today rings card

Show exactly three activity rings with a compact legend to the right:

- **Tasks:** completed checklist tasks / total checklist tasks planned for today.
- **Focus:** actual focus time completed / the owner's daily focus goal. Display time in readable minutes or hours.
- **Deen:** combined completion of the day's five Salah checks and four planned Qur'an revision pages. The legend must also show the separate factual detail, for example `Salah 3/5` and `Qur'an 2/4 pages`, so the combined ring is never misleading.

Use the same ring size, dim track, rounded strokes, and restrained accent glow. Animate only when a value changes, not continuously. Never treat an unplanned item as missed. For the Tasks ring, count only items on My Tasks; the separate Salah, Qur'an, and Gym cards must not be silently counted again as task rows.

### 5.4 Up next card

Show the next scheduled item with a highlighted main block containing:

- Time remaining until start, where a real schedule is available.
- Activity title.
- Place/context, when known, such as School or Gym.
- Start time and end time when configured.

Below it, show two or three smaller upcoming rows with a narrow coloured side bar and time. The times in visual examples are placeholders until the owner's actual schedule is confirmed. Do not manufacture times or locations. If there is no upcoming item, use a quiet empty state such as “Nothing scheduled next” rather than fake content.

### 5.5 Focus card

When idle, show a minutes input/selector and a Start button. When running, show the countdown, “Focusing”, Pause, and End. Keep the card compact enough that it does not dominate Today; the dedicated Focus screen is the detailed timer view.

### 5.6 My Tasks card

Show today's planned checklist. Each row contains:

- A round tick box.
- Task title.
- Small area tag: Find Niche, Qur'an with Nature, or School.
- A short day/status label only when it conveys information that is not already obvious.

Completed rows become slightly dimmer and struck through; their tick uses the accent. Do not add unapproved task types. If there are no planned tasks, show a simple empty state rather than placeholder tasks.

### 5.7 Qur'an revision card

Show today's target of four pages, the current Juz, weekly revision progress, and weakest page. The page count, Juz, weekly progress, and weakest-page value must come from owner-entered or saved progress; do not generate them. Support a visible way to record page progress without adding a complicated workflow. Do not add religious quotations or hadith to this card unless the owner requests them separately.

### 5.8 Gym card

Show the scheduled Push, Pull, or Legs session and its configured time. Hide the Gym card on Friday, as specified. Do not display a made-up session or time when no session is configured.

### 5.9 Streak card

Show the current no-contact streak as a plain day count. Keep it restrained; no fireworks, praise badges, or emotional claims. The dedicated Streak tab contains the detailed streak view.

## 6. Focus timer

The Focus screen is full-screen and visually quiet. It contains:

- A large countdown ring in the centre.
- Minutes input when idle.
- Quick-duration chips: 15, 25, 45, and 60 minutes.
- One clear Start button while idle.
- Pause and End controls while running.
- A clear paused state.

The timer can be opened from any task or subject. When opened from a task, show that task's name and associate the session with it. When opened without a task, the session is a general focus session and must not be assigned to an invented task.

Behavioral states for the UI:

- **Idle:** duration choice and Start.
- **Running:** animated ring/countdown, task or general-focus label, Pause, End.
- **Paused:** frozen remaining time and Resume/End controls.
- **Ended:** return to the prior screen and reflect the actual elapsed time in Focus progress.

The floating pill remains available on other screens while a session is running or paused. On the Focus screen itself, the large ring replaces the pill. Ending a session saves only actual elapsed focus time; scheduled duration must not be counted as completed if the session was ended early. Do not add Pomodoro, Deep Work, or other timer modes beyond the durations and controls above.

## 7. Progress

Progress uses glass cards and a plain, evidence-based summary:

1. **Week at a glance:** seven day circles, each filled according to the fraction of that day's planned work completed. Empty or future days must not look like failed days.
2. **Focus chart:** a bar chart of actual focus time per day for the current week. Include clear day labels and units.
3. **Done vs not done:** a straightforward list or split showing completed and unfinished planned items. Distinguish unfinished from not scheduled. No lectures or exaggerated praise.
4. **Streaks:** current and best no-contact streak as plain values.
5. **Qur'an revision:** the week's progress, current Juz, and weakest page, using saved information only.

The default view is the current week. Do not add Month/Year tabs unless the owner approves them. Avoid tiny chart labels, unnecessary gridlines, gamification, and comparisons with other people.

## 8. Rest-day screen

Rest mode must be noticeably quieter than Locked In:

- Show the Salah card first.
- Show one tiny task only.
- Show one large, calm message card with short wording, for example: “Don't forget Allah”, “Don't doomscroll all day”, or “Try resting without your phone”. These are examples, not final locked copy.
- Dim the visual intensity of the accent.
- Hide the Today rings card and the Focus card.
- Keep layout sparse, with extra whitespace and no guilt-oriented language.

If a Focus session was already active or paused before Rest mode was selected, the global Focus pill remains available to manage that existing session. Rest mode must not offer a new Focus session from its hidden Focus card.

## 9. Busy-day screen

Busy mode shows only:

1. Salah.
2. Qur'an revision.
3. The love-strengthening message card.

Hide rings, general task checklist, Gym, Streak summary, and Up next from the Busy screen. The message card may use only evidence or text the owner has personally supplied or explicitly approved. It must not assert what another person feels, intends, or will do. The global Focus pill may remain visible only if a session is already running or paused; Busy mode does not add a new Focus card.

## 10. Streak screen

Show:

- A large current no-contact day counter.
- Best streak.
- A row of milestones; reached milestones use the accent, and upcoming milestones remain dim.
- A Reset streak button.

Reset must require a confirmation dialog explaining that it resets the **current** streak. The best streak and historical records remain intact unless the owner separately chooses and confirms a distinct delete-history action; do not add that action to this design by default. No celebration effects or shame messages.

The UI must be explicit about the date boundary used for counting. Use the device's local calendar day unless the owner later specifies another rule. Never fabricate a streak value if the start date or saved data is missing; show a clear setup/unknown state instead.

## 11. Settings and appearance

### 11.1 Theme wallpaper

Show ten small preview tiles with the name directly underneath. Themes are wallpapers behind the glass, not separate app identities:

1. Ash — plain dark.
2. Sand.
3. Sage.
4. Aurora.
5. Smoke.
6. Tide.
7. Bloom.
8. Ember.
9. Grove.
10. Dusk.

Selected theme has a clear accent ring and tick. Previews must stay low-contrast enough that the UI text remains legible. Avoid using bright wallpapers behind text or adding decorative art to every card.

### 11.2 Accent colour

Show six colour dots in a row: blue, purple, pink, orange, green, grey. Green is selected by default. Selected dot uses a tick and a restrained glow; selection must also be identifiable without colour alone. Accent choice is independent of wallpaper choice.

### 11.3 Glass intensity

Provide a segmented control:

- **Clear:** more wallpaper visible through cards.
- **Tinted:** more opaque/darker glass, with greater text separation.

### 11.4 Reduce transparency

A toggle switches glass cards to solid surfaces with no frosting. Keep the same layout and hierarchy after switching; do not redesign the app as a different theme.

### 11.5 Focus defaults

Show controls for the default focus-session length and break length. Keep the break-length setting only as a preference; do not add a break timer or another timer mode unless separately approved. Clearly label values and provide a sensible selected state.

### 11.6 Notifications

Provide simple On/Off controls by notification type, plus quiet rules for Rest days. Types:

- Schedule reminder.
- Focus reminder.
- Random 100 istighfar reminder with the approved love-strengthening message.

These are actual Android phone notifications/alarms in the intended product, not in-app badges. The settings UI must show whether notifications are enabled and handle denied Android notification permission with a clear explanation and a route to system settings. Do not imply a notification will fire if permission is denied.

For the “random” istighfar reminder, the UI should communicate its permitted time window and frequency once those are decided. It must respect quiet hours and Rest-day rules. Do not silently invent an all-day schedule or send multiple unexpected reminders.

## 12. Notification appearance examples

Create compact mock phone-notification cards in the same dark, glass-inspired visual language. They are examples of real OS notifications, not dashboard badges.

- **Schedule reminder:** states where the owner should be and the relevant current/start time, only when schedule data exists.
- **Focus reminder:** points back to the owner's selected goal or task without fabricated motivational claims.
- **Random 100 istighfar:** invites the owner to do 100 istighfar and may include the approved love-strengthening message. Wording must remain respectful and based on the owner's own supplied material.

Notification content should be short, private, and readable on a lock screen. Avoid exposing sensitive relationship text unless the owner explicitly chooses to allow it on the lock screen.

## 13. Component system

- **Glass card:** standard translucent container with blur and a subtle 1 px border.
- **Option card:** large selectable panel used for the single-choice path/area steps.
- **Multi-select task card:** task/subject option with a persistent selected state and check marker; multiple cards can remain selected at once.
- **Build my day action:** bottom-pinned primary button on Step 3, paired with the selected-item count.
- **Activity ring:** animated rounded-stroke ring with a dim track and adjacent factual legend.
- **Task row:** tick box, task title, area tag, and optional useful status/day label.
- **Tag chip:** compact coloured area pill.
- **Stat chip:** small glass pill containing a number and label.
- **Focus pill:** global timer indicator for running/paused sessions.
- **Primary button:** accent-filled, high contrast, rounded.
- **Secondary button:** glass surface with a restrained border.
- **Segmented control:** for settings such as Clear/Tinted.
- **Toggle:** accessible on/off setting control.
- **Colour dot:** accent selection with tick/selected state.
- **Theme tile:** wallpaper preview with name, selected ring, and tick.
- **Bottom tab bar:** Today, Progress, Streak, Settings.

Components must have consistent pressed, selected, disabled, running, paused, completed, and empty states wherever applicable.

## 14. Motion and interaction details

- Ring progress eases from the old value to the new value when saved activity changes.
- Cards fade in subtly on navigation; avoid delaying access to content for decorative animation.
- Pressed controls compress or brighten slightly, then return to rest.
- Selected setup cards get a brief accent glow, not a persistent neon halo.
- Theme changes crossfade gently; avoid a full-screen flash.
- Do not animate static cards continuously. Do not use fireworks, confetti, reward popups, or flashy streak effects.
- Respect Android's reduced-motion preference where available. Also provide a low-motion behavior if animation proves uncomfortable; keep all information available without animation.

## 15. Visual states that must be designed

Do not design only the ideal, fully populated screen. Include the following states in the UI system:

- First launch before any daily setup is saved.
- Each of the three setup steps, including selected/unselected path and area options, multiple selected tasks, selected-item count, and disabled/enabled Build my day action.
- Today with incomplete tasks and with everything completed.
- No tasks planned.
- No upcoming schedule item.
- No saved Qur'an revision details yet.
- Focus idle, running, paused, and ended early.
- Notification permission allowed and denied.
- Rest and Busy paths.
- Streak unknown/not yet initialized, active, and reset-confirmation dialog.
- Settings selected states for theme, accent, glass, and transparency.
- Reduced-transparency appearance.

Every empty state should explain the missing information briefly and offer only the relevant next action. Never fill empty states with invented demo statistics in the real app. Sample data may be used in mockups only if it is visibly illustrative and not presented as real activity.

## 16. Accessibility and readability

- Text and control contrast must remain sufficient over every wallpaper and glass setting.
- Do not rely on colour alone: use ticks, labels, icons, or text for selected/completed states.
- Make touch targets comfortably tappable on a phone.
- Preserve readable text sizes on narrow screens and when Android font scaling is increased.
- Charts must include labels and understandable values, not colour alone.
- Reduced transparency must produce a legible, solid-card interface.
- Animations must be restrained and must not block interaction.

## 17. Explicit exclusions

Unless the owner separately approves them, do not add:

- Amanah branding, colours, screen structures, or relationship-app features.
- Social feeds, messaging, profiles, followers, or public sharing.
- Pomodoro/Deep Work mode menus or extra timer types.
- Month/Year tabs on Progress.
- New tasks, subjects, categories, or morning questions.
- Extra Deen content, quotes, Hadith collections, or religious features not named here.
- Fake schedules, prayer times, activity statistics, weakest pages, or streak counts.
- Gamified rewards, badges, confetti, motivational lectures, or comparison rankings.
- Any database, authentication, notification, or deployment implementation at the design stage.

## 18. Image-generation brief for future UI concept images

When generating visual concept images for Nusi, show several **Android portrait phone screens** in a coherent dark-glass visual system—not a desktop dashboard. Include the screens and components specified here: three-step multi-task setup with path and area selection plus multiple selected task cards, Today with Salah first and three rings, Up next, tasks, Qur'an revision, Gym, global Focus pill, full Focus timer, weekly Progress, Streak with confirmation dialog, Rest, Busy, Settings with all ten theme tiles and six accent dots, and sample OS notification cards.

Use charcoal, translucent frosted panels, low-contrast wallpaper, rounded cards, near-white typography, and green accents by default. Show gentle animation cues visually only where useful, such as a ring in progress or soft selected-card glow. Keep the composition clean and readable, with consistent screen margins, realistic phone proportions, and no clutter.

Do not copy text, branding, avatars, names, or layout from the source reference. Do not introduce features outside this PRD. Generated screens are illustrative mockups, not functional software; small text in generated imagery may be imperfect, so the written PRD remains authoritative.

## 19. Decisions and open items

### Resolved for this design pass

- Use dark frosted glass as the core identity, distinctly separate from Amanah.
- Use green as the default accent, with the six specified alternatives.
- Use a four-tab bottom navigation: Today, Progress, Streak, Settings.
- Use three setup screens: path and primary area auto-advance after one selection each; the third screen allows multiple task/subject selections and a single “Build my day” action. Do not limit the owner to one task.
- The Focus pill is global while active/paused; the full Focus screen does not show a duplicate pill.
- Rest and Busy hide their specified productivity cards; they do not fabricate replacement metrics.
- The current streak reset does not erase the best streak or history by default.
- The generated UI must represent all required screens and settings, not merely the home screen. Show the multi-task selection state accurately; do not depict the third step as a single-choice screen.

### Still needs the owner's decision before implementation

1. **App name spelling:** confirm whether the final name is “Nusi” or another spelling.
2. **Schedule source and exact times:** confirm the real school, gym, and other schedule times and whether they are entered manually or sourced elsewhere. Until confirmed, example times in mockups are placeholders only.
3. **Salah timing:** confirm whether the UI should show prayer times at all and, if so, what reliable source/settings will supply them. Never invent them.
4. **Random istighfar timing:** choose the allowed time window, maximum frequency, and whether this notification is allowed on Busy days as well as normal days. Rest-day quiet rules must be respected.
5. **Love-strengthening material:** confirm how the owner supplies/approves evidence and message wording, and whether sensitive text may appear on the lock screen. No unsupported claims about another person's feelings.
6. **Break length behavior:** confirm whether the break-length preference is simply saved for later or whether a break timer is desired in a future scope. The current UI does not add a break timer.
7. **Streak counting rule:** confirm what event starts/continues/resets a day of the no-contact streak and what counts as a completed day. The UI must follow one explicit rule and not guess.
8. **Build route:** confirm the eventual implementation platform. MIT App Inventor was discussed, but its ability to deliver reliable background alarms must be evaluated before choosing it. This is outside the current design-only approval.

## 20. Approval boundary

This PRD defines the intended visual system and screen behavior only. **No build, code change, data migration, permission setup, notification implementation, or deployment may begin until the owner explicitly says to build.**
