# Publishing a new AVOTREX version

Development happens in the private repo (`avotrex_dev`). This public repo only receives finished versions. Both repos sit side by side in `Documents/GitHub_repos/`.

## Checklist

1. **In `avotrex_dev`**: run the pipeline (`01_update_data.R` → `04_merge_data.R` and the imputation), and save the final table as `releases/db_avotrex_vX_Y.csv`. Commit and tag it there (e.g. `git tag v1.1.0`).

2. **Copy the file here** as a plain comma-separated CSV without row names:

   ```r
   d <- read.table("../avotrex_dev/releases/db_avotrex_v1_1.csv", header = TRUE)
   dir.create("data/v1.1", recursive = TRUE)
   write.csv(d, "data/v1.1/avotrex_v1.1.csv", row.names = FALSE, na = "")
   ```

   Never edit an older `data/vX.Y/` folder. Those files must stay exactly as released.

3. **Update the text**
   - `CHANGELOG.md`: add a new entry at the top (the template is in the file)
   - `_config.yml`: `latest_version` and `latest_data`
   - `README.md`: add a row to the data table
   - `CITATION.cff`: `version`
   - `variables.md`: only if variables were added or renamed

4. **Commit and push**

   ```bash
   git add .
   git commit -m "Release v1.1.0"
   git push
   ```

5. **Create the GitHub release**: on GitHub go to *Releases → Draft a new release*, create tag `v1.1.0`, paste the changelog entry and publish. If the repo is linked to Zenodo, this automatically archives the release and mints a DOI.

6. **After the first Zenodo release**: copy the *concept DOI* (it always points to the latest version) into `zenodo_doi` in `_config.yml` and into the README.
