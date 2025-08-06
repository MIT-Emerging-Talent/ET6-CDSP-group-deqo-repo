<!-- markdownlint-disable MD013 -->
# 🤝 Contributing Guideline

Welcome, and thank you for your interest in contributing to the **Emerging Talent 6 Collaborative Data Science Project (CDSP)**! This guide will help you set up your local environment, understand our workflow, and collaborate efficiently with the team.

---

## 🚀 Getting Started

To get up and running with this project locally, follow these steps:

### 1. Clone the Repository

```bash
git clone https://github.com/MIT-Emerging-Talent/ET6-CDSP-group-deqo-repo
cd ET6-CDSP-group-deqo-repo
```

### 2. Set Up Your Environment

**Using pip**:

```bash
pip install -r requirements.txt
```

**Using Conda** (recommended):

```bash
conda create --name et6-cdsp python=3.10
conda activate et6-cdsp
pip install -r requirements.txt
```

---

## 🧰 Tools & Environment

We primarily use:

- **Python 3.10+**
- **Jupyter Notebook / JupyterLab** (for interactive data exploration)
- Core libraries: `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`
- **Git + GitHub** for version control and project tracking

**Optional but helpful:**

- VS Code or any Python IDE
- Code formatters: `Black`, `Flake8`

---

## 📁 Folder Structure

Refer to `README.md` and `guide.md` for a complete layout of folders and files.

> Tip: Always reference the source of your data. For example, if you use a cleaned dataset from /2_data_preparation, mention that in your notebook under /3_data_exploration.
>

---

## 🔄 Collaboration Workflow

To streamline teamwork, follow this process:

### 1. Create a Branch

Always branch off from `main`:

```bash
git checkout main
git pull
git checkout -b your-feature-name
```

### 2. Make Meaningful Commits

- Commit frequently with clear messages.
- Use descriptive messages like:

### 3. Push and Open a Pull Request (PR)

```bash
git push origin your-feature-name
```

Then, go to GitHub and open a **pull request** against the `main` branch.

### 4. Review & Merge

- Every PR must be reviewed by at least one teammate.
- Request a reviewer and describe your changes clearly.
- Only merge after approval.

---

## 📓 Documentation Guidelines

- Comment your code and use Markdown cells to explain your work.
- Keep file names clear and meaningful (e.g., `explore_survey_responses.ipynb`, **not** `final2_updated.ipynb`).
- Update any relevant `README.md` when changes affect a folder’s content or purpose.

---

## 🔁 Retrospectives & Communication

- Use the `/collaboration` folder to log retrospectives at the end of each milestone.
- Capture strategy shifts, challenges faced, feedback, and key lessons learned.

---

## 🧠 Best Practices for Data Science Projects

- **Prioritize reproducibility**: Others should be able to run your code without guesswork.
- **Keep it modular**: Break your work into clear stages (e.g., cleaning, analysis, modeling).
- **Never overwrite raw data**: Save processed files separately.
- **Use comments and markdown generously** to explain your logic and process.
- **Restart and run notebooks before committing** to maintain clean execution order.
- **Avoid redundancy**: Reuse code using helper scripts or utility functions.
- **Cross-reference** dependencies between scripts and data files.
- **Test your work**: Make sure your pipeline runs smoothly on a clean setup.
- **Ask early, collaborate often**: Don't hesitate to open issues or ask questions in the team chat.

---

Thanks for helping us build a transparent, collaborative, and impactful data science project! 💡✨
