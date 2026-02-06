  <meta charset="utf-8" />
  <title>Breast Cancer Detection Using Machine Learning</title>
  <style>
    body {
      font-family: Arial, Helvetica, sans-serif;
      line-height: 1.5;
      max-width: 900px;
      margin: 32px auto;
      padding: 0 16px;
    }
    h1, h2, h3 {
      margin-top: 24px;
    }
    table {
      border-collapse: collapse;
      width: 100%;
      margin-top: 12px;
    }
    th, td {
      border: 1px solid #000;
      padding: 8px;
      text-align: center;
    }
    th {
      font-weight: bold;
    }
    .header {
      text-align: left;
      margin-bottom: 24px;
    }
  </style>
</head>

<body>

  <div class="header">
    <p><strong>Mohammed Abdulai</strong><br>
    AI in Healthcare<br>
    Michigan Technological University</p>
  </div>

  <h1>Breast Cancer Detection Using Machine Learning</h1>
  <p><strong>Dataset:</strong> Breast Cancer Wisconsin (Diagnostic)</p>

  <h2>1.0 Objective</h2>
  <p>
    The goal of this project is to build a machine learning model to classify breast cancer tumors
    as malignant or benign using clinical features. The project applies k-fold cross-validation,
    hyperparameter tuning, and evaluates final performance on a held-out test dataset.
  </p>

  <h2>2.0 Methodology</h2>
  <p>
    The dataset was split into 80% training and 20% testing sets using stratified sampling to
    preserve class balance. The test set was held out and used only for final evaluation.
  </p>
  <p>
    A Random Forest classifier was selected due to its robustness, ability to model nonlinear
    relationships, and strong performance in medical classification tasks. Five-fold stratified
    cross-validation was performed only on the training set to estimate model performance.
  </p>
  <p>
    To improve model performance, GridSearchCV was used to tune key hyperparameters, including
    the number of trees, maximum tree depth, minimum samples per split and leaf, and feature
    selection strategy. The F1-score was used as the optimization metric to balance precision
    and recall.
  </p>

  <h2>3.0 Model Performance</h2>
  <p>
    Cross-validation results on the training set showed stable and consistent performance across
    all folds, indicating good generalization and low variance.
  </p>
  <p>
    Final evaluation on the held-out 20% test set produced strong performance across all metrics,
    including accuracy, precision, recall (sensitivity), and F1-score, demonstrating that the
    tuned model performs well on unseen data.
  </p>

  <h3>Table 1: Performance Metrics</h3>
  <table>
    <thead>
      <tr>
        <th>Performance Metrics</th>
        <th>Accuracy</th>
        <th>Precision</th>
        <th>Recall</th>
        <th>F1</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>5-Fold CV</td>
        <td>0.963 ± 0.018</td>
        <td>0.976 ± 0.017</td>
        <td>0.965 ± 0.025</td>
        <td>0.970 ± 0.015</td>
      </tr>
      <tr>
        <td>Evaluation on 20% Unseen data</td>
        <td>0.96</td>
        <td>0.96</td>
        <td>0.96</td>
        <td>0.96</td>
      </tr>
    </tbody>
  </table>

</body>
</html>
