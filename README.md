# RL-for-robotic-grasp-orientation


pip install mujoco-py==0.5.7
pip install gym[Robotics]
pip install gym[MuJoCo]
pip install gym[box2d]
pip install gym[atari]
import gym
gym.make('CartPole-v0')
gym.make('Breakout-v0') # to test Atari environment
gym.make('LunarLander-v2') # to test Box2D environment

# Finalized project
import gym
from gym import envs
print(envs.registry.all())

## Create an environment
env = gym.make("HandManipulateEggRotate-v0")

max_ep = 10 # maximum number of episodes to loop over
for ep_cnt in range(max_ep):
	step_cnt = 0 # tracks number of steps taken in an episode
	ep_reward = 0 # tracks total reward accumulated in an episode
	done = False # boolean flag indicating if terminal state is reached
	state = env.reset() # first observation read from the environment on initialization

	while not done: # loop over agent-environment interactions until terminal state is reached, i.e. episode ends 
		next_state, reward, done, _ = env.step(env.action_space.sample()) # perform a random action within the environment
		env.render() # render a frame showing state of environment in a human-friendly format
		step_cnt += 1
		ep_reward += reward
		state = next_state

	print('Episode: {}, Step count: {}, Episode reward: {}'.format(ep_cnt, step_cnt, ep_reward))
env.close()

import gym

env = gym.make('CartPole-v0')
state = env.reset()

action = env.action_space.sample() # similar to having a random agent, i.e., an agent that performs only random actions and does not learn anything
next_state, reward, done, info = env.step(action)

# To observe the information captured in each of the variables
print('State: '.format(state))
print('Action: '.format(action))
print('Next state: {}; Reward: {}; Done: {}; Info: {}'.format(next_state, reward, done, info))












