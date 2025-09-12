## Contributing to this repo

First off, thank you for considering contributing!
This repository is a collection of "Today I Learned" (TIL) notes on software development, deployment, API security, and other engineering topics. Your contributions help make it more valuable for the developer community.

## How to Contribute

### 1. Fork the repository
Click the **Fork** button at the top of the repo and clone your forked version:

```bash
git clone https://github.com/selfmadecode/TILs.git
cd TILs
```

### 2. Create a new branch

Always create a new branch for your changes, your branch name should be the name of your til:

```bash
git checkout -b add-my-til
```

### 3. Add your TIL

* Go to the relevant topic folder under `topics/` (or create a new one if needed).
* Create a new Markdown file for your TIL. Example:

```text
topics/deployment/deploy-to-nuget.md
```

* Use lowercase, hyphen-separated filenames.
* Include a **clear title** at the top and a concise explanation with examples if possible.

### 4. Commit your changes
Use clear commit messages:
```bash
git add .
git commit -m "Add TIL on deploying to NuGet"
````

### 5. Push your branch

```bash
git push origin add-my-til
```

### 6. Open a Pull Request

* Go to your fork on GitHub.
* Click **Compare & Pull Request**.
* Write a clear description of your TIL contribution.
* Tag relevant topics if needed.

---

## Guidelines

* **Be concise and clear.** Focus on one lesson per file.
* **Provide examples** where possible; code snippets help others understand quickly.
* **Follow Markdown formatting** for readability.
* **Organize by topic**: If a new topic is needed, create a folder under `topics/` and add an `index.md` with a short description.

---

## Code of Conduct

Be respectful and constructive in all contributions and discussions. Any inappropriate content may be removed. See [CODE\_OF\_CONDUCT.md](CODE_OF_CONDUCT.md) for details.

---

Thank you for helping make this TIL collection a valuable resource for developers!