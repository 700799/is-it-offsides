# is-it-offsides

**Is It Offside?** — a graphical walkthrough of the whole offside law, plus a
thirteen-scenario quiz. Each scenario animates a passage
of play on a pitch and freezes at the moment the ball is played, with a dashed offside
line drawn through the second-last opponent. You call it **Offside** or **Onside**, and
get the answer explained against IFAB's Law 11.

The scenarios run easy → very hard. They cover the case most people get wrong — an attacker
past the second-last defender when the ball goes somewhere else entirely, who never becomes
involved and is therefore onside — then the three ways a ball can reach
you off an opponent, back to back, because that is where the real arguments live: a
*deliberate save* never resets offside, a *deliberate play* does, and a *deflection* does not.
It finishes on the assistant referee's delayed flag.

The pitch reframes itself to whatever it is drawn on: on a phone it rotates to portrait so
the attack runs up the screen and the figures are roughly twice the size, and each scenario
is framed to its own action rather than always showing the whole half. `⛶ Full` hands the
diagram the entire viewport with the answer buttons pinned over it.

An assistant referee runs the touchline of every scenario, holding their required position:
level with the second-last defender, or with the ball once the ball is nearer the goal line.
Their flag stays down while the call is yours, and only goes up once you have answered.

A floating status bar keeps a running tally of right and wrong answers,
and your on-screen character starts as an American football player in a helmet and pads,
morphing towards an actual footballer as you get calls right. You finish in one of four
ranked categories.

## The tutorial

The landing page walks through **all 17 rules of Law 11**, in the four parts the law
itself uses — where you are, why being there is legal, what happens when the ball comes
off an opponent, and timing/exceptions/restart. Every rule gets its own diagram, resting
on the decisive frame with the offside line and the verdict already drawn, and every rule
quotes what the book actually says. There is a contents grid to jump around, and the quiz
is one button away at any point, before or after reading.

Most tutorial diagrams are derived from a quiz scenario's geometry by id rather than drawn
again, so the pictures cannot drift from the scenarios they teach; only four situations
needed drawing from scratch (own half, arms, players off the field, and the restart).

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
