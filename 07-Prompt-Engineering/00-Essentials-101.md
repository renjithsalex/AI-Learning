# How to Get LLMs to Do What You Want

![LLM Prompt Engineering](https://images.unsplash.com/photo-1620712943543-bcc4688e7485?q=80&w=1200)

## Table of Contents
- [Introduction](#introduction)
- [What's an LLM?](#whats-an-llm)
- [What is a Prompt?](#what-is-a-prompt)
- [What is Prompt Engineering?](#what-is-prompt-engineering)
- [How to Improve Results When Prompting LLMs](#how-to-improve-results-when-prompting-llms)
- [Prompt Engineering Best Practices](#prompt-engineering-best-practices)
- [Your Next Steps](#your-next-steps)

## Introduction

LLMs are powerful, and the way we interact with them via prompts matters. For example, have you ever tried asking an LLM a question, but it can't really figure out what you're trying to ask? Understanding the power of prompts (and the limitations that come with them) can help you become even more productive.

In this post, we'll explore:
- How LLMs work and how prompts are processed.
- How to engineer the most effective prompts.
- How to troubleshoot prompts when we don't get the outcomes we want.

## What's an LLM?

Large language models are a type of AI that are trained on a large (hence the name) amount of text data to understand and generate human-like language.

By predicting the next word in a sentence based on the context of the words that came before it, LLMs respond to humans in a way that is relevant and coherent. Sort of like an ultra-smart autocomplete!

When it comes to using LLMs, there are three important things to understand:

1. **Context**: This is the surrounding information that helps an LLM understand what you're talking about. Just like when you have a conversation with a friend, the more context you offer, the more likely the conversation will make sense.

2. **Tokens**: For LLMs, text is broken down into units of tokens. This could be a word, part of a word, or even just one single letter. AI models process tokens to generate responses, so the number of tokens you use with an LLM can impact its response. Too few tokens can lead to a lack of context, but too many could overwhelm the AI model or run into its built-in token limits.

3. **Limitations**: LLMs are powerful, but not all-powerful. Instead of understanding language like humans, LLMs rely on patterns and probabilities from training data. Taking a deeper dive into training data is beyond the scope of this post, but as a general rule, the ideal data set is diverse and broad. Models are never perfect—sometimes they can hallucinate, provide incorrect answers, or give nonsensical responses.

## What is a Prompt?

A prompt is a natural language request that asks an LLM to perform a specific task or action. A prompt gives the model context via tokens, and works around the model's potential limitations, so that the model can give you a response. 

> **Example**: If you prompt an LLM with "Write a JavaScript function to calculate the factorial of a number," it will use its training data to give you a function that accomplishes that task.

Depending on how a specific model was trained, it might process your prompt differently, and present different code. Even the same model can produce different outputs. These models are **nondeterministic**, which means you can prompt it the same way three times and get three different results. This is why you may receive different outputs from various models out in the world, like OpenAI's GPT, Anthropic's Claude, and Google's Gemini.

Now that we know what a prompt is, how do we use prompts to get the outputs we want?

## What is Prompt Engineering?

Imagine that a friend is helping you complete a task. It's important to give them clear and concise instructions if there's a specific way the task needs to be done. The same is true for LLMs: a well-crafted prompt can help the model understand and deliver exactly what you're looking for. The act of crafting these prompts is **prompt engineering**.

That's why crafting the right prompt is so important: when this is done well, prompt engineering can drastically improve the quality and relevance of the outputs you get from an LLM.

### Key Components of Effective Prompting:

- ✅ An effective prompt is **clear and precise**, because ambiguity can confuse the model.
- ✅ It's important to provide enough **context**, but not too much detail, since this can overwhelm the LLM.
- ✅ If you don't get the answer you're expecting, don't forget to **iterate and refine** your prompts!

### Let's Try It Out!

#### Example: How to Refine Prompts to Be More Effective

Imagine you're using GitHub Copilot and say: 

> *"Write a function that will square numbers in a list in a new file with no prior code to offer Copilot context."*

At first, this seems like a straightforward and effective prompt. But there are a lot of factors that aren't clear:
- What language should the function be written in?
- Do you want to include negative numbers?
- Will the input ever have non-numbers?
- Should it affect the given list or return a new list?

How could we refine this prompt to be more effective? Let's change it to:  

> *"Write a Python function that takes a list of integers and returns a new list where each number is squared, excluding any negative numbers."*

This new prompt is clear and specific about:
- The language (Python)
- What the function should do (square numbers)
- What constraints there are (exclude negatives)
- The expected input type (list of integers)
- The expected output (a new list)

When we give GitHub Copilot more context, the output will be better aligned with what we want from it!

Just like coding, prompt engineering is about effective communication. By crafting your prompts thoughtfully, you can more effectively use tools like GitHub Copilot to make your workflows smoother and more efficient. That being said, working with LLMs means there will still be some instances that call for a bit of troubleshooting.

## How to Improve Results When Prompting LLMs

As you continue working with GitHub Copilot and other LLM tools, you may occasionally not get the output you want. Oftentimes, it's because your initial prompt wasn't specific enough. Here are a few scenarios you might run into when prompting LLMs.

### 1. Prompt Confusion

It's easy to mix multiple requests or be unclear when writing prompts, which can confuse the model you're using. Say you highlight something in Visual Studio Code and tell Copilot:  

> *"Fix the errors in this code and optimize it."*

Is the AI supposed to fix the errors or optimize it first? For that matter, what is it supposed to optimize for? Speed, memory, or readability?

#### Solution:
Break your prompt down into concrete steps with context:

> *"First, fix the errors in the code snippet. Then, optimize the fixed code for better performance."*

Building a prompt iteratively makes it more likely that you'll get the result you want because the specific steps the model needs to take are more clear.

### 2. Token Limitations

Remember, tokens are units of words or partial words that a model can handle. But there's a limit to how many tokens a given model can handle at once (this varies by model, too—and there are different models available with GitHub Copilot). 

If your prompt is too long or the expected output is very extensive, the LLM may:
- Hallucinate
- Give a partial response
- Fail entirely

#### Solution:
- Keep your prompts concise
- Iterate on smaller sections
- Only provide necessary context
- Break large tasks into smaller components

> **Ask yourself**: Does the LLM actually need an entire code file to return your desired output, or would just a few lines of code in a certain function do the trick? Instead of asking it to generate an entire application, can you ask it to make each component step-by-step?

### 3. Assumption Errors

It's easy to assume that the LLM knows more than it actually does. If you say *"Add authentication to my app"*, does the model know:
- What your app does?
- Which technologies you're using?
- What authentication methods you prefer?

#### Solution:
Explicitly state your requirements by:
- Outlining specific needs
- Mentioning technologies and preferences
- Including context about your application
- Specifying any constraints or best practices

By stating your requirements clearly, you'll help ensure the LLM doesn't overlook critical aspects of your request.

## Prompt Engineering Best Practices

Prompt engineering can be tricky to get the hang of, but you'll get better the more you do it. Here are some best practices to remember when working with GitHub Copilot or any other LLM:

| Best Practice | Description |
|---------------|-------------|
| **Provide Context** | Give the model enough information while considering any limitations it might have |
| **Be Clear & Concise** | Prompts should be clear, specific, and precise for the best results |
| **Break Down Tasks** | If you need multiple tasks completed, break down your prompts into smaller chunks |
| **Be Specific** | Clearly state your requirements and constraints so the model understands exactly what you need |
| **Iterate** | If at first you don't get what you want, refine your prompt and try again |

## Your Next Steps

We covered quite a bit when it comes to prompt engineering:
1. What LLMs are and why context is important
2. How to define and craft effective prompts
3. Common pitfalls when working with large language models and how to avoid them

### Additional Resources

If you want to watch this demo in action, we've created a [YouTube tutorial](https://www.youtube.com) that accompanies this blog.

If you have any questions, pop them in the [GitHub Community thread](https://github.com/community) and we'll be sure to respond.

---

