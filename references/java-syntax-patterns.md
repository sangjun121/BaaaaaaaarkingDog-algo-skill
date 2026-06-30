# Java Syntax and Implementation Patterns

Use this reference when the user asks for Java-based coding-test preparation, implementation templates, memorization notes, or syntax patterns.

Keep answers practical. Prefer patterns the user can copy into BOJ, Programmers, or SWEA.

## Fast Input

Use `BufferedReader` and `StringTokenizer` by default for BOJ-style input.

```java
import java.io.*;
import java.util.*;

public class Main {
    static BufferedReader br = new BufferedReader(new InputStreamReader(System.in));

    public static void main(String[] args) throws Exception {
        StringTokenizer st = new StringTokenizer(br.readLine());
        int n = Integer.parseInt(st.nextToken());
        int m = Integer.parseInt(st.nextToken());
    }
}
```

Memorize:

- `BufferedReader br = new BufferedReader(new InputStreamReader(System.in));`
- `StringTokenizer st = new StringTokenizer(br.readLine());`
- `Integer.parseInt(st.nextToken())`
- `StringBuilder sb = new StringBuilder();`

## Output

Use `StringBuilder` when printing many lines.

```java
StringBuilder sb = new StringBuilder();
for (int x : arr) {
    sb.append(x).append('\n');
}
System.out.print(sb);
```

## Arrays

```java
int[] arr = new int[n];
int[][] board = new int[n][m];
boolean[][] visited = new boolean[n][m];
Arrays.fill(dist, -1);
Arrays.sort(arr);
```

For 2D fill:

```java
for (int i = 0; i < n; i++) {
    Arrays.fill(dist[i], -1);
}
```

## BFS Grid Template

Use `ArrayDeque<int[]>` for BFS queues. Do not use `LinkedList` unless there is a specific reason.

```java
static int n, m;
static int[][] board;
static int[][] dist;
static int[] dx = {-1, 1, 0, 0};
static int[] dy = {0, 0, -1, 1};

static void bfs(int sx, int sy) {
    ArrayDeque<int[]> q = new ArrayDeque<>();
    q.add(new int[]{sx, sy});
    dist[sx][sy] = 0;

    while (!q.isEmpty()) {
        int[] cur = q.poll();
        int x = cur[0];
        int y = cur[1];

        for (int dir = 0; dir < 4; dir++) {
            int nx = x + dx[dir];
            int ny = y + dy[dir];

            if (nx < 0 || nx >= n || ny < 0 || ny >= m) continue;
            if (board[nx][ny] == 0 || dist[nx][ny] != -1) continue;

            dist[nx][ny] = dist[x][y] + 1;
            q.add(new int[]{nx, ny});
        }
    }
}
```

Memorize:

- distance array can replace `visited`
- mark visited when pushing into the queue, not when polling
- boundary check first
- wall/blocked-cell check second

## DFS Recursion

```java
static boolean[] visited;
static ArrayList<Integer>[] graph;

static void dfs(int cur) {
    visited[cur] = true;

    for (int nxt : graph[cur]) {
        if (visited[nxt]) continue;
        dfs(nxt);
    }
}
```

Watch recursion depth. For very deep graphs, Java recursion can stack overflow; use iterative DFS or increase caution.

## Backtracking

```java
static int n, m;
static int[] selected;
static boolean[] used;

static void backtrack(int depth) {
    if (depth == m) {
        // use selected
        return;
    }

    for (int i = 1; i <= n; i++) {
        if (used[i]) continue;
        used[i] = true;
        selected[depth] = i;
        backtrack(depth + 1);
        used[i] = false;
    }
}
```

Memorize:

- choose
- recurse
- unchoose
- base case before loop

## Sorting

Primitive array:

```java
Arrays.sort(arr);
```

Object or 2D-style data:

```java
Arrays.sort(points, (a, b) -> {
    if (a[0] != b[0]) return Integer.compare(a[0], b[0]);
    return Integer.compare(a[1], b[1]);
});
```

Avoid `a[0] - b[0]` when values can be large.

## Priority Queue

```java
PriorityQueue<int[]> pq = new PriorityQueue<>((a, b) -> Integer.compare(a[0], b[0]));
pq.add(new int[]{cost, node});
int[] cur = pq.poll();
```

Use this for Dijkstra and greedy scheduling patterns.

## HashMap

```java
HashMap<String, Integer> map = new HashMap<>();
map.put(key, map.getOrDefault(key, 0) + 1);
if (map.containsKey(key)) {
    int value = map.get(key);
}
```

## Common Java Coding-Test Mistakes

- Using `Scanner` for large input.
- Forgetting `throws Exception` or try/catch around `BufferedReader`.
- Comparing strings with `==` instead of `.equals`.
- Using `int` when path cost or count needs `long`.
- Forgetting to reset static arrays between test cases.
- Using recursive DFS on a path of 100,000 nodes.
- Mutating objects stored in `PriorityQueue` after insertion.
- Sorting with subtraction comparator when overflow is possible.
