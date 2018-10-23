Want it hosted under a virtual directory
----------------------------------------
  Needed for viewing at https://kstreith.github.io/wyam/  
  ```
  wyam build -s LinkRoot="/wyam"
  ```

Azure DevOps Pipeline
---------------------
 - Easier to do visual build, then go to top and ask for Yaml view
 - Have to manually create packages.config, point at that
    - Specify in Advanced options to restore to packages/ subfolder
 - Script has to reference actual version of Wyam in it, default build to output folder.
 - Copy to artifacts directory from output folder.
 - Release 
    - Artifact has an alias, so it will end up in that subfolder
    - Have to add Publishes to GitHub pages as custom task from marketplace.
        - Have to exit and come back for it to be something you can add to release.
        - Artifacts auto pulled down under their alias.
        - Set a secret variable
        - Assumes gh-pages branch already exists in the repo.
