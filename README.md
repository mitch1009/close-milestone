# Close Completed Milestones and Create PR Action

This action automatically closes completed milestones and creates a pull request to a specified branch with information about the closed milestones.

## Usage

```yaml
uses: Mitch1009/close-milestone@main
with:
  github-token: ${{ secrets.GITHUB_TOKEN }}
  target-branch: main
```

## Inputs

### `github-token`

**Required** The GitHub token to use for authentication.

### `target-branch`

**Optional** The branch to create the PR against. Default is 'main'.

## What it does

1. Checks out the repository code.
2. Scans for open milestones and closes any that have all issues resolved.
3. If any milestones were closed, it:
   - Creates a new branch
   - Adds a file with information about the closed milestones
   - Creates a pull request to merge these changes into the specified target branch

## Example workflow

```yaml
name: Close Milestones
on:
  schedule:
    - cron: '0 0 * * *'  # Runs daily at midnight
  workflow_dispatch:  # Allows manual triggering

jobs:
  close-milestones:
    runs-on: ubuntu-latest
    steps:
      - name: Close Completed Milestones
        uses: Mitch1009/close-milestone@main
        with:
          github-token: ${{ secrets.GITHUB_TOKEN }}
          target-branch: main
```

This workflow will run daily and can also be triggered manually. It will close any completed milestones and create a pull request with the results.

## License

This project is licensed under the [MIT License](LICENSE).
