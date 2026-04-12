# AI co-maintainer plugin

This repository contains an AI co-maintainer plugin for GitHub repositories. The co-maintainer agent is designed to assist with regular maintenance work on GitHub, particularly focusing on reviewing pull request changes, assessing selected code against repository conventions, checking for code duplication, generating marketing materials of the project like social media posts, helping in improving project documentation and manuals, handling issues, and gaining deep understanding of the project to provide valuable feedback and insights and instructions.

> Tip: For the best experience please use the plugin with 'Claude Sonnet 4.6' or 'Claude Opus 4.6' or similar or newer and better models.

The co-maintainer agent is currently capable of performing:

- PR reviews - it may perform PR reviews either based on locally checked out branch or based on PR from GitHub Repo. 
- Generating marketing materials - it may generate social media posts and other promotional content for the project, such as LinkedIn posts.
- creating release blog posts - ... in progress
- handling issues - ... in progress 
- generating and maintaining project documentation - ... in progress
- providing instructions and insights about the project/codebase - ... in progress

## Setup

### VS Code

#### Plugin Setup

> Note: The below setup for VS Code might be change quite soon

Currently VS Code does not support installing plugin from other GitHub Repo then the approved or added plugin marketplaces, this might change very soon, but for now in order to use the plugin you need to clone this repository locally. Then open VS Code and use `Chat: Plugin Locations` setting to add the path to the cloned repository. After that you should be able to see `co-maintainer Agent` in the list of available plugins when using `Chat: Open Customizations` view, and together with this plugin you should see the related skills and agent.
In GitHub Copilot Chat view switch to `co-maintainer Agent` or use one of the custom prompts.

### GitHub CLI

In order to add the plugin to GitHub Copilot CLI simply run the Copilot CLI in terminal and run `/plugin install Adam-it/ai-co-maintainer-copilot-plugin`. After that use the `/agent` command to switch to `co-maintainer Agent`.

## Usage examples

// TODO

## Additional useful resources / other helpful tools 

- [Anvil](https://burkeholland.github.io/anvil/) - Anvil verifies every change before you see it builds, tests, lints, then has other AI models try to break it. You get proof, not promises.
- [promoptfoo](https://github.com/promptfoo/promptfoo) - picking best LLM for your prompt, testing prompts and AI tooling security vulnerabilities 
- [Impeccable](https://github.com/pbakaus/impeccable) - skills for reviewing and correcting application UIs
- [awesome copilot](https://github.com/github/awesome-copilot) - library with reusable agents, skills, prompts
