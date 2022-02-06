# Continuous Control Project
# Udaicity Nanodegree - Deep Reinforcement Learning

## Introduction

The Continouus Control project solves an environemnt where the agent - a double-jointed arm - has the task mantain contact with a target location idicated by a ball.

### Rewards
`+0.1` for each time step at the target position 

### Actions 
The exact actions are not forther defined. Each postion in the action vector should have a value betwenn `0` and `1`.

### State
defined by a 33 dimensional vector (position, rotation, velocity, and angular velocities of the arm)

### Goal
Average score of +30 over 100 consecutive episodes

## Requirements
A detailed description on how to set up the environment and install the needed dependencies can be found on the GitHub page of the [deep reinfocement learning nanodegree](https://github.com/udacity/deep-reinforcement-learning#dependencies).

## Setup Guide
The Unity environment is already prepacked and can be downloaded using the following link:

 - [Linux](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Linux.zip)
 - [Mac OSX](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher.app.zip)
 - [Windows (32-bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86.zip)
 - [Windows (64-bit)](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/one_agent/Reacher_Windows_x86_64.zip)
