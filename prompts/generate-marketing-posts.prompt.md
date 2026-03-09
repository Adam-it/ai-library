---
description: "Generate social media posts"
agent: agent
model: [Claude Opus 4.6 (copilot), 'Claude Sonnet 4.6 (copilot)']
tools: [read, agent, search, web, 'context7/*']
---


## Aim

Your task is to generate 5-10 short social media post to promote the current project/product. Each post should be concise, engaging, and highlight one of the key features of the product. Use a friendly and professional tone suitable for developers and tech enthusiasts and use emojis. 
Your content should be generated based on the project `README.md` file and docs from the `./docs/src` folder.
Each of the key features should have a link to the relevant documentation page, so users can learn more about it.

## Criteria

- use Microsoft 365 product related hashtags like #SharePointOnline, #PowerApps... if needed. 
- always include #Microsoft365Dev hashtag
- use between 500 and 1500 characters for each post
- highlight one key feature per post
- include a call to action, encouraging users to try the extension or visit the documentation
- do NOT create any files in the repository, just return the posts as a response
- put each blog post in your response in a separate code block

## Context Tips

- always use `README.md` as context
- always use docs from `./docs/src` folder as context
- use context7 tools to get the relevant information about the project and its features
