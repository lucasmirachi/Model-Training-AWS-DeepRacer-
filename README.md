## Hyperparameter Tuning

This note describes each of the hyperparameters available in AWS DeepRacer and the implications they have for track performance. 

* Batch size: Defines how much of your training data your model should work through before each new update. In the case of AWS DeepRacer, it will basically determines how many images the model will use for training where the images are randomly sampled from the most recent experience.

![Batch Size](./images/batch_size.png)

* Epoch: This hyperparameter can sometimes be confused as batch size. While the batch size determines how much of the training to loop through before updating the model, the **epoch** determines how many times the algorithm will pass through the dataset before updating the training weights.

![Epoch](./images/epoch.png)

* Learning Rate: Controls the speed that the algorithm learns. 

![Learning Rate](./images/learning_rate.png)

* Exploration: This hyperparameter gives the option to find a balance between *exploitation* (when the algorithm makes decisions given the information it already has) and *exploration* (gathers additional information beyond whats already been collected). <mark>In Reinforcement Learning, this is a particularly important parameter since data is constantly beeing collected and sent back to your model. So the exploration can help preventing the model's neural network from beeing trapped in parts of the action space / local maximum. </mark>

![Exploration](./images/exploration.png)

* Entropy: It controls the degree of randomness of an action that your vehicle might take in a given situation. The larger the entropy, the more random actions the car will take for exploration, and vice versa.

![Entropy](./images/entropy.png)

* Discount Factor: <mark>The goal of the Reinforcement Learning algorithm is to maximize the sum of the rewards of the course of time.</mark> The discount factor specifies how much of the future reward contributes to the expected reward. With a small discount factor, the agent (your vehicle) will only consider immediate rewards while a large discount factor will make the agent consider long-term rewards.  

![Discount Factor](./images/discount_factor.png)

* Loss Type: Its a function used to update the network's weights. For AWS DeepRacer, we can choose between two loss types: Huber Loss and Mean Squared Error Loss. When you have convergence problems, it is recommended to use **Huber Loss**, and when convergence is not a problem and you just want to train faster, it is recommended to use **Mean Squared Error** loss.

![Loss Type](./images/loss_type.png)


* Number of episodes: Defines the number of tasks your algorithm will go through during training (and tasks are the loops your model runs through when the agent takes an action in the environment, changing the state and ultimately receiving a reward). <mark>In short, it defines how many times you'll go through this loop during training</mark>.
 