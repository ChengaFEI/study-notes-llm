# IA3

IA3 (Infused Adaptor by Inhibiting and Amplifying Inner Activations)

## Techniques

- Rescaling Vectors `lv, lk, lff` are learned to rescale and optimize the value map, key map, and the non-linearity layer
- 3 Losses
  - `L_LM`: Standard cross-entropy loss
  - `L_UL`: Unlikelihood loss (log-likelihood) to penalize incorrect predictions
  - `L_LN`: Length-Normalized loss to normalize influences of different sequence lengths

## Efficiency

- Compared with LoRA
  - IA3 has fewer trainable parameters
  - IA3 has higher accuracy, even higher than full-parameter fine-tuning
- Compared with ICL (in-context-learning)
  - IA3 has higher accuracy
  - IA3 uses fewer FLOPs per example
