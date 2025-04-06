Starts nice. Counts how many times opponent betrays. Makes them pay back more than they took. Gives a break every 7 rounds. Always betrays in last rounds.   
Like a shark: am am :)

1. Punishes when they owe:
```python
if debt > 0 and debt * 1.5 > sum(my_history) - sum(opponent_history): return 0
```
If they betrayed too much and owe you, you defect — even harder.

---

2. Gives a break every 7 rounds:
```python
if len(my_history) % 7 == 0: return 1
```
Once in a while, it cooperates to throw the opponent off guard.

---

3. Always betrays near the end:
```python
if rounds and len(my_history) >= rounds - 2: return 0
```
In the final rounds, we don’t trust anyone. We defect.

---

4. Reward recent cooperation:
```python
if opponent_history[-1] == 1: return 1
```
If the opponent was nice in the last round, they be ballin'.