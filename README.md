This Github Action converts a `writeup.pdf` found in the root directory into images on an orphan branch, then adds links to them into the README. This way anytime a full writeup was done in Latex/Word/etc, you have an easy way to add it to your code to be used in a portfolio.

A better way would have been to use pandocs.. but this requires handling math, images, etc, and this seemed a more appropriate level of work for what I needed it for.

## Using

To use, simply add the following files to your repo
* `.github/workflows/writeup_readme.yml` - The actual action
* `.README.md` - Is appended above images from writeup
* `writeup.pdf` - Actual writeup
* `README.md` - Need something there to begin with, whether it's empty or full, it WILL be replaced.

The action will be triggered on changes to `.README.md` or `writeup.pdf` in the master branch. Below is an example:

## Outline

Basically it does things in this order
* Convert `writeup.pdf` to images
* Force push them to an orphan branch
* Recreate `README.md`
* If `README.md` has changed, push it to master branch.

![image](https://github.com/contagon/PDFWriteupReadme/blob/readme_images/output-000.jpg?raw=true)
![image](https://github.com/contagon/PDFWriteupReadme/blob/readme_images/output-001.jpg?raw=true)
