# athena-workflows

Workflows that learner repos call but cannot change. Athena's night mode dispatches `destroy.yml` in each learner's infra repo, and that file only calls `.github/workflows/destroy.yml@v1` here.

The destroy run stops before it touches anything unless three account ids agree: the one Athena sends, the repo's `AWS_ACCOUNT_ID` variable, and the account the assumed role lands in. It only destroys `live/`, never `bootstrap/`.

Fixes move the `v1` tag. Breaking changes get `v2`.
