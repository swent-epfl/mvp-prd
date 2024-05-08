### Description

This repository contains a template for the PRD deliverable for the CS-311: The Software Enterprise (SwEnt) course.
You can find it in the `template` folder.

There is also a sample PRD under `samples/epfl-pocketcampus`; this is for the EPFL Pocketcampus app, which was developed during the very first intantiation of this course. You can use this sample PRD as a reference.

### Instructions

1. Fork this repo into your organization and clone it 
```
git clone git@github.com:<your-org-name>/prd.git
cd prd
```

2. Set up Github Actions
 
This repo includes a workflow called `build_pdf.yml` that uses GitHub Actions to automatically generate a PDF of your PRD.

After cloning this repo, customize the workflow for your own team by editing the workflow as follows:

- Line 40: Set the right team number, by replacing `26` with your team's number [here](.github/workflows/build_pdf.yml#40);
- Line 46: Same for the PDF artifact's name (replace `26` with your team's number) [here](.github/workflows/build_pdf.yml#46).
  
3. Write your PRD

To produce your own PRD, read the comments in italics, fill out the various sections, then remove the comments.
Use a collaborative workflow (branches, PRs, etc.) within your team to edit the PRD.
Pushing to `main` will generate the PDF. 

