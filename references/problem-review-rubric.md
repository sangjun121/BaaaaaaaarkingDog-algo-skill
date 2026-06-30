# Problem Review Rubric

Use this rubric when reviewing user code or wrong-answer reports.

## Correctness

Check these first:

- wrong state definition
- off-by-one
- uninitialized arrays
- visited timing
- wrong queue/stack order
- missing boundary checks
- duplicate handling
- overflow

## Complexity

Check these second:

- nested loops over large N
- repeated sorting
- unnecessary BFS/DFS restart
- inefficient erase from vector front
- recursion explosion without pruning

## Counterexample

Always try to provide one small failing input if possible.

## Fix Strategy

Prefer a minimal patch first.

Provide a cleaner rewrite only if the structure is fundamentally broken.

## Learning Feedback

Map the bug back to the algorithm concept.

Do not just say "이렇게 고치면 됩니다."
