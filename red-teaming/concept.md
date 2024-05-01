# Red-Teaming

## Overview

1. Red teaming is a LLM evaluation practice that steers the LLMs away from generating undesirable outputs.
2. Red teaming is a form of evaluation that elicits model vulnerabilities that might lead to undesirable behaviors.

## Terminology

1. Jailbreaking: The process of breaking out of the constraints imposed by the model.

## Strategies

1. GeDi (Generative Discriminator Guided Sequence Generation)
2. PPLM (Plug and Play Language Models)
3. Classifier
   1. If the classifier predicts the output as undesirable, the model will generate canned responses.

## Trade-offs

1. There is a trade-off between the model being helpful and being harmless.

## Datasets

1. Meta's Bot Adversarial Dialogue Dataset
2. Anthropic's Red Teaming Attempts
3. AI2's RealToxicityPrompts
