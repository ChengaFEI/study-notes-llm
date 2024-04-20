# RRHF

---

[Cheng]

## Problem

1. RLHF relies on complex and resource-intensive algos like PPO.
   1. RLHF steps
      1. SFT (Supervised Fine-Tuning)
         1. Purpose: Fine-tune initial models to learn to follow human instructions.
      2. Reward model training
         1. Method: Learn from the ranking of human preferences.
         2. Purpose: Generate scores to apply gradient policy in PPO to align human preferences.
      3. PPO (Proximal Policy Optimization)
         1. Components
            1. Policy model
            2. Value model
            3. Reward model
            4. Reference model
         2. Loss function
            1. First, value model estimates a baseline
            2. Then, an auxiliary model estimates an advantage function to compare whether the action was better than the baseline

## Paradigm

1. Use a ranking loss to score model responses based on their log-probability conditioned on prior responses. This method requires fewer models and hyper-parameter tuning than RLHF.
   1. RRHF steps
      1. Sample responses from various resources
         1. Model itself
         2. GPT-4
         3. Human-authored responses
      2. Score/Rank responses based on the log-probability provided by the language model
      3. Compute the ranking loss by comparing the language model's ranks with human preference labels or human preference reward models
   2. RRHF components
      1. Language model for generating responses
      2. Reward model for scoring responses

## Approach

1. Notation
   1. $x \sim D$: Query data distribution
   2. $y$: Response
   3. $R(x, y)$: Reward function
   4. $\pi$: Language model
   5. $\rho$: Initial language model
   6. $\rho^*$: Language model after each 3-epoch iteration
2. Loss function
   1. $L_{\text{rank}}$ Rank loss: encourage the model to assign higher probability to human-preferred responses
   2. $L_{\text{ft}}$ Cross-entropy loss: encourage the model to learn from human-preferred responses (high-ranked responses)
   3. $L = L_{\text{rank}} + L_{\text{ft}}$: unweighted sum of the two losses

## Experiment

1. Dataset: Anthropic's Helpful and Harmless dataset
2. Model: LLaMA and Alpaca
3. Sampling policy

---

[Joy]

## Result

## Analysis

## Limitation

1. Dependency on the quality of sampled responses.
2. Issues with scaling when dealing with more extensive language models and more complex alignment scenarios.
