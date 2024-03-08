# Diveristy and composition analysis of fungal communities of American beech bark

## Data explanations
- `asv_tab.csv` Full ASV table including all sample with >= 1000 total sequences. Each sample represents a single tree. Sample IDs are row names
- `asv_taxonomy.csv` Taxonomy of ASVs. ASV IDs are row names
- `taxonomy_and_trophic_modes.csv` ASV taxonomy joined with primary and secondary trophic modes assigned by Genus. See [here](https://github.com/ewmorr/FungalTraits_Polme)
- `metadata.csv` **Sample metadata.**
    - tree level metrics of BBD severity and tree condition:
        - dbh
        - NeoFruiting
        - RaisedCanker
        - TarrySpots
        - Wax
        - Xylococcus
        - TreeCond
        - dbh_quartile
    - site level metrics of each of the above variables were calculated by walking a transect at each site, assessing each variable for each beech tree on the transect, and taking the mean of each variable.
        - site level means use the names as above with `Site_mean.` prepended
    - climate variables -- 30 year normals, site level
        - ppt
        - MAT
        - tmin
        - tmax
    - climate variables -- growing and nongrowing season averages for the ten years prior to sampling
        - GDD (HDD4), 
        - number of freeze thaw events (freezeThaw) 
        - precipitation (ppt)
        - growing season length (length)
            - means and standard deviations are calciualted for each variable (mean or sd follow variable name)
            - growing or nongrowing season is indicated after mean or sd
    
- `rarefactions.rds` List of subsampled ASV tables. Subsampled to minimum sequencing depth over 1000 iterations. See [run_and_save_rarefaction.R](./R_scripts/run_and_save_rarefaction.R)
- 'asv_tab.rarefaction_avg.csv' The average counts per ASV per sample were calculated across the
- Distance metrics and diversity metrics were calculated across subsamples and average. See [avg_dist_and_div.R](./R_scripts/avg_dist_and_div.R)
    - Distance metrics reside in `data/avg_dist`. R data structure dist objects 
    - Table of average diversity in `data/avg_div`
