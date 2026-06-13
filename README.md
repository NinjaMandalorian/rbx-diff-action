# rbx-diff-action

Uses [rbx-fileview](https://github.com/Barocena/RBX-Fileview) to create readable yaml diffs for file changes

## Usage

Add this action to your GitHub Actions workflow to generate readable diffs for Roblox files (`.rbxl` and `.rbxlx`):

```yaml
steps:
  - name: Generate Roblox File Diffs
    uses: NinjaMandalorian/rbx-diff-action@v1
    with:
      comment: 'true'
```

Set `comment: 'true'` to post the generated report back to the pull request or issue when the workflow has a valid token and target number.

## Inputs

| Input | Description | Default | Required |
| --- | --- | --- | --- |
| `comment` | Comment the generated report on the pull request or issue | `false` | No |
| `max-modified-lines` | Maximum modified lines before diff output is omitted | `1000` | No |
| `max-display-lines` | Maximum diff lines displayed per file | `300` | No |
| `report-path` | Path to generated markdown report | `viewfile-report.md` | No |

## Outputs

| Output | Description |
| - | - |
| `report-path` | Path to the generated markdown report |
| `changed-files-count` | Number of Roblox files processed |
| `has-large-changes` | Whether any file exceeded the large-change threshold |
