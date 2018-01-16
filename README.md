# gym-super-mario
#### **This is a environment bundle for OpenAI Gym. It allows AI agents to play Super Mario Bros. on the NES.**
---
Installation
============
You **must** have OpenAI Gym installed and a *envs* directory under your `python3.x/site-packages/gym/` directory. If you do not, **do not continue**. Install OpenAI Gym, then return here.

## Symlink Version
1. Git clone this repository to a empty directory. In this example, let's say `$HOME/Git/`.
```
cd $HOME/Git
git clone [replace this with repo url]
```
2. You will then have a folder that represents the git repository. It'll be called `gym-super-mario`. We need to symlink this inside the envs directory like so:

```
ln -s [repo directory path]/ppaquette_gym_super_mario $HOME/.local/lib/python3.x/site-packages/gym/gym_super_mario
```

3. You're done! That was a piece of cake, right?

## The gym-pull version
(This is the older method and may not work)

1. You need to first install [gym-pull](https://github.com/koltafrickenfer/gym-pull)

```shell
    pip install gym-pull
```
...and then at the python CLI interpreter:
```python
import gym
import gym_pull
# Only required once, envs will be loaded with import gym_pull afterwards
gym_pull.pull('github.com/koltafrickenfer/gym-super-mario')
env = gym.make('meta-SuperMarioBros-Tiles-v0')
```

After-clone Requirements
============
Add this to your `$HOME/.local/python3.x/site-packages/gym/envs/__init__.py` to finish your install, as gym_pull is depricated and does not completely work. Majority of the time it will self-destruct and report a segmentation fault after it actually did something.

```python
register(
	id='meta-SuperMarioBros-Tiles-v0',
	entry_point='gym.envs.gym_super_mario:MetaSuperMarioBrosEnv',
	kwargs={ 'draw_tiles': 1},
	reward_threshold=(3266 - 40),
	nondeterministic=True,	
)		
```

## You've successfully installed the Super Mario Bros environment. It is now ready for use.
