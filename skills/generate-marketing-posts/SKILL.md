---
name: generate-marketing-posts
description: "Generate 5-10 short social media posts to promote a given locally checked out repo/project"
---

# Generate Marketing Posts Skill

## Aim

Your task is to generate 5-10 short social media posts to promote a locally checked out repository. Each post should be concise, engaging, and highlight one of the key features of the project. Use a friendly and professional tone suitable for developers and tech enthusiasts and use emojis.

## Context Gathering

Before generating posts, gather context about the repository:

1. Read the project `README.md` file to understand the project's purpose, features, and target audience.
2. Search for a documentation folder (e.g., `docs/`, `documentation/`, `wiki/`) and read available docs to understand the key features in depth.
3. Check for a project website or homepage URL in the README or `package.json`/config files — use it for linking in posts.
4. Identify the project's tech stack, primary language, and ecosystem to tailor hashtags appropriately.

## Criteria

- choose relevant hashtags based on the project's tech stack and ecosystem (e.g., #TypeScript, #React, #DotNet, #OpenSource, etc.)
- use between 500 and 1500 characters for each post
- highlight one key feature per post
- include a call to action, encouraging users to try the project, star the repo, or visit the documentation
- where possible, include a link to the relevant documentation page or repo section so users can learn more
- do NOT create any files in the repository, just return the posts as a response
- put each post in your response in a separate code block
