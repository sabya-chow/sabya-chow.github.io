# Launch Steps — sabya-chow.github.io

## One-time setup (do this once, ~15 minutes)

### 1. Create the GitHub repo

Go to https://github.com/new and create a repo named exactly:
  sabya-chow.github.io

Make it **Public**. Don't add README/gitignore — keep it empty.

---

### 2. Create your local repo folder

Open Terminal and run these commands one by one:

```bash
mkdir ~/sabya-chow.github.io
cd ~/sabya-chow.github.io
git init
git remote add origin https://github.com/sabya-chow/sabya-chow.github.io.git
```

---

### 3. Copy the site files into the repo folder

```bash
# Copy the index.html Claude built
cp "/path/to/index.html" ~/sabya-chow.github.io/

# Create the GitHub Actions folder
mkdir -p ~/sabya-chow.github.io/.github/workflows

# Copy the deploy workflow
cp "/path/to/deploy.yml" ~/sabya-chow.github.io/.github/workflows/
```

---

### 4. Convert your notebook to HTML

Make sure jupyter is installed (it is — you have it), then run:

```bash
cd "/path/to/your/causal_chaturvedi/final_assignment"
jupyter nbconvert --to html "final submission.ipynb" --output "final_submission"
```

This creates `final_submission.html`. Then:

```bash
mkdir -p ~/sabya-chow.github.io/causal-alpha
cp final_submission.html ~/sabya-chow.github.io/causal-alpha/index.html
```

---

### 5. Enable GitHub Pages in repo settings

Go to: https://github.com/sabya-chow/sabya-chow.github.io/settings/pages

Under "Source" → select **GitHub Actions**. Save.

---

### 6. Push and go live

```bash
cd ~/sabya-chow.github.io
git add .
git commit -m "initial launch"
git branch -M main
git push -u origin main
```

Wait ~60 seconds. Your site is live at:
  https://sabya-chow.github.io

---

## Every future update

Edit any file, then:
```bash
cd ~/sabya-chow.github.io
git add .
git commit -m "update: <what you changed>"
git push
```
Done. GitHub redeploys automatically.
