https://justinsteinmetz.github.io/QuestionMarket/

# Question Market

**Band 1 · Unit 3 · In our free time · Grades 5–6**

A self-study grammar game. An answer appears on screen — the student writes the question that produces it. Designed for Band 1 learners practising wh-question formation with present simple.

---

## How to use

Open `index.html` in any browser. No installation, no server, no dependencies beyond a Google Fonts request.

### For students
1. Read the answer on screen
2. Select a question word from the chips to start your question
3. Finish typing and press **Check** or hit Enter
4. Review the feedback and model answer, then move to the next round
5. At the end, see your score and a full review of every answer

### For teachers
The game works as a warm-up, a timed individual task, or a live class challenge on a shared screen. It takes roughly 5–8 minutes to complete all 10 rounds.

---

## Question words covered

| Word | Example answer |
|------|----------------|
| What | The cooking club. |
| Which | Mr Bauer's group. |
| Where | In the school gym. |
| When | On Tuesdays and Thursdays. |
| Who | My best friend Alice. |
| Why | Because it's really fun! |
| How often | Three times a week. |
| How many | Twelve members. |
| Whose | Mr Bauer's. |

---

## Scoring

- **⭐ Score** — one point per correct question
- **🔥 Streak** — resets to zero on any wrong answer
- **Confetti** fires when a streak of 3 is reached (once per streak cycle)
- Questions are shuffled on every play-through

### What counts as correct

A question is marked correct if it:
1. Starts with the accepted question word for that answer
2. Contains a helper verb somewhere after the question word (`do`, `does`, `is`, `are`, `can`, `have`, `has`, `did`, `was`, `were`)

This means `How many people are in your club?` passes correctly — the helper verb doesn't need to be the very first word after the question phrase.

---

## Customising the content

All question data lives in the `DATA` object at the top of the `<script>` block — nothing is buried in the logic. To change or add rounds, edit only that section:

```js
const DATA = {
  title: "Band 1 · Unit 3 · In our free time",
  rounds: [
    {
      answer: "The cooking club.",      // text shown on the answer card
      hint: "Think about a club.",      // smaller hint text beneath
      accept: ["what", "which"],        // accepted question word(s), lowercase
      models: [                         // shown as examples in feedback
        "What club do you go to?",
        "Which club is your favourite?"
      ]
    },
    // ... more rounds
  ]
};
```

To create a version for a different unit, duplicate the file and replace the `DATA` object. The game engine requires no other changes.

---

## Accessibility

- All interactive chips are `<button>` elements — fully keyboard navigable
- Score and streak counters have `aria-label` attributes
- The text input has a proper associated `<label>` (visually hidden)
- Feedback is announced via `aria-live="assertive"`
- Decorative emoji have `aria-hidden="true"`
- Progress bar uses `role="progressbar"` with `aria-valuenow`

---

## Files

```
QuestionMarket/
├── index.html    — the entire game (self-contained)
└── README.md     — this file
```

No build step. No framework. No external scripts beyond Google Fonts.

---

*Deutsche Schule Prag · English Department*
