Absurdle Solver
---

[Absurdle](https://absurdle.online/) is an online word puzzle game that closely resembles the massively popular [Wordle](https://www.nytimes.com/games/wordle/index.html), implementing several of its core mechanics in the pursuit of a user correctly determining an unseen 5-letter word pattern through the repeated testing of several test patterns (guesses) to determine common letters and letter placements. The objective of a puzzle is to determine the unseen word with as few test patterns as possible.

The key difference with Absurdle is its __adversarial__ nature. As opposed to a fixed hidden pattern which is revealed through several test patterns, Absurdle dynamically determines the target word based on test patterns. It does so by maximising the entropy of the search: at each guess, the partition containing the 'target' word is chosen to be the largest collection of words sharing a matching pattern with the provided guess. This continues until the partition contains precisely one word, the target word. More details on the game's mechanics can be found in the [Absurdle Blog](https://qntm.org/absurdle).

While convergence to a target word is guaranteed, the reduction in the search space can be slow based on the user's sequence of guesses. As a result, Absurdle requires noticeably more turns to derive a solution than Wordle. While a seasoned Wordle player can often pick the next move which sufficiently minimises entropy, an Absurdle player is locked into pursuing the maximal entropic sequence based on their word choices.

This workbook employs search strategies to determine an optimal Absurdle playing: that is, the shortest sequence of guesses required to end the game.