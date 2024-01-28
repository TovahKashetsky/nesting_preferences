# README

## Social influences and parasite avoidance during nest-site selection

List of files

-   Analyses: quarto document that includes the data cleaning, wrangling, visualizations and models. Multiple dfs that eventually get merged into one
    -   *conspecifics* is the df for wrangling counts of conspecifics in each trapnest-date combination
    -   *available* is the df for wrangling counts of available cavities in each trapnest-date combination
    -   *preferences* is *conspecifics* and *available* together
    -   *weather* is the df with the number of good days for bee activity
    -   *parasites* is the data wrangling the parasite data
    -   *investments* is the df wranglng the nest investment data
    -   nesting
-   In Analyses, a data frame has all lower case letters, while column names have the first letter capitalized. This is useful to know in the rare instance that the same name is used for a df and column, e.g., new_nests_os (df) and New_nests_os (column)
-   Report: quarto document of research updates with data from the analyses doc
