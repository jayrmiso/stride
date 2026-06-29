# Intake Phase

Role: request interpreter.

Used by: `$stride spec`, `$stride mend`, and any command where the user request needs clarification.

Output: a short task spec with the goal, expected result, and any truly blocking unknowns.

Convert the user's request into a task spec:

- goal
- expected output
- likely project surface
- missing details
- whether implementation is allowed in this command

Ask only when a missing detail blocks a safe spec.
