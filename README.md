# Russian Arms Exporters

By Andrea Christelle, Ian Forrest, David Hang, Curtis McKendrick, & Andre Savkin

C4ADS aims to identify non-state arms exporters and front companies for state-sponsored arms exports using profiles created from known exporters and manufacturers. This training set of tagged data consists of exports from Ukrainian and Russian state-owned arms exporters, with the aim of training a model for the identification of smaller companies exporting similar products or trading with similar parties. This information may be shared with export control authorities (C4ADS has a direct partnership with the IAEA Department of Safeguards).

The project was started in Labs16, and was carried over and documented beautifully in Labs18 by data scientists Sean Antosiak, Elliot Gunn, Andrew Mikol, & Jason Nova. Labs18 team's initial groundwork and guidance was critical to Labs20 success. Their work can be found in the Labs18 folder of this SageMaker instance, and their project writeup can be accessed via the following link: https://docs.google.com/document/d/1nyjZ-eFwbfiQjSgNTu9eL-2cWWc7CuvRxOJMZZIKcWQ/edit.

Our project aimed to build these 'profiles' for known Russian arms exporters analyzing text through natural language processing (NLP). The dataset we analyzed, provided by C4ADS, contained over 10 million rows of Russian trade information. Using NLP, we analyzed the text in the 'description' of every trade, and subsequently grouped bodies of similar text together using machine learning and KMeans clustering.

Once grouped, our customized product analyzes the patterns in the text of those trades and compares it with trading patterns of known arms exporters. This is accomplished by looking at the inverse euclidian distances and pairwise distances between the observations in n-dimensional space. In other words, it checks how similar the cluster ratios of each company are to known arms exporters.

For example, let's say trade text for known arms exporters fall heavily in clusters 2, 5, and 7. Companies whose trade text falls in clusters 2, 5, and 7 will likely have a high similarity to known arms exporters. Companies whose trade text falls in clusters 0, 1, and 6 will likely have a low similarity to known arms exporters, and thus not considered by our product.

The notebooks in this repository will explore our process.