# Code review

## Purpose

To ensure the team's quality standards are upheld, facilitate knowledge sharing across the team, improve documentation, detect bugs and logic errors, identify security vulnerabilities, and provide mentoring opportunities for junior and senior developers alike [examples](examples.md).

## Types

### Automated

Automated reviews are generally performed within the CI/CD pipeline using linters, static analysis tools, and test runners. They catch formatting errors, enforce code style, verify test coverage thresholds, and detect regressions introduced by changes.

### Manual

Manual reviews are performed by other developers on the team. They catch logic errors, architectural issues, design flaws, and quality problems that automated tools cannot detect. Manual reviews also serve as a crucial knowledge-sharing and mentoring opportunity.

## Before Review

- Ensure the code compiles and works as intended
- Self-review your own changes before requesting others
- Keep merge requests (MRs) small and focused
- Write a clear, descriptive MR title and description
- Ensure tests are written and passing
- Verify CI pipelines pass
- Flag areas of uncertainty or where you'd like specific feedback

## Look For

Reviewers should be looking for:

- Readability and maintainability of the code
- Security vulnerabilities and best practices
- Adherence to code quality standards and team conventions
- Correctness of logic and implementation
- Performance implications of the changes
- Code smells and anti-patterns
- Adequate test coverage for the changes

## Feedback

Reviews should be:

- Specific - reference exact lines or code blocks
- Reasoned - explain the "why" behind the suggestion
- Constructive - offer alternatives, not just criticism
- Kind - respectful and professional in tone
- Balanced - acknowledge what was done well, not just what needs fixing
