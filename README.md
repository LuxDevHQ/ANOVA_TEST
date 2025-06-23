# ANOVA Coding Test with Explanations

## PART 1: One-Way ANOVA Questions (7 Tasks)

These have **one independent variable** (categorical) and **one dependent variable** (numeric).

---

### Q1: Teaching Method vs Test Scores

**Explanation**: Test if 3 teaching methods (A, B, C) lead to different average student scores.

```python
method_A = [85, 90, 88, 75, 95]
method_B = [70, 65, 78, 72, 68]
method_C = [88, 85, 84, 90, 92]
```

**Use**: One-Way ANOVA

---

### Q2: Diet Type vs Weight Loss

**Explanation**: Test whether people lose more weight on different diets (Keto, Vegan, Mediterranean).

```python
keto = [5.1, 4.8, 6.2, 5.7, 6.0]
vegan = [3.2, 2.9, 3.8, 4.0, 3.6]
mediterranean = [4.3, 4.0, 4.5, 4.2, 4.1]
```

**Use**: One-Way ANOVA

---

### Q3: Phone Brand vs Battery Life

**Explanation**: Check if battery life differs significantly across 3 phone brands.

```python
brand_X = [10, 12, 11, 13, 14]
brand_Y = [8, 9, 10, 9.5, 8.5]
brand_Z = [11, 12, 11.5, 13, 12.5]
```

**Use**: One-Way ANOVA

---

### Q4: Study Hours vs Grades

**Explanation**: Does study time affect student grades?

* Group 1: <2 hours
* Group 2: 2–4 hours
* Group 3: >4 hours

```python
group_1 = [65, 60, 58, 63, 61]
group_2 = [70, 72, 74, 71, 69]
group_3 = [85, 87, 90, 86, 88]
```

**Use**: One-Way ANOVA

---

###  Q5: Job Training Program vs Productivity

**Explanation**: Are there productivity differences between employees in different training programs?

```python
program_1 = [60, 65, 68, 64, 66]
program_2 = [70, 75, 72, 74, 76]
program_3 = [62, 60, 61, 63, 59]
```

**Use**: One-Way ANOVA

---

### Q6: Fertilizer Type vs Plant Growth

**Explanation**: Test if average plant height varies by fertilizer.

```python
fertilizer_A = [22, 24, 23, 21, 25]
fertilizer_B = [28, 30, 29, 27, 31]
fertilizer_C = [19, 18, 17, 20, 16]
```

**Use**: One-Way ANOVA

---

### Q7: Branch vs Customer Satisfaction

**Explanation**: Test if customer satisfaction ratings vary across 3 store branches.

```python
branch_1 = [4.5, 4.7, 4.6, 4.8, 4.9]
branch_2 = [4.0, 3.8, 4.1, 3.9, 4.2]
branch_3 = [4.3, 4.4, 4.5, 4.2, 4.6]
```

**Use**: One-Way ANOVA

---

##  PART 2: Two-Way ANOVA Questions (7 Tasks)

These involve **two categorical independent variables** and one numeric dependent variable.

---

### Q8: Gender & Teaching Method vs Exam Scores

**Explanation**: Test if exam scores differ based on teaching method, gender, or their interaction.

```python
import pandas as pd
data = pd.DataFrame({
    "score": [85, 88, 90, 72, 75, 78, 83, 85, 87, 65, 68, 70],
    "gender": ["M", "M", "M", "F", "F", "F", "M", "M", "M", "F", "F", "F"],
    "method": ["A", "A", "A", "A", "A", "A", "B", "B", "B", "B", "B", "B"]
})
```

**Use**: Two-Way ANOVA using `statsmodels`

---

### Q9: Machine Type & Operator vs Output

**Explanation**: Test how output levels differ by machine type, operator, or both.

```python
data = pd.DataFrame({
    'output': [100, 102, 105, 98, 99, 101, 107, 108, 106],
    'machine': ['X', 'X', 'X', 'Y', 'Y', 'Y', 'Z', 'Z', 'Z'],
    'operator': ['A', 'B', 'C', 'A', 'B', 'C', 'A', 'B', 'C']
})
```

**Use**: Two-Way ANOVA

---

### Q10: Day & Store Location vs Sales

**Explanation**: Test if sales differ based on day of the week, store location, or interaction.

```python
# Columns: 'sales', 'day' (e.g., Mon, Tue), 'location' (e.g., Urban, Rural)
```

**Use**: Two-Way ANOVA

---

### Q11: Exercise Type & Gender vs Heart Rate

**Explanation**: Test if heart rate depends on exercise type, gender, or both.
**Use**: Two-Way ANOVA

---

### Q12: Temperature Setting & Brand vs Washing Time

**Explanation**: Test if washing time is influenced by brand, temperature setting, or both.
**Use**: Two-Way ANOVA

---

### Q13: Internet Plan & Age Group vs Download Speed

**Explanation**: Test if speed varies based on internet plan, age group, or interaction.
**Use**: Two-Way ANOVA

---

### Q14: Food Type & Region vs Taste Rating

**Explanation**: Test if taste rating depends on food type, region, or both.
**Use**: Two-Way ANOVA

---

##  Template for Two-Way ANOVA

```python
import statsmodels.api as sm
from statsmodels.formula.api import ols

# Example: df with columns 'value', 'factor1', 'factor2'
model = ols('value ~ C(factor1) + C(factor2) + C(factor1):C(factor2)', data=df).fit()
anova_table = sm.stats.anova_lm(model, typ=2)
print(anova_table)
```
