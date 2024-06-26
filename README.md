# NLP_Project
# Sentiment Analysis and Topic Modeling with Presidential Debates 2024

# Introduction: 

In recent years, there has been a growing fascination with leveraging the capabilities of NLP and AI techniques to forecast election outcomes. This interest spans diverse methodologies including sentiment analysis, fake news identification, fact-checking, and topic modeling. Advanced models intertwine deep learning with foundational statistical approaches. Our study delves into the thematic fabric of primary Presidential campaign debates, employing sentiment analysis to gauge the emotional tone of each speech, organizing sentiments by respective candidates. Additionally, we explore topic modeling and honesty classification among candidates. Our goal involves thoroughly analyzing these debates using a wide range of ML and NLP techniques. This encompasses various practices like topic modeling, sentiment analysis, and text classification among others.

# Data Collection & Preprocessing:

Data collection was carried out by scraping the transcript of the three Republican Presidential Debates into CSV files and creating a combined dataset with all three debates and an indicator variable for which debate the statement came from.
For precision, our analysis excludes the speeches of moderators to ensure a focused dataset aligned with the original topics discussed. We specifically focus on the candidates participating in all three debate rounds.
To preprocess the data and ensure quality analysis we used: Tokenization, Lowercasing, Punctuation and Numbers Removal, Stop Words Removal and Lemmatization

# Topic Modelling:

Our project delves into the realm of topic modeling, a powerful method for uncovering concealed themes within extensive text datasets. Techniques such as LSA, PLSA, and the widely popular LDA serve to reveal abstract topics by scrutinizing distributions of words and topics within documents. LDA, particularly favored, has proven its worth in various fields like software engineering and political science, offering valuable insights that span scientific content analysis, sentiment evaluation, and financial domains.
This project was built upon the robust capabilities of BERTopic, complemented by the SentenceTransformer "all-MiniLM-L6-v2" model, which empowered us to extract and scrutinize topics from a textual dataset. The fusion of BERTopic and SentenceTransformer facilitated a comprehensive representation of textual data through embeddings, while UMAP aided in refining the process by reducing dimensionality, thus enabling a deeper understanding of the content.
Critical to our methodology was the evaluation of topic coherence. Leveraging the CoherenceModel, we discovered that BERTopic exhibited approximately 10% higher coherence than traditional LDA methods, signifying its proficiency in extracting more meaningful and coherent topics.
Moreover, our approach personalized the analysis for each speaker in the dataset, employing unique BERTopic models. This tailored strategy allowed for a nuanced exploration of topic distributions, reflecting individual disparities within the textual data. This amalgamation of advanced NLP techniques and personalized topic modeling granted us profound insights into underlying themes and patterns within the data.
Our analysis highlighted distinct relationships among topics. Notably, Topics 1 and 5, “future” and “hope”, showed high correlation, while Topics 2-4 centered on negative aspects such as “demands”, “fears”, and “constraints”. Topic 4, “constraints”, offered intriguing insights into discussions revolving around challenges, money, and opportunities, often linked to current President Biden, possibly reflecting attempts by Republican candidates to differentiate themselves from his policies.
Topic 1, “Future”, shed light on discussions encompassing words like “look”, “going”, and “answer”, revealing deliberations about former President Donald Trump’s potential role in the party’s future leadership. Despite his absence from debates, his presence in discussions indicated the party’s contemplation about his future influence.

# Topic Modelling Per Candidate:

A.	Chris Christie:

Candidate-specific modeling suggests that Chris Christie was highly focused on where the country is going. He frequently referenced former President Donald Trump. Similar to Topic 1: “future”, Christie’s interest appears to be on looking toward the future and assessing whether or not former President Trump is the most qualified candidate for the Republican Presidential nomination.

B.	Nikki Haley:

The most negative candidate across all three debates, Nikki Haley’s specific language suggests a focus on what people need and want. Her frequent references to “China” and “America” suggest a focus on international affairs that is consistent with her history as the UN Ambassador for the US. Additionally, her frequent use of the word “make” implies a level of force not present in other candidates’ language.

