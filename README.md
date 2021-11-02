# Recommender-systems

This is going to be the list of done tasks:

Fourth of October: added SVG + removed the projects type + changed the categories with small number of vars to cat type + corrected the previous dataset, it still had people with less than 5 donations and projects with less than 30 donations!



---
### Evaluation

`project_i` = a project the donor has donated to in the test set 

`all_projects` = projects the donor has donated to in the test set


for each projects (`project_i`) in `all_projects`:

1. Select 100 random projects the donor had not donated to.
2. Put `project_i` among these 100 random projects
3. See where `project_i` is ranked by the algorithm

Count for what number of times donated projects have been in the top 3, 5, and 10.

* Recall@n : # of projects ranked as top n / count(`all_projects`) 
---

| Rec | Model  | Results | Specifications |
| -- | ------------- | ------------- | ------------- |
| 1 | TFIDF  | {'modelName': 'Content-Based', 'recall@3': 0.2672732442422519, 'recall@5': 0.3210122263292579, 'recall@10': 0.4139891953369349}  | Spec.1 |
| 2 | SVG  | {'modelName': 'Collaborative Filtering', 'recall@3': 0.6124537958487347, 'recall@5': 0.6994597668467444, 'recall@10': 0.809212396929201}  | |
| 3 | Embeddings  | {'modelName': 'Content-Based-Embeddings', 'recall@3': 0.10093829968723343, 'recall@5': 0.13392095535968154, 'recall@10': 0.20926926357691214} | |
| 4 | Hybrid  | {'modelName': 'Hybrid', 'recall@3': 0.6050611316462895, 'recall@5': 0.6724481091839636, 'recall@10': 0.752061415979528} | Spec.2 |
| 5 | Graph-based  | {'modelName': 'graph_based', 'recall@3': 0.14260089686098654, 'recall@5': 0.18684603886397608, 'recall@10': 0.2687593423019432} | Spec.3 |
---

`Spec.1`: 

The text consists of the following:

['Project ID', 'Project Subject Subcategory Tree', 'Project Title', 'Project Need Statement', 'School State']

* I believe the results of this and embedding can get much better with just adding more expl.
* The stopwords could be removed
* Add posted year
* Add <SEP>

`Spec.2`:

the result of ALL models were added. - TFIDF, embedding, SVD


Things to change or check in the future:
* Add Dates


`Spec.3`

External dataset source: [link](https://www.unitedstateszipcodes.org/zip-code-database/)
I'm using the same people who have donated at least 5 times.
For external 0.998 percent of people remain after merging the datasets (external and the main df)

* The stopwords could be removed

I used the same method as I did in the embedding notebook for calculating the preference of donors (the embeddings). More specifically, the embeddings of project he\she has donated to, will be multiplied by the amount of donation and then summed up.

* I did not remove any stopwords
*Overall we have projects_df, donor_profile_df, donor_profile_emb



### <span style="color:lightgreen">Things to be changed/proposals </span>
* We could use the last n donations of each user for the test set

 *Doing a random split would not be fair, as we could potentially be using a user’s recent reviews for training and earlier reviews for testing.* [link](https://towardsdatascience.com/deep-learning-based-recommender-systems-3d120201db7e)