# is-it-offsides

**Is It Offside?** — a ten-scenario soccer offside quiz. Each scenario animates a passage
of play on a pitch and freezes at the moment the ball is played, with a dashed offside
line drawn through the second-last opponent. You call it **Offside** or **Onside**, and
get the answer explained against IFAB's Law 11.

The scenarios run easy → very hard, ending on the pair that splits crowds: a rebound off
a goalkeeper's *deliberate save* (still offside) versus a defender's *deliberate play*
(which resets it). A floating status bar keeps a running tally of right and wrong answers,
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

- Rule wording follows the IFAB Laws of the Game, Law 11 — Offside.
- All characters are original cartoon figures. No licensed marks, real clubs, or real players.
- Respects `prefers-reduced-motion`: scenes render as the frozen freeze-frame with the
  transport controls removed rather than animating.
