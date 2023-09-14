# Awesome Deliberative Prompting [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

**>>> 🚧 UNDER CONSTRUCTION 🚧 <<<**

**How to ask Large Language Models (LLMs) to produce reliable reasoning and make reason-responsive decisions.**

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
- [Self-Correction](#self-correction)
- [Limitations, Failures, Puzzles](#limitations-failures-puzzles)
- [Datasets](#datasets)
- [Tools and Frameworks](#tools-and-frameworks)
- [Other Resources](#other-resources)


## Success Stories

_Striking evidence for effectiveness of deliberative prompting._

- 🎓 The original "chain of though" (CoT) paper, first to give clear evidence that deliberative prompting works. "Chain-of-Thought Prompting Elicits Reasoning in Large Language Models." 2022-01-28. [[>paper](https://arxiv.org/abs/2201.11903)]
- 🎓 Deliberative prompting improves ability of Google's LLMs to solve unseen difficult problems, and instruction-finetuned (Flan-) models are much better at it.
  - "Scaling Instruction-Finetuned Language Models." 2022-12-06. [[>paper](https://arxiv.org/abs/2210.11416)]
  - "PaLM 2 Technical Report." 2023-05-17. [[>paper](https://arxiv.org/abs/2305.10403)]
- 🎓 Deliberative prompting is highly effective for OpenAI's models (Text-Davinci-003, ChatGPT, GPT-4), increasing accuracy in many (yet not all) reasoning tasks in the EvalAGI benchmark. "AGIEval: A Human-Centric Benchmark for
Evaluating Foundation Models." 2023-04-13. [[>paper](https://arxiv.org/abs/2304.06364)]
- 🎓 Deliberative prompting unlocks latent cognitive skills and is more effective for bigger models. "Challenging BIG-Bench tasks and whether chain-of-thought can solve them." 2022-10-17. [[>paper](https://arxiv.org/abs/2210.09261)]


## Prompting Patterns and Strategies 

_Prompting strategies and patterns to make LLMs deliberate._


### Beyond "Let's think step by step" 

_Instructing LLMs to reason (in a specific way)._

- Weighing Pros and Cons: This universal deliberation paradigm can be implemented with LLMs.
  - 👩‍💻 A _{{guidance}}_ program that does: 1. Identify Options → 2. Generate Pros and Cons → 3. Weigh Reasons → 4. Decide. [[>code](https://github.com/guidance-ai/guidance/blob/main/README.md#role-based-chat-model-example-notebook)]
- 🎓 👩‍💻 Plan-and-Solve Prompting. "Plan-and-Solve Prompting: Improving Zero-Shot Chain-of-Thought
Reasoning by Large Language Models." 2023-05-06. [[>paper](https://aclanthology.org/2023.acl-long.147.pdf)] [[>code](https://github.com/AGI-Edgerunners/Plan-and-Solve-Prompting)]
- 🎓 Note-Taking. "Learning to Reason and Memorize with Self-Notes." 2023-05-01. [[>paper](https://arxiv.org/abs/2305.00833)]
- 🎓 Deliberate-then-Generate improves text quality. "Deliberate then Generate: Enhanced Prompting Framework for Text Generation." 2023-05-31. [[>paper](https://arxiv.org/abs/2305.19835)]
- 🎓 Make LLM spontaneously interleave reasoning and Q/A. "ReAct: Synergizing Reasoning and Acting in Language Models." 2022-10-06. [[>paper](https://arxiv.org/abs/2210.03629)]
- 🎓 'Divide-and-Conquer' instructions substantially outperform standard CoT. "Least-to-Most Prompting Enables Complex Reasoning in Large Language Models" 2022-05-21. [[>paper](https://arxiv.org/pdf/2205.10625.pdf)]


### Multi-Agent Deliberation

_Let one (or many) LLMs simulate a free controversy._

- 🎓 Leverage wisdom of the crowd effects through debate simulation. "Improving Factuality and Reasoning in Language Models through Multiagent Debate." 2023-05-23. [[>paper](https://arxiv.org/abs/2305.14325)] 
- 🎓 👩‍💻 Emulate Socratic dialogue to collaboratively solve problems with multiple AI agents. "The Socratic Method for Self-Discovery in Large Language Models." 2023-05-05. [[>blog]https://princeton-nlp.github.io/SocraticAI/] [[>code](https://github.com/RunzheYang/SocraticAI)]


### Reflection and Meta-Cognition

_Higher-order reasoning strategies that may improve first-order deliberation._

- 🎓 👩‍💻 Clarify→Judge→Evaluate→Confirm→Qualify Paradigm. "Metacognitive Prompting Improves Understanding in Large Language Models." 2023-08-10. [[>paper](https://arxiv.org/abs/2308.05342)] [[>code](https://github.com/EternityYW/Metacognitive-Prompting)]
- 🎓 👩‍💻 Find-then-simulate-an-expert-for-this-problem Strategy. "Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm." 2021-02-15. [[>paper](https://arxiv.org/abs/2102.07350)] [[>lmql][lmql-playground]] 


## Text Generation Techniques 

_Text generation techniques, which can be combined with prompting patterns and strategies._

- 🎓 Better problem-solving and deliberation through few-shot trial-and-error (in-context RL). "Reflexion: Language Agents with Verbal Reinforcement Learning" [[>paper]](https://arxiv.org/abs/2303.11366)
- 🎓 External guides that constrain generation of reasoning improve accuracy by up to 35% on selected tasks. "Certified Reasoning with Language Models." 2023-06-06. [[>paper]](https://arxiv.org/abs/2306.04031)
- 🎓 👩‍💻 Highly effective beam search for generating complex, multi-step reasoning episodes. "Tree of Thoughts: Deliberate Problem Solving with Large Language Models." 2023-05-17. [[>paper]](https://arxiv.org/abs/2305.10601) [[>code](https://github.com/princeton-nlp/tree-of-thought-llm)]
  - 👩‍💻 A minimalistic implementation of Tree-of-Thoughts as plain prompt. [[>code](https://github.com/dave1010/tree-of-thought-prompting)]
  - 👩‍💻 An experimental [LMQL][lmql-site] implementation of Tree-of-Thoughts. [[>code](https://github.com/amazon-science/auto-cot)]
- 🎓 👩‍💻 LLM auto-generates diverse reasoning demonstration to-be-used in deliberative prompting. "Automatic Chain of Thought Prompting in Large Language Models." 2022-10-07. [[>paper]](https://arxiv.org/abs/2210.03493) [[>code](https://github.com/LachlanGray/lmql-tree-of-thoughts)]


## Self-Correction

_Let LLMs self-correct their deliberation._

- 🎓 Excellent review about self-correcting LLMs, with application to unfaithful reasoning. "Automatically Correcting Large Language Models: Surveying the landscape of diverse self-correction strategies." 2023-08-06. [[>paper]](https://arxiv.org/abs/2308.03188) 


## Limitations, Failures, Puzzles

_Things that don't work, or are poorly understood._

- 🎓 LLMs judge and decide in function of available arguments (reason-responsiveness), but are more strongly influenced by fallacious and deceptive reasons as compared to sound ones. "How susceptible are LLMs to Logical Fallacies?" 2023-08-18. [[>paper](https://arxiv.org/abs/2308.09853)]
- 🎓 Incorrect reasoning improves answer accuracy (nearly) as much as correct one. "Invalid Logic, Equivalent Gains: The Bizarreness of Reasoning in Language Model Prompting." 2023-07-20. [[>paper](https://arxiv.org/abs/2307.10573)]
- 🎓 LLMs may systematically fabricate erroneous CoT rationales for wrong answers, NYU/Anthropic team finds. "Language Models Don't Always Say What They Think: Unfaithful Explanations in Chain-of-Thought Prompting." 2023-05-07. [[>paper](https://arxiv.org/abs/2305.04388)] 


## Datasets

_Datasets containing examples of deliberative prompting, potentially useful for training models / assessing their deliberation skills._

- Instruction-following dataset augmented with "reasoning traces" generated by LLMs.
  - 🎓 _ORCA_ - Microsoft's original paper. "Orca: Progressive Learning from Complex Explanation Traces of GPT-4." 2023-06-05. [[>paper](https://arxiv.org/abs/2306.02707)] 
  - 👩‍💻 _OpenOrca_ - Open source replication of ORCA datasets. [[>dataset](https://huggingface.co/datasets/Open-Orca/OpenOrca)]  
  - 👩‍💻 _Dolphin_ - Open source replication of ORCA datasets. [[>dataset](https://huggingface.co/datasets/ehartford/dolphin)]  
- 👩‍💻 _OASST1_ - contains more than 200 instructions to generate pros and cons \(acc. to nomic.ai's [map](https://huggingface.co/spaces/nomic-ai/OpenAssistant_oasst1)\). [[>dataset](https://huggingface.co/datasets/OpenAssistant/oasst1)]
- 🎓 _LegalBench_ - a benchmark for legal reasoning in LLMs [[>paper](https://arxiv.org/abs/2308.11462)]


## Tools and Frameworks 

_Tools and Frameworks to implement deliberative prompting._

- 👩‍💻 _LMQL_ - a programming language for language model interaction. [[>site][lmql-site]]
  - 👩‍💻 Interactive LMQL Playground [[>site][lmql-playground]]
  - 🎓 "Prompting Is Programming: A Query Language for Large Language Models." 2022-12-12. [[>paper](https://arxiv.org/abs/2212.06094)] 
- 👩‍💻 _{{guidance}}_ - a language for controlling large language models. [[>code](https://github.com/guidance-ai/guidance)]
- 👩‍💻 _LangChain_ - a python library for building LLM chains and agents. [[>code](https://github.com/langchain-ai/langchain)]


## Other Resources

_More awesome and useful material._

- 📚 _Survey of Autonomous LLM Agents_ (continuously updated). [[>site](https://github.com/Paitesanshi/LLM-Agent-Survey)]
- 👩‍💻 _LLM Dashboard_ - explore task-specific reasoning performance of open LLMs [[>app](https://huggingface.co/spaces/CoreyMorris/MMLU-by-task-Leaderboard)]
- 📚 _Prompt Engineering Guide_ set up by [DAIR](https://dair.ai). [[>site](https://www.promptingguide.ai/)]


[lmql-site]: https://lmql.ai/
[lmql-playground]: https://lmql.ai/playground
