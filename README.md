# Data science lab: process and methods
Lecture notes from the Polytechnic of Turin.

Slides: https://dbdmg.polito.it/dbdmg_web/index.php/2023/09/27/data-science-lab-process-and-methods-2023-24/

This is a collections of notes from labs and exercises.


## 📚 Lecture 2023-10-04:
*Slides: 01-Python-Intro all, 02-Python-Programming to page 26*

Python is an interpreted language. 🙀

Python is an object oriented language, every piece of data in the program is an Object. 👍

A single Python object can have multiple references (alias).

A variable is a reference to an object.

Basic immutable data types: int, float, bool, str, None.

Composite data types: tuple (immutable), list, set, dict.


## 📚 Lecture 2023-10-11:
*Slides: 02-Python-Programming to page 75*

Arguments: tuple, list, set, dictionary, if/elif/else, iterations, class.


## 📚 Lecture 2023-10-16:
*Slides: labs/lab1*

- [Iris flowers dataset matplotlib](labs/lab1/iris.ipynb)
- [Citybikes dataset - find nearest station](labs/lab1/citybikes.ipynb)
- [MNIST dataset and euclidean distance](labs/lab1/mnist.ipynb)


## 📚 Lecture 2023-10-16 bis:
*Slides: 02-Python-Programming all, 03-Python-Projects all*

Arguments: dict, methods, classes, package, module, import


## 📚 Lecture 2023-10-23:
*Slides: labs/lab2*

- [Temperatures dataset fix missing values](labs/lab2/temperatures.ipynb)
- [IMDB (movie database) tf-idf](labs/lab2/movie_db_tf-idf.ipynb)

tf-idf = term frequency–inverse document frequency.

Compute the inverse document frequency (IDF). While the TF gives an idea of the weight of a token within a document, the IDF is used to find its significance among the entire collection of documents

Compute the TF-IDF. Combine the definitions of term frequency (TF) and inverse document frequency (IDF), to produce a composite weight for each term in each document. The TF-IDF weighting scheme assigns to a term t a weight in the document.


## 📚 Lecture 2023-10-25:
*04-Numpy to 36*


## 📚 Lecture 2023-10-30:
*Slides: labs/lab3*

- [Online retail with Apriori and FP-growth algorithms](labs/lab3/online_retail_apriori_fpgrowth.ipynb)

Using `pandas` and `from mlxtend.frequent_patterns import fpgrowth`


## 📚 Lecture 2023-11-08:
*04-Numpy to all*
https://github.com/dbdmg/data-science-lab/blob/master/exercises/2-Numpy%20Examples-Solution.ipynb


## 📚 Lecture 2023-11-13:
*Slides: labs/lab4*

- [K-Nearest Neighbors algorithm on Iris dataset](labs/lab4/k-neareset-neighbors.ipynb)

Build your own version of the K-Nearest Neighbors algorithm (a.k.a. KNN) using the NumPy library.
