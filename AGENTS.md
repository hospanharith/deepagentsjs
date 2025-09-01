<general_rules>
When writing code, always ensure it adheres to the following guidelines:
- **Linting**: Run `yarn lint` to check for linting errors. To automatically fix some issues, use `yarn lint:fix`. The ESLint configuration (`eslint.config.js`) enforces rules such as disallowing explicit `any` types, unused variables, and `console.log` statements.
- **Formatting**: Use `yarn format` to automatically format your code with Prettier. To check for formatting issues without fixing them, run `yarn format:check`.
- **Building**: Before committing, ensure your code builds correctly by running `yarn build` for the main project and `yarn build:examples` for examples.
- **Spelling**: The CI pipeline includes a spell check using `codespell` for `README.md` and the `apps/open-swe/src` directory. Be mindful of spelling in these areas.
</general_rules>

<repository_structure>
This repository is structured as follows:
- **`src/`**: This directory contains the core TypeScript source code for the Deep Agents library, including definitions for graphs, models, prompts, state management, sub-agents, tools, and types.
- **`examples/`**: This directory holds example implementations demonstrating how to use the Deep Agents library. Specifically, `examples/research/` contains a `langgraph.json` file and a `research-agent.ts` example.
- **`dist/`**: This directory is where the compiled JavaScript output of the main project is placed after a successful build.
- **`dist-examples/`**: This directory stores the compiled JavaScript output of the examples.
- **`.github/workflows/`**: This directory contains the GitHub Actions workflow definitions for continuous integration and deployment.
</repository_structure>

<dependencies_and_installation>
- **Package Manager**: This project uses `yarn` as its package manager (specifically `yarn@1.22.22`).
- **Installation**: To install the project dependencies, run `yarn install` in the root directory of the repository. It is recommended to enable `corepack` first by running `corepack enable` if you encounter issues with `yarn` commands.
</dependencies_and_installation>

<testing_instructions>
- **Running Tests**: While `package.json` indicates "Error: no test specified", the CI pipeline's `unit-tests.yml` workflow executes `yarn test`. This suggests that a test runner is expected to be configured, even if not explicitly defined in the `test` script in `package.json`.
- **CI Environment**: Unit tests are run on Ubuntu using Node.js versions 18.x and 20.x.
</testing_instructions>

<pull_request_formatting>
Pull request titles must adhere to the Conventional Commits specification. The following types are allowed:
- `feat`: A new feature
- `fix`: A bug fix
- `docs`: Documentation only changes
- `style`: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc.)
- `refactor`: A code change that neither fixes a bug nor adds a feature
- `perf`: A code change that improves performance
- `test`: Adding missing tests or correcting existing tests
- `build`: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
- `ci`: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)
- `chore`: Other changes that don't modify src or test files
- `revert`: Reverts a previous commit
- `release`: New release

Scopes are not required. If a PR title does not conform to these rules, it will fail the PR Title Lint check in CI. You can bypass this check by adding the `ignore-lint-pr-title` label to your pull request.
</pull_request_formatting>
