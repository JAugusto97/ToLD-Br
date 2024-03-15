# Toxic Language Dataset for Brazilian Portuguese (ToLD-Br)
Repository for ToLD-Br: a dataset with tweets in Brazilian Portuguese annotated according to different toxic aspects.

## Dataset
* ToLD-BR.csv - Each column has a value from 0 to 3 representing the number of times this example got flagged as toxic.
* ToLD-BR_alpha.csv - Annotations are not aggregated for each class, so values are either 0 or 1 and each class has 3 columns.

**If you want access to the full dataset with demographic information for each annotator or the tweet IDs collected for this paper, contact us.**

## Citing ToLD-Br
```
@inproceedings{leite-etal-2020-toxic,
    title = "Toxic Language Detection in Social Media for {B}razilian {P}ortuguese: New Dataset and Multilingual Analysis",
    author = "Leite, Jo{\~a}o Augusto  and
      Silva, Diego  and
      Bontcheva, Kalina  and
      Scarton, Carolina",
    editor = "Wong, Kam-Fai  and
      Knight, Kevin  and
      Wu, Hua",
    booktitle = "Proceedings of the 1st Conference of the Asia-Pacific Chapter of the Association for Computational Linguistics and the 10th International Joint Conference on Natural Language Processing",
    month = dec,
    year = "2020",
    address = "Suzhou, China",
    publisher = "Association for Computational Linguistics",
    url = "https://aclanthology.org/2020.aacl-main.91",
    pages = "914--924",
    abstract = "Hate speech and toxic comments are a common concern of social media platform users. Although these comments are, fortunately, the minority in these platforms, they are still capable of causing harm. Therefore, identifying these comments is an important task for studying and preventing the proliferation of toxicity in social media. Previous work in automatically detecting toxic comments focus mainly in English, with very few work in languages like Brazilian Portuguese. In this paper, we propose a new large-scale dataset for Brazilian Portuguese with tweets annotated as either toxic or non-toxic or in different types of toxicity. We present our dataset collection and annotation process, where we aimed to select candidates covering multiple demographic groups. State-of-the-art BERT models were able to achieve 76{\%} macro-F1 score using monolingual data in the binary case. We also show that large-scale monolingual data is still needed to create more accurate models, despite recent advances in multilingual approaches. An error analysis and experiments with multi-label classification show the difficulty of classifying certain types of toxic comments that appear less frequently in our data and highlights the need to develop models that are aware of different categories of toxicity.",
}
```

## License
ToLD-Br is licensed under a Creative Commons BY-SA 4.0 license that can be found in the file LICENSE_ToLD-Br.txt.
The code available for reproducing experiments is licensed under a MIT license that can be found in the file LICENSE_code.txt.

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
