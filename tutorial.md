# Function in Chatito Bothub Extension

## Train_chatito
This function is used to train sentences in *bothub* via API, using a *rasa dataset* (json) file generated by [Chatito DSL](https://rodrigopivi.github.io/Chatito/)

To use this function, first create your *.chatito* file to use in DSL. Use the [examples](/examples) directory files to test this function.

Example of how to use this function:

```bash
python main.py train_chatito examples/pizza
```

## Export_to_json
If you need to list in a file all the sentences trained in your bothub intelligence, this function will work for you. As the name implies, this function exports to a json file all sentences of bothub intelligence.

To use it, call it with the *filename* parameter that the code should save. If you have no idea, use "sentences".

Use the following code:

```bash
python main.py export_to_json my_bothub_sentences
```

## Train_json_sentences
Do you need to clone your bothub intelligence? This function can help you. It reads an exported json file using the *export_to_json* function and trains all sentences from the read file.

Use the following code:

```bash
python main.py train_json_sentences my_bothub_sentences
```

A tip for you: If you still understanding how to clone your bothub intelligence, following this list:
- First, create another intelligence. It will be the clone;
- Get the *repository_uuid* and *repository_version_id* of your base intelligence, and run the *export_to_json* function;
- You will use the generated json file to train the sentences of your base intelligence in the new bothub intelligence (clone);
- So, change the environment variables (in .env file) to the new bothub intelligence *repository_uuid* and *respository_version_id*.
- Now, use *train_json_sentences*.


## Delete_by_intent
Your project has changed and that "intent x" will no longer be used, but is there 99999 sentences created using it? This function can help you.

Just call *delete_by_intent* with the parameter *intent name* and this function will delete all sentences that use the informed intent.

## And more
Nothing that you saw here help you? Don't worry! You can use bothub_api.py, which contains simple functions that use bothub API to automate manual processes.

If you have any ideas, any new functions, please send a *Pull Request*. Any ideas will be considered!