The purpose of this assignment is to familiarize you with n-gram language modeling and a handful of smoothing techniques.


PROGRAM 1: letterLangId.ipynb
    - This program implements 3 Letter Bigram Models in order to classify whether an input sentence is English, Italian, or French without any smoothing and with add-one smoothing. Its algorithm is as follows:
            1. Preprocess text:
                - all lowercase; remove numerical values
                - remove whitespace before terminal punctuation marks 
                - tokenize (character)
                - add beginning/end sentence markers <s>, </s>
            2. Identify rare tokens in trainining set based on freq threshold (UNK_threshold) 
            3. Replace all rare tokens in training set with <UNK>
            4. Create new vocabulary V’: all tokens in modified training set (V’ = {all 
               common tokens, <UNK>, <s>, </s>})
            5. Generate unigram matrix frequency table
            6. Generate bigram matrix table (all possible bigrams from V') 
            7. Count frequencies of occurring bigrams 
            8. Normalize & compute MLE values
                - Laplace smoothing applied here 
            9. In test string, replace all unseen tokens with <UNK> 
            10. Compute probability and perplexity of test string  
            11. Return perplexities of each test string as list
            12. Compare each of the 3 language models' perpelxities for each test string 
                ex. If English model has lowest perplexity of a sentence, then decide test string is English, etc. 
            13. Write test results to text file
            14. Assess accuracy of model --> % correct 
    - The output of the highest performing model implementation is found in letterLangId.out. 
        - I have commented out other model implementations I tried (different hyperparameters); feel free to run these model implementations to obtain performance metrics. 
    - This program will run in Jupyter Notebook under 5 minutes and all necessary files are obtained using relative paths (file paths found in system-description.txt). 
    
PROGRAM 2: wordLangId.ipynb
    - This program implements 3 Word Bigram Models in order to classify whether an input sentence is English, Italian, or French without any smoothing and with add-one smoothing. Its algorithm similar to that of Program 1's, however input is tokenized by words and not individual characters. 
    - The output of the highest performing model implementation is found in wordLangId.out. 
        - I have commented out other model implementations I tried (different hyperparameters); feel free to run these model implementations to obtain performance metrics. 
    - This program will run in Jupyter Notebook under 5 minutes and all necessary files are obtained using relative paths (file paths found in system-description.txt). 

PROGRAM 3: wordLangId2.ipynb
    - This program implements 3 Word Bigram Models in order to classify whether an input sentence is English, Italian, or French with Good Turing Smoothing. Its algorithm similar to that of Program 1 and 2's, however input is tokenized by words and not individual characters and step 8 is now as follows:
            8. GT Smoothing:
                - generate a frequency of frequency table that keeps track of the count frequencies in the dataset
                - for bigrams with a count frequency between 0 and 10, GT probabilities are calculated. (count freq of 1 is  
                  treated as 0)
                - for bigrams with a count frequency greater than 10, MLE is calculated.
    - The output of the highest performing model implementation is found in wordLangId2.out. 
        - I have commented out other model implementations I tried (different hyperparameters); feel free to run these model implementations to obtain performance metrics. 
    - This program will run in Jupyter Notebook under 5 minutes and all necessary files are obtained using relative paths (file paths found in system-description.txt). 
    
