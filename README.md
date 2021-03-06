## Introduction
- A classification of Sentiment Analysis which is implemented by pytorch.
* There are many data in [data](https://github.com/zenRRan/Sentiment-Analysis/tree/master/data), *.txt of that are came from [sent-conv-torch](https://github.com/harvardnlp/sent-conv-torch), *.conll.out of that are generated from our lab's parser.
    * TREC
    * SUBJ
    * MR
    * CR
    * MPQA

- My processed data by preprocessed.sh will be saved in [processed_data](https://github.com/zenRRan/Sentiment-Analysis/tree/master/processed_data).
* There are many models in [models](https://github.com/zenRRan/Sentiment-Analysis/tree/master/models).
    * Pooling
    * CNN
    * Multi_Channel_CNN
    * Multi_Layer_CNN
    * CharCNN
    * GRU
    * LSTM
    * LSTM_CNN
    * TreeLSTM
    * biTreeLSTM
    * TreeLSTM_rel
    * biTreeLSTM_rel
    * CNN_TreeLSTM(ready to refresh)
    * LSTM_TreeLSTM(ready to refresh)
    * Transformer(TODO)
- My log will be saved in [log](https://github.com/zenRRan/Sentiment-Analysis/tree/master/log).
* There are many scripts in [utils](https://github.com/zenRRan/Sentiment-Analysis/tree/master/utils).
    * Alphabet.py which is used to build dictionary.
    * Common.py which is saved unk-key and pad-key.
    * Embedding.py which is used to load pre_train embedding by Yang Song.
    * Evaluate.py which is used to calculate the F1.
    * Feature.py which is implemented a sentence's features, including word, word_id, label, root and so on.
    * build-batch.py which is used to build the data's mini batch.
    * log.py which is used to save the log.
    * opts.py which is implemented the argparses.
    * trainer.py which is used to train the data.
    * tree.py which is implemented the tree's methods.

## Requirement
        python : 3.5+
        pytorch : 0.4.0
        cuda : 8.0 (support GPU, you can choose)

## Usage
- first step

        sh preprocess.sh
- second step

        sh run.sh

## Result


| Data/Model(acc)   | TREC  | SUBJ  | MR    | CR    | MPQA  |
| ------            | ------ | ------ | ------ | ------ | ------ |
| Pooling           | 76.12 | 89.58 | 74.51 | 80 | 86.43 |
| CNN               | 90.4  | 91.98 | 77.73 | 84.38 | 88.96 |
| Char_CNN          | 91.52 | 93.33 | 78.91 | 84.38 | 86.33 |
| Multi_Channel_CNN | 89.06 | 94.06 | 79.59 | 83.12 | 88.48 |
| Multi_Layer_CNN   | 91.74 | 93.65 | 79    | 84.06 | 89.36 |
| LSTM              | 89.73 | 92.5  | 80.57 | 83.75 | 89.65 |
| LSTM_CNN          | 92.63 | 92.19 | 81.05 | 83.12 | 89.16 |
| GRU               | 89.06 | 92.6  | 79.1  | 83.44 | 89.75 |
| TreeLSTM          | 89.96 | 92.71 | 78.61 | 84.38 | 88.67 |
| biTreeLSTM        | 92.41 | 92.08 | 78.91 | 82.81 | 89.26 |
| TreeLSTM_rel      | 91.29 | 92.19 | 79.69 | 84.06 | 89.06 |
| biTreeLSTM_rel    | 91.07 | 91.46 | 78.81 | 82.81 | 89.45 |
| CNN_TreeLSTM      | - | - | - | - | - |
| LSTM_TreeLSTM     | - | - | - | - | - |

### In addition:

#### Data
 - TREC: `TREC question dataset` - task involves classifying a question into 6 question types (whether the question is about person, location, numeric information, etc.) (Li and Roth, 2002).
 - SUBJ: `Subjectivity dataset` where the task is to classify a sentence as being subjective or objective (Pang and Lee, 2004).
 - MR: `Movie reviews` with one sentence per review. Classification involves detecting positive/negative reviews (Pang and Lee, 2005).
 - CR: `Customer reviews` of various products (cameras, MP3s etc.). Task is to predict positive/negative reviews (Hu and Liu, 2004).
 - MPQA: `The MPQA Opinion Corpus` contains news articles from a wide variety of news sources manually annotated for opinions and other private states (i.e., beliefs, emotions, sentiments, speculations, etc.).

#### Emphasize
 - `pre_trained_embed` which is using `glove.6B.100d.txt`.
 - `TreeLSTM` which is using `ChildSum` method.
#### Future Work
 Other methods about `TreeLSTM` will be updated in the near future.

## Question
Glad to receive your report by `zenrran@qq.com`, If you have any questions about this code !