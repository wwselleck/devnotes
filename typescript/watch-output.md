# Typescript Watch Output

When running `tsc` in watch mode (`tsc -w`), the terminal output will get cleared on every source file change, with the new build output taking its place. There are instances where you don't want this behavior, most notably for me, when you're running your Typescript build in parallel with something else (maybe `nodemon`, or just another `tsc -w` instance when running a build across all yarn workspaces). To stop this behavior and keep all watch output on the screen without erasing, pass the `--preserveWatchOutput` flag.

`tsc -w --preserveWatchOutput`
