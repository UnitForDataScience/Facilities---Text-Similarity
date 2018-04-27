# Facilities---Text-Similarity
1. Currently working on approx 43000 HVAC related issues from Topic modeling.
2. Preproceessing steps:
	- Join columns 'Action.Requested', 'General.Comments', 'Task.Comments' for each issue that forms all the textual data for any issue
	- Remove Punctuations
	- Tokenize into words
	- Lemmatize the words(currently not doing POS Tagging)
	- Stem the words to get root word(Using Porter Stemmer)
	- Un-tokenize the words back into sentence
3. Get TFIDF matrix for each sentence removing stop words(add 'nan' to stop word list)
4. Train a Word2Vec model from the stemmed sentences to get text embeddings
5. Use TFIDF weighted sum of word vectors to get issue vectors(sentence or document level embedding)
6. Save the issue vectors to 'issue_text_vector.pkl'