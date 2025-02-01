\documentclass{article}
\usepackage{hyperref}
\usepackage{listings}

\title{\huge \textbf{ House Price Prediction with XGBoost}}
\author{}
\date{}

\begin{document}

\maketitle

\section*{ What This Project Offers}
\begin{itemize}
\item  Data analysis and preprocessing with Pandas and NumPy
\item  Exploratory Data Analysis (EDA) with Seaborn and Matplotlib
\item  Model training using XGBoost Regressor
\item  Performance evaluation with Scikit-Learn metrics
\end{itemize}

\section*{ How to Get Started}
\begin{enumerate}
\item Clone this repository:
\begin{lstlisting}[language=bash]
git clone https://github.com/yourusername/house-price-prediction.git
cd house-price-prediction
\end{lstlisting}
\item Install dependencies:
\begin{lstlisting}[language=bash]
pip install -r requirements.txt
\end{lstlisting}
(Need a \texttt{requirements.txt}? Run \texttt{pip freeze > requirements.txt} to generate one.)
\item Open and run the Jupyter Notebook:
\begin{lstlisting}[language=bash]
jupyter notebook
\end{lstlisting}
\end{enumerate}

\section*{ The Dataset}
We're using the \textbf{California Housing dataset}, which comes built-in with Scikit-Learn:
\begin{lstlisting}[language=Python]
from sklearn.datasets import fetch_california_housing
data = fetch_california_housing()
\end{lstlisting}

\section*{ Training the Model}
The model is trained using the \textbf{XGBoost Regressor}:
\begin{lstlisting}[language=Python]
from xgboost import XGBRegressor
model = XGBRegressor(n_estimators=100, learning_rate=0.1, max_depth=6)
model.fit(X_train, Y_train)
\end{lstlisting}

\section*{📈Evaluating Performance}
To check how well the model performs, we use RMSE and R² Score:
\begin{lstlisting}[language=Python]
from sklearn.metrics import mean_squared_error, r2_score
predictions = model.predict(X_test)
mse = mean_squared_error(Y_test, predictions)
r2 = r2_score(Y_test, predictions)
print(f"RMSE: {mse ** 0.5}")
print(f"R² Score: {r2}")
\end{lstlisting}
