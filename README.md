# Recommender-systems

This is going to be the list of done tasks:

Fourth of October: added SVG + removed the projects type + changed the categories with small number of vars to cat type + corrected the previous dataset, it still had people with less than 5 donations and projects with less than 30 donations!

Task: 
create a clean eda notebook
continue svg

| Rec | Model  | Results | Specifications |
| -- | ------------- | ------------- | ------------- |
| 1 | TFIDF  | {'modelName': 'Content-Based', 'recall@3': 0.2672732442422519, 'recall@5': 0.3210122263292579, 'recall@10': 0.4139891953369349}  | Spec.1 |
| 2 | SVG  | {'modelName': 'Collaborative Filtering', 'recall@3': 0.6124537958487347, 'recall@5': 0.6994597668467444, 'recall@10': 0.809212396929201}  | |
| 3 | Embeddings  | {'modelName': 'Content-Based-Embeddings', 'recall@3': 0.10093829968723343, 'recall@5': 0.13392095535968154, 'recall@10': 0.20926926357691214} | |
| 4 | Hybrid  | {'modelName': 'Hybrid', 'recall@3': 0.6050611316462895, 'recall@5': 0.6724481091839636, 'recall@10': 0.752061415979528} | Spec.2 |
| 5 | Graph-based  |  | Spec.3 |


`Spec.1`: 

The text consists of the following:

['Project ID', 'Project Subject Subcategory Tree', 'Project Title', 'Project Need Statement', 'School State']

* I believe the results of this and embedding can get much better with just adding more expl.
* Add posted year
* Add <SEP>

`Spec.2`:

the result of ALL models were added. - TFIDF, embedding, SVD


Things to change or check in the future:
* Add Dates


`Spec.3`

External dataset source: [link](https://www.unitedstateszipcodes.org/zip-code-database/)
I'm using the same people who have donated at least 5 times.