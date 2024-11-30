

# GPT

## Table of Contents 

- [Introduction](#introduction)
- [About](#about)
- [Requirements](#requirements)
- [Installation](#installation)
- [Architecture](#architecture)
- [Dataset](#dataset)
- [List of inputs](#list-of-inputs)
- [Usage](#usage)
- [Results](#results)
- [Limitations](#limitations)
- [Future Work](#future-work)
- [License](#license)


## Introduction 

This project involves the implementation of a GPT-based model trained on a dataset from Project Gutenberg. The goal is to explore the potential of language models in generating coherent, contextually relevant text. Using the Transformer architecture, the project focuses on enhancing the ability of AI models to understand and generate natural language. By training the model on a vast corpus of literary works, the model will be able to generate meaningful text, simulate creative writing, and assist with language understanding tasks.

>### What is a transformer? 

A Transformer is a deep learning neuronal network designed to understand context and meaning bt analyzing the relationship between different words in a sequence.

- Casual-Attention: This allows the model to focus on important parts of a sentence, campuring context effectively

- Parallel Processing: Transformers process all elements of a sequence simultaneously.


![levels](/images/levels.png)

## About 

This project was developed as part of the study of language models for my Artificial Intelligence concentration at Tecnológico de Monterrey. It demonstrates how transformer-based architectures can be applied to generate coherent and contextually meaningful text outputs.

By leveraging the Transformer architecture, this project explores the key components of modern natural language processing, including self-attention, causal attention, and parallel processing, to efficiently analyze and generate text. Using a dataset from Project Gutenberg, which contains a rich repository of literary works, the model is trained to mimic patterns, grammar, and structures found in human-authored text.

The objective of the project is to showcase how advancements in AI, such as transformer-based models, can extend beyond traditional computational tasks to more creative domains, such as literature generation and language understanding.

## Requirements

- Python 3
- CUDA  > 12.2
- Pytorch
  
        pip install pandas
        pip install asyncio
        pip install aiohttp
        pip install bs4
        pip install matplotlib 
        pip install pickle 

## Installation

- Clone the next repositories locally

        git clone git@github.com:MiguelCabreraVictoria/GPT.git ~/Desktop
        
        git clone git@github.com:c-w/gutenberg.git ~/

- Run the following Sections
        
  - Libraries
  - Architecture 
  - GPT Model
  - Read Text books content
  - Tokenize content & Data Loaders
  - Training Model 
  - Additional Features


## Architecture

The model architecture is based on the transformer architecture

Pre-LayerNorm: Layer Normalization before MultiHeadAttention 
        and dropout (leads to better training dynamics).  

Shorcut Connection: Maintain large gradient values (vanishing gradients)

Normalization(Unit variance): Mean of 0 and variance of 1

![architecture](/images/architecture.png)

> My architecture configurations

        Embedding Size: 128
        Number of header: 6 (count of attention heads in the multi-head attention mechansim)
        Number of layers: 6 (number of transformer blocks in the model)
        Dropout: 0.3

> GPT2 configurations

        Embedding size: 768
        Number of headers: 12
        Number of layers: 12



## Dataset 

![datasetImage](/images/projectGutemberg.png)

![book1](/images/book1.jpeg) 
![book2](/images/book2.jpeg)
![book3](/images/book3.jpeg)

- The dataset is sourced from Project Gutemberg, an online library of free eBooks.

- Complex linguistic structures and extensive vocabulary 

- Spans Various genres, eras, and styles.

- deep semantic undestanding 

- Books are stored in <b>.txt</b> fomat.

- The content is pre-proccessed

![content_memoryUsage](/images/memory_content.png)

For more information about the dataset visit the next link [Project Gutemberg](https://www.gutenberg.org/browse/scores/top1000.php)


### Zipf's Law

Statistical principle that describes the frequency distribution of words in natural language. It states that the frequency of a word is inversely propotional to its rank in the frequency table.


$$
f(r) \propto \frac{1}{r^s}
$$


- This law explains the power-law distribution of word frequencies, where a few words appear very frequently, while most words are rare. This principle is crucial for understanding tokenization, vocabulary design, and model optimization in NLP.


- Frequent words dominates training dataset, which can bias the model.

![zipf_graph](/images/zipf_1.png)
![zipf_](/images/zipf_2.png)

### Example Moby Dick 

![zipf_](/images/zipf_3.png)


## List of Inputs

[Single book](/books/one.txt): /books/one.txt

[Ten books](/books/ten.txt): /book/ten.txt

[One hundred books](/books/hundred.txt): /book/hundred.txt


## Results

- ### One book 

![training_lossOne](/loss_functions/one_book.png)

- Unmasked text generator

        User: "Once upon a time in a distant land"
        
        GPT: Once upon a time in a distant land ,  and the magistrate ,  I am sent to be replaced ,  for the first time ,  and I was not to be proved that I am to see me .  Kirwin ,  I am fearless to be replaced ,  and I am fearless to be replaced ,  and I am fearless to be replaced ,  and I am fearless to be replaced ,  and I am fearless to be replaced ,  and I am fearless to be replaced ,  and I am fearless to be replaced


- Masked text generator 

         User: "It was on a dreary night of November when I beheld the accomplishment"

        GPT: It was on a dreary night of November when I beheld the accomplishment ;  and as itssecut to reach them on my destiny .  But have already made me with a person of death ;  but it was the first time that the first night had beaten that of his companions ,  a dream ,  and my eyes was very agitation ,  and for I had departed . ”   “Are you entered that I have no surprise .  “What me ,  apprehend ,  on his father became infl ,  I am for well as a dream of fortune ,  so unaccount ,  that my father .  How thought ,  to me as the magistrate ;  his father ,  and I should fill them in the first graspingonies that the corpse that had passed before its countenance .



- ### Ten books

![training_lossTen](/loss_functions/ten_books.png)


        User: Today is a beutiful day for being happy   

        GPT: Today is a beutiful day for being happy       Be as to you ,  or ,  or have you seen ,  We’ll see you now anon .  And I will not be revenged ,  where you wot not .   ARCITE .  But it shall be a woman in the prison .  A room in the prison  Scene II .  The forest  Scene V .  Athens  The Jailer .  Thebes ,  my lord ,  I am a fair man .  If this world be well said I had rather been myself .  I would not ;  And when I hear I can .   ARCITE .  Thou art a heavenly man ,  not a gentlewoman ,  I should ,  And

- ### One hundred books

![training_lossHundred](/loss_functions/hundred_books.png)



## Usage

- Select one model 

> oneBook_model [option 1]

> tebBooks_model [option 2]

> hundredBooks_model [option 3]



![memory_modelsUsage](/images/memory_models.png)

- Go to the Test models Section 
- Insert your option and prompts (> 8 tokens)

![usage](/images/usage.png)


## Limitations

- Most of the dataset use archic styles or vocabulary

- Books in other languages

- Requires high-end GPU for training 

- Training time 

- Large storage requirements for dataset

## Future Work 

- Optimize dataset
 
  - Select books on genres that align with the desired text generation objectives
  - Select english texts to maintain consitency and avoid multi-language tokenization complexities
  - Balance the dataset for better performance
 

- Interactive Interface
  - Create a web-based interface for easier interaction with the trained models

- Fine tuning 
  - Fine-tune the model on specific genres to improve domain-specific text generation

## License

This project is licensed under the MIT License
