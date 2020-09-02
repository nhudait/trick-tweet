# TrickTweet
TrickTweet is a dynamic language Character model for for Twitter. I utilized the [tweepy](https://www.tweepy.org/) API to gather tweets from an inputted user.

This code was developed on Google Colab. In order to use it locally, you will need to change your path accordingly.

You have a few options when running the notebook

- Train a new base model: A base model is just a model trained on generic tweets that are not from a specific user. Training over a large corpus an iterating over it multiple times will allow us to have a general model that can be fine-tuned on a per user basis. This can be modified by making
    - `TRAIN_BASE_MODEL = True`
- Iterate on the base model: You can load the base model, iterate on it and save it back thus making the generic model better. This can be modified by making
    - `TRAIN_BASE_MODEL=True`
    - `USE_OLD_MODEL=True`
- Create a new user-specific model: Input a user’s Twitter handle. By default, it will just create a new model from scratch
    - Everything can remain False
- Create a user model from the base model: You can load the base model and train the user model on top of it. This is particularly useful for users who have few tweets. It also allows you to do far fewer epochs than a new model from scratch.
    - `USE_BASE_MODEL = True`
- Train on an existing model: You can train on an existing user model and iterate on it just like iterating on the base model
    - `USE_OLD_MODEL = True`
