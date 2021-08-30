# Audio-visual deep reinforcement learning in image-oriented environments
## What is this repository? 
Created as a part of the Carnegie Vacation Scholarship project.

A deep reinforcement learning agent is like a little robot inside the computer that learns to do complicated things like flying a plane. Sometimes it is obvious what the agent needs to observe to solve the problem. For an agent to learn how to play chess, it needs to see the game board; to learn how to generate songs, it needs to listen to music. But it is not always the case. For example, do we allow the agent that drives a car to hear what is happening on the road? It could help to avoid road accidents in certain situations. But on the other hand, such an amount of information could also confuse it and lead to more crashes. Or maybe there is no difference at all? 
My project focuses on environments where audio does not need to be used to solve the problem but could potentially be valuable. The aim was to test a hypothesis and find out whether adding audio information has any effect on a sighted agent in such scenarios, and if so - what this effect is.

## How?
* The code that makes it possible to train an agent using audio from Atari 2600 emulator was written. 
* It can be accessed here: https://github.com/rienath/stable-baselines3/tree/gym-to-retro. 
* A lot of motivation behind it can be found here: https://github.com/DLR-RM/rl-baselines3-zoo/issues/133.
* The agents that can both hear and see and only see were trained in 3 image-oriented games using the PPO algorithm for 10M frames.
* notebooks/Experiment Launcher.ipynb has all the code for running the experiments.
* The games tested are Breakout, Centipede and VideoPinball.
* However, any game from the retro gym can be used with the code provided.
* If you want to experiment with audio-visual RL yourself, have a look at the example in notebooks/Audiovisual Retro RL Demonstration.ipynb.
* Score averages of each trial were computed using the 100 final episodes.
* The experiment was repeated 4 times with different random number generator seeds.
* The results of experiments (tfevent log files) can be found in __experiments__ folder.
* The experiment was repeated 4 times with different random number generator seeds.
* Welch’s t-test was performed to test the null hypothesis: *The provision of audio-visual information provides no significant advantage or disadvantage over visual-only information for deep reinforcement learning in image-oriented environments*

## Results
You can more information about the results in notebooks/Data Processing and Visualization.ipynb. Breakout and VideoPinball performed significantly worse with audio and video compared to just video. Centipede, on the other hand, performed better with audio but the difference was not significant at least with 4 repeats (p=0.054).

### Breakout
![image](https://user-images.githubusercontent.com/30183178/131376360-29f88322-b175-4e4c-9acc-d3a0dd71cb0f.png)
![image](https://user-images.githubusercontent.com/30183178/131376541-51d620fe-faaa-4b6f-944b-fe7e1a270d27.png)


### Centipede
![image](https://user-images.githubusercontent.com/30183178/131376454-38274bb0-6815-4f73-95d9-1f34c45397a7.png)
![image](https://user-images.githubusercontent.com/30183178/131376578-27790a1e-38aa-4c50-8d3b-840499c68897.png)


### VideoPinball
![image](https://user-images.githubusercontent.com/30183178/131376485-b245553a-bb05-4ea0-8492-64b80bd4f148.png)
![image](https://user-images.githubusercontent.com/30183178/131376607-aeac91c3-81d8-4e14-a199-60a1b957da94.png)
