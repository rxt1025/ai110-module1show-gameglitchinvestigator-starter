# 💭 Reflection: Game Glitch Investigator

Answer each question in 3 to 5 sentences. Be specific and honest about what actually happened while you worked. This is about your process, not trying to sound perfect.

## 1. What was broken when you started?

- What did the game look like the first time you ran it?
The first time when I ran the game the output says go lower.I was expecting to run the game when I will enter an input.
- List at least two concrete bugs you noticed at the start  
  (for example: "the hints were backwards").
  1. At first attempt, even if I enter a number according to the instruction, it tells me to enter a number again even if it was correct.
  2. The page needs to be refresh during even attempt to work on it and during new game it needs to be refresh to work. 
 

**Bug Reproduction Log**

Document at least 3 bugs you found. Add rows as needed.

| Input | Expected Behavior | Actual Behavior | Console Output / Error |
|-------|-------------------|-----------------|------------------------|
|Guess 40| Too Low           |Too High(GO Lower)| 40<54(secret),the correct hint should be Go High
|Guess 55| Too High         |  No response     | Stored guess 40 insted of 55       
|Guess 30| Too Low          | Too High         |   30<37(Secret number), hint is incorrect

---

## 2. How did you use AI as a teammate?

- Which AI tools did you use on this project (for example: ChatGPT, Gemini, Copilot)?
  I have used Claude Code for VScode on this project.
- Give one example of an AI suggestion that was correct (including what the AI suggested and how you verified the result).
I told the AI that there is a glitch on the check_guess function. Because when I enter a number lower than the secret number, it tells me that Go Lower.
AI suggestion: The glitch is in the hint messages, which are swapped.
Analysis: I swaped the messages "GO LOWER" and "GO HIGHER"
- Give one example of an AI suggestion that was incorrect or misleading (including what the AI suggested and how you verified the result).
AI suggested me to delete str(secret) and use str(st.session_state.secret) to avoid during even attempts. However, it didn't work even after changing the code.
---

## 3. Debugging and testing your fixes

- How did you decide whether a bug was really fixed?
When I try to play the game again and saw the results, I was sure that the bug was fixed.For example: on app.py I chnaged the check_guess function.
- Describe at least one test you ran (manual or using pytest)
and what it showed you about your code.
I run the test app.py and it showed me No module named 'streamlit'

- Did AI help you design or understand any tests? How?
Yes, when I asked AI to show me why after each even attempt I need to refresh the page to get a result.
---

## 4. What did you learn about Streamlit and state?

- How would you explain Streamlit "reruns" and session state to a friend who has never used Streamlit?

--- Everytime you intract with streamlt, you need to click a button, type in a box and it throws aways everything and runs entire app.py
State is a special dictionary that remembers values between those re-runs, so the game can hold onto the secret number, your score, and how many guesses you've made.

## 5. Looking ahead: your developer habits

- What is one habit or strategy from this project that you want to reuse in future labs or projects?
  - This could be a testing habit, a prompting strategy, or a way you used Git.
  I would look at app/game where I have a doubt and I would come back to the exact function of the code to see what is incorrect about the code.
- What is one thing you would do differently next time you work with AI on a coding task?
Before asking AI and delve myself into cofusion, I would first verify the problem by myself first.
- In one or two sentences, describe how this project changed the way you think about AI generated code.
I used to think that AI generated code meaning evrything is given by AI. It is true at some extent. However, AI is not correct all the time. To verify it we need to have the skill to check it, it will not be correct all the time.