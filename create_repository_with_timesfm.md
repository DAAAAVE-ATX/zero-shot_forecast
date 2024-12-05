
# How to Set Up a Repository with TimesFM and a Virtual Environment

This guide walks you through creating a new project repository with a dedicated virtual environment, `.gitignore`, and integration with TimesFM.

---

## Steps

### 1. Create the Repository Structure
1. Create a folder for your repository, e.g., `zero-shot_forecast`.
2. Inside the folder, create the following subdirectories:
   - `timesfm_env/` (for the virtual environment)
   - `src/` (for your code)

---

### 2. Set Up a Virtual Environment
1. Navigate to the root directory of your project:
   ```bash
   cd zero-shot_forecast
   ```
2. Create a virtual environment:
   ```bash
   python -m venv timesfm_env
   ```
3. Activate the virtual environment:
   - On **macOS/Linux**:
     ```bash
     source timesfm_env/bin/activate
     ```
   - On **Windows**:
     ```bash
     timesfm_env\Scripts\activate
     ```

---

### 3. Install TimesFM
1. Clone the TimesFM repository next to your project folder:
   ```bash
   git clone https://github.com/google-research/timesfm.git
   ```
   - Ensure the structure looks like this:
     ```
     /project-root/
     ├── zero-shot_forecast/
     ├── timesfm/
     ```
2. Install TimesFM in editable mode:
   ```bash
   pip install -e ../timesfm
   ```

---

### 4. Set Up Jupyter
1. Install Jupyter and create a kernel for your virtual environment:
   ```bash
   pip install notebook ipykernel
   python -m ipykernel install --user --name=timesfm_env --display-name "Python (timesfm_env)"
   ```

---

### 5. Set Up a `.gitignore` File
1. In the root of your repository (`zero-shot_forecast`), create a `.gitignore` file.
2. Add the following contents to exclude unnecessary files:
   ```plaintext
   # Exclude virtual environment
   timesfm_env/

   # Byte-compiled files
   __pycache__/
   *.py[cod]

   # Jupyter Notebook checkpoints
   .ipynb_checkpoints/

   # System files
   .DS_Store
   Thumbs.db
   ```

---

### 6. Save Dependencies
1. As you install packages, save them to a `requirements.txt` file:
   ```bash
   pip freeze > requirements.txt
   ```

---

## Workflow for Development

1. Activate the virtual environment:
   ```bash
   source timesfm_env/bin/activate  # macOS/Linux
   timesfm_env\Scripts\activate     # Windows
   ```
2. Write your code in the `src/` folder.
3. Launch Jupyter for notebooks:
   ```bash
   jupyter notebook
   ```
4. Test importing TimesFM:
   ```python
   import timesfm
   print(timesfm.__version__)
   ```

---

## Pushing to GitHub
1. Initialize the Git repository:
   ```bash
   git init
   git remote add origin https://github.com/your-username/zero-shot_forecast.git
   ```
2. Add and commit your files:
   ```bash
   git add .
   git commit -m "Initial commit"
   git push -u origin main
   ```

---

## Folder Structure Example
```
/project-root/
├── zero-shot_forecast/
│   ├── timesfm_env/         # Virtual environment (excluded by .gitignore)
│   ├── src/                 # Code and notebooks
│   ├── requirements.txt     # Dependencies
│   ├── .gitignore           # Ignore unnecessary files
│   ├── README.md            # Documentation
├── timesfm/                 # Cloned repository for TimesFM
```
