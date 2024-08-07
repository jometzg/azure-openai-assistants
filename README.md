# Azure OpenAI Assistants demonstration

A sample of using an OpenAI Assistant to use the code interpreter to solve a maths problem. This is based on this [Learn](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/assistant) documentation, but is a really simple maths problem.

This repo used the Visual Studio Code [REST client extension](https://github.com/Huachao/vscode-restclient) so that you can see the exact HTTP requests that go over the wire.

## The Scenario
This is a really simple maths problem of getting the square root of a number. Traditionally LLMs are not good at these problems. Assistants solve this by using some compute in a [sandboxed environment](https://learn.microsoft.com/en-us/azure/ai-services/openai/how-to/code-interpreter?tabs=python). This avoids issues of where an LLM could generate code that may be unsafe to run in a more conventional environment.

## The sample
It is best to clone this repo and run inside Visual Studio code with the REST client.

The HTTP requests will need your Azure OpenAI resource name, key and the name of a model deployment. I suggest you use gpt-4o for this as this is the model that this has been tested against.
There are also limits on the region's in which the assistants API is currently deployed. The example has been tested on Sweden Central.

[Request.http](./request.http)
