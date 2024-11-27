## Guardian of the Ensembles: Introducing Pairwise Adversarially Robust Loss for Resisting Adversarial Attacks in DNN Ensembles
### Training PARL
To train models with PARL loss run the notebook *train_parl.ipynb*.

1. Specify the required training parameters in the cell below *PARL Training Specification*.
```
n_ensemble = 3 # Number of classifiers in the ensemble
n_layers = 5 # Number of initial conv layers to be considered in PARL loss
dataset = 'CIFAR-100' # CIFAR-10, CIFAR-100
gamma = 0.25 # Hyperparameter to control the relative importance of the penalty term in PARL loss
epochs = 50 # training epochs
```

2. Run the cell below *Train* to start training.


### Evaluation
To perform black box transfer attacks run the notebook *attacks.ipynb*.

1. Specify the dataset in the cell below *Load Clean Data*.
```
dataset = 'CIFAR-10' # CIFAR-10, CIFAR-100
```
2. Load pre-trained models under *Load Pre-Trained Models* section. Specify *n_ensemble* accordingly.
```
n_ensemble = 3 # Number of classifiers in the enemsemble
```

3. Run PGD (with restarts), MDI2-FGSM and SGM individually by running the respective cells and generate the adversarial samples.

4. Run the cell below *Perform All Attacks* to evaluate robustness of PARL against different perturbation strengths.


### Additional Data and Pre-Trained Models
Additionally, some pretrained ResNet20 models and the 1000 randomly sampled clean images (normalized) and their respective labels for both CIFAR-10 and CIFAR-100 dataset are available in the *additional* directory. Nomenclature of those files is similar to what is used in the notebooks.
