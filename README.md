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
