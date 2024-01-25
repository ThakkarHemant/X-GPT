
# X - GPT
Introducing X GPT, your personalized chatbot designed to revolutionize your online interactions with unparalleled customization and fine-tuning capabilities. X GPT is not just another chatbot; it's your virtual companion tailored to cater to your unique preferences and needs.

### Tailored Conversations
X GPT understands the importance of personalized communication. Whether you're seeking friendly banter, professional advice, or deep philosophical discussions, X GPT adapts its tone, language, and style to match your individual communication style.


<img src="https://i.imgur.com/H4F6gyp.png" />

### Fine-Tuning Expertise
X GPT goes beyond the ordinary by allowing you to fine-tune its responses according to your specifications. With intuitive customization options, you can easily adjust the bot's responses, ensuring that every conversation aligns perfectly with your expectations. X GPT is constantly learning from your interactions, becoming more attuned to your preferences over time. As you engage in conversations, the chatbot analyzes your inputs and refines its responses, ensuring a seamless and tailored chatting experience.

### Privacy and Security
Your privacy and security are paramount. X GPT is designed with robust privacy measures, ensuring that your conversations remain confidential. You can chat freely, knowing that your data is protected and your interactions are secure.

### Seamless Integration
X GPT seamlessly integrates into various platforms and applications, enhancing your user experience across different digital environments. Whether you're chatting on a messaging app, a social media platform, or a website, X GPT adapts effortlessly to provide consistent personalized interactions.

In a world where personalization is key, X GPT stands as the epitome of tailored chatbot technology. Experience the future of conversation, where every interaction is uniquely crafted for you. X GPT isn't just a chatbot; it's your personal chat companion, finely tuned to meet your individual needs and preferences.

## Prerequisites

- [Python 3.x](https://www.python.org/)
- [Streamlit](https://streamlit.io/)
- Basic understanding of API's and Python programming Language

## Installation

```bash
pip install openai
pip install streamlit
pip install Pillow
```

## How to Run this Project

```bash
python -m streamlit run app.py
```

## Fine Tuning
GPT models have been pre-trained on a vast amount of text. To use the models effectively, we include instructions and sometimes several examples in a prompt. Using demonstrations to show how to perform a task is often called "**few-shot learning**."

Fine-tuning improves on few-shot learning by training on many more examples than can fit in the prompt, letting you achieve better results on a wide number of tasks. Once a model has been fine-tuned, you won't need to provide as many examples in the prompt. This saves costs and enables lower-latency requests.

Fine-tuning is currently available for the following models:
- gpt-3.5-turbo-0613 (recommended)
- babbage-002
- davinci-002
We expect gpt-3.5-turbo to be the right model for most users in terms of results and ease of use, unless you are migrating a legacy fine-tuned model.

Example format
In this example, our goal is to create a chatbot that occasionally gives sarcastic responses, these are three training examples (conversations) we could create for a dataset:
```
{"messages": [{"role": "system", "content": "Marv is a factual chatbot that is also sarcastic."}, {"role": "user", "content": "What's the capital of France?"}, {"role": "assistant", "content": "Paris, as if everyone doesn't know that already."}]}
{"messages": [{"role": "system", "content": "Marv is a factual chatbot that is also sarcastic."}, {"role": "user", "content": "Who wrote 'Romeo and Juliet'?"}, {"role": "assistant", "content": "Oh, just some guy named William Shakespeare. Ever heard of him?"}]}
{"messages": [{"role": "system", "content": "Marv is a factual chatbot that is also sarcastic."}, {"role": "user", "content": "How far is the Moon from Earth?"}, {"role": "assistant", "content": "Around 384,400 kilometers. Give or take a few, like that really matters."}]}
```
The conversational chat format is required to fine-tune gpt-3.5-turbo. For babbage-002 and davinci-002, you can follow the prompt completion pair format used for legacy fine-tuning as shown below.
```
{"prompt": "<prompt text>", "completion": "<ideal generated text>"}
{"prompt": "<prompt text>", "completion": "<ideal generated text>"}
{"prompt": "<prompt text>", "completion": "<ideal generated text>"}
```
We generally recommend taking the set of instructions and prompts that you found worked best for the model prior to fine-tuning, and including them in every training example. This should let you reach the best and most general results, especially if you have relatively few (e.g. under a hundred) training examples.

If you would like to shorten the instructions or prompts that are repeated in every example to save costs, keep in mind that the model will likely behave as if those instructions were included, and it may be hard to get the model to ignore those "baked-in" instructions at inference time.

It may take more training examples to arrive at good results, as the model has to learn entirely through demonstration and without guided instructions.




# Reference
* [A Guide to OpenAI's API](https://blog.streamlit.io/beginners-guide-to-openai-api/)
* [API Reference](https://platform.openai.com/docs/api-reference/introduction?lang=python)
* [Basic Image Operations With the Python Pillow Library](https://realpython.com/image-processing-with-the-python-pillow-library/#:~:text=PIL%20stands%20for%20Python%20Imaging,includes%20support%20for%20Python%203.)
* [GPT Production Best Practices](https://platform.openai.com/docs/guides/production-best-practices)
* [How do I use Stop Sequences?](https://help.openai.com/en/articles/5072263-how-do-i-use-stop-sequences)
* [Fine-tuning](https://platform.openai.com/docs/guides/legacy-fine-tuning)
* [Using GPT-3.5 and GPT-4 via the OpenAI API in Python](https://www.datacamp.com/tutorial/using-gpt-models-via-the-openai-api-in-python)

# Authors
Santosh Arron, Hemant Thakkar

# LICENSE
```
Copyright 2023 Santosh Arron & Hemant Thakkar

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```
