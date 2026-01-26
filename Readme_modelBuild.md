
---

# 🏗️ Model Building Jargon Dictionary

Building a machine learning model involves a specific vocabulary. This guide breaks down the essential terms used during each phase of the project lifecycle.

---

## 📂 Stage 1: Data Preparation

*Before the math starts, we must prepare the "fuel" (data).*

* **Features ():** The input variables or independent variables used to make a prediction (e.g., square footage, number of rooms).
* **Target ():** The specific outcome you want to predict (e.g., price). Also known as the **Ground Truth**.
* **Train/Test Split:** Dividing your data (e.g., 80% for training, 20% for testing) to evaluate how well the model performs on unseen information.
* **Normalization/Scaling:** The process of shifting and rescaling data so that all features have a similar range (usually 0 to 1).

---

## 🧠 Stage 2: Model Architecture

*Defining the "brain" and its settings.*

* **Parameters ():** Internal variables that the model updates itself.
* **Weights ():** The "importance" assigned to each feature.
* **Bias ():** An offset that allows the model to fit data that doesn't pass through the origin.


* **Hyperparameters:** Settings defined by the *user* before training (e.g., Learning Rate, Batch Size).
* **Vanilla Model:** A basic, standard version of an algorithm without any advanced modifications.

---

## 📉 Stage 3: The Training Process

*The phase where the model "learns" from its mistakes.*

* **Forward Pass:** When data flows through the model to produce a prediction.
* **Loss Function (Cost Function):** A formula that quantifies the error between the prediction and the ground truth.
* **Backpropagation:** Moving backward from the error to calculate how much each weight contributed to that error.
* **Gradient Descent:** The optimization algorithm that "walks" the model toward the lowest possible error.
* **Learning Rate ():** The size of the "step" taken during Gradient Descent.

---

## 🏁 Stage 4: Evaluation & Performance

*Judging the final result.*

* **Epoch:** One full pass of the entire dataset through the model.
* **Convergence:** The point where the loss stops decreasing significantly; the model has "learned" all it can.
* **Overfitting:** When the model memorizes the training data too well, including the noise, and fails to generalize to new data.
* **Underfitting:** When the model is too simple to capture the underlying pattern of the data.

[Image comparing underfitting, balanced fitting, and overfitting on a scatter plot]

---

