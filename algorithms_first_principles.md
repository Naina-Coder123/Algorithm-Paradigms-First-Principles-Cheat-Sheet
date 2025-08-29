1. Brute Force

First Principle:
Try all possible solutions and pick the best one.

Flowchart:

Start
 ↓
Generate all possible candidates
 ↓
For each candidate:
    Check if it satisfies problem
    If yes, record/compare
 ↓
Select the best solution
 ↓
End


General Pseudocode:

function bruteForce(problem):
    best_solution = null
    for candidate in all_possible_candidates(problem):
        if candidate is valid:
            best_solution = updateBest(best_solution, candidate)
    return best_solution


Memory Tip:
“Check everything.” Like trying every key on a keyring until the door opens.

2. Divide and Conquer

First Principle:
Divide the problem into smaller independent subproblems, solve recursively, combine solutions.

Flowchart:

Start
 ↓
Is problem small enough?
 ↙       ↘
Yes       No
 ↓          ↓
Solve directly  Divide problem
               ↓
           Solve subproblems recursively
               ↓
           Combine results
 ↓
End


General Pseudocode:

function divideAndConquer(problem):
    if problem is simple enough:
        return solveDirectly(problem)
    subproblems = divide(problem)
    results = []
    for sub in subproblems:
        results.append(divideAndConquer(sub))
    return combine(results)


Memory Tip:
“Divide, solve, combine.” Like solving smaller pieces of a puzzle first.

3. Dynamic Programming (DP)

First Principle:
Store solutions of overlapping subproblems to avoid recomputation.

Flowchart:

Start
 ↓
Define subproblem
 ↓
Have we solved it before?
 ↙       ↘
Yes       No
 ↓          ↓
Use stored solution  Solve subproblem
                        ↓
                    Store solution
 ↓
Combine subproblem solutions
 ↓
End


General Pseudocode:

memo = empty storage
function DP(problem):
    if problem is simple:
        return solution
    if problem in memo:
        return memo[problem]
    subproblems = divide(problem)
    results = []
    for sub in subproblems:
        results.append(DP(sub))
    memo[problem] = combine(results)
    return memo[problem]


Memory Tip:
“Remember results.” Like taking notes to avoid repeating work.

4. Greedy Algorithms

First Principle:
At each step, make the locally optimal choice, hoping it leads to a global optimum.

Flowchart:

Start
 ↓
Initialize solution
 ↓
While solution not complete:
    Select best candidate according to greedy criteria
    Add candidate to solution
    Update problem/state
 ↓
Return solution
 ↓
End


General Pseudocode:

function greedy(problem):
    solution = empty
    while problem not solved:
        candidate = selectBestCandidate(problem)
        add candidate to solution
        update problem/state
    return solution


Memory Tip:
“Best choice now → best overall.” Think: choosing the tastiest fruit first from a basket of options.

5. Backtracking

First Principle:
Build solutions incrementally and abandon partial solutions that fail constraints.

Flowchart:

Start
 ↓
Choose a candidate for the next step
 ↓
Is it valid?
 ↙       ↘
Yes        No
 ↓          ↓
Add candidate  Backtrack
 ↓
Is solution complete?
 ↙       ↘
Yes        No
 ↓          ↓
Record/Return candidate  Repeat
 ↓
End


General Pseudocode:

function backtrack(solution):
    if solution is complete:
        process(solution)
        return
    for each candidate in possible_candidates(solution):
        if candidate is valid:
            add candidate to solution
            backtrack(solution)
            remove candidate from solution  // backtrack


Memory Tip:
“Try, check, undo.” Maze analogy: move forward until blocked, then backtrack.

6. Graph Traversals

DFS First Principle:
Explore as deep as possible, then backtrack.

DFS General Pseudocode:

function DFS(node):
    mark node as visited
    process(node)
    for neighbor in neighbors(node):
        if neighbor not visited:
            DFS(neighbor)


BFS First Principle:
Explore neighbors level by level.

BFS General Pseudocode:

function BFS(start):
    queue = empty
    enqueue start
    mark start as visited
    while queue not empty:
        node = dequeue()
        process(node)
        for neighbor in neighbors(node):
            if neighbor not visited:
                enqueue(neighbor)
                mark neighbor as visited


Memory Tip:
DFS = depth (maze), BFS = breadth (wave).

7. Branch and Bound

First Principle:
Systematically explore branches but prune branches that cannot improve the current best.

Flowchart:

Start
 ↓
Initialize best_solution
 ↓
Branch problem into subproblems
 ↓
For each subproblem:
    if subproblem can improve best_solution:
        solve subproblem recursively
 ↓
Update best_solution
 ↓
End


General Pseudocode:

function branchAndBound(problem, best_solution):
    if problem is complete:
        best_solution = updateBest(best_solution, solution)
        return best_solution
    for subproblem in branches(problem):
        if canImprove(subproblem, best_solution):
            best_solution = branchAndBound(subproblem, best_solution)
    return best_solution


Memory Tip:
“Only explore promising paths.” Like cutting off unfruitful tree branches.

8. Randomized Algorithms

First Principle:
Use randomness to simplify or speed up a solution.

General Pseudocode:

function randomizedAlgorithm(problem):
    while problem not solved:
        candidate = chooseRandomly(options(problem))
        if solution(candidate) valid:
            return candidate


Memory Tip:
“Flip a coin when stuck.” Randomness guides the search.
