# Fine-Tuning

## Production Deployment

- User-level fine-tuning
  - Fine-tune LLMs for each user
    - Strength: Accuracy
    - Weakness: Scalability
  - Fine-tune one all-purpose LLM for all users

## FT vs. Transfer Learning

- In fine-tuning, we use the original model as a whole. Then we either train all parameters or only train the active parameters.
- In transfer-learning, we can adopt only some layers of the original model and integrate them into the new model by adding some more layers.
