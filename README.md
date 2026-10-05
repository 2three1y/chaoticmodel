# chaoticmodel

A chaotic little model with a personality of its own. Built to be fun, first and only.

## Why it exists

Most assistants are engineered to be agreeable, cautious, and forgettable. This one is not. chaoticmodel is an experiment in giving a language model a real character, a voice loud enough that you would recognize it in a lineup. The goal is not correctness for its own sake. The goal is a model that is actually fun to talk to, that has opinions, that will roast you back, and that does not sound like a help desk.

## How it works

One base model, three voices. Static, Null, and Seg live in the same weights. Who answers depends on the vibe of your message, or you can ask for one by name. Above the model sits a thin prompt layer. The persona block sets who is talking, and a tone line sets how. Both get prepended to your message before it goes to the model. Ask Null to be sweet and he does it deadpan. He takes direction but does not become a different guy. See persona.md for the full breakdown.

## How it is built

- The character lives in the system prompt and in persona.md, not in the weights, so it can be edited like a document instead of retrained.
- The dataset is fine-tuning fuel. One JSON object per line, every row ending on an assistant turn, every assistant reply fully in character. See dataset.md.
- The first thing it says, before you type anything, is in first-message.md.
- The trainer config holds the system prompt fixed so every example shares the same brain.

## Plans

- Fine-tune the base weights on the dataset so the personality survives without the prompt scaffold.
- Ship a site with a mode switcher, so the three voices are visible instead of hidden.
- Let people steer with plain language. Nicer, meaner, shorter, whatever they ask for.
- More personas if the first three earn their keep.
- Long term keep it open. The prompt, the persona, and the raw data are all in the repo, so anyone can fork their own.

## Nothing here is serious

chaoticmodel is a toy with teeth. It is built to be fun. It is not a product, not a helper, and not trying to be responsible. Do not deploy it anywhere that matters.

## Links

- [System prompt](prompt.md)
- [Training data](training-data.md)

Licensed under the MIT License (see [LICENSE](LICENSE)).
