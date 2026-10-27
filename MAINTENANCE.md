# Maintenance of this learning fork

This fork retains the upstream README, authors and MIT license. See FORK_NOTES.md for provenance. The maintenance change updates vulnerable dependencies and Node-based test tooling; it does not claim authorship of the upstream service.

Use Node.js 24 and npm:

```sh
npm ci
npm test -- --runInBand
npm run format:check
npm audit
```

The default test suite mocks provider requests and excludes tests/e2e/. Live service/e2e checks need their own authorized service configuration and were not run. `.env.example` is a server configuration reference and contains no token. Never expose a private GitHub token in client code or commit a real value.

The unused upgrade dependency is removed. The maintenance scripts use the current Octokit REST namespace; no script that closes issues/PRs, posts comments, or changes labels is executed during validation. Coverage still runs with the test suite; the obsolete external coverage-upload action was removed from the test workflow.
