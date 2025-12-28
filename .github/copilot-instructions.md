# AI Coding Guidelines for MML Study Companion

## Project Overview
This repository implements mathematical concepts from "Mathematics for Machine Learning" (Deisenroth et al.) using NumPy. Focus on translating theory into code, building foundations in Linear Algebra, Calculus, and Probability.

## Architecture & Structure
- **Chapter Folders** (02_linear_algebra/, 03_analytic_geometry/, etc.): Contain topic-specific notebooks
- **Micro Labs** (micro_labs/): Focused implementations of specific concepts with verification
- **Capstones**: Larger integrative projects (planned)
- **docs/progress.md**: Tracks completion status and links to artifacts

## Development Patterns
### Code Style
- Use `import numpy as np` at cell top
- Functions with type hints: `def func(A: np.ndarray) -> np.ndarray:`
- Docstrings reference book sections: `"""Solves Ax=b from chapter 2.1"""`
- Implement core logic from scratch, use `np.linalg.*` for verification

### Verification Approach
- Use `np.allclose()` for floating-point comparisons
- Example: `is_correct = np.allclose(np.dot(A, x), b)`
- Print intermediate results for educational demonstration

### Notebook Structure
- Single-function cells for concept isolation
- Follow pattern: define function → call with example → verify results
- Example from `solve_linear_system.ipynb`:
  ```python
  def solve_linear_system():
      A = np.array([[4, 4], [2, -4]])
      b = np.array([5, 1])
      x = np.linalg.solve(A, b)
      print(f"Verification (Ax == b): {np.allclose(np.dot(A, x), b)}")
  ```

## Workflows
- **Development**: Edit in VS Code Jupyter extension, run cells interactively
- **Testing**: Manual verification via printed assertions and `np.allclose`
- **Progress Tracking**: Update `docs/progress.md` with new implementations

## Key Files
- `requirements.txt`: Minimal dependencies (numpy, jupyter)
- `docs/progress.md`: Current status and artifact links
- Example implementations: `02_linear_algebra/solve_linear_system.ipynb`, `04_matrix_decompositions/micro_labs/micro_lab_01_enigendecomposition.ipynb`

## Conventions
- Matrix naming: `A` for coefficients, `b` for vectors, `x` for solutions
- Error handling: Catch `np.linalg.LinAlgError` for singular matrices
- Educational focus: Prioritize clarity and mathematical correctness over optimization