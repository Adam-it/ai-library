# AI Library

## Overview

The aim of this repo is to store different AI approaches and techniques I use with GitHub Copilot in VS Code and CLI. 

The repo showcase reusable agents, skills and prompts that help me with my maintainers work.

## Features

### PR reviewer

This feature consists of an reusable prompt which is your starting point to perform full review of the changes made in the PR. The prompt inits the pr-review agents which has defined the specific role and uses the pr-review skill to perform the review and provide structured feedback. 

You may also perform review on specific files or selection instead of on the full PR. In this case the pr-review skill may be used by Github Copilot agent mode.

### Feature builder

This is a set of agents present in the `feature-builder-team` folder which are designed to work together to help you build a new feature. In order to use it you should start with the `build-feature` prompt which will add additional instructions to your prompt to use the feature builder team agents. Use this reusable prompt together with the description of your feature.

### Marketing posts generator

This is a reusable prompt which you can use to generate social media posts to promote your project/product. 

## How to use

This repo is just a collection of markdown files, each describing a different agent, skill or prompt. Once you find something interesting, you can copy the relevant markdown content and configure it to use it locally in your own project or (recommended) setup it globally so that it may be used between different projects.

## Global setup guidance 

> Note: ATM custom agents and skills are considered a preview feature of VS not yet available in the insiders version yet.
> Note: GitHub CLI retrieves skills from the same location as VS Code, but does not support 

### VS Code setup

#### Agents

In order to configure an agent globally in VS Code 

1. hit `Chat: Configure Custom Agent` command 
2. select `Create new custom agent`
3. select `User Data` 
4. set the name of the agent as the `name` property defined in the markdown file
5. copy the content of the markdown file

#### Skills

In order to configure a skill globally in VS Code

1. hit `Chat: Configure Skills` command
2. select `New skill`
3. select `<your-user-path>/.copilot/skills` folder
4. set the name
5. copy the content of the markdown file

#### Prompts

In order to configure a reusable prompts globally in VS Code

1. hit `Chat: Configure Prompt Files` command
2. select `New prompt file`
3. select `User Data` 
4. set the name
5. copy the content of the markdown file

### GitHub CLI

// ToDo

## Additional useful resources 

- [Anvil](https://burkeholland.github.io/anvil/) - Anvil verifies every change before you see it builds, tests, lints, then has other AI models try to break it. You get proof, not promises.
