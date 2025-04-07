# POLICY ITERATION ALGORITHM

## AIM
To develop a Python program to find the optimal policy for the given MDP using the policy iteration algorithm.


## PROBLEM STATEMENT
The aim of this experiment is to find optimal policy for the mdp using policy iteration. Policy iteration includes policy evaluation and policy improvement where evaluation function is used to find optimal value function of each state and then improvement function is used to find best policy by comparing all the action value function as well as policy.
## POLICY ITERATION ALGORITHM

# Step1 :
we are going to do policy evaluation of each state to get the state value function where the initial policy is defined randomly to the mdp.

# Step2:
Once we obtain convergence in the policy evaluation then implement policy improvement where we are going to find best optimal policy until the previous and current policy are same

## POLICY IMPROVEMENT FUNCTION
### Name: ANUSHARON S
### Register Number:212222240010
```
def policy_improvement(V, P, gamma=1.0):
  Q=np.zeros((len(P),len(P[0])))
  for s in range(len(P)):
      for a in range(len(P[s])):
          for prob, next_state, reward, done in P[s][a]:
              Q[s][a] += prob * (reward + gamma * V[next_state] * (not done))
  new_pi = lambda s: {s:a for s, a in enumerate(np.argmax(Q, axis=1))}[s]
  return new_pi

```
## POLICY ITERATION FUNCTION
### Name: ANUSHARON S
### Register Number: 212222240010
```
def policy_iteration(P, gamma=1.0, theta=1e-10):
    pi = lambda s: np.random.choice(list(P[s].keys()))  # Initialize with a random policy
    while True:
        V = policy_evaluation(pi, P, gamma, theta)  # Evaluate policy
        new_pi = policy_improvement(V, P, gamma)   # Improve policy
        if all(pi(s) == new_pi(s) for s in range(len(P))):  # Check convergence
            break
        pi = new_pi  # Update policy
    return V, pi
```

## OUTPUT:
### 1. Policy, Value function and success rate for the Adversarial Policy
![Screenshot 2025-04-07 105017](https://github.com/user-attachments/assets/1551e697-8c0c-44d3-b228-0f6b7c2cc455)
![Screenshot 2025-04-07 105053](https://github.com/user-attachments/assets/bddca6e4-8740-4ec3-8315-4033468e25d9)
![Screenshot 2025-04-07 105117](https://github.com/user-attachments/assets/071c4e07-db3b-49ea-ab22-c9afe7ff4846)


### 2. Policy, Value function and success rate for the Improved Policy
![Screenshot 2025-04-07 104827](https://github.com/user-attachments/assets/e6593075-7b3e-454a-aec8-784c3a586098)
![Screenshot 2025-04-07 104859](https://github.com/user-attachments/assets/899fcc52-abc5-44d8-9ae2-845284882580)
![Screenshot 2025-04-07 104924](https://github.com/user-attachments/assets/93c7896e-c948-41b6-9675-b3de8a120d6d)


### 3. Policy, Value function and success rate after policy iteration
![Screenshot 2025-04-07 104645](https://github.com/user-attachments/assets/13737f1f-a74f-4e40-bea9-9f5a162b9458)
![Screenshot 2025-04-07 104718](https://github.com/user-attachments/assets/7e9b1a36-749f-49b0-939f-238cf348208b)

![Screenshot 2025-04-07 104741](https://github.com/user-attachments/assets/6c65018d-dc9a-414a-b6f0-a9b301138e44)


## RESULT:

Thus, The Python program to find the optimal policy for the given MDP using the policy iteration algorithm is successfully executed.
