# Contributing

This repository is an archival analysis companion to a peer-reviewed article. Contributions should improve reproducibility, documentation, accessibility, or the faithful implementation of the reported analyses.

## Reporting a problem

When possible, include:

- the file and section involved;
- the expected and observed result;
- the operating system and R or Python version;
- the shortest sequence of commands that reproduces the problem; and
- any relevant warning or error output.

Do not include participant-level records, credentials, or other sensitive information in an issue.

## Proposing a change

Keep changes focused and explain whether they affect code, numerical results, interpretation, or documentation. Changes to an analysis should preserve the original workflow unless they are explicitly labeled as a correction or extension. A proposed correction should identify the relevant claim in the article or report and show how the revised result was obtained.

Before submitting a change:

1. restore the recorded environment (`renv.lock` or `requirements.txt`);
2. rerun the affected analysis from the `Analysis` directory;
3. confirm that the rendered report completes without an error; and
4. document any numerical differences from the archived output.

## Data access

Participant-level data are not distributed through this repository. Direct access requests to the study authors, and do not attach participant data to issues, pull requests, or other public repository content.

## Scope

Methodological extensions are welcome as clearly separated analyses. General-purpose portfolio material, business demonstrations, and unrelated software features are outside this repository's scholarly scope.
