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

## [BC] Applying mean in the observed data

```yaml
type: BlanksChallenge
key: 8a565a9166
```

`@context`
Consider observations stored in `data`.

`@code1`
```{python}
import numpy as np
data = {{var1}}
print({{_func1}}
```

`@pre_challenge_code`
```{python}
import dccpu.generators as g
```

`@variables`
```yaml
var1:
- '!expr g.int_vector(lo=-3, hi=3, sort=True, size=5)'
func1:
- 'np.mean(data)'
```

`@distractors`
```yaml
func1:
- 'np.std(data)'
- 'np.max(data)'
- 'np.min(data)'
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
