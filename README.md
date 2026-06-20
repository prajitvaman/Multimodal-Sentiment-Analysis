Objective
The goal of this project is to design and develop a multimodal sentiment analysis system using Transformers for the task of Memotion Analysis. This will involve analyzing
internet memes, which are composed of both textual and visual data, and classifying them based on their sentiment, humor type, and offense level.
The project will utilize state-of-the-art transformer models to perform sentiment classification, humor classification, and offense detection across multimodal inputs.


Task Breakdown
This project involves three main tasks:
Sentiment Classification
Humor Classification
Scales of Semantic Classes (including Humor, Sarcasm, Offense, Motivation)
Each task has specific input formats, output formats, and evaluation criteria


# Task A: Sentiment Classification  

## Objective  
Classify the sentiment of a given meme as **Positive**, **Negative**, or **Neutral**.  

## Approach  
- Use both **text** (caption or embedded text in the meme) and **image** (visual content) to predict sentiment.  
- Utilize the following models:  
  - **Text Processing**: Transformer-based models such as **BERT, RoBERTa,** or **DistilBERT**.  
  - **Image Processing**: Vision-based models such as **Vision Transformer (ViT)** or **CNN-based models**.  
- Combine the outputs of both models using a **multimodal fusion layer**.  

## Input  
- **Text**: Caption or embedded textual content of the meme.  
- **Image**: The meme image itself.  

## Output  
- **Positive** (+1)  
- **Negative** (-1)  
- **Neutral** (0)  

## Evaluation Criteria  
The performance is measured using the **Macro F1 score**.  


# Task B: Humor Classification  

## Objective  
Identify the type of humor expressed in the meme. Categories include **Sarcastic, Humorous, Offensive,** or **Other**.  

## Approach  
- Use the **multimodal approach**, where both text and image contribute to humor classification.  
- **Transformer models** can be used for the textual component, while **CNN** or **Vision Transformers (ViTs)** can handle the image part.  
- Use a **classification head** after multimodal fusion to predict the humor type.  

## Input  
- **Text**: Meme caption or embedded text.  
- **Image**: The image of the meme itself.  

## Output  
- **Humor**: 0 (Not Humorous) or 1 (Humorous, Funny, Hilarious).  
- **Sarcasm**: 0 (Not Sarcastic) or 1 (Sarcastic, Twisted Meaning, Very Twisted).  
- **Offensive**: 0 (Not Offensive) or 1 (Slight, Very Offensive, Hateful Offensive).  

## Evaluation Criteria  
The performance is measured using **Macro F1** for each subtask (**Humor, Sarcasm, Offense**) and their average.  


# Task C: Scales of Semantic Classes  

## Objective  
Quantify the extent to which the meme expresses specific effects such as **Humor, Sarcasm, Offense,** and **Motivation**.  

## Approach  
- Use a **regression head** on top of the multimodal fusion model to predict a scale for each category.  
- The **transformer model** will be responsible for encoding the text, while a **CNN** or **ViT** will process the image.  
- For each category (**Humor, Sarcasm, Offense, Motivation**), predict values based on the scale provided.  

## Input  
- **Text**: Caption or embedded textual content of the meme.  
- **Image**: The image of the meme.  

## Output (on a scale of 0-3)  
- **Humor**: 0 (Not Funny), 1 (Funny), 2 (Very Funny), 3 (Hilarious).  
- **Sarcasm**: 0 (Not Sarcastic), 1 (General), 2 (Twisted Meaning), 3 (Very Twisted).  
- **Offense**: 0 (Not Offensive), 1 (Slight), 2 (Very Offensive), 3 (Hateful Offensive).  
- **Motivation**: 0 (Not Motivational), 1 (Motivational).  

## Evaluation Criteria  
The performance is measured using **Macro F1** for each subtask and their average.  
