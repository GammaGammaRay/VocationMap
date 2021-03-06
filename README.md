Vocation Map: Linking Social Media-Predicted Personality Traits and
Occupations
================

This repository contains code and data accompanying the publication
“Social Media-Predicted Personality Traits Can Help Match People to
their Ideal Jobs” [\[Kern et al,
PNAS’20\]](https://www.pnas.org/content/116/52/26459).

# Reference:

    [Kern et al, PNAS'20] Kern, Margaret L., Paul X. McCarthy, Deepanjan Chakrabarty, and Marian-Andrei Rizoiu. 
    2019. “Social Media-Predicted Personality Traits and Values Can Help Match People to Their Ideal Jobs.” 
    Proceedings of the National Academy of Sciences 116(52):26459–64. https://doi.org/10.1073/pnas.1917942116 

# Repository content:

This repository contains the following code scripts:

  - `scripts/build-professions-profiles.R` – R script that starts from
    `data/all_users_data.csv.xz`, and builds the profession profiles
    (stored in the file `data/profession-profiles.csv`);
  - `scripts/vocation-map.R` – R script that starts from
    `data/profession-profiles.csv` to build the Vocation Map starting
    from occupation psychological profiles;
  - `scripts/predict-profession-python.ipynb` – Python Jupyter notebook
    to build predictors for forecasting user occupation.
  - `scripts/prediction-step1-run-prediction.sh` – Bash script to
    transform the Jupyter notebook to a `py` file and run it without a
    graphical interface;
  - `scripts/prediction-step2-read-prediction-models-from-Python.R` – R
    script (using the `reticulate` package, which reads Python data
    sctructures produced by `scripts/predict-profession-python.ipynb`
    and builds R structures);
  - `scripts/prediction-step3-plot-prediction.R` – R script that plots
    the prediction performance indicators (Precision, Recall, F1 score
    and Accuracy);
  - `scripts/construct-confusion-matrix.R` – R script that loads the
    prediction results (see `data/prediction-results`) and builds the
    confusion matrix.
  - `scripts/utils.R` – additional functions for reading, writing data
    and plotting.

The following data and plots is also available:

  - `data/profession-profiles.csv` – contains the psychological profiles
    for each occupation in the Vocation Map.
  - `data/prediction-results/*` – CSV files containing the model
    prediction for each classifier, and each fold.
  - `plots/vocation-map-static.pdf` – a static version of the Vocation
    Map.
  - `plots/vocation-map-interactive.html` – the interactive version of
    the Vocation Map. Also available at
    <http://bit.ly/vocation-map-interactive> .
  - `plots/confusion-heatmap-dendogram.pdf` – the confusion map for the
    XGBoost classifier (based on `data/prediction-results/*`)

![A static version of the Vocation Map.](plots/vocation-map-static.png)
![Confusion map showing that even when the prediction is wrong, it is
still pretty good.](plots/confusion-heatmap-dendogram.png)

# Additional data file:

The following files cannot be publicly shared due to the Twitter’s and
IBM Watson’s Terms of Service. However, these files could be provided
privately upon request, requests are evaluated at a case-by-case basis.

  - `data/all_users_data.csv.xz` – contains the psychological profiles
    of all 128,278 users in our study;
  - `data/10_professions_data.csv.xz` – contains the Big5 and the
    personal values (10 features) for 38,073 users in the occupation
    prediction part of the paper;
  - `data/10_professions_data_big5.csv.xz` – contains solely the Big5
    traits for the 38,073 users above (useful for the ablation study);
  - `data/10_professions_data_values.csv.xz` – contains solely the
    personal values for the 38,073 users above (useful for the ablation
    study).

# License

Both data set and code are distributed under the General Public License
v3 (GPLv3) license, a copy of which is included in this repository, in
the LICENSE file. If you require a different license and for other
questions, please contact us at <Marian-Andrei@rizoiu.eu>
