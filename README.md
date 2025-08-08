# fiboa Extensions

This repository provides you with all information about [existing extensions](#list-of-extensions) 
and also guides you how to [create your own extension](#adding-a-new-extension).

## List of extensions

| Title | Description |
| ----- | ----------- |
| [Ai Ecosystem Extension](https://github.com/fiboa/ai-ecosystem-extension) | Extension for properties needed for fiboa to interface with AI ecosystem |
| [Crop Extension](https://github.com/fiboa/crop-extension) | Identify crop codes and crop names from a custom codelist |
| [Flik Extension](https://github.com/fiboa/flik-extension) | The area identifier (FLIK) is a 16-digit key to clearly identify field blocks and other entities, used mostly in Germany. |
| [Hcat Extension](https://github.com/fiboa/hcat-extension) | This Fiboa extension enables validation against the Hierarchical Crop and Agriculture Taxonomy (HCAT), which harmonizes all declared crops across the European Union.  |
| [Inspire Extension](https://github.com/fiboa/inspire-extension) | Extension to define INSPIRE-compliant fields |
| [Tillage Extension](https://github.com/fiboa/tillage-extension) | Fiboa extension to describe tillage on a field |
| [Timestamps Extension](https://github.com/fiboa/timestamps-extension) | Timestamps for the whole lifetime of field boundaries. |

* **Last updated:** Aug 08 2025, 01:44 
* **Count:** 7

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
7. Set the visibility of the repository to 'Public'
   (i.e. anyone on the internet can see this repository, but you choose who can commit).
8. Finish this by clicking the 'Create repository' button.
9. You'll be redirected to your new repository for the extension.
10. Add the `extension` topic to the repository:
    1. In the 'About' section of the repository, click the gear icon.
    2. In the field for "Topics", add `extension`.
11. It should be enabled by default, but if CI is not running make sure that it is enabled:
    1. In the repository 'Settings' go to 'Pages'.
    2. Ensure that the 'Source' is set to 'Deploy from a branch'.
    3. Ensure that the 'Branch' is set to 'gh-pages' and '/ (root)'.
    4. If you had to change anything, click 'Save'.
    5. In the repository 'Settings' go to 'Actions' and then "General".
    6. Ensure that the 'Workflow permissions' is set to 'Read and write permissions'.
    7. If you had to change anything, click 'Save'.
12. Clone the newly created repository to your machine.
13. Install fiboa CLI using `pip install fiboa-cli`

### Write your extension

* Use [fiboa CLI to replace the template placeholders](https://github.com/fiboa/cli?tab=readme-ov-file#update-an-extension-template-with-new-names)
* `README.md`:
    * Update the owner to be your GitHub handle.
    * Update the properties, select where they can be used, add documentation, etc. in the README.md
* `schema/schema.yaml`:
    * Update the Schema accordingly to your changes in the README.md
      The Schema language is similar to JSON Schema, but has some specifics, especially the data types.
      See [fiboa Schema](https://github.com/fiboa/schema) for details.
* `examples/` folder:
    * Add at least one GeoJSON example
    * Add a GeoParquet example. You can generate it from GeoJSON with the [fiboa CLI](https://github.com/fiboa/cli).
* Run the tests
* `CHANGELOG.md`: Update the Changelog
* Let people discuss your extension, e.g. via chat, email, etc.
* Eventually, release the extension via GitHub Releases.
  This will automatically publish the schemas.
* Add your extension to the list above if needed.
  All extensions hosted in the fiboa organization will be added automatically each night.
  You can add external/community extensions to the list above by editing the [config file](https://github.com/fiboa/extensions/edit/main/config.yaml) and creating a PR from it.