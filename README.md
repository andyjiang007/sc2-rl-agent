# Deep RL Agents with PySC2

This repository implements a A2C agent baseline for the
[pysc2](https://github.com/deepmind/pysc2/)
environment as described in the DeepMind paper
[StarCraft II: A New Challenge for Reinforcement Learning](https://deepmind.com/documents/110/sc2le.pdf).
We use a synchronous variant of A3C (A2C) to effectively train on GPUs and
This repository is part of a course project for CS229 Fall 2018 with An Jiang (jianga@stanford.edu)

### License

This project is licensed under the MIT License (refer to the LICENSE file for details).

## Results

On the mini games, we get the following results:

| Map | mean score (DeepMind) | mean score (ConvLSTM) |
| --- | --- | --- |
| MoveToBeacon | 26 | 26 |
| FindAndDefeatZerglings | 45 | 48 |

The score are collected from 3 indepedently trained agents with 5 individual test runs on the mini-gameis.

## Usage

### Software Requirements
- Python 3
- pysc2 (tested with v1.2)
- TensorFlow (tested with 1.4.0)
- StarCraft II and mini games (see below or
  [pysc2](https://github.com/deepmind/pysc2/))

### Quick Install Guide
- `pip install numpy tensorflow-gpu pysc2==1.2`
- Install StarCraft II. On Linux, use
[3.16.1](http://blzdistsc2-a.akamaihd.net/Linux/SC2.3.16.1.zip).
- Download the
[mini games](https://github.com/deepmind/pysc2/releases/download/v1.2/mini_games.zip)
and extract them to your `StarcraftII/Maps/` directory.

### Train & run
- run and train: `python run.py my_experiment --map MoveToBeacon`.
- run and evalutate without training: `python run.py my_experiment --map MoveToBeacon --eval`.

Summaries are written to `out/summary/<experiment_name>`
and model checkpoints are written to `out/models/<experiment_name>`.


## Acknowledgments
The code in `rl/environment.py` is based on
[OpenAI baselines](https://github.com/openai/baselines/tree/master/baselines/a2c),
with adaptions from
[sc2aibot](https://github.com/pekaalto/sc2aibot)
and
[pysc2-rl-agents](https://github.com/simonmeister/pysc2-rl-agents).
Some of the code in `rl/agents/a2c/runner.py` is loosely based on
[sc2aibot](https://github.com/pekaalto/sc2aibot).
