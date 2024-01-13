# Finding subject areas for scientific articles based on their titles and abstracts 

This assignment was about finding subject areas for approximately 20,000 scientific articles, given their titles and abstracts. The data is provided in a CSV file and includes columns indicating whether each article belongs to various subject areas such as Computer Science, Physics, Mathematics, etc. The goal is to create a network graph of the articles, with edges representing how relevant pairs of articles are to each other, and to examine whether the resulting communities in the network correspond to the given subject areas. The correlation between articles can be calculated using a language model that provides sentence embeddings, and the precision of the results will be evaluated based on how well they match the given subject areas. I used Python for the completion of this assignment and the following libraries : 

● NetworkX
● Pandas
● Sklearn
● Community Louvain
● SentenceTransformers
● Numpy

This was a project for class ''Network Theory'' of the winter semester of 2022-23 .

