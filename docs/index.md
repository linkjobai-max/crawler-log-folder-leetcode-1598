# Crawler Log Folder (LeetCode 1598): Depth Counting Without a Stack

Given a list of folder operations ('../', './', 'x/'), return the minimum number of operations to get back to the main folder. It looks like a path problem but only needs one integer.

## Approach

Track the current depth. '../' decreases it but never below zero, './' does nothing, and anything else increases it by one. The final depth is the answer.

```python
def min_operations(logs):
    depth = 0
    for op in logs:
        if op == '../':
            depth = max(0, depth - 1)
        elif op != './':
            depth += 1
    return depth
```

## Complexity

O(n) time and O(1) space.

## Interview pitfalls

The clamp at zero is the only trap. Say why a stack is unnecessary here (folder names never matter), and how you'd switch to one if the question asked for the final path.

## Practicing out loud

Easy problems are where you can rehearse a crisp explanation: approach, complexity and one edge case in under a minute. Disclosure: I work on Linkjob AI, a real-time interview assistant. If you want live practice help, see [Linkjob](https://www.linkjob.ai/).
