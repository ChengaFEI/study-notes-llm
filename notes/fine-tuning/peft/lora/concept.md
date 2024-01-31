# LoRA

## Definition

LoRA (Low Rank Adapters)

## Strengths

- Ideal for multi-tenancy architectures, where the LLM is shared while adaptors are fine-tuned.
- Adaptors are small (megabyte-level size)

## Variants

- QLoRA
- LongLoRA

## Mechanism

- Ranking
  - Instead of training a large matrix `W` of size `A * B` where `A` and `B` are large, we train two relatively smaller matrices `W1` and `W2` of size `A * R` and `R * B` respectively, where `R` is called the rank, and is much smaller than `A` and `B`.
