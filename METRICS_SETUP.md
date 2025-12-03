# GitHub Metrics Setup Guide

This repository uses automated GitHub workflows to generate comprehensive GitHub statistics and visualizations.

## 🎯 Features

The following GitHub metrics and visualizations are automatically generated:

1. **GitHub Stats** - General statistics including stars, commits, PRs, and issues
2. **Top Languages** - Most used programming languages
3. **GitHub Streak** - Contribution streak statistics
4. **GitHub Trophies** - Achievement badges based on GitHub activity
5. **GitHub Metrics** - Detailed metrics including activity, habits, and notable contributions
6. **Contribution Snake** - Animated snake eating your contributions
7. **Activity Graph** - Visual representation of your recent GitHub activity

## 🔧 Setup Instructions

### Required Secrets

To enable the GitHub Metrics workflow, you need to set up a personal access token:

1. **METRICS_TOKEN** (Required for metrics.yml workflow):
   - Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Click "Generate new token (classic)"
   - Set a name like "GitHub Metrics"
   - Select the following scopes:
     - `repo` (Full control of private repositories)
     - `read:org` (Read org and team membership, read org projects)
     - `read:user` (Read ALL user profile data)
     - `read:packages` (Download packages from GitHub Package Registry)
   - Generate and copy the token
   - Go to your repository Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `METRICS_TOKEN`
   - Value: Paste your token
   - Click "Add secret"

### Automated Workflows

The repository includes two GitHub Actions workflows:

#### 1. GitHub Metrics (`metrics.yml`)
- **Schedule**: Runs daily at 00:00 UTC
- **Manual Trigger**: Can be run manually from the Actions tab
- **Output**: Generates `github-metrics.svg` in the `output` branch
- **Features**:
  - Isometric calendar
  - Language statistics
  - Achievements
  - Notable contributions
  - Activity timeline
  - Coding habits
  - Lines of code changed

#### 2. Contribution Snake (`snake.yml`)
- **Schedule**: Runs every 12 hours
- **Manual Trigger**: Can be run manually from the Actions tab
- **Output**: Generates contribution grid snake animations in the `output` branch
- **Features**:
  - Light and dark theme variants
  - Animated SVG showing contribution activity

### First Run

After setting up the `METRICS_TOKEN`:

1. Go to the "Actions" tab in your repository
2. Click on "GitHub Metrics" workflow
3. Click "Run workflow" → "Run workflow"
4. Wait for the workflow to complete (may take a few minutes)
5. Similarly, run the "Generate Snake Animation" workflow
6. The generated images will be available in the `output` branch

### Customization

You can customize the metrics by editing `.github/workflows/metrics.yml`:

- **Theme**: Change `config_timezone` to your timezone
- **Plugins**: Enable/disable plugins by setting `plugin_name: yes/no`
- **Duration**: Adjust time ranges for statistics (e.g., `plugin_isocalendar_duration`)
- **Limits**: Control the amount of data displayed with various `_limit` parameters

For more customization options, see the [lowlighter/metrics documentation](https://github.com/lowlighter/metrics).

## 📝 Notes

- The snake animation and metrics SVG files are stored in the `output` branch
- Workflows run automatically on schedule, but you can trigger them manually anytime
- The `GITHUB_TOKEN` secret is automatically provided by GitHub Actions (no setup needed)
- Images may take a few minutes to update after workflow runs

## 🔗 Resources

- [GitHub Metrics](https://github.com/lowlighter/metrics)
- [Contribution Snake](https://github.com/Platane/snk)
- [GitHub Profile Trophy](https://github.com/ryo-ma/github-profile-trophy)
- [GitHub Readme Stats](https://github.com/anuraghazra/github-readme-stats)
- [GitHub Readme Streak Stats](https://github.com/DenverCoder1/github-readme-streak-stats)
- [GitHub Readme Activity Graph](https://github.com/ashutosh00710/github-readme-activity-graph)
