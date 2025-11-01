# 🧬 Heredity — Genetic Trait Probability AI

A Python-based AI that uses **Bayesian networks** to model genetic inheritance and infer the likelihood that a person possesses or exhibits a particular trait. The program computes joint probabilities over gene inheritance and observable traits across generations, demonstrating reasoning under uncertainty through probabilistic inference.

---

## 🧠 Description

This project models heredity and genetic traits using **Bayesian inference**. Each individual in a dataset has a probabilistic distribution over the number of mutated genes they carry (0, 1, or 2) and whether they express a given trait (True or False).

Using parental information and trait observations, the AI determines:

* The probability of each person having 0, 1, or 2 copies of a gene.
* The probability of each person exhibiting the trait.

The program takes into account:

* **Inheritance:** Each child inherits one gene from each parent, with mutation probabilities.
* **Mutation:** A small chance of genetic mutation altering the inherited gene.
* **Observation:** Known traits influence the probability distribution.

This model showcases **Bayesian reasoning**, **conditional probability**, and **joint probability normalization** to make data-driven genetic predictions.

---

## ⚙️ Features

* Models genetic inheritance using a **Bayesian Network**
* Computes **joint probability distributions** over genes and traits
* Performs **probabilistic inference** with normalization
* Uses **realistic biological parameters** (e.g., mutation, trait likelihood)
* Outputs probability tables for every person in the dataset

---

## 🧩 Example Usage

Run the program on a sample dataset:

```bash
$ python heredity.py data/family0.csv
```

Example output:

```
Harry:
  Gene:
    2: 0.0092
    1: 0.4557
    0: 0.5351
  Trait:
    True: 0.2665
    False: 0.7335
James:
  Gene:
    2: 0.1976
    1: 0.5106
    0: 0.2918
  Trait:
    True: 1.0000
    False: 0.0000
Lily:
  Gene:
    2: 0.0036
    1: 0.0136
    0: 0.9827
  Trait:
    True: 0.0000
    False: 1.0000
```

---

## 🧩 Key Functions

### `joint_probability(people, one_gene, two_genes, have_trait)`

Calculates the joint probability of the given configuration of genes and traits across all people.

### `update(probabilities, one_gene, two_genes, have_trait, p)`

Updates overall probabilities with a new joint probability contribution.

### `normalize(probabilities)`

Normalizes all probabilities so that each distribution sums to 1.

---

## 📊 Concepts Demonstrated

* **Bayesian Networks**
* **Conditional Probability**
* **Joint Probability Distributions**
* **Normalization and Inference**
* **Genetic Modeling and Mutation**

---

## 📂 Dataset Example

`data/family0.csv`

| name  | mother | father | trait |
| ----- | ------ | ------ | ----- |
| Harry | Lily   | James  |       |
| James |        |        | 1     |
| Lily  |        |        | 0     |

---

## 🧪 Dependencies

* Python 3.x
* Standard libraries only (`itertools`, `csv`, `sys`, etc.)

---

## 🧩 How It Works

1. **Load Data:** Parses CSV files containing family relationships and traits.
2. **Enumerate Probabilities:** Calculates all possible combinations of gene and trait distributions.
3. **Compute Joint Probability:** Uses inheritance and mutation probabilities to calculate likelihoods.
4. **Update and Normalize:** Updates each individual’s probability distribution and ensures all probabilities sum to 1.
5. **Output Results:** Prints the probability of each person’s genetic and trait outcomes.

---

Part of **CS50’s Introduction to Artificial Intelligence with Python**
