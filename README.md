# 🎮 Game Glitch Investigator: The Impossible Guesser

## 🚨 The Situation

You asked an AI to build a simple "Number Guessing Game" using Streamlit.
It wrote the code, ran away, and now the game is unplayable. 

- You can't win.
- The hints lie to you.
- The secret number seems to have commitment issues.

## 🛠️ Setup

1. Install dependencies: `pip install -r requirements.txt`
2. Run the broken app: `python -m streamlit run app.py`

## 🕵️‍♂️ Your Mission

1. **Play the game.** Open the "Developer Debug Info" tab in the app to see the secret number. Try to win.
2. **Find the State Bug.** Why does the secret number change every time you click "Submit"? Ask ChatGPT: *"How do I keep a variable from resetting in Streamlit when I click a button?"*
"st.session_state"
Everytime I type my guess in Streamlit, it re-runs the entire script from top to bottom. That's why any normal variable get recreated from scratch.

3. **Fix the Logic.** The hints ("Higher/Lower") are wrong. Fix them.
4. **Refactor & Test.** - Move the logic into `logic_utils.py`.
   - Run `pytest` in your terminal.
   - Keep fixing until all tests pass!

## 📝 Document Your Experience

 
Describe the game's purpose.
- [The purpose of this game is to act like a player who guess the correct secret numbe.However, this game associated with glitch as well which makes it name as the Game Glitch Investigator ]

Detail which bugs you found.
- [I have fould few bugs such as the even attempt conversion,check_guess function, update_score function] 

Explain what fixes you applied.
- [1. Deleted this "st.session_state.attempts % 2 == 0" and replace with this "secret = st.session_state.secret"
2.  Switch Go Lower with too high anf Go Higher with too low.]


## 📸 Demo Walkthrough

Describe your fixed game in numbered steps so a reader can follow along without watching a video:

1. The idea behind this game is to you have to select the difficulty level and enter a guess between 1 and 100. Eight attempt has been given, and within this attempt you have to gues the secret number. If you enter a number lower than secret number, the output will tell you to go higher and same with a higher number.
2. One of the glitch in this game is to if you enter a number higher than the secret number, it tells you to go higher instead of lower. And because of that I changed the code under the check guess function.
3. Earlier if you enter 40; > 34, it tells you to go higher. And this is where I made the chnage and wrote Go Lower. 
4. Moreover, I deleted st.session_state.attempts % 2 == 0
5. modulus 2 was deliberately planned as a glitch
every even-numbered attempt (2nd, 4th, 6th…) converts the secret number into a string with str(...).

**Screenshot** *(optional)*: <!-- Insert a screenshot of your fixed, winning game here -->
[I added the screenshot under the file]


## 🧪 Test Results

```
# Paste your pytest output here, e.g.:
# pytest tests/
# ========================= X passed in 0.XXs =========================


 python -m pytest
========================================= test session starts ==========================================
platform darwin -- Python 3.11.5, pytest-9.0.3, pluggy-1.6.0
rootdir: /Users/_rifahtasfia/ai110-module1show-gameglitchinvestigator-starter
plugins: anyio-4.13.0
collected 3 items                                                                                      

tests/test_game_logic.py ...                                                                     [100%]

========================================== 3 passed in 0.01s ===========================================




## 🚀 Stretch Features

- [ ] [If you choose to complete Challenge 4, describe the Enhanced UI changes here — a screenshot is optional]
