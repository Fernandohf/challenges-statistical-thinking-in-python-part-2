---
title: ' Parameter estimation by optimization'
output: html_document
description: ""
---

## [MC] Optimal Parameters

```yaml
type: MultipleChoiceChallenge
key: 115qFYuQ4pPlifqZze0QkDORLwVufanGIfC
```

`@assignment1`
Choose the right answer about **Optimal Parameters**.

`@options1`
- They are calculated from the observed data.
- They represent parameters that best approximates the model the actual data.
- Their relevance depends if the selected model is appropriate for the observed data.
- [All the alternatives.]

---

## [BC] Calculating optimal parameters for normal distributions

```yaml
type: BlanksChallenge
key: 8a565a9166
```

`@context`
Consider observations of a normally distributed variable stored in `data` with optimal parameters `0` and `1`.

`@code1`
```{python}
import numpy as np
mu = {{_func1}}(data)
sigma = {{_func2}}(data)
print(mu, sigma)
```

`@pre_challenge_code`
```{python}
data = [-1,-1,-2, 0,0,0,0,0,0,1,1,2]
```

`@variables`
```yaml
func1:
- 'np.mean'
func2:
- 'np.std'
```

`@distractors`
```yaml
func1:
- 'np.avg'
- 'np.max'
- 'np.min'
- 'np.median'
func2:
- 'np.standard'
- 'np.devi'
- 'np.confidence'
```

---

## [BC] Checking theoretical distribution

```yaml
type: BlanksChallenge
key: 77ac115e68
```

`@context`
Consider observations of a normally distributed variable stored in `data`. Repeat the steps to calculate samples from the theoretical distribution with optimal parameters.

`@code1`
```{python}
import numpy as np

mean = np.mean(data)
std = np.std(data)

samples = {{_func1}}(mean, std, size=10000)
(np.mean(samples) - np.mean(data)) < 0.01
```

`@pre_challenge_code`
```{python}
data = list(range(100))
```

`@variables`
```yaml
func1:
- 'np.random.normal'
```

`@distractors`
```yaml
func1:
- 'np.normal'
- 'np.random.gaussian'
- 'np.random.exponential'
```

---

## [OC]  Understand np.polyfit output

```yaml
type: OutputChallenge
key: 6258197972
```

`@context`
Consider two related variables `x` and `y`.

`@code1`
```{python}
import numpy as np

x = {{var1}}
y = {{var2}}

print(np.polyfit(x, y, 1))
```

`@pre_challenge_code`
```{python}

```

`@variables`
```yaml
var1:
- '[1., 2., 3., 4.]'
var2:
- '[1., 2., 3., 4.]'
- '[1., 1., 1., 1.]'
- '[0., 0., 0., 0.]'
- '[2., 2., 2., 2.]'
```

---

## [OC] Create a line with np.polyfit

```yaml
type: OutputChallenge
key: 3ca2c3b03e
```

`@context`
Consider two related variables `x` and `y`.

`@code1`
```{python}
import numpy as np

x = {{var1}}
y = {{var2}}

slope, intercept = np.polyfit(x, y, 1)

line_x = np.linspace(1, 4, 4)
line_y = line_x * slope + intercept
print(line_y)
```

`@pre_challenge_code`
```{python}

```

`@variables`
```yaml
var1:
- '[1, 2, 3 ,4]'
var2: 
- '[1, 2, 3 ,4]'
- '[2, 4, 6 ,8]'
- '[1, 1, 1 ,1]'
- '[0, 0, 0 ,0]'
```

---

## [MC] Anscoimbe's Quartet

```yaml
type: MultipleChoiceChallenge
key: ea4062f9a4
```

`@assignment1`
Regarding Anscombe's quartet, choose the right answer.

`@assignment2`
Consider the picture of Anscombe's quartet and answer.
![quartet](https://assets.datacamp.com/production/repositories/4790/datasets/88543fe1a3c06b0a4376241f29c82ff083eaf589/anscombes_quartet.png "Anscombe's quartet")

`@options1`
- The quartet shows that only descriptive statistics can fully represent a dataset.
- The quartet shows that graphical EDA is a waste of time. 
- [None of the alternatives]
- The quartet shows that outliers have little influence in the estimated parameters.

`@options2`
- In all datasets of the quartet, seems to exist a linear relation between `x` and `y`.
- [In 3 datasets of the quartet, seems to exist a linear relation between `x` and `y`.]
- In no dataset of the quartet, seems to exist a linear relation between `x` and `y`.
- In 2 datasets of the quartet, seems to exist a linear relation between `x` and `y`.
