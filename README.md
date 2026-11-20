# CBP-21097 parallel-sibling reusable-workflow repro

Minimal standalone reproduction of the bug in CBP-21097 / PR #7940:
three parallel reusable-workflow branches fan out from one manual-trigger
job; the middle branch fails inside its nested reusable workflow; the two
non-failing sibling branches should resolve to SKIPPED (grey) once the run
is terminal, but instead stay stuck PENDING_APPROVAL / PENDING (yellow).

Modeled directly on the real QA repro (mluzcabrera/testreusableworkflows3
override-tests.yaml + mluzcabrera/reusableworkflowsrepo reusable3.yaml,
both public), reduced to a single self-contained repo.

trigger
