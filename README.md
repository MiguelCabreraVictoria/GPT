# GPT

Miguel Angel Cabrera Victoria

A01782982 

## Table of Contents 

- [About](#about)
- [Requirements](#requirements)
- [Installation](#installation)
- [Architecture](#architecture)
- [Dataset](#dataset)
- [List of inputs](#list-of-inputs)
- [Usage](#usage)
- [Results](#results)
- [License](#license)


## About 



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

        git clone git@github.com:MiguelCabreraVictoria/GPT.git ~/Desktop
        
        git clone git@github.com:c-w/gutenberg.git ~/




## Architecture

The model architecture is based on the transformer architecture

![architecture](/images/architecture.png)


## Dataset 

![datasetImage](/images/projectGutemberg.png)

- The dataset is sourced from Project Gutemberg, an online library of free eBooks.

- Books are stored in <b>.txt</b> fomat.

- The content is pre-proccessed

For more information about the dataset visit the next link [Project Gutemberg](https://www.gutenberg.org/browse/scores/top1000.php)


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



## Usage

One you have set up the environment and installed the dependencies, unzip the folder models.zip 

        unzip models.zip -d ~/Desktop/GPT

- Select one model 

        > oneBook_model
        > tebBooks_model
        > hundredBooks_model

- Go to the Test models cell
- Insert your option and prompts (> 8 tokens)



## License

This project is licensed under the MIT License




