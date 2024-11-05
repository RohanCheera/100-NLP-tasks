Here's how you can use regular expressions in Python to find words that start with a specific prefix, such as "un":

```python
import re

def find_words_with_prefix_regex(words, prefix="un"):
    # Compile a regex pattern to match words starting with the specified prefix
    pattern = re.compile(rf'^{prefix}')
    # Use list comprehension to filter words that match the pattern
    result = [word for word in words if pattern.match(word)]
    return result

# Example list of words
words = ["unfit", "undo", "happy", "unknown", "unite", "example", "unusual", "dog", "uncertain"]

# Find words starting with "un"
words_with_un = find_words_with_prefix_regex(words, "un")
print("Words starting with 'un':", words_with_un)
```

### Explanation

1. **Regex Pattern**: The `^` in `rf'^{prefix}'` specifies that the word should start with the prefix. The `rf` string prefix allows us to include variables directly in the regex pattern.
2. **Filter Words**: Using list comprehension, we filter words that match the regex pattern.

### Output

```
Words starting with 'un': ['unfit', 'undo', 'unknown', 'unite', 'unusual', 'uncertain']
```

This code is flexible, so you can specify any prefix you like by changing the `prefix` parameter in `find_words_with_prefix_regex`.
