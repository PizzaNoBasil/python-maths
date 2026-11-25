# python-maths

Solutions to maths-oriented university coursework, written in Python with NumPy, pandas and scikit-learn. Each lab is a self-contained Jupyter notebook. The task statements and comments inside the notebooks are in Russian.

## Contents

| Notebook | Topic | What's covered |
|---|---|---|
| [`lab1VVC.ipynb`](lab1VVC.ipynb) | NumPy basics and gradient descent | 10 vectorised NumPy exercises, plus linear regression trained with hand-written gradient descent |

### Lab 1 in detail

**Part 1: NumPy exercises.** Each task is a small function solved with array operations instead of Python loops:

1. Weighted, rounded sum of marks (course grade from weights)
2. Replace every third element of an array with a given number
3. Indices of "close" element pairs whose absolute difference is within a tolerance
4. Build a 2×2 block matrix from one block
5. Product of the non-zero entries on a square matrix's diagonal
6. Column-wise normalisation (z-score), safe for constant columns (no `NaN`)
7. Antiderivative of a polynomial given its coefficients
8. Turn a triangular matrix into a symmetric one
9. Matrix of `m` identical rows counting from `a` to `b`
10. Cosine similarity of two vectors

**Part 2: gradient descent.** Linear regression with 10 features and an intercept on a 1,000-row dataset, minimising mean squared error:

- `calculate_mse_loss`: MSE for the current weights
- `calculate_gradient`: gradient of the MSE in matrix form, without loops
- `iteration`: one update step, β ← β − η·∇Q(β)
- `learn`: repeats updates until the change in MSE drops below a threshold

As a reference, the notebook first fits scikit-learn's `LinearRegression`, which gives coefficients 1, 2, …, 10 and an intercept of about 4.37. The hand-written gradient descent stops at an MSE of about 0.011, with weights from about 0.89 to 9.86 and an intercept of about 4.95.

## Running the notebooks

Requires Python 3.11 or newer. Tested with Python 3.14, NumPy 2.5, pandas 3.1 and scikit-learn 1.9.

```bash
python -m venv .venv
# Windows: .venv\Scripts\activate    macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
jupyter notebook
```

You can also open the notebooks in VS Code with the Jupyter extension and choose the `.venv` interpreter as the kernel.

Part 2 of Lab 1 downloads its dataset from a public link provided by the course, so it needs an internet connection.

## Notes

- Task statements, function skeletons and the Part 2 dataset were provided by the course; the solutions are my own.
- Saved outputs are left in the notebooks so results can be read on GitHub without running anything.
