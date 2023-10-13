# Knowledge-Graph-Construction-for-Food-Nutrition
The global COVID-19 pandemic has prompted heightened attention to individual health, influencing various aspects of life. Empirical evidence posits that a well-established dietary structure positively impacts both physiological and psychological well-being. However, a barrier between nutritional science knowledge and public awareness, hindering the populace's access to expert dietary counsel. This research seeks to bridge the gap by offering specialized nutritional advice to the general public through the integration of computer science knowledge.

Here's a simplified version of the research process diagram:
![process diagram](https://github.com/haidisuper/Knowledge-Graph-Construction-for-Food-Nutrition/blob/main/process%20diagram.png)
## 1.Data Collection:
Utilizing "Nutrition Science," "Chinese Food Composition Table," Baidu Baike, and the Chinese Health and Wellness Website as data sources.

## 2.Data Processing:
Extract, process, and annotate data to build a corpus.  
Manually annotate chapters 2 to 11 of "Nutrition Science". Using regular expressions for rule-based extraction of content from the first three chapters of the "Chinese Food Composition Table," focusing on widely consumed and distributed food items.
 
## 3.Model Design:
Focus on nutrition, diseases, and demographics, constructing 7 node labels and 15 relationship types, with a designed pattern layer。

## 4.Data Fusion:
Address entity heterogeneity issues by designing an entity alignment algorithm based on the attribute of entities being resistant to change, using cosine similarity of word vectors to determine if they represent the same entity.

## 5.Data Storage:
Employ the Neo4j graph database to store nutritional data.    
Transform and import data into CSV format, utilizing Python's py2neo functions for entity and relationship creation.

## 6.Visualization and Recommendations:
Support basic queries and progressive retrieval.

Its pattern layer is as follows:
![pattern_lay](https://github.com/haidisuper/Knowledge-Graph-Construction-for-Food-Nutrition/blob/main/pattren_lay.png)

## This is a simple query demo. 
Take the "cardiovascular disease" node as an example, and query with the command: "MATCH (a:disease{name:“cardiovascular disease”})-[r]->(b) RETURN a,b."
![sample](https://github.com/haidisuper/Knowledge-Graph-Construction-for-Food-Nutrition/blob/main/sample.png)


For elderly individuals prone to cardiovascular ailments, it is recommended to include flavonoid-rich foods like hawthorn and pineapple in their diet. However, if diabetes, a prevalent condition among the elderly, coexists, pineapple consumption should be avoided. Notably, cardiovascular disease may manifest as a complication of iron-deficiency anemia. Supplementation with iron and vitamin C-enriched spinach can effectively curb iron-deficiency anemia and diminish the occurrence of cardiovascular disease.

## This is a example of a progressive query.

![lab](https://github.com/haidisuper/Knowledge-Graph-Construction-for-Food-Nutrition/blob/main/lab.png)
