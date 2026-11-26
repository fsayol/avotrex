# AVOTREX: a global dataset of extinct birds and their traits

This is the public home of the AVOTREX database. Website: **https://OWNER.github.io/avotrex/** (update once the repo exists).

AVOTREX gives species traits for all birds known to have gone extinct in the last 130,000 years: taxonomy, geography, extinction status, island endemicity, flight ability, body mass, and external and skeletal morphology.

## Data

| Version | File | Notes |
|---|---|---|
| 1.0 | [`data/v1.0/`](data/v1.0/) | Identical to the Dryad deposit (doi:10.5061/dryad.zgmsbcckk), without the AVONET file |

Variable descriptions: [`variables.md`](variables.md). What changed between versions: [`CHANGELOG.md`](CHANGELOG.md).

## Citation

Sayol, F., Wayman, J. P., Dufour, P., Martin, T. E., Hume, J. P., Wagner Jørgensen, M., Martínez-Rubio, N., Sanglas, A., Soares, F. C., Cooke, R., Mendenhall, C. D., Margolis, J. R., Illera, J. C., Lemoine, R., Benavides, E., Lapiedra, O., Triantis, K. A., Pigot, A. L., Tobias, J. A., Faurby, S. & Matthews, T. J. (2024). AVOTREX: A global dataset of extinct birds and their traits. *Global Ecology and Biogeography*, 33(12), e13927. https://doi.org/10.1111/geb.13927

Each release from v1.1 onward is archived on Zenodo with its own DOI.

## Related resources

- Original v1 data on Dryad: https://doi.org/10.5061/dryad.zgmsbcckk
- `avotrex` R package (phylogenies with extinct species): https://doi.org/10.32614/CRAN.package.avotrex

## Report an error

Please [open an issue](../../issues/new/choose) or email ferran.sayol@uvic.cat.

## Licence

Data: [CC0 1.0](https://creativecommons.org/publicdomain/zero/1.0/). See [`LICENSE`](LICENSE).

## Repository structure

```
data/vX.Y/        one folder per released version (never edited after release)
index.md          website home page
species.md        searchable species table
variables.md      data dictionary
CHANGELOG.md      version history (also shown on the website)
RELEASING.md      checklist for publishing a new version
```

Development happens in a separate private repository. Only finished versions are published here.
