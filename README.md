# AI co-maintainer plugin

This repository contains an AI co-maintainer plugin for GitHub repositories. The co-maintainer agent is designed to assist with regular maintenance work on GitHub, particularly focusing on reviewing pull request changes, assessing selected code against repository conventions, checking for code duplication, generating marketing materials of the project like social media posts, helping in improving project documentation and manuals, handling issues, and gaining deep understanding of the project to provide valuable feedback and insights and instructions.

The co-maintainer agent is currently capable to perform:

- PR reviews - it may perform PR reviews either based on locally checked out branch or based on PR from GitHub Repo. 
- Generating marketing materials - it may generate social media posts and other promotional content for the project, such as LinkedIn posts.
- handling issues - ... in progress 
- generating and maintaining project documentation - ... in progress
- providing instructions and insights about the project/codebase - ... in progress

## Setup

### VS Code

#### Plugin Setup

The easiest way to configure this plugin in VS Code is by opening the chat customization view by executing the VS Code command `Chat: Open Customizations`, then go to the plugin tab and hit the `+` button to add a new plugin. After that provide the GitHub repository URL of this plugin `https://github.com/Adam-it/ai-co-maintainer-plugin` and hit enter. After that you should see a new agent and skills in the chat customizations view. 
In GitHub Copilot Chat view switch to `co-maintainer Agent` or use one of the custom prompts.

#### Prompts

In order to configure a reusable prompts globally in VS Code

1. hit `Chat: Configure Prompt Files` command
2. select `New prompt file`
3. select `User Data` 
4. set the name
5. copy the content of the markdown file

### GitHub CLI

// TODO

## Usage examples

// TODO

## Additional useful resources / other helpful tools 

- [Anvil](https://burkeholland.github.io/anvil/) - Anvil verifies every change before you see it builds, tests, lints, then has other AI models try to break it. You get proof, not promises.
- [promoptfoo](https://github.com/promptfoo/promptfoo) - picking best LLM for your prompt, testing prompts and AI tooling security vulnerabilities 
- [Impeccable](https://github.com/pbakaus/impeccable) - skills for reviewing and correcting application UIs
- [awesome copilot](https://github.com/github/awesome-copilot) - library with reusable agents, skills, prompts