C.	Ron DeSantis:

Ron DeSantis’ language reveals that he relied heavily on his experience as a Florida governor to talk about the country as a whole. In fact, “florida” and “country” appear to be used almost the same amount, suggesting that DeSantis may have leveraged the debates as an opportunity to market how his tenure in Florida can be exported to a national level. He also relies on future-looking language with “going”, but his use of “decline” and “need” suggests negativity in his outlook.

D.	Tim Scott:

While immigration is a high-profile issue in the United States, only Tim Scott and Vivek Ramaswamy have an explicitly immigration-related word on their most frequently used list. Scott frequently used both “border”, “America”, and “country”, suggesting that he is particularly focused on migration into the US. Additionally, his high use of “Biden” suggests that he may have been raising immigration as a way to lodge a critique at current President Biden. Tim Scott has not stepped out of the primary race. However, his participation in the debates is still useful for demonstrating that a high focus on immigration throughout all three debates was not a winning strategy for this particular candidate, despite its salience to the Republican Party.

E.	Vivek Ramaswamy:

Vivek Ramaswamy, like Tim Scott, frequently used the word “border”, however, he also frequently used “China” rather than “America”. Like Nikki Haley, he may be particularly interested in foreign affairs. However, unlike Nikki Haley, who focused entirely on countries in her most frequently used words, Ramaswamy’s high use of the word “border” suggests that he is particularly interested in immigration. Additionally, his use of “think”, “want”, and “people” far and above other words suggests that Ramaswamy may be relying on populist rhetoric for his campaign.

# Sentiment Analysis:

Our project also explores sentiment analysis, a technique pivotal in categorizing sentiments as positive, negative, or neutral, offering crucial insights into aligning information with entities. While recent advancements in machine learning and deep learning have bolstered sentiment analysis algorithms, the labor-intensive nature of manually classifying sentiment words remains a challenge.
In the context of elections, detecting sarcasm emerges as a persistent obstacle, urging continuous research endeavors. Despite these challenges, sentiment analysis stands as a crucial tool, especially in unraveling the intricate nuances within political conversations during pivotal events.
Our project included an exhaustive sentiment analysis and misinformation detection exercise on a text dataset, employing advanced NLP techniques. In light of this, we deployed a sentiment analysis pipeline that segmented the text data into manageable chunks to accommodate the pipeline’s limitations. Each chunk underwent sentiment analysis, and an average sentiment score was derived to portray the overall sentiment of the text. This approach, applied across texts associated with different speakers, facilitated the aggregation of sentiment scores by candidate, unveiling a nuanced understanding of each speaker’s expressed sentiment within the dataset.
Simultaneously, we addressed the challenge of misinformation detection, utilizing a labeled dataset that distinguished between fake and real news. After preprocessing steps like handling missing values and splitting the data into training and test sets, we crafted a machine learning pipeline amalgamating a TF-IDF vectorizer with an SVM classifier, a proven approach in text classification. The classifier was trained on the training data and subsequently employed to predict labels on the test set, culminating in a comprehensive classification report assessing its performance.
Applying this trained misinformation detection model to our dataset allowed us to assign predicted labels to each text, creating a summary of the “honesty” of each speaker based on the proportion of their texts classified as real or fake news. This dual approach, embracing both sentiment analysis and misinformation detection, yielded a comprehensive perspective on the textual data, providing insights into both the emotional tenor and the factual reliability of the content.
Our analysis revealed a pervasive negativity across topics and candidates during the Republican debates, consistent with sentiment analysis findings. Despite minor variations, the sentiment analysis identified all candidates as consistently expressing highly negative sentiments throughout the three debates. Notably, Nikki Haley’s comments garnered the most negative classification, while Vivek Ramaswamy and Tim Scott exhibited relatively less negativity. Overall, the Republican debates depicted a predominantly negative outlook on American affairs, reflecting the sentiment prevalent in the debates.
