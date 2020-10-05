# Toxic Language Dataset for Brazilian Portuguese (ToLD-Br)
Repository for [Toxic Language Detection in Social Media for Brazilian Portuguese: New Dataset and Multilingual Analysis]().

## Dataset
* ToLD-BR.csv - main dataset. Each column has a value from 0 to 3 representing the number of times this example got flagged as toxic.
* ToLD-BR_alpha.csv - same dataset but annotations are not aggregated for each class, so values are either 0 or 1

## Trained Model
You can download a pre-trained Multilingual BERT fine-tuned with ToLD-Br for your application at https://drive.google.com/file/d/1Q8MuO4SsND0xzDIW9TNvzfl5Fc2NGwAJ/. This model has been trained with a binary representation of ToLD-Br and only predicts toxic vs non-toxic examples.

* model/example.ipynb shows how to load the model and use it for binary classification.

## Reproducing the Experiments

### AutoML Baseline
* Unzip experiments/data/annotator1.zip
* Run experiments/automl.ipynb

### BERT
* Upload experiments/classification.ipynb to a Google Collab with GPU enabled
* Run the desired section

### Inter Annotator Agreement
* install mwetoolkit3 at https://gitlab.com/mwetoolkit/mwetoolkit3
* ```run mwetoolkit3/bin/kappa.py -i -r -c FILE.csv``` where FILE.csv is one of the category files at experiments/data/agreement_files