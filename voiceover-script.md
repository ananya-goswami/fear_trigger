# Activity 1 — "Find the Fear Triggers" — Voiceover Extraction

Source: `Act_1/Activity 1 — Find the Fear Triggers (1)/Activity 1 — Find the Fear Triggers/completelayout/index.js`
Purpose: regenerate each line in **Narakeet**, then implement in **Act_3**.

## Global voice settings (apply to ALL lines)

| Setting | Value in source | Narakeet equivalent |
|---|---|---|
| Engine | Web Speech API (browser TTS) | — |
| Voice / language | `en-IN` (Indian English) | Pick an **Indian English** voice. Act_3's character is **Simran** (female) → use an Indian-English **female** voice. |
| Speed (`rate`) | **0.88** | Set **speed ≈ 0.9** (Narakeet build setting `speed: 0.9`). |
| Pitch | `1` (normal) | Default. |
| Per-word pauses | **NONE** | Do **not** add artificial word gaps. |
| Sentence/clause pauses | From punctuation `.` `,` `:` only | Keep the punctuation exactly as written below. |

> Note: a few words are **spelled out for the TTS** in the source (e.g. `2 hrs` → "two hours", `sbi-secure-verify.xyz` → "sbi secure verify dot x y z"). Those spelled-out forms are preserved below so Narakeet says them the same way. Keep them.

---

## Screens (in play order)

### Screen 1 — Phone Notification  (Step 1 of 3)
- Plays: on load / when the alert screen appears.
- **Voiceover:**
  > A scary alert has appeared on Simran's phone. Tap the notification to open the Messages app.
- Pauses: one full stop after "phone."

### Screen 2 — Messages Inbox  (Step 1 of 3)
- Plays: after tapping the notification.
- **Voiceover:**
  > You are now in Messages. Tap the unread SBI Alert conversation to open the message.
- Pauses: full stop after "Messages."

### Screen 3 — Select the Triggers  (Step 2 of 3)
- Plays: when the selection screen opens. (Phrase tapping is enabled only AFTER this line finishes.)
- **Voiceover:**
  > Select the triggers. First listen to the message, then tap every boxed phrase that is a fear trigger. Leave normal details unselected. The message says: SBI Alert. Urgent. Your SBI account will be blocked in two hours. Verify now: sbi secure verify dot x y z.
- Pauses: full stops after "triggers." / "unselected." ; colon after "says:" ; the read-out of the message has deliberate stops ("SBI Alert. Urgent. ... two hours. Verify now:").
- Spell-outs: "two hours" (= 2 hrs), "sbi secure verify dot x y z" (= sbi-secure-verify.xyz).

### Screen 4 — Feedback after "Check"  (two variants)
- Plays: right after the learner taps **Check**.
- **Voiceover (CORRECT):**
  > Correct. You found all four fear triggers. Now watch how each clue works.
- **Voiceover (WRONG):**
  > Good try. The real triggers are urgent, blocked, two hours, and the fake-looking URL. Review the highlighted explanation next.
- Pauses: commas create the list rhythm in the WRONG variant.

### Screen 5 — Why These Are Triggers  (Step 3 of 3, explanation intro)
- Plays: when the explanation screen opens. (Clue highlights auto-start AFTER this line finishes.)
- **Voiceover:**
  > Why these are triggers. Watch the message one clue at a time. The safest move is to stop, check the official app or website, and ask a trusted adult.
- Pauses: stops after "triggers." / "time." ; commas in "stop, check ... , and ask ...".

### Screen 6 — Clue reveal (4 lines, played one after another)
- Plays: each clue highlights in turn. **A 350 ms silence gap separates each clue line** (handled by the player; if baking files, add ~0.35 s trailing silence or let Act_3 sequence them).
- Format spoken = `"{label}. {text}"`

  **Clue 1:**
  > URGENT. This word tries to create fear so you react quickly instead of checking calmly.

  **Clue 2:**
  > BLOCKED. The message threatens that the account will be blocked. Scammers use loss to push fast action.

  **Clue 3:**
  > 2 hrs. A short time limit creates urgency. Real support gives clear steps, not a panic clock.

  *(TTS reads "2 hrs" as "two hours". In Narakeet write it as "Two hours." for the same result.)*

  **Clue 4:**
  > Fake link. The link looks bank-related but is not the official bank domain. It is bait for a fake page.

### Screen 6b — Safe action  (plays after the last clue)
- Plays: immediately after Clue 4, before "Finish" unlocks.
- **Voiceover:**
  > Safe action. Do not tap the link. Open the real banking app or website yourself, or ask a trusted adult to help verify it.
- Pauses: stops after "Safe action." / "link." ; commas in "yourself, or ask ...".

### Screen 7 — Complete
- Plays: on the completion screen.
- **Voiceover:**
  > Fear trigger hunt complete. You found the pressure words and fake-link clues that phishing messages use to rush people.

