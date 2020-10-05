# Toxic Language Dataset for Brazilian Portuguese (ToLD-Br)
Repository for [Toxic Language Detection in Social Media for Brazilian Portuguese: New Dataset and Multilingual Analysis]().

## Dataset
* ToLD-BR.csv - Each column has a value from 0 to 3 representing the number of times this example got flagged as toxic.
* ToLD-BR_alpha.csv - Annotations are not aggregated for each class, so values are either 0 or 1 and each class has 3 columns.

**If you want access to the full dataset with demographic information for each annotator or the raw tweets collected for this paper, contact us.**

## Trained Model
You can download a pre-trained Multilingual BERT fine-tuned with ToLD-Br for your application at https://drive.google.com/file/d/1Q8MuO4SsND0xzDIW9TNvzfl5Fc2NGwAJ/. This model has been trained with a binary representation of ToLD-Br and only predicts toxic vs non-toxic examples.

* ```model/example.ipynb``` shows how to load the model and use it for binary classification.

## Reproducing the Experiments
* ```experiments/data/annotatorN.zip``` correspond to the train, development and test sets used on all experiments, where N is the number of flags that an example must be labelled in order to be considered toxic.

### AutoML Baseline
* Unzip ```experiments/data/annotatorN.zip```;
* Run ```experiments/automl.ipynb```.

### BERT
* Upload ```experiments/classification.ipynb``` to a Google Collab with GPU enabled;
* Run the desired section.

### Inter Annotator Agreement
* install mwetoolkit3 at ```https://gitlab.com/mwetoolkit/mwetoolkit3```;
* run ```mwetoolkit3/bin/kappa.py -i -r -c FILE.csv``` where FILE.csv is one of the category files at ```experiments/data/agreement_files```.

### Learning Curve
* (optional) run the learning curve experiment section on ```experiments/classification.ipynb``` and download the learning_curve.json file generated;
* run ```experiments/learning_curve.ipynb``` using ```experiments/data/learning_curve.json```.

### Word Cloud
* run ```experiments/wordcloud.ipynb```.

## Authors
* João Augusto Leite (Universidade Federal de São Carlos)
* Diego Furtado Silva (Universidade Federal de São Carlos)
* Kalina Bontcheva (University of Sheffield)
* Carolina Scarton (University of Sheffield)