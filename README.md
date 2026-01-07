# LaTeX Project with Bazel

This project uses Bazel to build a LaTeX document. The main file is `main.tex`, which includes other `.tex` files from the `sections` directory.

## Building the Project

To build the project, you need to have Bazel installed. You can find installation instructions on the [Bazel website](https://bazel.build/install).

Once Bazel is installed, you can build the project by running the following command in the root of the repository:

```bash
bazel build //:main
```

This will create a `main.pdf` file in the `bazel-bin` directory. You can find the exact path to the file in the output of the build command.

## Adding New LaTeX Packages

To add a new LaTeX package to the project, you need to do two things:

1.  **Add the package to the `BUILD.bazel` file.** In the `latex_document` rule, add a new entry to the `srcs` list for the package you want to add. The package name should be in the format `@bazel_latex//packages:<package_name>`. For example, to add the `amsmath` package, you would add the following line to the `srcs` list:

    ```bazel
    "@bazel_latex//packages:amsmath",
    ```

2.  **Add the `\usepackage` command to your main `.tex` file.** In `main.tex`, add a `\usepackage{<package_name>}` command to the preamble of the document. For example, to use the `amsmath` package, you would add the following line:

    ```latex
    \usepackage{amsmath}
    ```

### Included Packages

This project already includes the following packages by default:

*   `graphicx`: For including images.
*   `amsmath`, `amssymb`, `amsthm`: For advanced math typesetting.
*   `algorithm2e`: For writing algorithms and pseudocode.
*   `listings`, `xcolor`: For code listings with syntax highlighting.
*   `hyperref`: For creating hyperlinks in the document.
*   `cleveref`: For intelligent cross-referencing.
