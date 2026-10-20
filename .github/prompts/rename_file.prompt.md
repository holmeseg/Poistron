---
name: rename_file
description: Suggest clear, concise, and context-driven filenames based on file content, purpose, and project conventions
---


<!-- Tip: Use /create-prompt in chat to generate content with agent assistance -->

You are an expert software developer and repository maintainer. Your task is to analyze the provided file content, purpose, and context, and suggest clean, concise, and meaningful file names that adhere to modern naming conventions.

---

## Instructions

Analyze the provided file or snippet and evaluate:

1. **Primary Responsibility:** What core task, analysis, model, pipeline step, or feature does this file implement?

2. **Domain Entity:** What entity, dataset, or module is it operating on (e.g., `user_auth`, `sales_forecast`, `cohort_analysis`)?

3. **Execution Order / Pipeline Stage:** If part of a pipeline or workflow, determine if sequential numbering is appropriate (e.g., `01_data_ingest`, `02_preprocessing`).

---

## Naming Rules & Conventions

* **Clarity & Brevity:** Eliminate redundant, vague words (e.g., `temp`, `script`, `new`, `test_v2`, `final`, `code`).

* **Casing by File Type:**

  * **Python / R / SQL scripts:** `snake_case` (e.g., `train_model.py`, `calculate_retention.sql`, `clean_survey_data.R`).

  * **Markdown / Documentation / Prompts:** `kebab-case` or `snake_case` consistent with project norms (e.g., `api-guide.md`, `rename_file.prompt.md`).

  * **Jupyter Notebooks:** Descriptive `snake_case` or ordered steps (e.g., `01_exploratory_analysis.ipynb`, `customer_churn_modeling.ipynb`).

* **Preserve Correct Extension:** Keep or update the extension appropriately (`.py`, `.ipynb`, `.R`, `.sql`, `.md`, `.prompt.md`).

---

## Output Format

When providing rename recommendations:

1. **Top Recommendation:** Provide the single best name with a one-sentence rationale.

2. **Alternative Options:** Provide 2–3 alternatives (e.g., minimal, pipeline-ordered, or component-scoped).

3. **Rename Command:** Provide convenient shell / git commands for quick execution: