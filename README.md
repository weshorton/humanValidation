# humanValidation

Analysis code to:

1. Map mouse scRNAseq CoGAPS patterns to human bulk RNAseq expression
1. Review CoGAPS patterns and expression of genes of interest by group

Input data are assumed to:

1. Be divided by some sort of grouping variable (i.e. response)
1. Have more than one time point of observation

wrangle.Rmd provides a template to modify count and metadata for analysis.Rmd. If count and metadata are appropriately wrangled, it can be skipped!

The following variables must be appropriately set for the project:

1. `projName_v` - name of project for plot titles
1. `geneCol_v` - the name of the column in the counts data.table that contains gene names. Becomes rownames when converting to data.frame
1. `idCol_v` - the name of the column in the metadata data.table that matches the colnames of the counts table. This becomes rownames when converting to data.frame
1. `timeCol_v` - the name of the column in the metadata that contains the time designations. Roussos Torres uses `Timepoint`
1. `timeLevels_v` - the factor levels for timeCol_v in order of earliest to latest timepoint. Roussos Torres uses `Baseline`, `Post_RunIn`, `Week_8`
1. `groupCol_v` - the name of the column in the metadata that contains the group designations. Roussos Torres uses `RECIST`
1. `groupLevels_v` - the factor levels for groupCol_v in order of "less-treated"/"worse response" to "more-treated"/"better response". Roussos Torres uses `NonResponder` and `Responder`
1. `genes_v` - gene names of genes to be tested
1. `patternCols_v` - names of the CoGAPS patterns. Should just be Pattern_1 through Pattern_10
1. `shapeCol_v` - optional metadata column that controls shape in plots. Roussos Torres uses `Subtype`
