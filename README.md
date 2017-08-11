# Documents-Topic-Assignment
Assign Topic to Text Document by Cluster and LDA

Text documents are assigned into given number of topics by k-means cluster and LDA methods.

Firstly, the input text is transformed into a dtm format by applying "chinese.misc" package.
Secondly, the dtm data is used for k-means cluster and LDA.

Taxonomy Project
    Data Source: E-commerce products. The structure of such data set is well-structured.
        We use the “title” and “props” information in provided data. And for “props” there involves the names of features, which is not our interests. We propose to ignore the name words before token “:” and only the features are taken into consideration. 
    Applied Algorithm：LDA and HDP. 
        Both methods applied the Dirichlet distribution as prior for topics distribution. The difference of LDA and HDP is mainly about the number of topics that LDA requires a pre-setting but HDP not. The return of LDA contains a lot of information. Most useful things would be (1) Dictionary of all words in provided “title” and “props” and their contribution for all topics, (2) An assignment of topic label for each product depend on dictionary in (1). (One proposed adjustment here is based on our specific interested words. Based on any current method, if we can identify some important words and features, we could adjust their contribution in the dictionary as rescaling.) 
        Cautions in applying LDA and HDP: (1) The assignment of topic is based on similarity of whole text contents not certain clearly understanding keyword. (2) This clustering/grouping only gives a partition of data. Be careful for the data source. It is helpful in dealing with well-separated data. (3) After the assignment of topics, detailed in-group analysis is recommended to come up with useful dictionary in building the Taxonomy Tree. (4) To decide the clear topic in the result, the proportion contribution for total variance can be a criterion.
    Continued Work: (1) With a clustering result for current Taxonomy Tree, we can give sub-sub-category clustering result. The continued work could be using feature selection technique to find out a group words with main contribution to this cluster. Hence, we result a group of keywords for each sub-sub-category. (2) For new coming products, the prediction can be made in the following process: A. Select features for each current sub-group using known method. B. Matching new coming products words with features in A and decide its topic using maximum assigning probability rule. After large number of new products added, we can redo the LDA/HDP process to update our grouping and hence update the features in prediction for new products.

For the Taxonomy in R, please find the R-package, https://github.com/AcroGao/Documents-Topic-Assignment.
