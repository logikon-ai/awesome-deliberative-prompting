# Awesome Deliberative Prompting

**>>> 🚧 UNDER CONSTRUCTION 🚧 <<<**

**Awesome deliberative prompting: How to ask LLMs to produce reliable reasoning and make reason-responsive decisions.**

> **deliberation**, n.
>
> The action of thinking carefully about something, esp. in order to reach a decision; careful consideration; an act or instance of this. (OED)


## Contents

- [Success Stories](#success-stories)
- [Prompting Patterns and Strategies](#prompting-patterns-and-strategies)
  - [Beyond "Let's think step by step"](#beyond-lets-think-step-by-step)
  - [Multi-Agent Deliberation](#multi-agent-deliberation)
  - [Reflection and Meta-Cognition](#reflection-and-meta-cognition)
- [Text Generation Techniques](#text-generation-techniques)
- [Self-correction](#self-correction)
- [Limitations, Failures, Puzzles](#limitations-failures-puzzles)
- [Datasets](#datasets-for-deliberative-prompting)
- [Tools and Frameworks](#tools-and-frameworks)


## Success Stories

Striking evidence for effectiveness of deliberative prompting.

* The original CoT paper, first to give clear evidence that deliberative prompting works. [🚧 refs]
* CoT improves performance of Flan-PaLM etc. by X% in most difficult Big-bench tasks. [🚧 refs]


## Prompting Patterns and Strategies 

Prompting strategies and patterns to make LLMs deliberate.


### Beyond "Let’s think step by step" 

* 🎓 👩‍💻 Plan-and-Solve Prompting. "Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought
Reasoning by Large Language Models." 2023-05-06. [[>paper](https://aclanthology.org/2023.acl-long.147.pdf)] [[>code](https://github.com/AGI-Edgerunners/Plan-and-Solve-Prompting)]
* 🎓 Note-Taking. "Learning to Reason and Memorize with Self-Notes." 2023-05-01. [[>paper](https://aclanthology.org/2023.acl-long.147.pdf)] [[>code](https://github.com/AGI-Edgerunners/Plan-and-Solve-Prompting)]
* 🎓 Deliberate-then-Generate improves text quality. "Deliberate then Generate: Enhanced Prompting Framework for Text Generation." 2023-05-31. [[>paper](https://arxiv.org/abs/2305.19835)]
* ReAct [🚧 refs]


### Multi-Agent Deliberation

Let one (or many) LLMs simulate a free controversy.

* 🎓 Leverage wisdom of the crowd effects through debate simulation. "Improving Factuality and Reasoning in Language Models through Multiagent Debate." 2023-05-23. [[>paper](https://arxiv.org/abs/2305.14325)] 


### Reflection and Meta-Cognition

Higher-order reasoning strategies that may improve first-order deliberation.

* 🎓 👩‍💻 Clarify→Judge→Evaluate→Confirm→Moderate Paradigm. "Metacognitive Prompting Improves Understanding in Large Language Models." 2023-08-10. [[>paper](https://arxiv.org/abs/2308.05342)] [[>code](https://github.com/EternityYW/Metacognitive-Prompting)]
* 🎓 👩‍💻 Find-then-simulate-an-expert-for-this-problem Strategy. "Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm." 2021-02-15. [[>paper](https://arxiv.org/abs/2102.07350)] [[>lmql](https://lmql.ai/playground/)] 


## Text Generation Techniques 

Text generation techniques, which can be combined with prompting patterns and strategies.

* 🎓 External guides that constrain generation of reasoning improve accuracy by up to 35% on selected tasks. "Certified Reasoning with Language Models." 2023-06-06. [[>paper]](https://arxiv.org/abs/2306.04031)
* 🎓 👩‍💻 Highly effective beam search for generating complex, multi-step reasoning episodes. "Tree of Thoughts: Deliberate Problem Solving with Large Language Models." 2023-05-17. [[>paper]](https://arxiv.org/abs/2305.10601) [[>code](https://github.com/princeton-nlp/tree-of-thought-llm)]
  * 👩‍💻 A minimalistic implementation of Tree-of-Thoughts as plain prompt. [[>code](https://github.com/dave1010/tree-of-thought-prompting)]
  * 👩‍💻 An experimental [LMQL](https://lmql.ai) implementation of Tree-of-Thoughts. [[>code](https://github.com/LachlanGray/lmql-tree-of-thoughts)]

## Self-Correction

Let LLMs self-correct their deliberation.

* 🎓 Excellent review about self-correcting LLMs, with application to unfaithful reasoning. "Automatically Correcting Large Language Models: Surveying the landscape of diverse self-correction strategies." 2023-08-06. [[>paper]](https://arxiv.org/abs/2308.03188) 


## Limitations, Failures, Puzzles

Things that don't work, or we don't understand.

* 🎓 Incorrect reasoning improves answer accuracy (nearly) as much as correct one. "Invalid Logic, Equivalent Gains: The Bizarreness of Reasoning in Language Model Prompting." 2023-07-20. [[>paper]](https://arxiv.org/abs/2307.10573) 
* 🎓 LLMs may systematically fabricate erroneous CoT rationales for wrong answers, NYU/Anthropic team finds. "Language Models Don't Always Say What They Think: Unfaithful Explanations in Chain-of-Thought Prompting." 2023-05-07. [[>paper](https://arxiv.org/abs/2305.04388)] 


## Datasets for Deliberative Prompting

Datasets containing examples of deliberative prompting, potentially useful for training models / assessing their deliberation skills.

* OASST [🚧 refs]
* ORCA [🚧 refs]


## Tools and Frameworks 

Tools and Frameworks to implement deliberative prompting.

* LMQL.ai [🚧 refs]
* Guidance [🚧 refs]