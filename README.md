# fiboa Extensions

This repository provides you with all information about [existing extensions](#list-of-extensions) 
and also guides you how to [create your own extension](#adding-a-new-extension).

## List of extensions

| Title | Description |
| ----- | ----------- |
| [Ai Ecosystem](https://github.com/fiboa/ai-ecosystem) | Extension for properties needed for fiboa to interface with AI ecosystem |
| [Inspire Extension](https://github.com/fiboa/inspire-extension) | Extension to define INSPIRE-compliant fields |
| [Tillage Extension](https://github.com/fiboa/tillage-extension) | Fiboa extension to describe tillage on a field |

* **Last updated:** Mar 24 2024, 01:01 
* **Count:** 3

## Adding a new extension

Everyone is welcome to create and propose new extensions.
We created a template for it to give you a starting point, which includes
CI actions, templates for Markdown, Schema, and examples.

Here's a guideline how to use the extension template:

### Create the repository

1. Go to the [template repository](https://github.com/fiboa/extension-template)
2. Click the green 'Use this template' button and choose 'Create a new repository'
3. Don't change the 'Repository template'
4. Tick the checkbox 'Include all branches'
5. Pick the right place ('Owner' and 'Repository name') to create it.
   The name should have a `-extension` suffix.
   You can request to become a member of the fiboa organization or
   put the next repository under your personal account or any other organization.
6. Add a concise and clear description of the extension, it will be used as a description in the list above!
7. Finish this by clicking the 'Create repository' button.
8. You'll be redirected to your new repository for the extension.
9. Add the 'extension' topic to the repository:
   1. In the 'About' section of the repository, click the gear icon.
   2. In the field for "Topics", add 'extension'.
10. It should be enabled by default, but make sure that the CI is enabled:
   1. In the repository 'Settings' go to 'Pages'.
   2. Ensure that the 'Source' is set to 'Deploy from a branch'.
   3. Ensure that the 'Branch' is set to 'gh-pages' and '/ (root)'.
   4. If you had to change anything, click 'Save'.

**Write your extension:**

* `README.md`:
  * Update the title, identifier, property name prefix (must be unique), and owner (your GitHub handle).
  Don't mess around with the formatting or structure as this will be used to generate the table above!
  * Update the properties, select where they can be used, add documentation, etc. in the README.md
* `schema/schema.yaml`:
  * Update the Schema accordingly to your changes in the README.md
    The Schema language is similar to JSON Schema, but has some specifics, especially the data types.
    See [fiboa Schema / Validation](https://github.com/fiboa/specification/blob/main/core/validation.md) for details.
* `examples/` folder:
  * Add at least one GeoJSON example
  * Add a GeoParquet example. You can generate it from GeoJSON with the [fiboa CLI](https://github.com/fiboa/cli).
* Go through the files and update everything that is still named 'template' (or 'extension-template').
  The easiest way is to let an IDE/Editor search through all the files for 'template'.
* Run the tests
* `CHANGELOG.md`: Update the Changelog
* Let people discuss your extension, e.g. via chat, email, etc.
* Eventually, release the extension via GitHub Releases.
  This will automatically publish the schemas.
* Add your extension to the list above if needed.
  All extensions hosted in the fiboa organization will be added automatically each night.
  You can add external/community extensions to the list above by editing the [config file](https://github.com/fiboa/extensions/edit/main/config.yaml) and creating a PR from it.