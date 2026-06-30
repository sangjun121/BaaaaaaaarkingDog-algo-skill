# Level Assessment

Use this reference when the user asks where to start, whether they should skip early lectures, or how to study efficiently from their current level.

Do not over-test. The goal is to choose a starting point and immediate route, not to grade the user academically.

## Assessment Flow

Ask for answers in four areas. If the user wants a quick check, ask only one question per area.

1. Java syntax and IO
2. Basic implementation
3. Algorithm recognition
4. Debugging and counterexample ability

If the user already provides enough context, skip questions and infer the level.

## Quick Diagnostic Questions

Use these as a compact test.

### Java Syntax and IO

Ask the user to explain or write:

- `BufferedReader`, `StringTokenizer`, `StringBuilder`
- 1D and 2D array input
- when to use `int` vs `long`
- `ArrayDeque<int[]>` usage

### Basic Implementation

Ask one of:

- Read `N` integers and count frequencies.
- Read an `N x M` grid and count cells with value `1`.
- Sort pairs by first value, then second value.

### Algorithm Recognition

Give short scenarios and ask which algorithm fits:

- Minimum moves in a grid with walls.
- Generate all length-M sequences without duplicates.
- Find maximum value after applying many conditional operations.
- Count ways using previous answers.
- Choose maximum number of non-overlapping intervals.

Expected mapping:

- grid minimum moves: BFS
- sequence generation: backtracking
- many conditional state updates: simulation
- count ways from previous states: DP
- non-overlapping interval choice: greedy with sorting

### Debugging

Ask what can go wrong:

- visited is marked when polling from BFS queue
- recursive DFS on 100,000 nodes
- comparator uses `a[0] - b[0]`
- `int` stores path costs near 1e18

## Practical Levels

### Level 0: Java Setup Not Ready

Symptoms:

- cannot write fast input without searching
- struggles with arrays, loops, parsing
- cannot submit simple BOJ problems comfortably

Start at:

- 0x01-0x02 first
- Java syntax patterns in `java-syntax-patterns.md`

Do not start BFS or DP yet.

### Level 1: Basic Implementation Ready

Symptoms:

- can handle input/output and arrays
- slow or error-prone with stack, queue, sort, map
- cannot quickly choose algorithms from problem statements

Start at:

- 0x03 Array
- then 0x05-0x08 stack/queue/deque/parentheses

Skip:

- 0x04 Linked List unless the user wants fundamentals; it is lower priority for Java coding tests.

### Level 2: Core Data Structures Ready

Symptoms:

- can use arrays, sort, stack, queue
- has weak graph traversal or visited handling
- struggles with grid problems

Start at:

- 0x09 BFS

Then:

- 0x0A DFS
- 0x0B Recursion
- 0x0C Backtracking

### Level 3: Traversal Ready, Implementation Weak

Symptoms:

- understands BFS/DFS
- loses time in long implementation problems
- bugs come from state update order and edge cases

Start at:

- 0x0D Simulation

Then:

- 0x10 DP
- 0x11 Greedy

### Level 4: Core Algorithms Ready

Symptoms:

- solves common BFS, backtracking, simulation, DP, greedy basics
- needs broader topic coverage

Start at:

- 0x13 Binary Search
- 0x14 Two Pointer
- 0x15 Hash
- 0x17 Priority Queue
- 0x18 Graph
- 0x1C Floyd
- 0x1D Dijkstra

## Recommendation Output

After diagnosis, output:

1. **현재 레벨**
2. **바로 시작할 단원**
3. **건너뛰어도 되는 단원**
4. **절대 건너뛰면 안 되는 단원**
5. **앞으로 3일 루틴**
6. **다음 단계로 넘어가는 기준**

## Move-On Criteria

Use concrete criteria:

- Java IO: can write `BufferedReader` and `StringTokenizer` from memory.
- Array: can solve frequency/counting problems without reference.
- Stack/queue: can choose `ArrayDeque` and write push/pop/peek correctly.
- BFS: can write grid BFS with distance array from memory.
- Backtracking: can write choose/recurse/unchoose structure from memory.
- Simulation: can break implementation into state, command, update order, validation.
- DP: can define `dp[i]` or `dp[i][j]`, transition, base case, and iteration order.
- Greedy: can state the sorting/choice rule and test at least one counterexample.
