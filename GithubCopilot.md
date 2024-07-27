# Introduction

Github Copilot uses a couple of handy tag words to reference specific content. Here are a few:

- `@workspace`: sends information about current project and all contained files and folder structure
- `#file:[FILENAME]`: provides one specific file and its content

# Prompts

## Q&A Strategy Prompt

Helps with letting the AI improve your prompt by providing you with questions to think about that you didn't consider in the beginning. This is great because it captures the AI thinking as well and makes you aware of missing details for a correct prompt to get exactly what you want.

```
@workspace propose a file/folder structure for this project. Ask me a series of yes/no questions that will help you provide a better recommendation.
```

## Pros and Cons Prompt

Helps to provide well-rounded information.

```
What are a few different ways that I can implement this db connection logic? Give me the pros and cons of each strategy.
#file:db.ts
```

## Stepwise Chain of Thought Prompt

Introducing a little bit of more control over the AI output. Making it to break things down in chunks is especially helpful when asking for a big task. Using a keyword as a control mechanism to keep the conversation steered until the task is done.

_NOTE_ if you have to ask questions inbetween you will break the chain of thought and lose the connection to the keyword. In this case simply delete your intermittent questions from the chat memory.

```
Help me refactor the code in #file:vehiclesService.ts . Go one step at a time. Do not move to the next step until I give the keyword "next". Begin.
```

## Role Prompts (and Stepwise Chain of Thought)

These can help to give the AI a better context and speciality from the start and also sets the tone of the conversation making room for a very personalized experience.

```
You are a skilled instructor who makes complex topics easy to understand. You come up with fun exercises so that your students can learn by doing. Your goal is to teach students to be proficient with [TOPIC]. Move one step at a time and wait for the student to provide the correct answer before you move on to the next concept. If the student provides the wrong answer, give them a hint. Begin.
```

# References

This helpful collection was written up by myself from the following resources.

- Visual Studio Code - [Essential AI prompts for developers](https://www.youtube.com/watch?v=H3M95i4iS5c&list=LL)
