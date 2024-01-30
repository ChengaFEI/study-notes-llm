# LLM Alignment

## Why Alignment?

1. Generally
   1. Reliability
   2. Safety
   3. Fairness
   4. Resistance to Misuse
   5. Explainability
   6. Social Norm
   7. Robustness
2. Specifically
   1. Generate specific answers in specific formats/tones ...

## How Alignment?

1. Step 1: SFT (Supervised Fine-tuning)
   1. Purpose: Use prompt-answer pairs from users to fine-tune an LLM to generate desired answers.
2. Step 2: RM (Reward Model)
   1. Purpose: Ask the user to rank multiple answers generated w.r.t a prompt. Use the ranking to train a Reward Model.
3. Step 3: RLHF (Reinforcement Learning with Human Feedback)
   1. Purpose: For each prompt, use the SFT model to generate multiple answers, and use the Reward Model to rank the answers. Then, feed the prompt-answer pair into a Reinforcement Learning model to optimize the LLM.

### RLHF

#### RLHF Overview

- Why RL for LLM?
  - (监督式学习的固有缺陷) Natural interaction with human users.
    - (原来没有学) LLM is trained with the web-scale corpora, which doesn't exclude inappropriate or toxic information. Hence, we need to use direct human intervention to "brainwash" the LLM to suppress toxic contents.
    - (可能没法学) Higher levels of rich features in language expressions might not be quantifiable or linearly separable. For example, the tone, appropriateness, the degree of humor, cultural nuances.
  - (标记数据集的缺陷) Continuous learning with limited data.
    - High-quality labeled/annotated data is expensive and labor-intensive to obtain so that the (self-)supervised learning is not scalable and not applicable in continuous learning.
    - Lack of easy-to-retrieve data disables the (self-)supervised learning approach to align with nuances occurred real-time.
  - (定制化需求) Customized to specific tasks.

#### RLHF Features

- States are based on both contexts/prompts and tokens generated so far.
- Action space cover the whole vocabulary.
  - Therefore, we need to apply a efficient algorithm to balance exploration and exploitation.

#### MDP (Markov Decision Process) Components

- How to define the state/action space and reward function?
  - State space: the prompt and the generated tokens so far.
  - Action space: the next token to generate.
  - Reward function: user's feedback (ranking or binary (positive/neutral/negative)).

#### Optimization Algorithms

- Why TRPO (Trusted Region Policy Optimization) / PPO (Proximal Policy Optimization) for RLHF?
  - Balance between exploration and exploitation.
  - Scalability
  - Data efficiency
