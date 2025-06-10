# Guidelines for Starting an R Project with Quarto Documentation

If you're aiming to create well-organized, reproducible **Quarto documentation** in **R**, follow these steps:

---

## ✅ 1. Start with an RStudio Project

Creating a project gives you a self-contained environment with relative paths and workspace management.

### Steps:
1. Open **RStudio** → `File` → `New Project...`
2. Choose:
   - **New Directory** (to start fresh) or  
   - **Existing Directory** (if you already have files)
3. Choose **Empty Project**
4. Name your folder, pick a location, and click `Create Project`

> This creates a `.Rproj` file to manage your project settings.

---

## ✅ 2. Create a Quarto Document

With the R project open:

1. Go to `File` → `New File` → `Quarto Document...`
2. Fill in:
   - **Title**, **Author**
   - **Format**: `HTML`, `PDF`, etc.
   - **Engine**: `knitr` (R) or `Jupyter` (Python or both)
3. Click `Create`

> This will generate a `.qmd` file with starter YAML.

---

## ✅ 3. Organize Your Project

Use a clear directory structure:

```
your-project/
├── data/ # raw data
├── scripts/ # R scripts and helper functions
├── reports/ # rendered outputs
├── your-doc.qmd # main Quarto file
├── your-project.Rproj
```


---

## ✅ 4. Render Your Document

Click the **Render** button in RStudio or run:

```r
quarto::quarto_render("your-doc.qmd")
```

> Make sure you have the Quarto extension installed in RStudio.

---

## ✅ 5. Use renv for Dependency Management
Use `renv` to make your project reproducible by isolating package versions.

Initialize renv:

```{r}
renv::init()
```
This creates a `renv.lock` file and `renv/` folder.

Install packages as usual:

```r
install.packages("dplyr")
They will be tracked automatically.
```

Restore environment later (e.g., on another computer):
```r
renv::restore()
```
Commit `renv.lock` to version control, but do not commit the `renv/library/` folder.


---

## ✅ 6. Use Git (Optional but Recommended)

Version control helps track your work:

  - Initialize Git in the project folder
  - Connect to GitHub (or other platforms)

Use .gitignore to exclude data or output files you don't want in version control.

---

## ✅ 7. Optional: Use a Quarto Project YAML
If you plan to render multiple documents or need global options, create a `_quarto.yml`:

```
project:
  type: default
  output-dir: reports
```

