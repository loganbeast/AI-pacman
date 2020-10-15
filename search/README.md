# AI-pacman

### QUESTION 1: DFS (LIFO)

```
  -Note:
    visited : list of visited node
    actions : chain of actions to reach goal ( return )
  -Input = (problem)
  -Algorithm:
    fringe = new stack()
    push (start_state,[]) to fringe
    visited = new list()

      while fringe is not empty
        get current_state, actions from fringe.pop() (stack)
        add current_state to list of visited

        if current_state is goal_state
          return actions

         for each next_state, direction,cost in list_successor of current_state
            if next_state is not visitted
              push (next_state,actions + direction) to fringe
     return []

```

### QUESTION 2: BFS (FIFO)

```
  -Note:
    visited : list of visited node
    actions : chain of actions to reach goal ( return )
  -Input = (problem)
  -Algorithm:

    fringe = new queue()
    push (start_state,[]) to fringe
    visited = new list()

      while fringe is not empty
        get current_state, actions from fringe.pop() ( queue)
        add current_state to list of visited

        if current_state is goal_state
          return actions

         for each next_state, direction,cost in list_successor of current_state
            if next_state is not visitted
              add next_state to list of visited
              push (next_state,actions + direction) to fringe
     return []

```

### QUESTION 3: UCS

```
  -Note:
    visited : list of visited node
    actions : chain of actions to reach goal ( return )
    costs : the sum of cost from start_state to current state
    cost : cost from current_state to next_state
  -Input = (problem)
  -Algorithm:
    fringe = new priorityQueue()
    push ((start_state,[],0),0) to fringe
    visited = new list()

      while fringe is not empty
        get current_state, actions from fringe.pop() ( queue)
        add current_state to list of visited

        if current_state is goal_state
          return actions

         for each next_state, direction,cost in list_successor of current_state
            if next_state is not visitted
              total_cost = costs + cost
              push ((next_state,actions + direction,total_cost),total_cost) to fringe
     return []

```

### QUESTION 4: A\* Search

```
  -Note:
    visited : list of visited node
    actions : chain of actions to reach goal ( return )
    costs : the sum of cost from start_state to current state
    cost : cost from current_state to next_state
    heuristic_func : mahatan_calculate_func
  -Input = (problem, heuristic function)
  -Algorithm:
    fringe = new priorityQueue()
    push ((start_state,[],0),0) to fringe
    visited = new list()

      while fringe is not empty
        get current_state, actions from fringe.pop() ( queue)
        add current_state to list of visited

        if current_state is goal_state
          return actions

         for each next_state, direction,cost in list_successor of current_state
            if next_state is not visitted
              total_cost = costs + cost + heuristic_func(next_state,problem)
              push ((next_state,actions + direction,costs + cost),total_cost) to fringe
     return []

```

### Question 5: Finding All the Corners

```
  -Note:
    remained_corners = (1,2,3,4) : tuple contains 4 corners
    direction_cost: cost ( 0,1,-1) depends on direction (N,S,E,W)
  -Input (current_state)
  -Algorithm:
    def getStartState(self):
      return state = (start_state , (1,2,3,4))

    def isGoalState(self, state):
      return true if (1,2,3,4) is empty

    def getSuccessors(self, state):
      successors =[]
      for each action in [Directions.NORTH, Directions.SOUTH, Directions.EAST, Directions.WEST]:
        get x,y = start_state
        get next_position = (x + direction_cost,y +direction_cost )

        check if next_position is not hit walls :
          check if next_position is one of 4 corners
            remove it from remained_corners
          else do nothing

        add ((next_position,remained_corners),action,1)
       return successors
```

### Question 6: Corners Problem: Heuristic (THAM KHẢO CODE)

```
  -Note:
     remained_corners =  : list contains coordinate of 4 corners [(1,1),(1,top),(right,1),(right,top)]
     heuristicInfo : a dict contains keys
     mazeDistance : distance from current state to one of 4 corners
   -Algorithm:
    def cornersHeuristic(state, problem):
      check if (1,2,3,4) is empty
        return 0
      distanceList = []
      for each corner in remained_corners
        set key = current_position + corner
        if key is in heuristicInfo
          distance = heuristicInfo[key]
        else
          distance = mazeDistance(current_positsion , corner_position)
          heuristicInfo[key] = distance

        add distance to distanceList

      return max of(distanceList) as heuristic

```
