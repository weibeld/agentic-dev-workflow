# Agentic Development Workflow

This is a summary of a development methodology for a solo developer using agentic development. It attempts to make use of model knowledge, vibe coding, as well as production-grade agentic coding.

> **Note:** this is still work in progress and will be updated as more experience is gained.

## Table of Contents

1. [Phase 1: Exploration](#phase-1-exploration)
2. [Phase 2: Build Prototype Version](#phase-2-build-prototype-version)
3. [Phase 3: Build Production Version](#phase-3-build-production-version)
4. [Background](#background)
   1. [Using a model to get the "world-knowledge average solution" makes perfect sense](#1-using-a-model-to-get-the-world-knowledge-average-solution-makes-perfect-sense)
   2. [Using a vibe-coding agent to generate a quick-and-dirty prototype is also realistic and powerful](#2-using-a-vibe-coding-agent-to-generate-a-quick-and-dirty-prototype-is-also-realistic-and-powerful)
   3. [Why this workflow is ideal for a solo dev](#3-why-this-workflow-is-ideal-for-a-solo-dev)
   4. [Concerns you might have (and why they're non-issues)](#4-concerns-you-might-have-and-why-theyre-non-issues)
   5. [The ideal workflow you are describing](#5-the-ideal-workflow-you-are-describing)

## Phase 1: Exploration

- Generate throwaway version of the app with minimal input and specification
  - Just mention what kind of app and what the app should do, no details
- Can be seen as "consulting" the model for its view
  - The model's view can be seen as an "average engineers" solution (most streamlined, most baseline, most average solution, model contains "average" of world knowledge)
- Make sure that all core functionality gets actually implemented in a proof-of-concept way
  - No overall consistency required, different parts don't need to be functional at the same time

Goals:

- Reality checking: compare own conceptions with model's view
  - Avoid "missing" obvious things, avoid unnecessary complexities, be confronted with baseline implementations and best practices
- Proof of concept: verify feasibility, shape features
  - Make abstract feature ideas concrete (e.g. flow, requirements, etc.)
- Conceptual model: materialisation of flows and processes causes more stable mental model
  - Important for the planning in the subsequent phases

## Phase 2: Build Prototype Version

> **Note:** this must be based on the insights from the exploration phase.

1. Design user flows
2. Design UI prototype
3. Implement logic (using vibe coding)
4. Iterate

Goals:

- Rapid full implementation of app without quality requirements
  - App should fulfil its entire purpose
- Evaluation of app usefulness
  - For example, whether a production version is necessary or not
- Rapid shaping of features
  - Features can be added or removed without fulfilling quality requirements

## Phase 3: Build Production Version

> **Note:** at this stage, the extent of the entire app should be clear so that it can be specified in its entirety.

1. Design production UI
2. Write specification
   - Using frameworks like [Spec Kit](https://github.com/github/spec-kit)
3. Implement production logic
4. Iterate

Goals:

- Published version of app
  - Fulfilling all quality requirements, such as UX, security, robustness, extensibility, etc.

## Background

> **Note:** ChatGPT provided responses below.

### 1. Using a model to get the “world-knowledge average solution” makes perfect sense

LLMs do contain a kind of statistical average of:

- typical app architectures  
- common UI patterns  
- best practices that appear frequently in public code  
- the usual flows for certain categories of tools  
- typical pain points and typical solutions  

So if you give the model just a high-level problem description, you will often get:

- the mainstream architecture people use for this type of app  
- the “obvious” features everyone implements  
- a safe, conventional structure  
- typical screens / flows you might otherwise miss  

This is fantastic for reality checking:

- “Am I missing something obvious?”  
- “Is my idea consistent with how apps like this normally work?”  
- “What does the typical flow look like in the real world?”  

This kind of “baseline design” is exactly what LLMs are good at.

And because you said clearly:  
**this is throwaway**,  
you avoid the trap of locking yourself into mediocre early decisions.

This is a very healthy step before real design starts.

### 2. Using a vibe-coding agent to generate a quick-and-dirty prototype is also realistic and powerful

There are two types of prototypes you can make with vibe coding:

#### **A. Idea Exploration Prototype**

*(you described this)*

- Vague spec  
- Let the model decide UI layout, screens, flows  
- Let it choose components, state shapes, data models  
- Not meant to survive  
- Purely to reveal:  
  - flows you didn’t think about  
  - UX needs  
  - edge cases  
  - complexity pockets  
  - contradictions in your idea  
  - places where you forgot something obvious (Git flow, auth flow, etc.)  

This kind of prototype is extremely useful because humans have trouble imagining dynamic systems in the abstract, while an AI can just materialize something.

It lets you see the “shape” of what you’re dealing with.

This process is something most human designers do too — they just do it manually and slowly.

#### **B. Functional Proof-of-Concept Prototype**

🤖 → still throwaway  
🧪 → but contains some working logic  
📐 → and makes abstract ideas concrete  

This is especially powerful when:

- You have complex flows  
- You need to test an API  
- You want to validate Git integrations  
- You need to see how components interact  
- You want to feel the UX before committing to a real design  

Again, vibe coding tools are perfect for this because:

- They generate fast  
- They’re okay with being messy  
- They can mimic real function even with mocked data  
- They give you something interactive to click around  

This gives you a mental model of the system.

### 3. Why this workflow is ideal for a solo dev

Solo developers have one major challenge:

**You don’t have a team to sanity-check your vision.**

An LLM acts like:

- a second brain  
- a “default-case” engineer  
- a translator of your rough idea into concrete flows  
- a simulator of how “people usually solve this”  

This reduces design risk enormously.

### 4. Concerns you might have (and why they’re non-issues)

**“What if the model proposes something I don’t like?”**  
Great — that’s the point.  
Its proposal is a mirror that reveals design space you haven’t considered.

**“What if the prototype is low quality?”**  
It should be.  
Throwaway prototypes are supposed to be messy, fast, and disposable.

**“Isn’t it a waste of time?”**  
Not if it prevents:

- architectural dead ends  
- misunderstood flows  
- missing UI screens  
- premature decisions  

Time saved later is huge.

### 5. The ideal workflow you are describing

*(and yes, this is a legitimate, modern, effective methodology)*

#### **EXPLORATION PHASE (throwaway)**

1. Very rough description of the app → LLM  
2. LLM generates the “generic world average” solution  
3. Vibe-coding agent produces a junk prototype  
4. You inspect it and discover:  
   - missing flows  
   - UI needs  
   - complexity pockets  
   - data models  
   - new ideas  
5. You extract insights from this generation

#### **REAL DESIGN PHASE**

6. Now that you understand your app’s real shape, you design your own flow, UI, and architecture.  
7. Use vibe coding tools more seriously to generate production-quality segments.

#### **PRODUCTION PHASE**

8. Start building the real app (with or without AI).
