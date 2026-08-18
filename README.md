# is-it-offsides

**Is It Offside?** — a graphical walkthrough of the whole offside law, plus a
thirteen-scenario test called **the Offside Challenge**. Each scenario animates a passage
of play on a pitch and freezes at the moment the ball is played, with a dashed offside
line drawn through the second-last opponent. You call it **Offside** or **Onside**, and
get the answer explained against IFAB's Law 11.

The landing page is a title and two big buttons — *study the rules* or *take the
challenge* — each fronted by its own Japanese Chin: one in a referee's pinstripes with
the flag already up, one in a headband striking a ball. Every screen keeps a route back
to it.

The scenarios run easy → very hard. They cover the case most people get wrong — an attacker
past the second-last defender when the ball goes somewhere else entirely, who never becomes
involved and is therefore onside — then the three ways a ball can reach
you off an opponent, back to back, because that is where the real arguments live: a
*deliberate save* never resets offside, a *deliberate play* does, and a *deflection* does not.
It finishes on the assistant referee's delayed flag.

The pitch reframes itself to whatever it is drawn on: on a phone it rotates to portrait so
the attack runs up the screen and the figures are roughly twice the size, and each scenario
is framed to its own action rather than always showing the whole half. There are no view
controls to choose between — the diagram is always sized to the space it has.

The assistant referee appears on every scenario as their flag, travelling along the
touchline in the AR's required position: level with the second-last defender, or with the
ball once the ball is nearer the goal line. It stays down while the call is yours, and
only goes up once you have answered.

A floating status bar keeps a running tally of right and wrong answers,
and your on-screen character starts as an American football player in a helmet and pads,
morphing towards an actual footballer as you get calls right. You finish in one of four
ranked categories.

## The tutorial

The rules door covers the offside law in **seven chapters**, holding **17 diagrams**
between them:

1. Where you have to be — the two position tests, and who defines the line
2. The margins — level is onside, arms do not count
3. Being there is not the offence
4. The three ways to get involved — plays it, blocks an opponent, gains an advantage
5. The instant it is judged
6. When it comes off an opponent — deliberate play, a save, a deflection
7. Exceptions and the restart

Each chapter carries one diagram per point, selectable inside the card. Every diagram is
drawn with the smallest cast that can make its point — one passer, the attacker being
judged, the second-last defender, and the keeper — so there is nothing to read past, and
with only two opponents the second-last is unambiguous. The keeper wears his own side's
shirt and is told apart by his gloves, because the offside line has never cared who is
in goal. Players are drawn as flat jerseys rather than full figures, so team and role
read at a glance without competing with the pitch for attention. The passage plays, the card shows
one short line, and the assistant referee's flag is pinned to the edge of the frame where
it cannot cover anyone.

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

The whole site is a single self-contained `index.html` — inline CSS, inline vanilla JS,
inline SVG, and zero external requests. Open it directly:

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
