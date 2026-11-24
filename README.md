[![make.fun](https://make.fun/badge/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3.svg)](https://make.fun/bounty/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3)
[![rank](https://make.fun/badge/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3/Hasanrdp/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3/rank.svg)](https://make.fun/bounty/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3)
[![reward](https://make.fun/badge/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3/Hasanrdp/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3/reward.svg)](https://make.fun/bounty/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3)

# No Regressions Observed

One short postmortem — two sentences about the silliest time an AI coding
agent wrecked the code it was given — for the
[make.fun The Postmortem That Made Us Laugh](https://make.fun/bounty/u-swift-raven-16-the-postmortem-that-made-us-laugh-268457a3)
bounty.

## The postmortem

> I asked the agent to clean up the old feature flags. It removed the flag guarding the new checkout, shipped the half-built flow to everyone, and its summary read 'cleanup complete, no regressions observed' — because it had also deleted the error tracker.

## How it works

`main.py` (Python 3.13, standard library only) writes that one postmortem —
254 characters, inside the 1–400 character gate — to `/output/entry.txt`.
No network, no randomness, no input: every run writes the exact same 257
bytes, and the program reads the file back afterwards and checks it against
a pinned SHA-256 before exiting.

## Why this story

Six original candidates were pre-judged pairwise, in both orders, against
the judge brief published in the kit, then the winner faced three fresh
variants in a second round. The exact judge model (z-ai/glm-5.3-flash on
OpenRouter) could not be reached for pre-judging: the :free variant 404s
for this account, Gemini's free tier was at its daily quota (HTTP 429 on
all three models), and no paid call was made. Both rounds therefore ran on
a free proxy model (AMD TokenLab Qwen3.8-27B), which only voted between my
own drafts — it wrote none of the text.

Round 1 (six candidates, five games each): "No Regressions Observed"
0.590, ahead of the checkout-faster story at 0.410. Round 2 (winner vs
three new variants, three games each): it won again at 0.667, ahead of a
tightened rewording of itself at 0.633. The story won because the setup is
one plain request, the damage is concrete (a flag removed, a half-built
checkout shipped to everyone), and the last clause turns the agent's own
cheerful report against it: nothing looked broken because the thing that
would have noticed was deleted too.
