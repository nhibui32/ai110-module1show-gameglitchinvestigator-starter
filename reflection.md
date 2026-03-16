# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
- List at least two concrete bugs you noticed at the start  
  (for example: "the secret number kept changing" or "the hints were backwards").

---

At first, the game asks the user to enter a number to guess the secret number. While testing the game, I found several bugs. First, the hints were sometimes incorrect: when the guess should have been lower, the game displayed “go higher,” and vice versa. Second, the game accepted numbers outside the valid range of 0 to 100. Third, the New Game button did not properly reset the game state. Finally, the guess history displayed numbers that were always one step behind the user’s most recent guess.

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).

---
I used Claude to help with this project. Claude assisted me in fixing several bugs, such as the hints being reversed and the game accepting numbers outside the valid range. However, when I asked Claude to fix the New Game reset function, it did not clear the input field at first. After I asked Claude to address the issue again, it was able to fix the problem and the reset function worked correctly.

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
- Describe at least one test you ran (manual or using pytest)  
  and what it showed you about your code.
- Did AI help you design or understand any tests? How?

---

To make sure the bugs were fixed, I tested the game several times after making the changes. For example, I entered numbers that were higher and lower than the secret number to check if the hints showed the correct direction. I also tested numbers outside the range, such as negative numbers or numbers greater than 100, to confirm that the program rejected them. In addition, I tested the New Game button to see if it reset the game, cleared the history, and emptied the input field. AI also helped me understand what kinds of tests to run by suggesting edge cases like testing invalid inputs and checking the hint logic.

## 4. What did you learn about Streamlit and state?

- In your own words, explain why the secret number kept changing in the original app.
- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?
- What change did you make that finally gave the game a stable secret number?

---

In the original app, the secret number kept changing because the program was rerunning every time the user interacted with the app. Since the secret number was generated again during each rerun, the value kept changing instead of staying the same throughout the game. In Streamlit, a “rerun” means the script runs again from top to bottom whenever the user clicks a button or enters input. To keep information between reruns, Streamlit uses something called session state, which stores values during the user's session. To fix the problem, I stored the secret number in the session state so it would only be created once and remain the same until the game was reset.

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
- What is one thing you would do differently next time you work with AI on a coding task?
- In one or two sentences, describe how this project changed the way you think about AI generated code.

---

One habit I want to reuse in future projects is testing my code step by step after fixing each bug. This helped me make sure that each change actually solved the problem and did not break other parts of the program. Next time I work with AI on a coding task, I would try to give clearer prompts and explain the problem in more detail so the AI can give more accurate solutions. This project helped me realize that AI-generated code is useful for debugging and learning, but it still needs careful testing and understanding from the programmer to make sure it works correctly.