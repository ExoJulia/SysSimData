# SysSimData
This repository contains (mostly) binary data to be used by [SysSim](https://github.com/ExoJulia/ExoplanetsSysSim.jl).

It includes two directories/submodules:
- [inputs](https://github.com/ExoJulia/SysSimDataInputs):  Input text files used to generate files in data directory
- [scripts](https://github.com/ExoJulia/SysSimDataInputScripts):  Scripts to download large files separately and to generate binary files for use by SysSim.

## Files
- dr25_koi_mcmc_quant.csv: Quantiles for transit depths and durations computed from MCMC posterior samples
- DR25topwinfuncs.jld2: Window functions that cover nearly all the Kepler planet search targets
- GKSPCPapTable{1,2}_2020-04-16.txt: The Gaia-Kepler Stellar Properties Catalog (GKSPC) introduced by Berger et al. (2020)
- KeplerMAST_TargetProperties.jld2: Binary version of inputs/KeplerMAST_TargetProperties.csv
- q1q17_dr25_gaia_fgk.jld2: Stellar properties catalog used by Hsu et al. (2019)
- q1q17_dr25_gaia_fgk_relaxcut.jld2: A more comprehensive stellar properties catalog that removes two cuts imposed by Hsu et al. (2019)
- q1q17_dr25_gaia_berger_fgk_HFR2020b.jld2: Stellar properties catalog that incorporates the properties from GKSPC, originally used by He et al. (2020)
- q1q17_dr25_gaia_berger_fgk_HFR2020b_regen.jld2: A regenerated version of q1q17_dr25_gaia_berger_fgk_HFR2020b.jld2 (NOTE: the regen version includes a larger number of targets. TODO: figure out why there is a difference).
- q1_q17_dr25_koi.jld2: Binary version of q1_q17_dr25_koi.csv, likely incorporating updated values for stellar properties and transit depth and duration.

## Files not directly in the repository
- dr25fgk_relaxcut_osds.jld2: One-sigma depth functions for healthy subset of Kepler planet search targets.  (To be downloaded by scripts/make.jl)
- allosds.jld2: One-sigma depth functions for all Kepler planet search targets.  (Optional file that can be downloaded by 'julia scripts/make.jl --download-stellar-catalog --download-large-files')
- KeplerMAST_TargetProperties.csv: Which stars were observed which quarters as part of Kepler planet search (symlink to inputs/KeplerMAST_TargetProperties.csv)
- q1_q17_dr25_koi.csv: Kepler planet candidate properties as tabulated in DR25 catalog (symlink to inputs/q1_q17_dr25_koi.csv)
- gaiadr2_keplerdr25_crossref.csv: (File derived in some way from https://gaia-kepler.fun/. Required to run [scripts/combine_dr25_gaia.jl](https://github.com/hematthi/SysSimDataInputScripts/blob/master/combine_dr25_gaia.jl) if want to generate new stellar properties catalogs.)

