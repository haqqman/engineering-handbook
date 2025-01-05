# GitFlow

## A Custom GitFlow Tailored for Excellence

The GitFlow strategy used at Haqqman is a unique adaptation, designed and pioneered by **Abdulhaqq Sule**, CTO at Haqqman. This approach balances simplicity with structure, enabling teams to work effectively while maintaining clean, production-ready code. It provides a framework for managing development, testing, and deployment processes efficiently.

By implementing this strategy, Haqqman has streamlined its workflows and set a benchmark for other engineering teams to follow.

---

## Key Branches in Haqqman's GitFlow

The Haqqman GitFlow revolves around two core branches:

| Branch       | Purpose                                 |
|--------------|-----------------------------------------|
| **main**     | Production-ready code                  |
| **sandbox**  | Active development and integration     |

### Principles for Best Practice

1. Always create a new branch from `sandbox` for feature development or bug fixes.
2. Name branches descriptively and tie them to the related issue, e.g., `sandbox-add-new-payment-methods`.
3. Commit and push changes to your feature branch regularly.
4. Open a pull request when your work is ready for review, linking it to the associated issue.
5. Ensure that a pull request is reviewed by a team lead or an experienced developer before merging. For freelancers, thorough testing is strongly recommended as a substitute.
6. Merge approved pull requests into `sandbox`.
7. Delete the feature branch after merging.
8. Assign a label to every pull request, clearly indicating its purpose, and ensure that the relevant assignees are added.
9. Ensure any code in `main` is deployable for production.

---

## GitFlow Workflow in Action

### 1. Starting a Feature
   ```bash
   git checkout sandbox
   git checkout -b sandbox-feature-name
   ```
   - Commit and push changes:
   ```bash
   git add .
   git commit -m "Implement feature"
   git push origin sandbox-feature-name
   ```

### 2. Merging a Feature
   - Open a pull request and ensure it is reviewed by a team lead or an experienced developer. For freelancers, complete all necessary tests before proceeding.
   - After approval, merge your feature branch back into `sandbox`:
   ```bash
   git checkout sandbox
   git merge sandbox-feature-name
   git branch -d sandbox-feature-name
   ```

### 3. Creating a Release (Optional)
   ```bash
   git checkout sandbox
   git checkout -b release/1.0.0
   ```
   - Test, document, and finalize changes, then merge into both `main` and `sandbox`:
   ```bash
   git checkout main
   git merge release/1.0.0
   git checkout sandbox
   git merge release/1.0.0
   git branch -d release/1.0.0
   ```

### 4. Fixing a Hot Issue
   ```bash
   git checkout main
   git checkout -b hotfix-issue-name
   ```
   - Apply the fix and merge into both `main` and `sandbox`:
   ```bash
   git add .
   git commit -m "Fix issue"
   git checkout main
   git merge hotfix-issue-name
   git checkout sandbox
   git merge hotfix-issue-name
   git branch -d hotfix-issue-name
   ```

---

## Why Haqqman's GitFlow?

- **Efficient Development:** Enables parallel work streams while maintaining code stability.
- **Simplified Collaboration:** Clear branch naming, structured workflows, and mandatory reviews reduce confusion.
- **Production Confidence:** Only high-quality, tested code reaches `main`.

---

Haqqman's GitFlow exemplifies a well-thought-out approach to software development. It’s more than just a branching model; it’s a philosophy that ensures predictability, quality, and continuous improvement.

---

[← Previous: GitHub - Empowering Giants](./github-agile.md) | [Next: Complexity Costs](./complexity-costs.md)
