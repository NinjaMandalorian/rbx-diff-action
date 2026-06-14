# rbx-diff-action

Uses [rbx-fileview](https://github.com/Barocena/RBX-Fileview) to create readable yaml diffs for file changes

## Warning

This action **assumes** you have RBX-Fileview in the project's rokit.toml manifest. Ensure it does before usage.

## Usage

Add this action to your GitHub Actions workflow to generate readable diffs for Roblox files. You can target place files (`.rbxl`, `.rbxlx`), model files (`.rbxm`, `.rbxmx`), or both.

```yaml
steps:
  - name: Generate Roblox File Diffs
    uses: NinjaMandalorian/rbx-diff-action@v1.0.1
    with:
      comment: 'true'
      file-types: 'both'
```

Set `comment: 'true'` to post the generated report back to the pull request or issue when the workflow has a valid token and target number.

## Inputs

| Input | Description | Default | Required |
| --- | --- | --- | --- |
| `comment` | Comment the generated report on the pull request or issue | `false` | No |
| `file-types` | Which Roblox file types to include: `place`, `model`, or `both` | `both` | No |
| `max-modified-lines` | Maximum modified lines before diff output is omitted | `1000` | No |
| `max-display-lines` | Maximum diff lines displayed per file | `300` | No |
| `report-path` | Path to generated markdown report | `fileview-report.md` | No |

## Outputs

| Output | Description |
| --- | --- |
| `report-path` | Path to the generated markdown report |
| `changed-files-count` | Number of Roblox files processed |
| `has-large-changes` | Whether any file exceeded the large-change threshold |
