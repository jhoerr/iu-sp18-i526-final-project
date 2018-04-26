# Predicting Shelter Animal Outcomes

The goal of this project was to model and provide a basis for predicting the outcomes of shelter animals. I proposed to improve adoption rates by modeling and classifying shelter animal outcomes using a combination of observable and historical features. This model could be used by shelter staff to allocate resources in a way that maximizes their adoption goals.

Our data source (and inspiration) for this project is the Kaggle competition, Shelter Animal Outcomes. The training data set included outcomes for approximately 27,000 unique animals in the Austin, TX area from October 2013 to March 2016. This data was limited to cats and dogs, and included input features such as the animal’s name, age, sex, reproductive status, and breed, as well as visual information such as its coloring and coat pattern. The outputs included the classification of the animal outcome -- whether it was adopted or euthanized, among others – and often the reason for the animal entering the shelter.

Exploratory data analysis indicated that features such as age and reproductive status would play a strong role in determining outcomes. This analysis was confirmed by later observations of feature importance. The input features were engineered primarily for normalization. Ages were converted to days, discrete labels such as dog/cat, male/female, fixed/intact were isolated, and breeds, colors, and coat patterns were distilled to their dominant values. A log-loss scoring metric was selected so as to align with the Kaggle competition. A grid search was conducted using a range of classifiers selected for their ability to produce classification probabilities in order to minimize the log-loss score.

The best model achieved a log-loss score of ~0.87 with the engineered feature set and the X Gradient Boost classifier, narrowly outperforming our baseline Logistic Regression (Softmax) with the raw features. Neither model proved any more accurate than guessing.

On review of the data, the contextual information that would inform an animal’s outcome (such as being sick or a runaway) was included as an output feature rather than an input (if it was included at all.) I was thus attempting to model outcomes based purely on physical features. By request the city of Bloomington recently released our local shelter data which includes this valuable context on a per-animal basis. I will be revisiting this problem over the summer with the Bloomington data and sharing the results with the city.