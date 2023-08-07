# Playground

Playground for testing GitHub actions and integrations...

Test 2.

## Development

- All changes are made in feature branches and merged into the `main` branch via pull requests.

[![](https://mermaid.ink/img/pako:eNqdkbEOwjAMRH-l8lyGdsyMxMTEmsUkbhPRJJVxBlT13wlQJKSCQHg6nc9v8E1gkiVQ0HvZMY5Ox6qMSSF4WesjYzSu6gglM22aJeHInFKWlf9KeWYC-vgW1n6AtT_BAnFPX1nNH6zlRkeooWxKzJZ_TTdXgzgKpEEVaanDPIgGHecSxSzpcIkGlHCmGvJoUWjrsWcMoDoczsUl6yXx_tHBvYr5ClPdhQA?type=png)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNqdkbEOwjAMRH-l8lyGdsyMxMTEmsUkbhPRJJVxBlT13wlQJKSCQHg6nc9v8E1gkiVQ0HvZMY5Ox6qMSSF4WesjYzSu6gglM22aJeHInFKWlf9KeWYC-vgW1n6AtT_BAnFPX1nNH6zlRkeooWxKzJZ_TTdXgzgKpEEVaanDPIgGHecSxSzpcIkGlHCmGvJoUWjrsWcMoDoczsUl6yXx_tHBvYr5ClPdhQA)

## Release Candidate

- The existence of a branch named `release-candidate` indicates that a release candidate is in the process of being created.

- If issues are found in the `release-candidate` branch, the a fix pull request is opened against that branch.

- When the release candidate is finalized, a release is created from the `release-candidate` and the `release-candidate` branch is deleted.

[![](https://mermaid.ink/img/pako:eNqdUjEOwjAM_ErkGQY6dkZiYmLNYhK3jWiSKnUQCPF3ElohASoVzWSdz-c7xTdQXhOUUBveBewa6UR6yltr-Ls-BnSqEYFawp7WCp02GplGZkPq5CMLi8b9FnpRJ6TGRZW5rLuw-X_eUqjpY_zb3cCaSrPUbvEx844uDFEsDDGzYrAjjC6FhJEjzhsJgrHOWK5nfxdWkFwkXKdLuuWeBG7IkoSsoanC2HIWuicqRvaHq1NQcoi0gthlP1uDdUALZYVtn1DShn3YD9f5PNL7Awj_5qw?type=png)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNqdUjEOwjAM_ErkGQY6dkZiYmLNYhK3jWiSKnUQCPF3ElohASoVzWSdz-c7xTdQXhOUUBveBewa6UR6yltr-Ls-BnSqEYFawp7WCp02GplGZkPq5CMLi8b9FnpRJ6TGRZW5rLuw-X_eUqjpY_zb3cCaSrPUbvEx844uDFEsDDGzYrAjjC6FhJEjzhsJgrHOWK5nfxdWkFwkXKdLuuWeBG7IkoSsoanC2HIWuicqRvaHq1NQcoi0gthlP1uDdUALZYVtn1DShn3YD9f5PNL7Awj_5qw)

## Hotfix (without release candidate)

When there is no release candidate, hotfix follows an identical flow to the release candidate flow except the branch is named `hotfix`.

## Hotfix (with release candidate)

- When changes are merged into the `hotfix` branch, they are then merged to both the `release-candidate` and the `main` branches.

[![](https://mermaid.ink/img/pako:eNqlkzFvwyAQhf8KujkZ4m6eK3Xq1JXlCmeDasAi56pVlP9eKLZklySyVCY43vt49sEFVNAELfSWXyKORnqRhgrOWV7PhdWtkBBpIDyTBMHY58LnSULRvUf0yggTuLNfIkRNsRXNzDCkPsLEwqH19RGzdYYfFXptNTItlNMuyma-SCvmA-0d7LJdvmyTOK2PY1xiPu00O4o9zd59cYtjzbgR-oFoU7zRT5HbWLf0n3-xBLrn3cX-G7NZxWyqmHUD4QApRarrdMcveU8CG3LpBmeGpg6ngTPomqQ4cXj79gpajhMdYBpznmeLfUQHbYfDOVVJWw7xtbyb3-dz_QEC8hf1?type=png)](https://mermaid-js.github.io/mermaid-live-editor/edit#pako:eNqlkzFvwyAQhf8KujkZ4m6eK3Xq1JXlCmeDasAi56pVlP9eKLZklySyVCY43vt49sEFVNAELfSWXyKORnqRhgrOWV7PhdWtkBBpIDyTBMHY58LnSULRvUf0yggTuLNfIkRNsRXNzDCkPsLEwqH19RGzdYYfFXptNTItlNMuyma-SCvmA-0d7LJdvmyTOK2PY1xiPu00O4o9zd59cYtjzbgR-oFoU7zRT5HbWLf0n3-xBLrn3cX-G7NZxWyqmHUD4QApRarrdMcveU8CG3LpBmeGpg6ngTPomqQ4cXj79gpajhMdYBpznmeLfUQHbYfDOVVJWw7xtbyb3-dz_QEC8hf1)

## Deployments

- Development deployments happen manually and are targeted to a specific environment from a specific branch.

- Development deployments can be triggered by adding a label `Deploy to ${env}` to a pull request.

- Staging deployments happen automatically from either the `hotfix`, `release-candidate`, or `main` branch. The branches are ranked in that order. If a higher priority branch exists, then deployments will not be triggered from lower priority branches.

- Production deployments happen manually. They will deploy the latest release by default, but a different tag can be specified. An approval request will be sent for production deployments and they must be signed off by an approver.
