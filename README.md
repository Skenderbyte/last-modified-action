Automatic Last Modified Metadata 

GitHub Actions documentation for Markdown files 

This GitHub Action automatically updates the latest modification information in Markdown (.md) files within the repository. 

Purpose 

The Update Last Modified workflow automatically records the date, time, and display name of the person who last modified a Markdown document. 

Workflow 

File location 

.github/workflows/update-last-modified.yml 

Workflow name 

Update Last Modified 

The workflow is triggered automatically when a Markdown file is modified and pushed to the repository. Only modified Markdown files containing the required markers are updated. 

Required Configuration in Markdown Files 

Each Markdown file must contain the following block under the Last Modified section: 

#### Last Modified 
 
<!-- LAST_MODIFIED_START --> 
Not yet updated 
<!-- LAST_MODIFIED_END --> 

 

Important Requirements 

The LAST_MODIFIED_START marker is required. 

The LAST_MODIFIED_END marker is required. 

Everything between the markers is automatically replaced by the workflow. 

The marker block must be present for automatic updates to work. 

The heading #### Last Modified is recommended for consistency. 

How It Works 

A user modifies a Markdown file. 

The change is committed and pushed to GitHub. 

The Update Last Modified workflow is triggered. 

The workflow identifies the modified Markdown file and updates the date, time, and display name. 

The workflow automatically commits the updated metadata back to the repository. 

Example Result 

#### Last Modified 
 
<!-- LAST_MODIFIED_START --> 
23-09-2026 15:15:27 by Egzon Zeneli 
<!-- LAST_MODIFIED_END --> 

 

Notes 

Markdown files without the required markers are not changed. The workflow-generated commit is excluded from triggering the workflow again, preventing an infinite update loop. 
