# RegShape Homebrew tap

Install the RegShape command-line interface (CLI) with Homebrew:

```bash
brew install toddysm/regshape/regshape
regshape --help
```

The [formula](Formula/regshape.rb) installs RegShape and its pinned Python
dependencies into an isolated virtual environment.

## Validation

The [GitHub Actions workflow](.github/workflows/tests.yml) validates pull requests
and pushes to `main` on macOS and Linux. It checks formula style and tap syntax,
installs the formula from source, runs its smoke test, and performs a strict audit.
Both platform jobs run to completion independently.

`Homebrew/actions/setup-homebrew` checks out the event revision directly into the
tap. The workflow verifies that the tap's commit matches `GITHUB_SHA` before
validation. A second checkout or a local-path `brew tap` is unnecessary and can
replace the checkout or conflict with the tap's configured remote.

Installation, testing, and auditing use the fully qualified
`toddysm/regshape/regshape` formula so they cannot select another tap's formula.