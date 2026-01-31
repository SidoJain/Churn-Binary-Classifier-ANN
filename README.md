# Customer Churn Prediction using ANN

This interactive **Streamlit** web application predicts the probability of a customer leaving a bank (churn) by leveraging a Deep Learning **Artificial Neural Network (ANN)**.

By analyzing demographics and financial behavior, this tool helps businesses identify at-risk customers and implement retention strategies before they leave.

---

## Overview

The application takes 10 specific customer metrics, processes them through a trained ANN model, and outputs the likelihood of churn as a percentage.

### **Input Metrics**

The model evaluates the following variables to determine customer loyalty:

* **Geography:** Customer's country (France, Spain, or Germany).
* **Gender:** Male or Female.
* **Age:** Primary factor in financial stability and churn patterns.
* **Credit Score:** A numerical representation of credit-worthiness.
* **Balance:** Current account balance.
* **Estimated Salary:** Annual income of the customer.
* **Tenure:** Number of years the customer has been with the bank.
* **Number of Products:** How many bank products (accounts, loans, etc.) they use.
* **Has Credit Card:** Binary (Yes/No).
* **Is Active Member:** Binary (Yes/No) based on recent account activity.

---

## Tech Stack

* **Frontend:** [Streamlit](https://streamlit.io/)
* **Machine Learning Framework:** [TensorFlow / Keras](https://www.tensorflow.org/)
* **Data Manipulation:** Pandas, NumPy
* **Preprocessing:** Scikit-Learn

---

## Installation & Setup

To run this project locally, follow these steps:

1. **Clone the repository:**

    ```bash
    git clone https://github.com/SidoJain/Churn-Binary-Classifier-ANN.git
    ```

2. **Create a virtual environment:**

    ```bash
    python -m venv .venv
    source .venv/Script/activate
    ```

3. **Install dependencies:**

    ```bash
    pip install -r requirements.txt
    ```

4. **Launch the app:**

    ```bash
    streamlit run app.py
    ```

---

## 🧠 How the Model Works

The prediction pipeline ensures that raw user input is transformed into a format the neural network understands:

1. **Encoding:** Categorical variables (Geography and Gender) are encoded into numerical values.
2. **Feature Scaling:** Input values like `Balance` and `Salary` vary wildly. We apply scaling to normalize these values, ensuring the ANN's weights converge correctly.
3. **Neural Network Inference:** The processed data passes through the hidden layers of the ANN.
4. **Probability Output:** The final layer uses a Sigmoid activation function to output a value between 0 and 1.
    > **Note:** A result $> 0.5$ is generally classified as "Likely to Churn."
