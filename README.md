#📈 Polynomial Regression Project

This project shows how to use Polynomial Regression in Python to make predictions based on data that follows a curve (not a straight line). It's helpful when simple linear regression doesn't work well because the data doesn't form a straight line.

---

📌 What is Polynomial Regression?
Polynomial Regression is like Linear Regression but works better when the data forms a curve.
For example, if your data looks like a "U" shape or an upward curve, Polynomial Regression will fit it better.

🧰 Tools and Libraries Used
Make sure you have these Python libraries installed:
1. numpy → for numbers and math
2. pandas → for handling data
3. matplotlib → for making graphs
4. scikit-learn → for building machine learning models
5. To install them, run this in your terminal:

To install them, run this in your terminal:
pip install numpy pandas matplotlib scikit-learn

📁 What’s in This Project?
Creating the data: We generate fake data using a math formula like y = 0.5x² + 1.5x + 2 + noise.
Plotting the data: Shows the curve so you can see why a straight line won't work.
Linear Regression: Fits a straight line (doesn’t match well).
Polynomial Regression: Fits a curved line (matches the data much better).
R² Score: Tells us how good the model is.

🧪 How the Data Looks
We use this formula to create data:

X = 6 * np.random.rand(100, 1) - 3
y = 0.5 * X**2 + 1.5 * X + 2 + np.random.randn(100, 1)

This gives you 100 random values of X and Y which follow a curved pattern.

📉 Linear Regression vs Polynomial Regression
Linear Regression draws a straight line — but doesn’t match the curve.
Polynomial Regression fits a curved line — much better match!

🛠️ Code for Polynomial Regression
Here’s how we make the model:

from sklearn.pipeline import Pipeline
from sklearn.preprocessing import PolynomialFeatures
from sklearn.linear_model import LinearRegression

# Function to create and train polynomial regression model
def poly_regression(degree):
    poly_features = PolynomialFeatures(degree=degree, include_bias=True)
    lin_reg = LinearRegression()
    poly_pipeline = Pipeline([
        ("poly_features", poly_features),
        ("lin_reg", lin_reg)
    ])
    poly_pipeline.fit(X_train, y_train)
    return poly_pipeline

📊 How We Check Model Accuracy
We use R² Score to check how well our model is performing:

from sklearn.metrics import r2_score
score = r2_score(y_test, y_pred)
print("R2 Score:", score)
Higher score (closer to 1) = better model


Linear regression gives low score (bad fit)
Polynomial regression gives high score (good fit)

📈 Final Output
Graphs will show:
->The real data (scatter plot)
->Linear regression line (bad fit)
->Polynomial regression curve (good fit)

🏁 How to Run This Project
Make sure Python is installed.

Install the required libraries.

Open the .ipynb file in Jupyter Notebook or Google Colab.

Run the cells one by one to see the results.

✅ What You Will Learn
1. How to fit a curve using machine learning

2. The difference between linear and polynomial models

3. How to measure model performance using R² Score

4. How to make simple plots using matplotlib

