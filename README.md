# nlp
![710888b3ebc3889dad7850790ffa5393](https://github.com/Dipannita-Ray/nlp/assets/155419369/0c189231-999a-4a25-bf95-d6b436905cb6)

Natural Language processing is a subfield of linguistrics,computer science and the artificial intelligence concerned with the interactions betwwen computers and human language ,in particular how to program computers to process and analyze large amounts of natural language data.  
# Need for NLP:
in neuropsychology ,linguistics and the philosophy of language ,a natural or ordinary langyage is any langyage that has evolved naturally in humans through use and repetition without conscious planning or premeditation. Natural languages can take different forms ,such as speech or signing .they are distinguished from constructed and formal languages such as those used to program computers or to study logic  
# challenges in nlp:
- ambiquity(single sentence can have multiple meaning)
- contextual words(same words has different meaning)
- colloquialisms and slang(some sentence has difference meaning like 'pulling leg' has a difderent meaning for a human and a machine)
- synonyms
- irony and tone difference(make a lot of difference in the sentence)
- spelling erros
- creativity
- diversity in languages
# common nlp tasks :
- Text/document classification
- sentiment analysis
- information retrieval
- parts of spech tagging
- Laguage detection and machine translation
- conversational agents
- knowledge graph
- text summerization
- topic modelling
- text genration
- spell chaecking and grammer detection
- text parsing
- spech to text
# approaches 
### heuristic approch: rule base appproch (checking negative and positive in a sentence to predict sentiment)
2. regular expression
3. wordnet(lexical dictionary i.e. checking checking relationship between words)
4. open mind commonsense(database that contain common sense that can be used futher for nlp problem)
### macine learning approch:
1. rules are made by algorithm therefore is made by checking the data.
2. Ml workflow
3. Algo are: naives bayes, logistic regression, svm, lda, hidden markopv model.
### deep learning:
1. as ml changes texual data to numbers therefore it doesnt care about the sequencial ,but deep learning on the other hand care about the sequencial info .
2. feacture is automatic.
3. Archietecture used are:
4. rnn,LSTM,GRU?CNN,transformer,autoencoder
# NLP pipeline:\
- nlp pipelone is a set of steps followed to build an end to end nlp software.
- nlp software steps:
   1. data acquisition: we need to check if we have data that is interal or external or dont have a data.if we have data then proceed to next step or if we have data in the database then is teh job of a data engineer to give us the data .another type is that if we have a missing data then we use a technique known as data agumenttation or bigram flip or back translate or add adictonal noise .if we have external source tehn we have to do public dataset or web scrapping(beuatifull soup) or  go to any api(rapid api,lib is there request) ,audio data(speech to text librarry),pdf(),or image(ocr)
   2. text prepartion
       - text cleanup: html tags cleaning, emojis by unicode normalization,spelling checker(textblob),
       - basics Presprocessing(tokenization(sentence and word tokenization),word2word ,removing punctuation,stopwordsremoval,steming,lemmetization removing ounctuarion, lowercasing,laguage detection)
       - advance preprocessing(pos tagging,parsing,chunking,coreferencing resolution)
    3. feature Engineering: when text are comnverted into number it is called feature engineering(text vectorization,bag of words)
    4. modeling: this step is formed after data is prepared then a suitable a environment is used.
        - model building: to determine the which is better it depends on amount of of data, nature of problem,.transfer learning can also be used . 
           1. heuristic
           2. ml algo
           3. dl
           4. cloud api
        - evaluation: means how model is performing on unseen data.
            1. intrinsic evalution: on a technical level accuracy is check
            2. extrinsic evalution: after deployment accuaracy is checked on bussiness setting.
     5.deployment  :
          1. deployment, depends on what u r making , ex spam email project is a small project so we have to make an api then when the email system will gey a email it will connect to the api(micro service) then classification is made. for a chat bot deployment is different like a watsapp deployment,telegram deployement,
          2. monitoring , chekc if the model is working properly, generally  adashboard is used to check extrinsic and intrinsic evaluation and graph is made btw historical and new data 
          3.  model update,
   ### perplexity : tells how much confuse your nlp model is.
    ### points to remember :
  1. not a universal pipeline therefore every model can need different pipeline.
  2. deep learning pipelines are sligtly different.
  3. pipeline is non=linear. 
 ### exercise 
 # text prepocessing:
  ## 1. Basic text preprocessing:
  1. lowercasing
  2. remove html tags
  3. remove url
  4. remove punctuation
  5. chat word treatment: make a dictionary of the chat words and then write a function
      ``` def chat_conversion(text)
           new_text = []
           for w in text.split():
               if w.upper() in chat_words:
                   new_text.append(chat_words[w.upper()])
               else:
                    new_text.append(w)
              return " ".join(new_text)

   6. removing emojis: we can remove emoji or replace it with actual meaning of it.
       ``` import re
           def remove_emoji(text):
           emoji_pattern = re.compile("["u"\U0001f600-\U0001F64F""]+", flags=re.UNICODE)
           return emoji_pattern.sub(r'', text)   
        # or to replace with meaning
        import emoji
        print(emoji.demojize('Python is ')) 
        
  7. Tokenization: it can be word or sentence hence it gives a list in return. challenges in tokenization are. prefix: characters at the begining ex-$20 ,sufix: 20km,unfix : character in between ex-he/her, exception : special -case rule to split a string into several tokens or prevent a token from being split when punctauation rule are applied ex-let's, U.S
  8. stemming  : used in informTION retrival sysytem.NLTK loibrarry is used.algo that can be used are Porter Stemmer(for english) and snowball stemmer
  9. lemmetization: Unlike stemming ,reduces the inflected words properly ensuring that the root word belongs to the language .here root word is called lemma. word net is an english dictionary.while lemmetizing we also have to include the part of speech. 
  10.
 # feature Extraction:
 chnaging text to numbers. there is a need of feature extraction is due to importance of feature. 
 1. one hot encodung: problem: sementic meaning is lost,sparsity,no fixed size ,  
 2. bag of words: used in text claasification technique, here we create a vocabulary , order of the words doesnt matter , count vectorizee is used
 3. ngrams
 4. Tfidf
 5. custom feactures
 6. word2vec
# Advance Features:
Let us take an sentence: virat kohli is my favourite cricketer.here token are all the words, whereas  stopwords are the sementic words like is my which have no meaning but are used for sentence formation, words are the words that doesnt have stopwords
1. Token features:
     - cwc_min: ratio of number of common words to the length of the smaller  question.formula: common words/min(words(q1,q2))
     - cwc_max: ratio of number of common words to the length of the larger ques.
     - csc_min: ratio of no.of stopwords to the smaller stopwords count among the two ques.common stopwords/min(stopwords(q1,q2))
     - csc_max: ratio of no.of common stopwords to the larger stopwords count among the two ques.
     - ctc_min: ratio of no.of common tokens to the smaller token count among the two questions. common tokens/min(tokens(q1,q2))
     - ctc_max: this the ratio of no. of common tokens to the larger token count among the two ques
     - last_word_eg: 1 if the last word in the ques is same , 0 otherwise. 
     - first_word_eg: 1 if the first word in the two question is same ,0 otherwise.
   
2. length based features:
     - mean_len: mean of the length of the question(no.of words). (q1 +q2)/2
     - abs_len_diff: Absolute difference the length of the two ques(no.of words).(q1-q2) 
     - longest_substr_ratio: ratio of the length of the longest substring among the two questions to the length of the smaller ques. 
3. Fuzzy features:
   FuzzyWuzzy is a python package that can be used for string matching. We can run the following command to install the package –
   ``` pip install fuzzywuzzy ```
   
   - fuzz_ratio: fuzz_ratio score from fuzzywuzzy.
       ``` from fuzzywuzzy import fuzz
           Str1 = "Back"
           Str2 = "Book"
           Ratio = fuzz.ratio(Str1.lower(),Str2.lower())
           print(Ratio)```
    hence the output is 50.here order of the words also matters 
   - fuzz_partial_ratio: token_sort_ratio from fuzzywuzzy.The partial ratio helps us to perform substring matching. This takes the shortest string and compares it with all the substrings of the same length.
       ```Str1 = "My name is Ali"
        Str2 = "My name is Ali Abdaal"
        print(fuzz.partial_ratio(Str1.lower(),Str2.lower())) ```
   The output of the code gives 100 as partial_ratio() just checks if either string is a substring of the other.
   - token_set_ratio: toekn_set_ratio from fuzzywuzzy.Token set ratio performs a set operation that takes out the common tokens instead of just tokenizing the strings, sorting, and then pasting the tokens back together. Extra or same repeated words do not matter.
        ``` Str1 = "My name is Ali"
            Str2 = "Ali is my name name"
            print(fuzz.token_sort_ratio(Str1,Str2))
            print(fuzz.token_set_ratio(Str1,Str2))```
   The output of the token sort ratio comes to be 85 while that of the token set ratio comes to be 100 as the token set ratio doesn’t take into account the repeated words.   
