# LaTeX Project with Bazel

This project uses Bazel to build a LaTeX document. The main file is `main.tex`, which includes other `.tex` files from the `sections` directory.

## Building the Project

To build the project, you need to have Bazel installed. You can find installation instructions on the [Bazel website](https://bazel.build/install).

Once Bazel is installed, you can build the project by running the following command in the root of the repository:

```bash
bazel build //:main
```

This will create a `main.pdf` file in the `bazel-bin` directory. You can find the exact path to the file in the output of the build command.
