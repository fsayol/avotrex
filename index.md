---
layout: default
title: AVOTREX
---

**AVOTREX** is an open-access database of species traits for all birds known to have gone extinct in the last 130,000 years. Version {{ site.latest_version }} covers **610 extinct species**. For each one it gives taxonomy, geographic location, period of extinction, island endemicity, flight ability, body mass, and external and skeletal morphology, with missing measurements imputed. The companion R package `avotrex` grafts all extinct species onto a global phylogeny of extant birds (BirdTree).

AVOTREX is a living database. New extinct species are added and existing records corrected as new evidence becomes available. Each change is listed in the [changelog]({{ '/changelog/' | relative_url }}).

## Read the article

Sayol, F., Wayman, J. P., Dufour, P., Martin, T. E., Hume, J. P., Wagner Jørgensen, M., Martínez-Rubio, N., Sanglas, A., Soares, F. C., Cooke, R., Mendenhall, C. D., Margolis, J. R., Illera, J. C., Lemoine, R., Benavides, E., Lapiedra, O., Triantis, K. A., Pigot, A. L., Tobias, J. A., Faurby, S. & Matthews, T. J. (2024). AVOTREX: A global dataset of extinct birds and their traits. *Global Ecology and Biogeography*, 33(12), e13927. [{{ site.paper_doi }}]({{ site.paper_doi }})

## Download the data

- **Latest version ({{ site.latest_version }}):** all files are in [`{{ site.latest_dir }}`](https://github.com/{{ site.github.repository_nwo }}/tree/main/{{ site.latest_dir }}). The main tables are [taxonomy]({{ site.latest_dir | append: '/Avotrex_taxonomy_v1.csv' | relative_url }}) and [traits]({{ site.latest_data | relative_url }}); the folder also has the raw measurements (`RawData_D1`–`D8`) and the metadata. Each version can also be downloaded as a zip from the [Releases page](https://github.com/{{ site.github.repository_nwo }}/releases).
- **Variable descriptions:** [data dictionary]({{ '/variables/' | relative_url }})
- **Original v1.0 deposit:** [Dryad]({{ site.dryad_doi }}). The v1.0 files here are identical copies. AVONET, which the Dryad deposit also includes, is available from [Tobias et al. 2022](https://doi.org/10.1111/ele.13898).
- **Phylogenies with extinct species:** the [`avotrex` R package]({{ site.rpackage_url }}) on CRAN

```r
# Read the latest traits table directly in R
base <- "https://raw.githubusercontent.com/{{ site.github.repository_nwo }}/main/"
traits <- read.csv(paste0(base, "{{ site.latest_data }}"))
```

## Explore the data

[Browse and search all species]({{ '/species/' | relative_url }}) by name, family, archipelago or extinction status.

## Cite the data

If you use AVOTREX, please cite the article above. If you use a version released after v1.0, please also cite the archived version you used{% if site.zenodo_doi != "" %} ([Zenodo]({{ site.zenodo_doi }})){% endif %}, so that your results can be reproduced. AVOTREX includes data compiled from many original sources. Where those sources matter for your work, please cite them too.

## Report errors or missing species

Found an error, or know of an extinct species or a measurement that is missing? Please tell us:

- [Open an issue on GitHub](https://github.com/{{ site.github.repository_nwo }}/issues/new/choose) (needs a GitHub account){% if site.error_form_url != "" %}
- [Fill in the online form]({{ site.error_form_url }}) (no account needed){% endif %}
- Email [{{ site.contact_email }}](mailto:{{ site.contact_email }})

Please include a reference or specimen information wherever possible.

## Changes

See the [changelog]({{ '/changelog/' | relative_url }}) for what changed in each version.

---

<small>AVOTREX data are released under the [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/) public-domain dedication. Illustrations and silhouettes keep their own licences.</small>
