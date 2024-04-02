# Prompt Engineering

## Input

1. Zero-shot Prompting
2. Few-shot Prompting
   1. Example Selection
      1. Biases
         1. Majority Label Bias
         2. Recency Bias
         3. Common Token Bias
      2. Solutions
         1. k-NN clustering
            - References:
              - [What Makes Good In-Context Examples for GPT-$3$?](https://arxiv.org/abs/2101.06804)
         2. Graph searching
         3. Contrastive Learning
         4. Active Learning
         5. Q Learning
   2. Example Ordering: random
3. Instruction Prompting
   1. Natural Instruction
   2. RLHF

## Procedure

## Output

1. Self-Consistency Sampling
   1. Sample multiple outputs from LLMs with temperature > 0
   2. Select the best out of candidates with `majority vote`
