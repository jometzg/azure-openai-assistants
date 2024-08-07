# Azure OpenAI Assistants demonstration

A sample of using an OpenAI Assistant to use the code interpreter to solve a maths problem. This is based on this [Learn](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/assistant) documentation, but is a really simple maths problem.

This repo used the Visual Studio Code [REST client extension](https://github.com/Huachao/vscode-restclient) so that you can see the exact HTTP requests that go over the wire.

## The Scenario
This is a really simple maths problem of getting the square root of a number. Traditionally LLMs are not good at these problems. Assistants solve this by using some compute in a [sandboxed environment](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/code-interpreter?tabs=python). This avoids issues of where an LLM could generate code that may be unsafe to run in a more conventional environment.

## Prerequisites
There are limits on the region's in which the assistants API is currently [deployed](https://learn.microsoft.com/en-us/answers/questions/1694320/assistants-is-only-available-in-the-following-regi). The example has been tested on Sweden Central.

The HTTP requests will need your Azure OpenAI resource name, key and the name of a model deployment. I suggest you use gpt-4o for this as this is the model that this has been tested against.

## The sample
It is best to clone this repo and run inside Visual Studio code with the REST client.

[Requests.http](./requests.http)

## The Steps
The steps in this demo are marked in the requests.http file, but are described below in a little more detail.

1. STEP 1 - this creates the [assistant](https://learn.microsoft.com/en-us/azure/ai-services/openai/assistants-reference?tabs=python#create-an-assistant), gives it the instructions (AKA system prompt) and tells it to use the code interpreter. This returns an *assistant_id* which can be used later.
2. STEP 2 - this creates a [thread](https://learn.microsoft.com/en-us/azure/ai-services/openai/assistants-reference-threads?tabs=python), which is used to manage an overall conversation thread with the assistant.
3. STEP 3 - this creates a [message](https://learn.microsoft.com/en-us/azure/ai-services/openai/assistants-reference-messages?tabs=python#create-message) which is where we send the ask to the assistant. in this case "what is the square root of 16"
4.  
