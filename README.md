
# UI Generation LaTeX Template

This repository provides a LaTeX template designed to streamline the creation of user interface (UI) documentation. This template offers a structured framework for documenting UI components, facilitating consistency and efficiency in the documentation process.

## Features

- **Structured Layout**: Organizes UI elements into predefined sections, ensuring comprehensive coverage of all components.
- **Customization**: Allows easy modification to suit specific project requirements.
- **Compatibility**: Designed to work seamlessly with standard LaTeX editors and compilers.



1. **Compiling with PDFLaTeX**

Install LaTeX Distribution: Ensure you have a LaTeX distribution installed (e.g., TeX Live, MiKTeX).
Open the Template: Open the main.tex file in your LaTeX editor (e.g., TeXstudio).
Compile the Document: Select appropriate compiler and compile the document to generate the PDF report.
Or you can directly compile through command line.

```bash
latexmk -pdf -synctex=1 -interaction=nonstopmode -file-line-error -outdir=build main.tex

makeglossaries -d build main

latexmk -pdf -synctex=1 -interaction=nonstopmode -file-line-error -outdir=build main.tex
```
2.**Using Vs Code** 

i.Install LaTeX Workshop Extension: In VSCode, go to Extensions and install the "LaTeX Workshop" extension.

ii.Open VSCode settings.json and add the following configuration.

```Ctrl+Shift+P and Search "Preferences: Open User Settings (JSON)"```

```bash
{
"latex-workshop.latex.outDir": "%DIR%/build",
"latex-workshop.latex.recipes": [
    {
        "name": "latexmk (custom)",
        "tools": [
            "latexmk",
            "makeglossaries",
            "latexmk"
        ]
    },
],
"latex-workshop.latex.tools": [
    {
        "name": "latexmk",
        "command": "latexmk",
        "args": [
            "-synctex=1",
            "-interaction=nonstopmode",
            "-file-line-error",
            "-pdf",
            "-outdir=%OUTDIR%",
            "%DOC%"
        ],
        "env": {}
    },
    {
        "name": "makeglossaries",
        "command": "makeglossaries",
        "args": [
            "-d",
            "%OUTDIR%",
            "%DOCFILE%"
        ]
    },
],
}
```
iii. Open the Template: Open the main.tex file in VSCode with template directory as workspace.

iv. Compile the Document: Use the "LaTeX Workshop" extension to compile the document by clicking on the "TeX" icon in the toolbar and selecting "Build LaTeX project".


## Customization

Modify the `template.tex` file to include your specific UI components and details. The template is structured to accommodate various UI elements, allowing for flexible documentation.

## Contributing

Contributions are welcome. Please fork the repository, make your changes, and submit a pull request.

## License

This project is licensed under the MIT License.

For more information and updates, visit the [GitHub repository](https://github.com/SONICPO/UI-generation-latex-template).
