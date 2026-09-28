# 🎓 Graduate Admission Prediction using ANN

> 🧠 A **learning-focused Deep Learning project** built to understand how an Artificial Neural Network (ANN) can be used for **regression**.

> ⚠️ **This is a learning project, not a production-ready machine learning system.**
>
> The main goal is to understand the concepts behind ANN-based regression, experiment with the model, and build intuition about how neural networks learn.

---

## 🎯 Project Goal

The goal of this project is to predict a student's **Chance of Admit** using academic and profile-related features.

But the bigger goal was to learn:

- 🧠 What regression means in Machine Learning
- 🤖 How an ANN performs regression
- 🔢 How neurons process inputs
- 🏗️ Hidden layers and neurons
- ⚖️ Weights and biases
- ⚡ ReLU activation
- 📈 Linear output for regression
- 📏 Feature scaling
- 📉 Loss functions
- 🔄 Epochs
- 🏋️ Model training
- 🔮 Making predictions
- 📊 R² score
- 🧪 Experimenting with ANN architecture

---

## 📊 Dataset

The project uses a **Graduate Admission** dataset containing information about students and their admission chances.

The dataset contains **7 input features** used for prediction.

🎯 **Target variable:**

```text
Chance of Admit

🔄 Machine Learning Workflow
📂 Dataset
   ↓
🔍 Data Exploration
   ↓
🧹 Remove Serial No.
   ↓
✂️ Separate Features (X) and Target (y)
   ↓
📦 Train-Test Split
   ↓
📏 Feature Scaling
   ↓
🧠 Build ANN
   ↓
⚙️ Compile Model
   ↓
🏋️ Train Model
   ↓
🔮 Make Predictions
   ↓
📊 Evaluate using R² Score

🧹 Data Preprocessing
1️⃣ Remove Serial No.

The serial number was removed because it is simply an identifier and does not represent a meaningful feature.

2️⃣ Separate Input and Output
X → 7 input features
y → Chance of Admit
3️⃣ Train-Test Split

The dataset was divided into:

🟢 80% → Training data
🔵 20% → Testing data

A fixed random_state was used to make the split reproducible.

4️⃣ Feature Scaling

MinMaxScaler was used to scale the input features.

The scaler was fitted only on the training data:

X_train → fit_transform()
X_test  → transform()

This prevents information from the test set from being used while fitting the scaler.

🧠 ANN Architecture

The final ANN architecture used in this project is:
        7 Input Features
               │
               ▼
      ┌─────────────────┐
      │   Dense Layer   │
      │   7 Neurons     │
      │     ReLU        │
      └─────────────────┘
               │
               ▼
      ┌─────────────────┐
      │   Dense Layer   │
      │   7 Neurons     │
      │     ReLU        │
      └─────────────────┘
               │
               ▼
      ┌─────────────────┐
      │   Output Layer  │
      │    1 Neuron     │
      │     Linear      │
      └─────────────────┘
               │
               ▼
       🎯 Chance of Admit


🏗️ Architecture
Input → 7 → 7 → 1

The model contains 120 trainable parameters.

🔢 Parameter Calculation

First hidden layer:

7 inputs × 7 neurons + 7 biases
= 49 + 7
= 56

Second hidden layer:

7 inputs × 7 neurons + 7 biases
= 49 + 7
= 56

Output layer:

7 inputs × 1 neuron + 1 bias
= 7 + 1
= 8

Total:

56 + 56 + 8 = 120 parameters
⚡ Activation Functions
🔥 ReLU

The hidden layers use:

activation='relu'

ReLU introduces non-linearity into the network.

ReLU(x) = max(0, x)

This allows the network to learn more complex relationships between the input features and the target.

📈 Linear Output

The output layer uses:

activation='linear'

A linear output is suitable for regression because the model needs to predict a continuous numerical value.

📉 Loss Function

The model uses Mean Squared Error (MSE) as its loss function.

Conceptually:

MSE = average of (actual - predicted)²

During training, the neural network adjusts its weights and biases to reduce this loss.

⚙️ Model Training

The model was trained using:

🔧 Optimizer → Adam
📉 Loss      → Mean Squared Error
🔄 Epochs    → 100

The number of epochs was experimented with during the learning process.

Initially, training with fewer epochs produced a very poor R² score.

After increasing the training duration to 100 epochs, the model learned the relationship much better.

💡 Key observation:

A neural network needs sufficient training iterations to learn useful patterns from the data.

📊 Evaluation

Since this is a regression problem, classification accuracy is not the primary evaluation metric.

The main evaluation metric used was:

📈 R² Score

R² measures how much of the variation in the target variable is explained by the model.

The final result obtained in the notebook was approximately:

🎯 R² ≈ 0.74

This means the model explains roughly 74% of the variance in the test data.

🧠 Understanding R²
R² = 1
   → 🏆 Perfect prediction

R² = 0
   → 📉 No better than predicting the mean

R² < 0
   → ❌ Worse than the mean baseline

The goal of this project was not to maximize R², but to understand how ANN regression works.

🧪 Experiments

One of the main purposes of this project was experimentation.

🔄 Experiment: Number of Epochs

With fewer epochs, the model initially produced a very poor R² score.

After increasing:

🔄 Epochs: 10 → 100

the R² improved significantly to approximately:

📈 R² ≈ 0.74

This helped demonstrate how training duration affects the ability of a neural network to learn.

I also experimented with the hidden-layer structure and number of neurons to observe how changes in architecture affect model performance.

🧠 What I Learned

Through this project, I explored the basic workflow of building an ANN for regression.

📚 Concepts Explored
🔢 Regression vs Classification
📈 Continuous numerical prediction
✂️ Train-test splitting
📏 Feature scaling
🔄 MinMaxScaler
🧠 ANN architecture
🔹 Input layer
🏗️ Hidden layers
🔢 Neurons
⚖️ Weights and biases
⚡ ReLU activation
📈 Linear activation
➡️ Forward prediction
📉 MSE loss
⚙️ Adam optimizer
🔄 Epochs
🏋️ Model training
📊 R² score
🧪 ANN experimentation
💡 Key Learning

The main purpose of this project was not simply to get a high score.

The goal was to understand what actually happens when building and training an ANN.

The overall process can be viewed as:

📂 Data
  ↓
🧹 Preprocessing
  ↓
🏗️ Architecture
  ↓
➡️ Forward Pass
  ↓
📉 Loss
  ↓
⚙️ Weight Updates
  ↓
🏋️ Training
  ↓
🔮 Prediction
  ↓
📊 Evaluation

Changing things such as the number of epochs, hidden layers, or neurons can change how the model learns.

This project was therefore treated as an experiment for understanding Deep Learning concepts rather than an optimized prediction system.

⚠️ Limitations

This project is not production-ready.

It was created primarily for learning and experimentation.

🚧 Current Limitations
📦 Relatively small dataset
🧠 Simple ANN architecture
🔧 Limited hyperparameter tuning
📊 No systematic model comparison
🛠️ No extensive feature engineering
🌐 No deployment
📡 No production monitoring
⚠️ Predictions should not be treated as actual admission decisions

The R² score can also vary depending on the train-test split and neural-network initialization.

🚀 Future Learning

The next goal is not simply to increase the R² score.

The focus is on understanding the concepts behind neural networks more deeply.

📚 Topics to Explore
➡️ Forward propagation
📉 Loss calculation
🔙 Backpropagation
📐 Gradients
⬇️ Gradient descent
⚖️ Weight updates
🎚️ Learning rate
⚙️ Optimizers
📈 Overfitting
📉 Underfitting
🛡️ Regularization
🎲 Dropout
⏹️ Early stopping
🔧 Hyperparameter tuning
🧠 Deeper neural networks
🖼️ CNNs
🚀 More advanced Deep Learning projects
📁 Project Structure
graduate-admission-prediction-ann/
│
├── 📓 Graduate_Admission_Prediction_ANN.ipynb
├── 📖 README.md
└── 📦 requirements.txt
🛠️ Technologies Used
🐍 Python
🔢 NumPy
🐼 Pandas
📊 Matplotlib
📚 Scikit-learn
🧠 TensorFlow
⚡ Keras
☁️ Kaggle Notebook
▶️ Running the Project

The notebook was developed using Kaggle.

It can also be opened using environments that support Jupyter notebooks, such as:

☁️ Kaggle
🔵 Google Colab
📓 Jupyter Notebook
🧪 JupyterLab
💻 VS Code with Jupyter support

Install the required packages using:

pip install -r requirements.txt

Then open:

Graduate_Admission_Prediction_ANN.ipynb

and run the notebook cells sequentially.

📌 Project Status
🟢 Learning Project
       ↓
🧠 ANN Regression
       ↓
🧪 Experiments
       ↓
✅ Completed
       ↓
📊 R² ≈ 0.74

The project is considered completed from a learning perspective, while deeper neural-network concepts are still being explored.

👨‍💻 Author

Praveer Singh

🎓 B.Tech CSE
🏫 MNNIT Allahabad

⭐ Final Note

This repository represents one step in my journey of learning Deep Learning.

The goal was not:

🚫 "Build the world's best admission predictor."

The goal was:

🧠 "Understand what I am actually doing when I build an ANN."

This project focuses on learning, experimentation, and building intuition around neural networks rather than presenting a production-ready machine learning solution.

🔥 Learning > Just Getting a Score

Build it → Experiment with it → Understand it → Improve it → Learn the next concept. 🚀




