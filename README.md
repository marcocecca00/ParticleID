[![Made withJupyter](https://img.shields.io/badge/Made%20with-Jupyter-orange?style=for-the-badge&logo=Jupyter)](https://jupyter.org/try)
[![made-for-VSCode](https://img.shields.io/badge/Made%20for-VSCode-1f425f.svg)](https://code.visualstudio.com/)

<h1> Product Classification of Electron-Proton Scattering</h1>

Comparison of different *supervised learning* models for the *classification* of particles produced during inelastic electron-proton scattering. The goal is to identify particles and evaluate the best model among the following:

- **Decision Tree**
- **Random Forest**
- **Multilayer Perceptron**
- **K-Nearest Neighbor**

The data used are the product of the response of six different detectors, usanti through the simulation platform *[GEANT4](https://geant4.web.cern.ch/)*. The DataSet can be found at *[Kaggle](https://www.kaggle.com/datasets/naharrison/particle-identification-from-detector-responses)*.

## **DataSet composition**

The *features* in the dataset used are as follows:

|    Features    |              Meaning              | Dimension |
| :-------------: | :------------------------------------: | :--------------: |
|  **id**  |           Particle Name            |    $NoDim$    |
|   **p**   |           Momentum           |    $GeV/c$    |
| **theta** |          Scattering angle          |     $rad$     |
| **beta** | Relativistic Veliocityu $v$ e $c$ |    $NoDim$    |
| **nphe** |       Number of Photoelectrons       |    $NoDim$    |
|  **ein**  |          Input Energy         |     $GeV$     |
| **eout** |           Output Energy           |     $GeV$     |

A ciascun *id*  inoltre è associata una precisa particella:

|        id        | Particle |              Symbol              | Mass (MeV) |
| :--------------: | :--------: | :-------------------------------: | :---------: |
| **(-11)** | Positron |              $e^+$              |  $0.51$  |
| **(211)** |   Pion   | $\pi \quad (\pi^0,\pi^+,\pi^-)$ |   $137$   |
| **(321)** |   Kaon   |     $K \quad (K^0,K^+,K^-)$     |   $495$   |
| **(2212)** |  Proton  |               $p$               |   $940$   |

Regardless of the underlying physical model, i.e., the [Standard Model](https://it.wikipedia.org/wiki/Modello_standard), it is sufficient to know that each particle is characterized by a certain set of values and in particular their *rest mass*.

## **Exploratory Analysis & Data Preparation**.

The following libraries were exploited for preliminary data preparation:

- Numpy
- MatPlotLib
- Pandas
- Seaborn
- Imbalanced Learn

In addition, physical and intuitive observations enabled further preparation and simplification of the dataset.

Finally, prior to the construction of the MachineLearning models and their subsequent training, a **resampling** procedure was performed to correct the balance of the dataset.

## **Model Construction & Training**

Supervised learning was chosen for the choice of models, in particular, *classifiers* were exploited. The latter, based on the previously mentioned algorithms, are offered by the **Scikit Learn** library:

- DecisionTreeClassifier
- RandomForestClassifier
- MLPClassifier
- KNeighborsClassifier

Specifically for the **RandomForestClassifier** the *importance of features* for model training was evaluated, confirming what had been inferred in the exploratory analysis.

While for **MLPClassifier** an *optimization of hyperparameters* was chosen, by means of a *GridSearch*.

## **Comparison & Conclusion**

Finally, *accuracy* and ,visually, *confusion matrices* were used as metrics to evaluate the efficiency of the models. The results do not show a predominance of one model over another, but the KNeighborsClassifier is the least efficient.

| Classifier | Accuracy |
| :--------------------------: | :------: |
| **Decision Tree** | | 89.6% |
| **Random Forest** | | 93.2% |
| **ML Perceptron** | 93.1% |
| **K-Nearest Neighbor** | 88.6% |

## **Authors**

- [Marco Cecca](https://github.com/marcocecca00) - marcoccecca@gmail.com
