# is-it-offsides

**Is It Offside?** — a thirteen-scenario soccer offside quiz. Each scenario animates a passage
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
