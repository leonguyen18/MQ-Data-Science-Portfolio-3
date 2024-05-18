# COMP6200 Data Science - Portfolio 3: Analysis of Mobile Price Data

This project is part of the COMP6200 Data Science unit. It involves analyzing a new dataset named `Mobile_Price_Data.csv`, which contains numerous details about mobile phone hardware, specifications, and prices. 

The main task is to train classification models to predict mobile phone prices (`price range` in the dataset) and evaluate the strengths and weaknesses of these models.

## Dataset

The dataset includes comprehensive information about various mobile phones, such as battery power, Bluetooth, clock speed, dual SIM, front and rear camera megapixels, internal memory, mobile depth, mobile weight, number of cores, pixel resolution, RAM, screen height and width, talk time, and whether the phone supports 3G or 4G. 

The target variable is `price range`, which categorizes the phones into different price segments.

## Tools and Libraries Used
- **Jupyter Notebook**
- **Python**
  - `pandas`
  - `numpy`
  - `scikit-learn`
  - `seaborn`
  - `matplotlib`

## Project Tasks

### 1. Explore and Clean the Data
- Load the dataset and identify missing values.
- Remove rows with missing values in columns: _int_memory, m_dep, px_width, ram, three_g_.
- Provide a summary of the cleaned dataset.

### 2. Study the Correlation between 'Price Range' and Other Features
- Calculate and plot the correlation matrix.
- Select variables that are strongly correlated with `price range`.

### 3. Split the Dataset
- Split the dataset into training (80%) and testing data (20%) using `random_state = 142`.

### 4. Train a Logistic Regression Model & Evaluate the Performance
- Normalize features using `StandardScaler`.
- Train the logistic regression model using the selected features.
- Calculate the accuracy of the model on both training and testing sets.
- Analyze the model's performance and identify factors contributing to its accuracy.

### 5. Train a KNN Model & Calculate the Accuracy Scores
- Train a KNN model with an arbitrary K value and evaluate its performance.

### 6. Tune the Hyper-parameter K in KNN & Visualize the Results
- Tune the hyper-parameter K using `GridSearchCV` to find the optimal K value.
- Visualize how K influences the prediction performance.
- Train the final KNN model based on the optimal K value and report the accuracy score on the testing set.

## Findings

### Correlation Analysis
Selected variables:
- _ram_ (0.917131): Strong correlation with price range.
- _px_width_ (0.164763) and _px_height_ (0.147946): Moderate correlation with price range.
- _battery_power_ (0.202652): Moderate correlation with price range.

### Model Performance

#### Logistic Regression Model
- **Accuracy on Training Set**: 95.61%
- **Accuracy on Testing Set**: 96.74%
- **Comments**: The model performs well with a small gap between training and testing accuracy, indicating no overfitting. High precision, recall, and F1-score values suggest the model generalizes effectively.

#### KNN Model (Initial)
- **Accuracy on Training Set**: 95.49%
- **Accuracy on Testing Set**: 85.96%
- **Comments**: Initial KNN model with K=3 shows signs of overfitting with a significant drop in accuracy on the testing set.

#### KNN Model (Tuned)
- **Best K Value**: 11
- **Best (cross-validation) Accuracy Score**: 90.29%
- **Final Model Accuracy on Testing Set**: 90.48%
- **Comments**: The optimal K value of 11 improves the model's performance, reducing overfitting and achieving a balanced accuracy.

## Contributing

As this is an individual assignment, I am the main contributor. However, if you find any errors or areas of improvement, feel free to create an issue or submit a pull request.

## License

This project is part of a university assignment and the dataset was provided by the lecturer. Please use this for reference or educational purposes only.