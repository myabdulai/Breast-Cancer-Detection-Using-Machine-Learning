<!-- README.html -->
<body>
  <h1>Breast Cancer Detection Using Machine Learning</h1>
  <p>
    This project builds a machine learning classifier to detect breast cancer tumors as
    <strong>malignant</strong> or <strong>benign</strong> using the
    <em>Breast Cancer Wisconsin (Diagnostic)</em> dataset.
    The workflow uses an 80/20 train-test split, performs 5-fold cross-validation on the
    training set only, tunes hyperparameters via GridSearchCV, and reports final performance
    on the held-out test set.
  </p>

  <h2>Methodology</h2>
  <ol>
    <li><strong>Data Split:</strong> stratified 80% train / 20% test.</li>
    <li><strong>Cross-Validation:</strong> 5-fold stratified CV performed on the training set only.</li>
    <li><strong>Model:</strong> RandomForestClassifier.</li>
    <li><strong>Tuning:</strong> GridSearchCV used to tune key hyperparameters (e.g., n_estimators, max_depth, min_samples_split, min_samples_leaf, max_features).</li>
    <li><strong>Metrics:</strong> Accuracy, Precision, Recall (Sensitivity), and F1-score.</li>
  </ol>

  <h2>Results</h2>
  <p>
    The Cross-validation results on the training set showed stable and consistent performance across all folds, 
    indicating good generalization and low variance.
    Final evaluation on the held-out 20% test set produced strong performance across all metrics, 
    including accuracy, precision, recall (sensitivity), and F1-score, demonstrating that the tuned model performs well on unseen data.

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
        <td>0.95</td>
        <td>0.95</td>
      </tr>
    </tbody>
  </table>

  <h2>Requirements</h2>
  <ul>
    <li>Python 3.9+</li>
    <li>scikit-learn</li>
    <li>pandas, numpy</li>
  </ul>

   <hr />
  <p class="muted">
    Author: Mohammed Abdulai &nbsp;|&nbsp; Course: AI in Healthcare (Michigan Technological University)
  </p>
</body>
</html>
