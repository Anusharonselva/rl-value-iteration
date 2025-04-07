# VALUE ITERATION ALGORITHM

## AIM
To develop a Python program to find the optimal policy for the given MDP using the value iteration algorithm.


## PROBLEM STATEMENT
To find the optimal policy for the mdp using value iteration algorithm instead of policy iteration which is slower than value iteration.


## VALUE ITERATION ALGORITHM
Firstly the state value function and action value function for all the states of mdp are initialized to zero then while iterating through actions of each state the value function and action value function is caluculated for each state then the maximum action value function of each state is taken to find the best ploicy.


## VALUE ITERATION FUNCTION
### Name: Anusharon S
### Register Number:212222240010
```
def value_iteration(P, gamma=1.0, theta=1e-10):
    V=np.zeros(len(P), dtype=np.float64)
    while True:
      Q=np.zeros((len(P),len(P[0])), dtype=np.float64)
      for s in range(len(P)):
        for a in range(len(P[s])):
          for prob,next_state,reward,done in P[s][a]:
            Q[s][a]+=prob*(reward+gamma*V[next_state]*(not done))
      if np.max(np.abs(V-np.max(Q,axis=1)))<theta:
        break
      V=np.max(Q,axis=1)
      pi=lambda s: {s:a for s, a in enumerate(
          np.argmax(Q,axis=1))
     }[s]
    return V, pi
```
## OUTPUT:
![Screenshot 2025-04-07 110806](https://github.com/user-attachments/assets/0a707498-3c9c-4b34-993b-f46731a7ffb3)
![Screenshot 2025-04-07 110856](https://github.com/user-attachments/assets/17349e57-694d-4624-84ca-f3aceedc322e)
![Screenshot 2025-04-07 110922](https://github.com/user-attachments/assets/377772f5-2096-46be-a00d-57a9130ee0ab)

## RESULT:

Thus, The python program to find the optimal policy for the given MDP using the value iteration algorithm is successfully executed.

