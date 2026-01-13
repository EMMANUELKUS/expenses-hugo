## Pal Feature

In this feature, we added a JSON expense object property called `pal` which allowed us to specify the person who is going to pay the expense. If the expense object had no such property, then this means that no one said that they are going to pay the expense.

## Automatic Artefact Generation

**Option 1:** A way to run `hugo` each time the JSON data file is saved.
**Option 2:** A way to run `hugo` before a push to GitHub
**Option 3:** Remove the artefact from the repository, and add a *GitHub action* that generates the artefact on GitHub instead of generating it locally and comitting it to the repository.

### Option 1 (`feature/run-on-save`)

We are going to use a vscode extension called run on save.

Status :white_check_mark: Done

### Option 2

### Option 3