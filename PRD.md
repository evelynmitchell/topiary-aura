# PRD Product Requirements Doc

Gemini 2.5 thinking

## The Elevator Pitch

Topiary-Aura is a VS Code extension and GitHub App that seamlessly integrates ML experiment tracking into your git workflow, so you never lose track of a result again.

## The Core Problem It Solves

Experiment Management Hell, and Collaborative Friction

## How it Works:

### In VS Code:

        Smart Logger: A simple decorator or context manager (with topiary-aura.log():) that you wrap around your training loop. It automatically captures metrics (e.g., from print statements, TensorBoard logs, or a returned dictionary), system stats (GPU usage), and hyperparameters.

        Git Commit Integration: When you commit your code, Aura automatically associates the latest experiment results with that commit hash. The results are stored in a lightweight .topiary_aura/ directory (as JSON/YAML files) that you commit to your repo.

        "Time-Travel" Gutter UI: An icon appears in the VS Code gutter next to your training code. Clicking it opens a side panel showing a history of all previous runs for that code block, linked to their commits. You can see how metrics have changed over time.

        Experiment Diffing: Before you commit, the Source Control panel shows you a "results diff." For example: accuracy: 0.89 -> 0.91 (+0.02).

### In GitHub:

        Enriched Pull Requests: The Topiary-Aura GitHub App automatically posts a comment on any PR with a summary of the experimental changes. It shows a clear table of metrics, comparing the results from the base branch to the feature branch.

        "Model Performance" Check: This makes reviewing a PR incredibly powerful. A reviewer can immediately see if a code change actually improved the model, without having to pull the branch and re-run the training.

        Repo Dashboard: A simple, beautiful dashboard linked from the repo homepage that visualizes the best-performing experiments and key metrics over time.

## Monetization

Freemium model. Free for public repos and individual developers (with a limit on private experiments). Paid "Team" tier for unlimited private repos, advanced collaboration features, and security controls.

## Project Outline

    Start with "Topiary-Aura". Of the three, Topiary-Aura solves the most acute and frequent pain point. Its MVP (Minimum Viable Product) is also the clearest: a VS Code extension that logs metrics to a local file and associates it with a git commit. The GitHub PR comment is a killer feature that provides immediate, visible value.

    User Interviews: Find 10-20 AI developers on LinkedIn, Twitter, or in your network. Show them mockups. Ask them: "How do you track experiments now? What do you hate about it? Would a tool that puts results directly in your PRs be useful?"

    Analyze Competition: Look at Weights & Biases, MLflow, and CometML. Their strength is their powerful, standalone dashboards. Your competitive advantage is developer-native integration. You are not trying to replace them, but to offer a lightweight, git-centric alternative for developers who find those tools too heavy. Your wedge is the GitHub PR integration—something none of them do as deeply.

