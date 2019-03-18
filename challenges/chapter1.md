---
title: example_python_challenges
output: html_document
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
import dccpu.generators as g

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
import dccpu.generators as g

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

## [OC] popping lists

```yaml
type: OutputChallenge
key: 6258197972
```

`@context`


`@code1`
```{python}
l1 = {{l1}}
p = l1.pop()
print(np.version.version)
```

`@code2`
```{python}
l1 = {{l1}}
p = l1.pop({{n}})
print(p)
```

`@pre_challenge_code`
```{python}
import dccpu.generators as g
import numpy as np
```

`@variables`
```yaml
l1:
- '!expr g.int_vector(size=6)'
n:
- '!expr g.rand_int(hi=5)'
```
