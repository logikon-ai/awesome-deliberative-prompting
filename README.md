# Awesome Deliberative Prompting [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

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
- [Reasoning Analytics](#reasoning-analytics)
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
- 🎓 Experimentally introducing errors in CoT reasoning traces decreases decision accuracy, which provides indirect evidence for reason-responsiveness of LLMs. "Stress Testing Chain-of-Thought Prompting for Large Language Models." 2023-09-28. [[>paper](https://arxiv.org/abs/2309.16621)]
- 🎓 Reasoning (about retrieval candidates) improves RAG. "Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection." 2023-10-17. [[>paper](https://arxiv.org/abs/2310.11511)]
- 🎓 Deliberative reading notes improve RAG. "Chain-of-Note: Enhancing Robustness in Retrieval-Augmented Language Models." 2023-11-15. [[>paper](https://arxiv.org/abs/2311.09210)]
- 🎓 Good reasoning (CoT) causes good answers (i.e., LLMs are reason-responsive). "Causal Abstraction for Chain-of-Thought Reasoning in Arithmetic Word Problems." 2023-12-07. [[>paper](https://aclanthology.org/2023.blackboxnlp-1.12.pdf)]
- 🎓 Logical interpretation of internal layer-wise processing of reasoning tasks yields further evidence for reason-responsiveness. "Towards a Mechanistic Interpretation of Multi-Step Reasoning Capabilities of Language Model." 2023-12-07. [[>paper](https://arxiv.org/abs/2310.14491)]
- 🎓 Reasoning about alternative drafts improves text generation. "Self-Evaluation Improves Selective Generation in Large Language Models." 2023-12-14. [[>paper](https://arxiv.org/abs/2312.09300)]



## Prompting Patterns and Strategies 

_Prompting strategies and patterns to make LLMs deliberate._


### Beyond "Let's think step by step" 

_Instructing LLMs to reason (in a specific way)._

- 🎓 Reason over and over again until verification test is passed. "Plan, Verify and Switch: Integrated Reasoning with Diverse X-of-Thoughts." 2023-10-23. [[>paper](https://arxiv.org/abs/2310.14628)]
- 🎓 Generate multiple diverse deliberations, then synthesize those in a single reasoning path. "Ask One More Time: Self-Agreement Improves Reasoning of Language Models in (Almost) All Scenarios." 2023-11-14. [[>paper](https://arxiv.org/abs/2311.08154)]
- 🎓 Survey of CoT regarding task types, prompt designs, and reasoning quality metrics. "Towards Better Chain-of-Thought Prompting Strategies: A Survey." 2023-10-08. [[>paper](https://arxiv.org/abs/2310.04959)]
- 🎓 Asking a LLM about a problem's broader context leads to better answers. "Take a Step Back: Evoking Reasoning via Abstraction in Large Language Models." 2023-10-09. [[>paper](https://arxiv.org/abs/2310.06117)]
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



- 🎓 Systematic peer review is even better than multi-agent debate. "Towards Reasoning in Large Language Models via Multi-Agent Peer Review Collaboration." 2023-11-14. [[>paper](https://arxiv.org/abs/2311.08152)]
- 🎓 Collective critique and reflection reduce factual hallucinations and toxicity. "N-Critics: Self-Refinement of Large Language Models with Ensemble of Critics." 2023-10-28. [[>paper](https://arxiv.org/abs/2310.18679)]
- 🎓 👩‍💻 Delphi-process with diverse LLMs is veristically more valuable than simple debating. "ReConcile: Round-Table Conference Improves Reasoning via Consensus among Diverse LLMs." 2023-09-22. [[>paper](https://arxiv.org/abs/2309.13007)] [[>code](https://github.com/dinobby/ReConcile)]
- 🎓 Multi-agent debate increases cognitive diversity increases performance. "Encouraging Divergent Thinking in Large Language Models through Multi-Agent Debate." 2023-05-30. [[>paper](https://arxiv.org/abs/2305.19118)]
- 🎓 Leverage wisdom of the crowd effects through debate simulation. "Improving Factuality and Reasoning in Language Models through Multiagent Debate." 2023-05-23. [[>paper](https://arxiv.org/abs/2305.14325)] 
- 🎓 👩‍💻 Emulate Socratic dialogue to collaboratively solve problems with multiple AI agents. "The Socratic Method for Self-Discovery in Large Language Models." 2023-05-05. [[>blog](https://princeton-nlp.github.io/SocraticAI/)] [[>code](https://github.com/RunzheYang/SocraticAI)]


### Reflection and Meta-Cognition

_Higher-order reasoning strategies that may improve first-order deliberation._

- 🎓 👩‍💻 Reflecting on task allows LLM to autogenerate more effective instructions, demonstration, and reasoning traces. "Meta-CoT: Generalizable Chain-of-Thought Prompting in Mixed-task Scenarios with Large Language Models." 2023-10-11. [[>paper](https://arxiv.org/abs/2310.06692)] [[>code](https://github.com/Anni-Zou/Meta-CoT)] 
- 🎓 👩‍💻 LLM-based AI Instructor devises effective first-order CoT-instructions (open source models improve by up to 20%). "Agent Instructs Large Language Models to be General Zero-Shot Reasoners." 2023-10-05. [[>paper](https://arxiv.org/abs/2310.03710)] [[>code](https://github.com/wang-research-lab/agentinstruct)]
- 🎓 👩‍💻 Clarify→Judge→Evaluate→Confirm→Qualify Paradigm. "Metacognitive Prompting Improves Understanding in Large Language Models." 2023-08-10. [[>paper](https://arxiv.org/abs/2308.05342)] [[>code](https://github.com/EternityYW/Metacognitive-Prompting)]
- 🎓 👩‍💻 Find-then-simulate-an-expert-for-this-problem Strategy. "Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm." 2021-02-15. [[>paper](https://arxiv.org/abs/2102.07350)] [[>lmql][lmql-playground]] 


## Text Generation Techniques 

_Text generation techniques, which can be combined with prompting patterns and strategies._

- 🎓 Having (accordingly labeled) correct _and_ erroneous (few-shot) reasoning demonstrations improves CoT. "Contrastive Chain-of-Thought Prompting." 2023-11-17. [[>paper]](https://arxiv.org/abs/2311.09277)
- 🎓 Better problem-solving and deliberation through few-shot trial-and-error (in-context RL). "Reflexion: Language Agents with Verbal Reinforcement Learning." 2023-03-20. [[>paper]](https://arxiv.org/abs/2303.11366)
- 🎓 External guides that constrain generation of reasoning improve accuracy by up to 35% on selected tasks. "Certified Reasoning with Language Models." 2023-06-06. [[>paper]](https://arxiv.org/abs/2306.04031)
- 🎓 👩‍💻 Highly effective beam search for generating complex, multi-step reasoning episodes. "Tree of Thoughts: Deliberate Problem Solving with Large Language Models." 2023-05-17. [[>paper]](https://arxiv.org/abs/2305.10601) [[>code](https://github.com/princeton-nlp/tree-of-thought-llm)]
  - 👩‍💻 A minimalistic implementation of Tree-of-Thoughts as plain prompt. [[>code](https://github.com/dave1010/tree-of-thought-prompting)]
  - 👩‍💻 An experimental [LMQL][lmql-site] implementation of Tree-of-Thoughts. [[>code](https://github.com/LachlanGray/lmql-tree-of-thoughts)]
- 🎓 👩‍💻 LLM auto-generates diverse reasoning demonstration to-be-used in deliberative prompting. "Automatic Chain of Thought Prompting in Large Language Models." 2022-10-07. [[>paper](https://arxiv.org/abs/2210.03493)] [[>code](https://github.com/amazon-science/auto-cot)]

## Self-Correction

_Let LLMs self-correct their deliberation._


- 🎓 Reinforced Self-Training improves retrieval-augmented multi-hop Q/A. "ReST meets ReAct: Self-Improvement for Multi-Step Reasoning LLM Agent." 2023-12-15. [[>paper](https://arxiv.org/abs/2312.10003)]
- 🎓 Conditional self-correction depending on whether critical questions have been addressed in reasoning trace. "The ART of LLM Refinement: Ask, Refine, and Trust." 2023-11-14. [[>paper](https://arxiv.org/abs/2311.07961)]
- 🎓 Iteratively refining reasoning given diverse feedback increases accuaracy by up tp 10% (ChatGPT). "MAF: Multi-Aspect Feedback for Improving Reasoning in Large Language Models." 2023-10-19. [[>paper](https://arxiv.org/abs/2310.12426)]
- 🎓 Instructing a model just to "review" its answer and "find problems" doesn't lead to effective self-correction. "Large Language Models Cannot Self-Correct Reasoning Yet." 2023-09-25. [[>paper](https://arxiv.org/abs/2310.01798)]
- 🎓 LLMs can come up with, and address critical questions to improve their drafts. "Chain-of-Verification Reduces Hallucination in Large Language Models." 2023-09-25. [[>paper](https://arxiv.org/abs/2309.11495)]
- 🎓 LogiCoT: Self-check and revision after each CoT step improves performance (for selected tasks and models). "Enhancing Zero-Shot Chain-of-Thought Reasoning in Large Language Models through Logic." 2023-09-23. [[>paper](https://arxiv.org/abs/2309.13339)]
- 🎓 Excellent review about self-correcting LLMs, with application to unfaithful reasoning. "Automatically Correcting Large Language Models: Surveying the landscape of diverse self-correction strategies." 2023-08-06. [[>paper](https://arxiv.org/abs/2308.03188)]


## Reasoning Analytics

_Methods for analysing LLM deliberation and assessing reasoning quality._

- 🎓 Minimalistic GPT-4 prompts for assessing reasoning quality. "SocREval: Large Language Models with the Socratic Method for Reference-Free Reasoning Evaluation." 2023-09-29. [[>paper](https://arxiv.org/abs/2310.00074)]


## Limitations, Failures, Puzzles

_Things that don't work, or are poorly understood._

- 🎓 LLMs may produce "encoded reasoning" that's unintelligable to humans, which may nullify any XAI gains from deliberative prompting. "Preventing Language Models From Hiding Their Reasoning." 2023-10-27. [[>paper](https://arxiv.org/abs/2310.18512)]
- 🎓 LLMs judge and decide in function of available arguments (reason-responsiveness), but are more strongly influenced by fallacious and deceptive reasons as compared to sound ones. "How susceptible are LLMs to Logical Fallacies?" 2023-08-18. [[>paper](https://arxiv.org/abs/2308.09853)]
- 🎓 Incorrect reasoning improves answer accuracy (nearly) as much as correct one. "Invalid Logic, Equivalent Gains: The Bizarreness of Reasoning in Language Model Prompting." 2023-07-20. [[>paper](https://arxiv.org/abs/2307.10573)]
- 🎓 Zeroshot CoT reasoning in sensitive domains increases a LLM's likelihood to produce harmful or undesirable output. "On Second Thought, Let's Not Think Step by Step! Bias and Toxicity in Zero-Shot Reasoning." 2023-06-23. [[>paper](https://arxiv.org/abs/2212.08061)]
- 🎓 LLMs may systematically fabricate erroneous CoT rationales for wrong answers, NYU/Anthropic team finds. "Language Models Don't Always Say What They Think: Unfaithful Explanations in Chain-of-Thought Prompting." 2023-05-07. [[>paper](https://arxiv.org/abs/2305.04388)] 
- 🎓 LLMs' practical deliberation is not robust, but easily let astray by re-wording scenarios. "Despite 'super-human' performance, current LLMs are unsuited for decisions about ethics and safety" 2022-12-13. [[>paper](https://arxiv.org/abs/2212.06295)] 


## Datasets

_Datasets containing examples of deliberative prompting, potentially useful for training models / assessing their deliberation skills._

- Instruction-following dataset augmented with "reasoning traces" generated by LLMs.
  - 🎓 _ORCA_ - Microsoft's original paper. "Orca: Progressive Learning from Complex Explanation Traces of GPT-4." 2023-06-05. [[>paper](https://arxiv.org/abs/2306.02707)] 
  - 👩‍💻 _OpenOrca_ - Open source replication of ORCA datasets. [[>dataset](https://huggingface.co/datasets/Open-Orca/OpenOrca)]  
  - 👩‍💻 _Dolphin_ - Open source replication of ORCA datasets. [[>dataset](https://huggingface.co/datasets/ehartford/dolphin)]  
  - 🎓 _ORCA 2_ - Improved Orca by Microsoft, e.g. with meta reasoning. "Orca 2: Teaching Small Language Models How to Reason." 2023-11-18. [[>paper](https://arxiv.org/abs/2311.11045)]
- 🎓👩‍💻 _CoT Collection_ - 1.84 million reasoning traces for 1,060 tasks. "The CoT Collection: Improving Zero-shot and Few-shot Learning of Language Models via Chain-of-Thought Fine-Tuning." [[>paper](https://arxiv.org/abs/2305.14045)] [[>code](https://github.com/kaistAI/CoT-Collection)]
- 👩‍💻 _OASST1_ - contains more than 200 instructions to generate pros and cons \(acc. to nomic.ai's [map](https://huggingface.co/spaces/nomic-ai/OpenAssistant_oasst1)\). [[>dataset](https://huggingface.co/datasets/OpenAssistant/oasst1)]
- 🎓 _LegalBench_ - a benchmark for legal reasoning in LLMs [[>paper](https://arxiv.org/abs/2308.11462)]


## Tools and Frameworks 

_Tools and Frameworks to implement deliberative prompting._

- 👩‍💻 _LMQL_ - a programming language for language model interaction. [[>site][lmql-site]]
  - 👩‍💻 Interactive LMQL Playground [[>site][lmql-playground]]
  - 🎓 "Prompting Is Programming: A Query Language for Large Language Models." 2022-12-12. [[>paper](https://arxiv.org/abs/2212.06094)] 
- 👩‍💻 _{{guidance}}_ - a language for controlling large language models. [[>code](https://github.com/guidance-ai/guidance)]
- 👩‍💻 <i>outlines ~</i> - a language for guided text generation. [[>code](https://github.com/outlines-dev/outlines)]
- 👩‍💻 _DSPy_ - a programmatic interface to LLMs. [[>code](https://github.com/stanfordnlp/dspy)]
- 👩‍💻 _LangChain_ - a python library for building LLM chains and agents. [[>code](https://github.com/langchain-ai/langchain)]


## Other Resources

_More awesome and useful material._

- 📚 _Survey of Autonomous LLM Agents_ (continuously updated). [[>site](https://github.com/Paitesanshi/LLM-Agent-Survey)]
- 👩‍💻 _LLM Dashboard_ - explore task-specific reasoning performance of open LLMs [[>app](https://huggingface.co/spaces/CoreyMorris/MMLU-by-task-Leaderboard)]
- 📚 _Prompt Engineering Guide_ set up by [DAIR](https://dair.ai). [[>site](https://www.promptingguide.ai/)]


[lmql-site]: https://lmql.ai/
[lmql-playground]: https://lmql.ai/playground
