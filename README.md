**Reenforcement leraring** : is an area of machine learing conceted with how software agents ought to take actions in an evniroment in order to maximumze the notion of cumulative reward.

or RL is teaching a software agent how to behave in an environment by telling it how good its doing.

loss_fn = > bellman 



### model used 

this game uses Deep Q-Network(DQN) model for Reinforcement learing (RL) . 

**overview:what is DQN?**

- *deep q networks* are a type of reinformcement learning model where an agent learns to take actions in an environment to maximize cumulative rewards overt time.

- instead fo maintaing a Q table ( used in traditinal Q-learning) , the agent uses a neural network to approximate the Q-values for state action pairs.

**components of the code**

**linear_qnet class** 
this class defines the nerual network architecture for the Q function aproximation.


** attributes**
  - `linear1`: a fully connected (dense) layer that mps the `input_size` to a hidden layer of size `hidden_size`

  - `linear2`: another fully connected layer that maps the hidden layer to the `output_size`, represnting q-values for all possible actions.


**forward pass**
  - input `X` goes through `linear1` and applies the *RELU activation function*
  - the output of `linear1` is passed to `linear2` to compute the final q-values.
**save method**
  - saves the models weights (`state_dict()`) toa file (`model.pth`) i a directory called `./model`
** QTrainer Class **

this class hanles the training process for th model using Q-learning principles
** attributes:**
- model: the neural network ( an instance of Linear_qnet).
- lr: learning rate for the optimizer.
- gamma: discount factor for future rewards.
- optimzer: an adam optimzer that updates the model parameters during training .
- criterion: the loss fuction , specifically mean squred error to calcuate the difference etween predicted q-values and target q-values.


