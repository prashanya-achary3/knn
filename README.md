🚀 Project Workflow
1. Dataset

Used the Breast Cancer Wisconsin dataset

Columns include statistical measurements of cell nuclei (radius, texture, smoothness, perimeter, etc.)

Target variable: diagnosis

0 = Benign

1 = Malignant

🔧 Steps Followed
✔ 1. Load Dataset

Loaded the CSV file using pandas.

✔ 2. Remove Unnecessary Columns

id column removed because it does not help in prediction.

✔ 3. Check Missing Values

Ensured that dataset contains no null values.

✔ 4. Outlier Detection (Before Normalization)

Used the IQR (Interquartile Range) method to count outliers in each numeric column.

Formula:

IQR = Q3 – Q1

Lower Limit = Q1 – 1.5 × IQR

Upper Limit = Q3 + 1.5 × IQR

Outliers were detected and optionally removed.

✔ 5. Feature & Target Split
X = df.drop("diagnosis", axis=1)
y = df["diagnosis"]

✔ 6. Train-Test Split

20% test data, 80% training data.

✔ 7. Feature Scaling (Standardization)

Used StandardScaler to normalize the numeric features.

Standardization is important for KNN because the algorithm depends on distance calculations.

✔ 8. Finding the Best K

Trained the KNN model for k = 1 to 20 and plotted accuracy values.

Best K found: K = 9

✔ 9. Final Model Training

Trained final KNN model using the best K value.

✔ 10. Model Evaluation

Evaluation metrics used:

Accuracy Score

Confusion Matrix

Classification Report

📊 Final Results

Accuracy: 96.49%

Confusion Matrix:

[[69  2]
 [ 2 41]]


Precision & Recall (Both Classes): ~95–97%

The model provides strong and reliable predictions.

📈 Key Insights

KNN works best after normalizing the data

Outliers impact IQR values but KNN still performed well after scaling

Best performance achieved at K = 9

Balanced performance for both benign and malignant cases

🛠 Technologies Used

Python

Pandas

NumPy

Matplotlib

Scikit-learn

📂 How to Run the Project
1. Install dependencies:
pip install numpy pandas scikit-learn matplotlib

2. Run the Jupyter Notebook or Python script.
🎯 Conclusion

This project demonstrates a complete KNN classification pipeline—from preprocessing to tuning and final evaluation—achieving 96% accuracy on breast cancer prediction.
The model is reliable, interpretable, and follows standard ML best practices.
