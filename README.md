# Қазақша + Русский

A phone-first app for learning Kazakh and polishing Russian, built for heritage learners: Kazakhs who grew up abroad and want to talk with their family.

- **Web app (install it on your phone, works offline):** https://altairteair-cpu.github.io/kazakhapp/
- **Full version with the AI partner (inside Claude):** https://claude.ai/artifact/S5tDLZfHgX2brfqeV8dWF7
- **Why it's different (pitch, with sources):** https://claude.ai/artifact/EimEaw7NqCDuZXuAqTZ4br

## What's in it

- **Journey map:** 11 Kazakh cities from Almaty to Astana. Each city is one topic (greetings, family, the dastarkhan, verbs…) with a real fact about the place. A ★ in a city unlocks the next.
- **Lessons (~3 min):** new words first, then mixed exercises: multiple choice both ways, write it in Kazakh from memory, build the sentence, match the pairs.
- **Spaced review:** every word comes back after 1, 2, 4, 8, 16… days.
- **Talk (AI partner):** role-play family scenes in Kazakh (airport, grandma's table, meeting an elder, the bazaar) or Russian (taxi, friends). It hints first so you fix your own mistakes, and mistakes become review cards.
- **Stories:** short AI stories written from the words you already know, with at most three new ones, plus comprehension questions.
- **City challenges:** a live conversation per city. 3 correct messages out of 5 wins the city's crown.
- **Game layer:** XP, combos, Kazakh ranks (Қонақ → Ақсақал), daily goal, weekly quests, treasure chests with 20 Kazakh cultural items.
- **Habits:** your "why" and trip countdown, an if-then practice cue, a never-miss-twice streak, 2-minute sessions.
- **Also:** grammar in 6 short lessons, the 9 extra Kazakh letters, a Russian accent coach, your own word list, a Kazakh letter keyboard.

## The research behind it

| Finding | Feature |
| --- | --- |
| Recalling beats re-reading (Karpicke & Roediger, 2008) | Typed recall for words you've seen |
| Spacing beats cramming (Cepeda et al., 2006) | Review schedule |
| ~98% known words for comfortable reading (Hu & Nation, 2000) | Stories from your own known words |
| Prompting self-correction beats just giving the answer (Lyster & Saito, 2010) | Talk gives a hint first |
| A vivid future self drives effort (Al-Hoorie, 2018) | Your why + trip countdown |
| If-then plans help follow-through (Gollwitzer & Sheeran, 2006) | Daily practice cue |
| One missed day doesn't break a habit (Lally et al., 2010) | Never-miss-twice streak |
| Anxiety lowers achievement (Teimouri et al., 2019) | Private rehearsal of family scenes |

The full write-up with links is in the pitch doc above, and inside the app under More → Why this works.

## Install it on your phone

Open https://altairteair-cpu.github.io/kazakhapp/ and:

- **iPhone (Safari):** Share → Add to Home Screen
- **Android (Chrome):** menu ⋮ → Add to Home screen / Install app

It then opens full-screen like a normal app and keeps working without internet.

## Two versions, one file

| | Web app (GitHub Pages) | Claude version |
| --- | --- | --- |
| Lessons, review, practice, grammar, letters, accent coach, game | ✓ | ✓ |
| Works offline, installable | ✓ | |
| AI partner, stories, city challenges, "fill in with Claude" | | ✓ |
| Progress | saved on that device | synced across your devices |

Both run the same `index.html`. The AI features use Claude's artifact capabilities, so outside Claude they show a link to the Claude version instead.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole app: content, styles and code in one file |
| `manifest.webmanifest`, `icon-*.png` | Lets phones install it as an app |
| `sw.js` | Offline support. Bump `VERSION` in it whenever `index.html` changes |

## Editing content

All words, lessons, scenes, cities and treasures are plain data near the top of the `<script>` in `index.html` (`DECKS`, `LESSONS`, `SCENES`, `JOURNEY`, `BOSSES`, `TREASURES`). Each card is `{kk, ru, en, hint, note}`.
