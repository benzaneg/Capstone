# Capstone


Executive Summary:
As an amateur historian I am intrigued in the relationshup between primary and secondary sources. The downstream exchange of ideas and knowledge from primary sources to secondary sources is an interesting and convultued path since secondary sources' foundation are primary sources which are written in a different milieu, without knowledge of all the pieces, and without a heavy dose of hind sight. How does it look to go up the stream from the estuary to the head waters of the information river? Do secondary sources have direct link to primary sources? On top of this exchange, I have explored other relationships within the texts such as temporal, document similairty, etc.

For this excersise I had two sources where I culled my natural language dataset, one primary and the other secondary. I used a renowned book series on history from Cambridge University called the "New Cambridge History of American Foreign Relations" as my secondary source. The secondary corpus is contains four volumes and a total of 42 chapters on the subject matter. I used a website from Ashland University called "Teaching American History" where they have collected thousands of primary source documents from diffrenet periods of American history. These two sources accurately, and in extreme detail, cover the history of America, but do cover slightly different material from a birds eye view, one being concetrated on foreign relations and the other on written material by people who shaped America. 

After completing the anlayses and try to parse out information which makes sense I think that historical text, historical data, is hard to pull conclusions from since you never have a complete dataset. The first hinderance is that material is generally lost over time from misplacement, corruption, ruin, etc. which means you are dealing with missing data with the only option is to ignore, you can't fabricate, you can't find means. The second is even if there are historical events or writings that have a complete "corporus", they most likely aren't stored in one spot and would be hard to compile and find. Wrestling with this limitation and hinderance was hard, but necessarcy. The next time I tackle a question of this nature I need to critically think about the documents I am analyzing. How many should there be? What quanity do I have at my disposal?

My main objective was to classify different topics in the primary source, secondary source, and together. Topic modeling is more ephemeral and doesn't quite have metrics other than readability. On top of topic classification I have used the topics in both the secondary source corpus and the primary source corpus to classify each other. None of these have metrics but are more by look and feel of the topics. Since I can delimit certain topics and time periods I can test how accurate my topic model does in classifying correct topics in primary source from a model trained with secondary sources documents and vice versa. Sadly though that is more visual than statistical.

As I mentioned earlier the data from the two sources aren't one - to - one meaning they cover slightly diffrent material, even with the actual date of publication ignored, and may have introduced errors into the work. The sources, while trying to be comphrenisve, are not. The Camrbidge History book is only one secondary source and another institution or person would write about the topic diffrently creating a narrow lense. The same goes for the primary source corpora where even though it contains 1725 documents from 100+ people there are voices missing.

I implemented the web scraping libraries Selenium and Beautiful Soup to accquire my data. Teaching American History is a free resource from Ashland University while Cambridge University is behind a paywall which I have access to through university connections. 

Since my data is NLP based and I conducted multiple anaylses I transformed my corpora in multiple ways. All of the data was lemmatized (to keep readibility of the words), stop words, and puncuation was taken out. From there I created a few more columns which just had named entities and one without named entities. Since I explore both Sklearn and GenSim's LDA model I had to split up the NL in different ways to for readable input.

I selected the GenSim LDA model since I was able to integrate Sklearn's CountVectorizer into the model pipeline enabling me to have more control on the data my model was seeing and taking advantage of GenSim's robust class methods, use a custom model as an input into DTM, and the output of the model in of itself seemed to be better even if the hyperparameters were the same. 