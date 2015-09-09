Run using: tsc --module commonjs app.ts

This is intended to show that without isolating referenced globals even for proper external modules
you will run into issues. This project has the following structure:

- app
  - mylib
    - es6-promise
  - myotherlib
    - es6-promise

Note that mylib, myotherlib, and es6-promise are all proper external modules. es6-promise introduces
a global by referencing a sibling definition file. That global conflicts and results in a "Duplicate
identifier" error.