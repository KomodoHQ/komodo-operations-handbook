Before opening a new PR, check through this list to make sure you've not missed something.

Git

[ ] Have you definitely created a new branch for this PR using `git checkout -b <branch name>`?
[ ] `git add` all your changes to the branch.
[ ] `git pull` on the branch that you've based the branch on, and then merge that branch in to your branch.
[ ] Are there conflicts? Fix them now.

Feature/Bug

[ ] Check each of the AC in the story. Have they all been achieved?
[ ] Check the designs. Does the feature look like the designs? Have differences been noted?
[ ] Check the bug replication steps. Is the bug definitely fixed?
[ ] Check other likely problem areas. Have you introduced any regressions? Fix them.
[ ] Does the change affect the details in the README file? Update the README.

UI

[ ] The UI must be responsive. Are all components working asynchronously (eg no awaits)? 
[ ] Things should fail gracefully. Are components handling their loading, loaded, and failing states properly?
[ ] API calls can be slow or fail entirely. Are slow/failing API calls handled by components well?

Tests

[ ] Are there tests for any new features? Is there enough coverage? Check.
[ ] Are the existing tests up to date with the code changes? Update any tests that should change.
[ ] Do all the tests pass? Fix any tests that are failing.
[ ] Does the feature work properly in all target browsers (Chrome, Edgium, Firefox, Safari)?
[ ] Does the feature work with network conditioning? Try it with 'Slow 3G'.

Code cleaniless

[ ] There should be no ambiguous variable names. Make sure it's clear what things are, especially in destructuring.
[ ] Is there any dead (commented) or unreachable code? Delete it.
[ ] Are there any inline styles? Refactor them out to CSS.
[ ] Are there any 'magic numbers' (values in code)? Refactor them out to a constants file.
[ ] Are there any secrets in the constants? Refactor them out to env vars.
[ ] If you've copy'n'pasted any code, update any old names or comments so they're relevant to the new code.
[ ] Is the linter complaining about anything? Fix lint errors (and warnings if possible).
[ ] Is this an opportunity to refactor? Check the code and see if there's anything to improve. Improve all the things!

PR

[ ] Link to the story in the project management app
[ ] Link to any other related PRs (eg API changes)
[ ] Write a useful description. Try not to just duplicate the story; describe what the change is, not what the change is doing.
[ ] Select any reviewers who need to check the code. Ask for more reviewers if there's only one.
[ ] If relevant add screenshots, or even a video.
[ ] Is this story going to be straightforward to test? Add some additional notes for testers if it isn't.