---

## Summary count
- **11 distinct audio lines** to generate:
  1. Notification
  2. Inbox
  3. Select-the-triggers
  4a. Feedback CORRECT
  4b. Feedback WRONG
  5. Explanation intro
  6. Clue 1 (URGENT)
  7. Clue 2 (BLOCKED)
  8. Clue 3 (2 hrs)
  9. Clue 4 (Fake link)
  10. Safe action
  11. Complete

## Suggested filenames (for Act_3 implementation later)
```
notification.mp3
inbox.mp3
select-triggers.mp3
feedback-correct.mp3
feedback-wrong.mp3
explanation-intro.mp3
clue-urgent.mp3
clue-blocked.mp3
clue-deadline.mp3
clue-fakelink.mp3
safe-action.mp3
complete.mp3   (optional, if reused)
```

---

## Narakeet settings + paste block

**Settings:** Language = English - Indian Accent · Voice = a **Female** Indian-accent voice (Simran) · Volume = standard · Speed = **normal** (source is 0.88; try `slow` if you want it more deliberate) · Format = mp3 · Output = **Separate audio file per paragraph**.

**Pauses:** Narakeet uses punctuation for pauses just like the source — paste the lines with punctuation exactly and add nothing. Each clue is a separate file, so the 350 ms inter-clue gap is handled by Act_3.

**Paste this (each blank-line block = one file, in order):**

```
A scary alert has appeared on Simran's phone. Tap the notification to open the Messages app.

You are now in Messages. Tap the unread SBI Alert conversation to open the message.

Select the triggers. First listen to the message, then tap every boxed phrase that is a fear trigger. Leave normal details unselected. The message says: SBI Alert. Urgent. Your SBI account will be blocked in two hours. Verify now: sbi secure verify dot x y z.

Correct. You found all four fear triggers. Now watch how each clue works.

Good try. The real triggers are urgent, blocked, two hours, and the fake-looking URL. Review the highlighted explanation next.

Why these are triggers. Watch the message one clue at a time. The safest move is to stop, check the official app or website, and ask a trusted adult.

URGENT. This word tries to create fear so you react quickly instead of checking calmly.

BLOCKED. The message threatens that the account will be blocked. Scammers use loss to push fast action.

Two hours. A short time limit creates urgency. Real support gives clear steps, not a panic clock.

Fake link. The link looks bank-related but is not the official bank domain. It is bait for a fake page.

Safe action. Do not tap the link. Open the real banking app or website yourself, or ask a trusted adult to help verify it.
```

Order → files: notification, inbox, select-triggers, feedback-correct, feedback-wrong, explanation-intro, clue-urgent, clue-blocked, clue-deadline, clue-fakelink, safe-action.

---

## CURRENT PLAN (supersedes Narakeet section above): Minimax + character "Avi" (male)

- TTS tool: **Minimax (minimax.ai)**. Character renamed **Simran → Avi (male)** — only Screen 1 names the character.
- **Voice:** young **male**, Indian-English / English. **Speed:** `0.9` (source 0.88). Pitch/volume default. Format mp3 or wav.
- **Pauses:** punctuation only (keep exactly). Minimax explicit-pause syntax is `<#0.5#>` (seconds) if ever needed — source used none within a line. 350 ms inter-clue gap handled by Act_3.
- Minimax makes one clip per input → generate **one line at a time**, in order:

1. notification — "A scary alert has appeared on Avi's phone. Tap the notification to open the Messages app."
2. inbox — "You are now in Messages. Tap the unread SBI Alert conversation to open the message."
3. select-triggers — "Select the triggers. First listen to the message, then tap every boxed phrase that is a fear trigger. Leave normal details unselected. The message says: SBI Alert. Urgent. Your SBI account will be blocked in two hours. Verify now: sbi secure verify dot x y z."
4. feedback-correct — "Correct. You found all four fear triggers. Now watch how each clue works."
5. feedback-wrong — "Good try. The real triggers are urgent, blocked, two hours, and the fake-looking URL. Review the highlighted explanation next."
6. explanation-intro — "Why these are triggers. Watch the message one clue at a time. The safest move is to stop, check the official app or website, and ask a trusted adult."
7. clue-urgent — "URGENT. This word tries to create fear so you react quickly instead of checking calmly."
8. clue-blocked — "BLOCKED. The message threatens that the account will be blocked. Scammers use loss to push fast action."
9. clue-deadline — "Two hours. A short time limit creates urgency. Real support gives clear steps, not a panic clock."
10. clue-fakelink — "Fake link. The link looks bank-related but is not the official bank domain. It is bait for a fake page."
11. safe-action — "Safe action. Do not tap the link. Open the real banking app or website yourself, or ask a trusted adult to help verify it."
