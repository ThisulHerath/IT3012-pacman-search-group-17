# IT3012 Pac-Man Search - Group 17

Search algorithm implementations for the IT3012 Intelligent Agents assignment, based on the UC Berkeley Pac-Man AI project.

## Implementation status

The `member1-dfs-bfs` branch contains the following completed questions:

| Question | Algorithm | Function in `search.py` | Local autograder result |
| --- | --- | --- | --- |
| 01 | Depth-First Search (DFS) | `depthFirstSearch` | 3/3; all five tests passed |
| 02 | Breadth-First Search (BFS) | `breadthFirstSearch` | 3/3; all five tests passed |

Q3-Q7 remain to be implemented on this branch.

DFS uses `util.Stack` to explore the deepest queued path first. BFS uses `util.Queue` to explore paths in increasing depth, finding a shortest path by number of actions when every move has equal cost. Both algorithms track expanded states to prevent cycles and repeated expansion, return a list of actions when a goal is reached, and return an empty list if the frontier is exhausted.

## Setup

Clone the repository and switch to the implementation branch:

```powershell
git clone https://github.com/ThisulHerath/IT3012-pacman-search-group-17.git
cd IT3012-pacman-search-group-17
git switch member1-dfs-bfs
```

Create a Python environment using Anaconda or Miniconda:

```powershell
conda create -n cs188 python=3.11 pip -y
conda activate cs188
python -m pip install numpy matplotlib
```

The graphical game requires Tkinter. Use the text-mode commands below if a graphical display is unavailable.

## Run Pac-Man

Start the interactive game:

```powershell
python pacman.py
```

Run DFS or BFS on `mediumMaze`:

```powershell
python pacman.py -l mediumMaze -p SearchAgent -a fn=dfs
python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs
```

For text mode, append `-t` to either command. For a quiet run without graphics:

```powershell
python pacman.py -l mediumMaze -p SearchAgent -a fn=dfs -q
python pacman.py -l mediumMaze -p SearchAgent -a fn=bfs -q
```

## Test the implementations

Run the supplied autograder from the repository directory:

```powershell
python -B autograder.py -q q1 --no-graphics
python -B autograder.py -q q2 --no-graphics
```

Verified locally on 6 October 2026:

| Algorithm | `mediumMaze` solution length | Nodes expanded |
| --- | --- | --- |
| DFS | 130 | 146 |
| BFS | 68 | 269 |

The autograder's "Your grades are NOT yet registered" message is a standard submission reminder. Passing local tests does not submit the assignment or register course marks; follow the instructor's submission guidelines.

## Project files

| File or folder | Purpose |
| --- | --- |
| `search.py` | Generic search algorithms; Q1 and Q2 are implemented here |
| `searchAgents.py` | Search agents, search problems, and heuristic placeholders |
| `pacman.py` | Game entry point |
| `util.py` | Stack, queue, priority queue, and other utilities |
| `autograder.py` | Supplied test runner |
| `test_cases/` | Tests for each question |
| `layouts/` | Pac-Man maze layouts |

## Attribution

The Pac-Man AI projects were developed at [UC Berkeley](http://ai.berkeley.edu). The core projects and autograders were primarily created by John DeNero and Dan Klein. Student-side autograding was added by Brad Miller, Nick Hay, and Pieter Abbeel.

Retain the licensing and attribution notices in the supplied source files. See those notices for the terms governing educational use and distribution.
