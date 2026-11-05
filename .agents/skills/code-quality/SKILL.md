---
name: code-quality
description: Review code quality when the user requests a code review or quality check of local files or changes. Report actionable findings; make fixes only when requested.
---

Review the requested files or diff. If no scope is given, review uncommitted
changes, including relevant untracked source files. If the working tree is clean,
review this small project's source; ask for a narrower scope for a large repository.

Read repository instructions and relevant surrounding code before drawing
conclusions. Identify configured checks from project files and documentation.

Focus on:
- Incorrect behavior, boundary cases, and error handling.
- Concrete security or data-handling defects in the reviewed code.
- Unnecessary complexity, duplication, and misleading names that impede maintenance.
- Missing tests for significant behavior or regressions.

Run relevant existing tests, linters, and type checks when available. Use check-only
modes during review. Do not install new tooling just to perform a review; report
missing tooling and distinguish checks not run from checks that passed.

Report findings in descending severity. For each finding, include the file and
line, the triggering condition, its practical impact, and a focused suggested fix.
Separate demonstrated defects from assumptions or questions. Avoid cosmetic
preferences unless they violate an established project convention.

Finish with checks performed and any remaining verification gaps. If there are
no actionable findings, say so without claiming the code is defect-free.

For a review-only request, leave files unchanged. When fixes are requested,
make focused changes and rerun the relevant checks. This skill does not itself
authorize commits, pushes, or posting reviews to GitHub.
