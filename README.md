# POLICY ITERATION ALGORITHM

## AIM
Write the experiment AIM.

## PROBLEM STATEMENT
Explain the problem statement.

## POLICY ITERATION ALGORITHM
```
import numpy as np

def policy_iteration(P, gamma=1.0, theta=1e-10):
    
    num_states = len(P)
    num_actions = len(P[0])
    
   
    pi = np.random.choice(num_actions, size=num_states)
    V = np.zeros(num_states, dtype=np.float64)  
    
    while True:
        V = policy_evaluation(pi, P, gamma, theta) 
        new_pi = policy_improvement(V, P, gamma)    
        
        if np.array_equal(pi, new_pi): 
            break
        
        pi = new_pi  
    return V, pi
optimal_V, optimal_pi = policy_iteration(P)
print("Name:Anusharon.S ")
print("Register Number: 212222240010 ")
print('Optimal policy and state-value function (PI):')
print_policy(optimal_pi, P, action_symbols=('<', '>'), n_cols=7)
def probability_success(env, pi, goal_state, n_episodes=1000, max_steps=100):
    results = []
    
    for _ in range(n_episodes):
        state, done, steps = env.reset(), False, 0
        
        while not done and steps < max_steps:
            action = pi[state]  
            state, _, done, _ = env.step(action)
            steps += 1
        
        results.append(state == goal_state)
    
    return np.mean(results)
def mean_return(env, pi, n_episodes=1000, max_steps=100):
    results = []
    
    for _ in range(n_episodes):
        state, done, steps = env.reset(), False, 0
        results.append(0.0)
        
        while not done and steps < max_steps:
            action = pi[state] 
            state, reward, done, _ = env.step(action)
            results[-1] += reward
            steps += 1
    
    return np.mean(results)
print('Reaches goal {:.2f}%. Obtains an average undiscounted return of {:.4f}.'.format(
    probability_success(env, optimal_pi, goal_state=goal_state)*100,
    mean_return(env, optimal_pi)))
print("Name:Anusharon.S      ")
print("Register Number:212222240010")
print_state_value_function(optimal_V, P, n_cols=7, prec=5)

```

## POLICY IMPROVEMENT FUNCTION
### Name
### Register Number
```python
Include the policy improvement function







```
## POLICY ITERATION FUNCTION
### Name
### Register Number
```python
Include the policy iteration function






```

## OUTPUT:
### 1. Policy, Value function and success rate for the Adversarial Policy
</br>
</br>

### 2. Policy, Value function and success rate for the Improved Policy
</br>
</br>

### 3. Policy, Value function and success rate after policy iteration
</br>
</br>


## RESULT:

Write your result here
