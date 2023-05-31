# Prompt Engineering Programming Patterns by Damien Benveniste

* Asking direct questions to the LLM is called **zero-shot prompting** 
* Adding few examples in the prompt is called **few-shot prompting**
* Adding reasoning in a few-shot prompt that leads to a specific answer is called **"Chain of thoughts"** (https://arxiv.org/pdf/2201.11903.pdf). 
* Adding similar behavior in zero-shot by prompting it to "think step by step" is referred to as **"Inception".** 
* "Chain of Thoughts" can take the form of intermediate questions and answers. This is called **"Self-ask"** (https://ofir.io/self-ask.pdf). 
* Asking LLM to act as an Assistant or a Physics Professor is called **"Memetic Proxy"** (https://arxiv.org/pdf/2102.07350.pdf). 
* Choosing a consistent answer over multiple queries increases the quality of the answers is called **"Self-consistency"** (https://arxiv.org/pdf/2203.11171.pdf)
* If you exchange multiple messages with the LLM, it is a good idea to use a memory pattern (https://arxiv.org/pdf/2201.06009.pdf) such that it can refer to previous interactions.

It becomes interesting when LLMs are given access to tools or databases. Based on questions they can decide to use tools. We can provide examples of question-action pairs (e.g. "What is the age of the universe?" -> [search on Wikipedia]) and this is called "Act". We get better results with "ReAct" (https://arxiv.org/pdf/2210.03629.pdf) when we induce intermediate thoughts from the LLM (e.g. "What is the age of the universe?" -> "I need to find more information on the universe" -> [search on Wikipedia]).

You can chain prompts (https://arxiv.org/pdf/2203.06566.pdf)! For example, you can prompt for using a tool, extract the information coming from the tool API call in the following prompt and use the result in the next prompt to answer the initial question. You can solve complex problems by inducing a plan of action (https://say-can.github.io/assets/palm_saycan.pdf). Each step of the plan can be used to generate its own chain of actions using ReAct. For example, AutoGPT is using the "Plan and execute" pattern on autopilot to solve complex problems. I guarantee that "Plan and execute" will be the source of many new startups in the coming years!

LLMs can be thought of as some sort of flexible subroutines taking inputs and producing outputs. Prompts are the molds that shape the subroutines to solve a specific problem. LLM applications consist of piecing together those subroutines to build novel capabilities.

![patterns](https://github.com/ArslanKAS/Prompt-Engineering-by-OpenAI/blob/master/Patterns/prompt_patterns.jpg)
