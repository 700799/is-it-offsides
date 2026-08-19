# is-it-offsides

**Is It Offside?** — a graphical walkthrough of the whole offside law, plus a
fifteen-scenario test called **the Offside Challenge**. Each scenario animates a passage
of play on a pitch and freezes at the moment the ball is played, with a dashed offside
line drawn through the second-last opponent. You call it **Offside** or **Onside**, and
get the answer explained against IFAB's Law 11.

Every call is put the same way round throughout: **one**, at the moment the ball was
played, was he in an offside position; **two**, did he then become involved in active
play. Get a no on the first and there is nothing left to judge.

The landing page is a title and two cards, side by side at every width — *study the rules*
or *take the challenge* — fronted by a husky coach with a tactics board and a number 9 with
both arms up. Each card takes its artwork's own background colour so the picture bleeds to
the button's edges, and both are locked to one aspect ratio so the two labels sit on the
same line. Nothing else is on that page but where the rules come from.

There are three screens and from any one of them the other two are one tap away: the main
page offers both, and the rules and the challenge each offer the main page and each other.
Leaving a part-finished challenge for the rules and coming back resumes it — only the main
page and *Play again* start a fresh run.

The scenarios run easy → very hard. They cover the case most people get wrong — an attacker
past the second-last defender when the ball goes somewhere else entirely, who never becomes
involved and is therefore onside — and the moment of the kick from both ends: the attacker
who times his run and beats the line legally, then the one who is beyond it at the kick and
is played level by a defence that steps up too late. Then the three ways a ball can reach
you off an opponent, back to back, because that is where the real arguments live: a
*deliberate save* never resets offside, a *deliberate play* does, and a *deflection* does not.
It finishes on the two ways a flag behaves when the offence is real: one that goes up late,
and one that never goes up at all because the defending team is better off playing on.

The pitch reframes itself to whatever it is drawn on: on a phone it rotates to portrait so
the attack runs up the screen and the figures are roughly twice the size, and each scenario
is framed to its own action rather than always showing the whole half. There are no view
controls to choose between — the diagram is always sized to the space it has.

The assistant referee appears on every scenario as their flag, travelling along the
touchline in the AR's required position: level with the second-last defender, or with the
ball once the ball is nearer the goal line. It stays down while the call is yours, and
only goes up once you have answered — except on the two passages where the law says it
should not go up at all, where it stays down and the explanation says why.

A floating status bar keeps a running tally of right and wrong answers,
and your on-screen character starts as an American football player in a helmet and pads,
morphing towards an actual footballer as you get calls right. You finish in one of four
ranked categories.

## The tutorial

The rules door covers the offside law in **eight chapters**, holding **21 diagrams**
between them:

1. Where you have to be — the two position tests, and who defines the line
2. The margins — level is onside, arms do not count
3. Being there is not the offence
4. The three ways to get involved — plays it, blocks an opponent, gains an advantage,
   and a fourth diagram for the near miss that is none of the three
5. The point of the kick — one frame decides it, and it cuts both ways
6. When it comes off an opponent — deliberate play, a save, a deflection
7. Exceptions and the restart
8. When the defence wins it anyway — no involvement, and advantage

Each chapter carries one diagram per point, selectable inside the card. Every diagram is
drawn with the smallest cast that can make its point — one passer, the attacker being
judged, the second-last defender, and the keeper — so there is nothing to read past, and
with only two opponents the second-last is unambiguous. The keeper wears his own side's
shirt and is told apart by his gloves, because the offside line has never cared who is
in goal. Players are drawn as flat jerseys rather than full figures, so team and role
read at a glance without competing with the pitch for attention. The passage plays, the card shows
one short line, and the assistant referee's flag is pinned to the edge of the frame where
it cannot cover anyone.

Chapter 5 pins down the disputed moment: the **first point of contact** of the play or
touch, not the follow-through and not when the ball leaves the boot, with the goalkeeper's
throw as the one exception. Chapter 8 answers the question everybody ends up asking — the
attacker was offside and the defence got the ball, so do you blow up? Usually no, for two
different reasons: a player who never becomes involved has committed nothing, and where an
offence *has* been committed the assistant holds the flag when the side it was committed
against is better off playing on.

Anything longer than a line lives behind **More detail**, which opens a drawer with the
full explanation and a quote of what the book actually says. There is a contents list to
jump around, and the challenge is one button away at any point, before or after reading.

Every chapter is sized to the viewport rather than to its content: **Prev / Replay / Next**
ride in a bar pinned to the bottom of the screen, and the diagram takes whatever height is
left once the fixed rows are placed, so none of the seventeen has to be scrolled through.
The chapter chips and tabs scroll sideways rather than wrapping, and on a short screen the
legend is dropped, so every chapter gets much the same diagram regardless of how long its
title or its one line runs. Below roughly 660px of viewport height there is not enough left
to be worth it, and the chapter reverts to scrolling rather than showing a diagram squeezed
to nothing.

## Running it locally

The site is `index.html` — inline CSS, inline vanilla JS, inline SVG — plus the two
front-page images under `art/`. Nothing is fetched from a third party. Open it directly:

```
open index.html
```

Or serve it over HTTP if you prefer:

```
python3 -m http.server 8000    # then visit http://localhost:8000
```

## Deploying

There is no build step and no dependencies. Vercel's zero-config static detection serves
`index.html` at `/` as-is. Deliberately **no `package.json`** — adding one would make
Vercel treat this as a Node project and attempt an install/build it does not need.

## Notes

- Rule wording follows the IFAB Laws of the Game 2026/27, Law 11 — Offside, together with
  the Practical Guidelines for Match Officials (AR positioning, the wait-and-see technique).
- The 2026/27 Laws permit competitions to use semi-automated offside technology; that changes
  who draws the line, not where it is, so every answer here is unaffected.
- All characters are original cartoon figures. No licensed marks, real clubs, or real players.
- Respects `prefers-reduced-motion`: scenes render as the frozen freeze-frame with the
  transport controls removed rather than animating.
