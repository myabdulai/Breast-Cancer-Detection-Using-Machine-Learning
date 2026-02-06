<!-- README.html -->
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Breast Cancer Detection Using Machine Learning (Random Forest)</title>
  <style>
    body { font-family: Arial, Helvetica, sans-serif; line-height: 1.5; max-width: 900px; margin: 32px auto; padding: 0 16px; }
    code, pre { font-family: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace; }
    pre { padding: 12px; overflow: auto; background: #f6f8fa; border: 1px solid #d0d7de; border-radius: 8px; }
    table { border-collapse: collapse; width: 100%; margin: 12px 0; }
    th, td { border: 1px solid #d0d7de; padding: 10px; text-align: left; }
    th { background: #f6f8fa; }
    .muted { color: #57606a; }
    .badge { display: inline-block; padding: 2px 8px; border: 1px solid #d0d7de; border-radius: 999px; font-size: 12px; margin-right: 6px; }
    ul { margin-top: 6px; }
  </style>
</head>

<body>
  <h1>Breast Cancer Detection Using Machine Learning</h1>

  <p>
    <span class="badge">Random Forest</span>
    <span class="badge">5-Fold CV</span>
    <span class="badge">GridSearchCV</span>
    <span class="badge">80/20 Train/Test Split</span>
  </p>

  <p>
    This project builds a machine learning classifier to detect breast cancer tumors as
    <strong>malignant</strong> or <strong>benign</strong> using the
    <em>Breast Cancer Wisconsin (Diagnostic)</em> dataset.
    The workflow uses an 80/20 train-test split, performs 5-fold cross-validation on the
    training set only, tunes hyperparameters via GridSearchCV, and reports final performance
    on the held-out test set.
  </p>

  <h2>Project Structure</h2>
  <ul>
    <li><strong>notebook/</strong> (optional) Jupyter notebook implementation</li>
    <li><strong>src/</strong> (optional) Python scripts (data loading, training, evaluation)</li>
    <li><strong>reports/</strong> one-page PDF report and result screenshots</li>
  </ul>

  <h2>Requirements</h2>
  <ul>
    <li>Python 3.9+</li>
    <li>scikit-learn</li>
    <li>pandas, numpy</li>
  </ul>

  <h2>How to Run</h2>

  <h3>1) Create environment & install dependencies</h3>
  <pre><code>pip install -U numpy pandas scikit-learn</code></pre>

  <h3>2) Train, cross-validate, tune, and evaluate</h3>
  <p class="muted">
    The pipeline follows these steps:
    (1) load data, (2) 80/20 stratified split,
    (3) 5-fold CV on training only,
    (4) GridSearchCV on training only,
    (5) final test evaluation.
  </p>

  <pre><code>python src/train_rf.py</code></pre>

  <p><em>Tip:</em> If you are using a notebook, run all cells from top to bottom to avoid missing variables.</p>

  <h2>Methodology</h2>
  <ol>
    <li><strong>Data Split:</strong> stratified 80% train / 20% test.</li>
    <li><strong>Cross-Validation:</strong> 5-fold stratified CV performed on the training set only.</li>
    <li><strong>Model:</strong> RandomForestClassifier.</li>
    <li><strong>Tuning:</strong> GridSearchCV used to tune key hyperparameters (e.g., n_estimators, max_depth, min_samples_split, min_samples_leaf, max_features).</li>
    <li><strong>Metrics:</strong> Accuracy, Precision, Recall (Sensitivity), and F1-score.</li>
  </ol>

  <h2>Results</h2>
  <p class="muted">
    Metrics below are taken from the submitted one-page report. :contentReference[oaicite:0]{index=0}
  </p>

  <table>
    <thead>
      <tr>
        <th>Evaluation</th>
        <th>Accuracy</th>
        <th>Precision</th>
        <th>Recall</th>
        <th>F1-score</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>5-Fold CV (on training set)</td>
        <td>0.963 ± 0.018</td>
        <td>0.976 ± 0.017</td>
        <td>0.965 ± 0.025</td>
        <td>0.970 ± 0.015</td>
      </tr>
      <tr>
        <td>Test Set (20% held-out)</td>
        <td>0.96</td>
        <td>0.96</td>
        <td>0.96</td>
        <td>0.96</td>
      </tr>
    </tbody>
  </table>

  <h2>Metric Definitions (Brief)</h2>
  <ul>
    <li><strong>Accuracy:</strong> Overall proportion of correct predictions.</li>
    <li><strong>Precision:</strong> Of predicted malignant cases, how many were truly malignant (controls false positives).</li>
    <li><strong>Recall (Sensitivity):</strong> Of truly malignant cases, how many were correctly detected (controls false negatives).</li>
    <li><strong>F1-score:</strong> Harmonic mean of precision and recall; balances false positives and false negatives.</li>
  </ul>

  <h2>Notes on Reproducibility</h2>
  <ul>
    <li>Set <code>random_state</code> for deterministic splits and model training.</li>
    <li>Ensure CV and GridSearchCV are performed on <strong>training data only</strong> to prevent leakage.</li>
  </ul>

  <h2>Report</h2>
  <p>
    The one-page PDF report summarizing the objective, methodology, and results is included in the repository:
    <code>reports/Mohammed_BreastCancerDetection-ML.pdf</code>. :contentReference[oaicite:1]{index=1}
  </p>

  <hr />
  <p class="muted">
    Author: Mohammed Abdulai &nbsp;|&nbsp; Course: AI in Healthcare (Michigan Technological University)
  </p>
</body>
</html>
