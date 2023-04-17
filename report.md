## Collaboration/Competition - Technical report
-------------------------------------------

Ramaiah Radhakrishnan
Apr 16 2023

-----------------------------

### Learning Algorithm

I was adopting the [Lowe and Wu et al](https://papers.nips.cc/paper/7217-multi-agent-actor-critic-for-mixed-cooperative-competitive-environments.pdf) 
Multi Agent Deep Detrministic Policy Gradient with decentralized actor and centralized critic. Both actor and critc neural network included two hidden layers
512 and 256 nodes respectively. I had to include batch normalization to control the high swings (instabilty) on the intial episode runs.

### Hyperparameters

I had to adjust the buffer_size and Learning rates for both actor and critic to stabilize the learning. My first attempt with 
hidden layers 256, 128 with buffersize int(1e6) and critic learning rate 3e-4 resulted in divergence withing the first 20 episode run. I had to stop the 
run and played with those four hyperparaments till I settled on the below.

BUFFER_SIZE = int(1e6)  # replay buffer size

BATCH_SIZE = 512        # minibatch size

GAMMA = 0.99            # discount factor

TAU = 1e-3              # for soft update of target parameters

LR_ACTOR = 1e-4         # learning rate of the actor 
LR_CRITIC = 1e-3        # learning rate of the critic

WEIGHT_DECAY = 0   # L2 weight decay

I also added noice epsilon decay for the initial 500 episodes to anable exploration for learning.
EPS_START = 5.0        # Intial value of epsilon

EPS_LEARN = 5

EPS_EP_END = 500       ## Number of episodes to end the noice decay

EPS_FINAL = 0.         # Final EPS value

### Plot of the scores (Results)

The plof of the scores at the time of the project goal is reached here

<img src="https://github.com/rradhakr-git/UdacityCollaborationCompetition/blob/main/Tennis_score.png?raw=true"/>

<img src="[https://github.com/rradhakr-git/UdacityColloborationCompetition/blob/main/Tennis_score.png](https://github.com/rradhakr-git/UdacityCollaborationCompetition/blob/main/Tennis_score.png)?raw=true"/>



### Future Work

 
 I want to get comfortable with building the unity environment in my own setup. 
 
 I also want to try 4 agents with doubles tennis with two agents colloborating to compete against two other agents.
