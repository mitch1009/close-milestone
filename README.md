# Close Milestones Action

This action closes milestones for a given repository.

## Usage

```yaml
uses: Mitch1009/close-milestone@main
with:
  github-token: ${{ secrets.GITHUB_TOKEN }}
  milestone-file: ${{ github.workspace }}/milestones.md
```


## Inputs

### `github-token`

**Required** The GitHub token to use for authentication.

### `milestone-file`

**Required** The path to the markdown file containing the milestones.

## Outputs

### `milestones-created`

The number of new milestones created.

### `milestones-updated`

The number of existing milestones updated.

### `issues-created`

The number of new issues created.
