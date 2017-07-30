# gym-super-mario
#### **Gym Super Mario is an environment bundle for OpenAI Gym**
---
<div id="installation"></div>Installation
============

You need to install [gym-pull](https://github.com/koltafrickenfer/gym-pull)

```shell
    pip install gym-pull
```

 To load and run the environments, run

```python
    import gym
	import gym_pull
	gym_pull.pull('github.com/koltafrickenfer/gym-super-mario')        # Only required once, envs will be loaded with import gym_pull afterwards
	env = gym.make('meta-SuperMarioBros-Tiles-v0')
```

Add this to your python3.5/site-packages/gym/envs/__init__.py to finish your install, gym_pull is depricated and does not completly work.
```python
	register(
	id='meta-SuperMarioBros-Tiles-v0',
	entry_point='gym.envs.gym_super_mario:MetaSuperMarioBrosEnv',
	kwargs={ 'draw_tiles': 1},
	reward_threshold=(3266 - 40),
	nondeterministic=True,
	
)		
```
