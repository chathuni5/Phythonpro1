# Phythonpro1
Here’s a Python script to help you find valid combinations for the remaining 15 Bingo numbers (since you selected 5 already) to reach a total sum of 999:

```python
import itertools

Your selected numbers
selected = [66, 60, 57, 45, 48]
current_sum = sum(selected)
remaining_sum = 999 - current_sum
numbers_left = 15  # total 20 - already picked 5

Define the number range
number_pool = list(range(0, 100))

Filter out already picked numbers
available_numbers = [n for n in number_pool if n not in selected]

Try to find one valid combination
for combo in itertools.combinations(available_numbers, numbers_left):
    if sum(combo) == remaining_sum:
        print("Remaining numbers to pick:", combo)
        break
else:
    print("No valid combination found.")
```

*Note:* This brute-force method checks combinations and may take time. You can modify it to find just 10 numbers instead of 15 if you’re only picking 10 in total.
