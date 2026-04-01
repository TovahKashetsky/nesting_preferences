# **README**

## **Social influences and parasite avoidance during nest-site selection**

### **Files**

-   **01_Wrangling.qmd**: Quarto document created for cleaning, organizing, and inspecting the data.

-   **02_Analyses.qmd**: Quarto document used for running the statistical analyses.

-   **03_Figures.qmd**: Quarto document for creating figures.

-   **04_Tables.qmd**: Quarto document used to create supplementary material of model summaries.

-   **custom-reference-doc.docx**: Word doc used as template for 04_Tables formatting.

### **Raw data**

-   **Aggregate_nesting_data_2023.csv** and **Aggregate_nesting_data_2024.csv**: Raw data files from our field data for 2023 and 2024, respectively.

    -   Site: Location of the nest-boxes, Conroy Pit (CP), Bruce Pit (BP), or Ottawa–Carleton Trailway (NN).

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite. Each site contained 6 subsites at a time.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box. Each contain 18 cavities and thus 18 nests at once.

    -   Treatment: Nest-box classification as the Low, Mid, or High-occupancy treatment.

    -   Cavity_size: Classification of the cavity diameter size, small, medium or large.

    -   Cavity_number: Cavity identification number within the nest-box, 1-18. 

    -   Straw_ID: Identification letter of each nest, as nests would be removed perpetually throughout the experiment and should share the same Cavity_number, starting at a.

    -   Straw_length_mm: Length of the straw in mm. Empty and pseudo nests contain NA, as well as nests that did not contain cells (inner wall only), were predated upon in the field, or were in too poor of shape from mold on rare occasions.

    -   Filled_length_mm: Length of cell contents that fill the straw in mm. Empty and pseudo nests contain NA, as well as nests that did not contain cells (inner wall only), were predated upon in the field, or were in too poor of shape from mold on rare occasions.

    -   Occupant: Genus of the mother, and in the case for pseudo nests, the genus of the imitation nest. Empty nests contain NA. Occupants other than Osmia and Megachile were filtered out in the wrangling.

    -   06-May – 09-Aug (Aggregate_nesting_data_2023.csv) and 05-Jun – 13-Aug (Aggregate_nesting_data_2024.csv): Dates of our field visits to log bee activity and establish a nest status. Non_existent means the nest did not exist at that time (e.g., a nest is built then removed and replaced with an empty straw, so the first nest will become non-existent once it is removed). No-visit means that field site was not visited that day. The remaining statuses are bee activity (inner walls, cells with provisions and eggs, end caps), pseudo nests, or empty.

    -   Notes: Noteworthy observations taken while collecting data.

-   **Emergence_data_2023.csv** and **Emergence_data_2024.csv**: Raw data files for the nesting data from occupant emergence for 2023 and 2024, respectively.

    -   Site: Location of the nest-boxes, Conroy Pit (CP), Bruce Pit (BP), or Ottawa–Carleton Trailway (NN).

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite. Each site contained 6 subsites at a time.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box. Each contain 18 cavities and thus 18 nests at once.

    -   Treatment: Nest-box classification as the Low, Mid, or High-occupancy treatment.

    -   Cavity_size: Classification of the cavity diameter size, small, medium or large.

    -   Cavity_number: Cavity identification number within the nest-box, 1-18. 

    -   Straw_ID: Identification letter of each nest, as nests would be removed perpetually throughout the experiment and should share the same Cavity_number, starting at a.

    -   Nest_ID: Unique code to identify each nest created from the nest-box number, cavity number, and straw ID. Can have nesting activity (inner walls, cells with provisions and eggs, end caps), be a pseudo nest (imitation nest that appears completed), or is empty. Nests in the emergence data have nesting activity.

    -   Cell_number (only in Emergence_data_2023.csv): Number to indicate the order of the cells within the nest, with number 1 corresponding to the first cell built and highest number to the last cell built. NA indicates unknown cell numbers.

    -   Cell_position: Whether the cell was the last cell built before the mother sealed the nest, or it was not the last cell. NA indicates cells that has a cell number and will be assigned a position through wrangling. 

    -   Date: Date the cell was constructed. NA indicates unknown dates. 

    -   Cell_occupant: Occupant inside the cell that emerged or failed to emerge. Identified as the genus for bees, 'parasite' for all parasites, larva (unable to be distinguished as bee or parasitic wasp larva), or if the cell was not developed, it was identified as empty, a pollen mass, or mold.

    -   Species_or_subtype: Species of Osmia or Megachile occupants, subtype of parasites, and NA for the non-target bee genera or undeveloped cells.

    -   Collection: If the occupant from that nest is kept as a voucher for the collection, and 'this cell' indicates the specimen was specific to that cell. 

    -   Sex: Sex of the vouchers and emerged occupants. NA for occupants not collected or their sex was not identified.

    -   Comments: Noteworthy comments about the emergence data.

-   **Empty_data_2023.csv**: Empty data with identical columns to Aggregate_nesting_data_2023.csv, used in the wrangling file. Raw data for 2024 contained the empty rows directly in the document.

-   **Weather_2023_data.csv** and **Weather_2024_data.csv**: Weather data used to calculate the number of days with weather appropriate for bee activity between our field visits.

    -   Date: Date of every day during the 2023 field season.

    -   Max_temp (only in Weather_2023_data.csv): Maximum temperature during the day.

    -   Rain (only in Weather_2023_data.csv): Amount of rain in mm or 'trace' if minimal precipitation but not zero.

    -   Sun_at_noon (only in Weather_2023_data.csv): Cloud cover at noon.

    -   Scale_to_3 (only in Weather_2023_data.csv): How many of the conditions (temperature, rain, and cloud cover) met the threshold for appropriate weather for bee activity.

    -   Visit_NN, Visit_BP_Os, Visit_BP_Meg, Visit_CP, Visit_BP: If we visited the site that day. NA for when the site did not exist (only NAs in Weather_2023_data.csv). 

    -   Weather: If the weather was good or bad for bee activity.

    -   Good_days_NN, Good_days_BP_Os, Good_days_BP_Meg, Good_days_CP, Good_days_BP: The number of days with good weather appropriate for bee activity between our field visits. NA for when we did not visit the field, or when the site did not exist.

### **Cleaned data**

-   **trapnesting_cleaned_osmia.csv** and **trapnesting_cleaned_megachile.csv**: Cleaned and organized dataframes containing nest-level data for Osmia and Megachile bees, respectively. Each row is a unique trapnest and date combination. Below, the "X" in the column names is a stand-in for Osmia and Megachile, respective to their dataframes. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes. Used for predictions 1 and 3a.

    -   Site: Location of the nest-boxes.

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box.

    -   Treatment: Nest-box classification for the occupancy treatment.

    -   Date: Date of nesting activity. 

    -   Day_of_year: Day of the year, better fit for the GLMMs than Date.

    -   Year: Year of data collection.

    -   Good_days: The number of days with good weather appropriate for bee activity between our field visits.

    -   Available_cavities_prior: Number of cavities available for bees to nest in prior to the new nests being built for this field visit. 

    -   New_nests_X: Number of new nests for that genus in each nest-box and date combination.

    -   X_ps_prior: Number of existing bee nests in each nest-box and date combination, including pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_no_ps_prior: Number of existing bee nests in each nest-box and date combination, excluding pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_active_mothers: Number of unsealed bee nests that are not abandoned, meaning the mother is actively building the nest, in each nest-box and date combination.

    -   DP_X_prior: Number of bee nests that are unsealed and parasitized, considered as nests with detectable parasites, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, excluding pseudo nests as congeneric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_ps_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, including pseudo nests as congeenric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

<!-- -->

-   **nesting_cells_cleaned_osmia.csv** and **nesting_cells_cleaned_megachile.csv**: Cleaned and organized dataframes containing cell-level data for Osmia and Megachile bees, respectively. Each row is a unique cell from within a Nest_ID. Below, the "X" in the column names is a stand-in for Osmia and Megachile, respective to their dataframes. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes. Used for prediction 2 and 3c.

    -   Site: Location of the nest-boxes.

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box.

    -   Treatment: Nest-box classification for the occupancy treatment.

    -   Nest_ID: Unique code to identify each nest created from the nest-box number, cavity number, and straw ID.

    -   Cell_ID: Unique code to identify each cell created from Nest_ID and a cell number, which may not correspond to the placement of the cell in the nest.

    -   Cell_position_bi: Binary for whether the cell was the last cell built before the mother sealed the nest (1) or it was not the last cell (0). NA indicates unknown cell positions. 

    -   Date: Date of nesting activity.  

    -   Cell_occupant: Occupant inside the cell that emerged or failed to emerge. Identified as the genus for bees, 'parasite' for all parasites, larva (unable to be distinguished as bee or parasitic wasp larva), or if the cell was not developed, it was identified as empty, a pollen mass, or mold.

    -   Species_or_subtype: Species of Osmia or Megachile occupants, subtype of parasites, and NA for the non-target bee genera or undeveloped cells.

    -   Cell_parasitized: Whether the cell is parasitized (1) or not (0).

    -   Nest_parasitized: Whether the nest contains a parasite.

    -   Occupant: Genus of the mother, and in the case for pseudo nests, the genus of the imitation nest.

    -   New_nests_X: Number of new nests for that genus in each nest-box and date combination.

    -   X_ps_prior: Number of existing bee nests in each nest-box and date combination, including pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_no_ps_prior: Number of existing bee nests in each nest-box and date combination, excluding pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_active_mothers: Number of unsealed bee nests that are not abandoned, meaning the mother is actively building the nest, in each nest-box and date combination.

    -   Day_of_year: Day of the year, better fit for the GLMMs than Date.

    -   Year: Year of data collection.

<!-- -->

-   **investment_cleaned_osmia.csv** and **investment_cleaned_megachile.csv**: Cleaned and organized dataframes containing nest-level data for Osmia and Megachile bees, respectively. Each row is unique nest that has a measured filled_length and straw_length. Below, the "X" in the column names is a stand-in for Osmia and Megachile, respective to their dataframes. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes. Used in prediction 3b.

    -   Site: Location of the nest-boxes, Conroy Pit (CP), Bruce Pit (BP), or Ottawa–Carleton Trailway (NN).

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box.

    -   Treatment: Nest-box classification for the occupancy treatment.

    -   Date: Date of nesting activity. 

    -   Day_of_year: Day of the year, better fit for the GLMMs than Date.

    -   Nest_ID: Unique code to identify each nest created from the nest-box number, cavity number, and straw ID.

    -   Sealed: Indicates if the nest is sealed an end cap, or remains active either with mothers building the nests or for abandoned nests. Empty and pseudo nests contain NA.

    -   Nest_parasitized: Whether the nest contains a parasite.

    -   Occupant: Genus of the mother.

    -   DP_X_prior: Number of bee nests that are unsealed and parasitized, considered as nests with detectable parasites, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, excluding pseudo nests as congeneric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_ps_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, including pseudo nests as congeenric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   Year: Year of data collection.

    -   Straw_length_mm: Length of the straw in mm. Empty and pseudo nests contain NA, as well as nests that did not contain cells (inner wall only), were predated upon in the field, or were in too poor of shape from mold on rare occasions.

    -   Filled_length_mm: Length of cell contents that fill the straw in mm. Empty and pseudo nests contain NA, as well as nests that did not contain cells (inner wall only), were predated upon in the field, or were in too poor of shape from mold on rare occasions.

-   **nesting_cleaned_osmia.csv** and **nesting_cleaned_megachile.csv**: Cleaned and organized dataframes containing nest-level data for Osmia and Megachile bees, respectively. Each row is a unique date and Nest_ID combination. Below, the "X" in the column names is a stand-in for Osmia and Megachile, respective to their dataframes. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes. Used for prediction 3d.

    -   Site: Location of the nest-boxes, Conroy Pit (CP), Bruce Pit (BP), or Ottawa–Carleton Trailway (NN).

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box.

    -   Treatment: Nest-box classification as the Low, Mid, or High-occupancy treatment.

    -   Nest_ID: Unique code to identify each nest created from the nest-box number, cavity number, and straw ID.

    -   Date: Date of nesting activity. 

    -   Day_of_year: Day of the year, better fit for the GLMMs than Date.

    -   Year: Year of data collection.

    -   Status: Status of the nest, which could be nesting activity (e.g., 2 new cells built, end cap built, etc.), or be a pseudo nest or empty.

    -   Occupant: Genus of the mother, and in the case for pseudo nests, the genus of the imitation nest.

    -   Good_days: The number of days with good weather appropriate for bee activity between our field visits.

    -   Bee_choice: A newly established nest is coded as 1 for the choice of a bee to nest. NA indicates empty cavities, pseudo nests, or activity in nests that were already established. 

    -   Available_cavities_prior: Number of cavities available for bees to nest in prior to the new nests being built for this field visit. 

    -   New_nests_X: Number of new nests for that genus in each nest-box and date combination.

    -   X_ps_prior: Number of existing bee nests in each nest-box and date combination, including pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_no_ps_prior: Number of existing bee nests in each nest-box and date combination, excluding pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_active_mothers: Number of unsealed bee nests that are not abandoned, meaning the mother is actively building the nest, in each nest-box and date combination.

    -   DP_X_prior: Number of bee nests that are unsealed and parasitized, considered as nests with detectable parasites, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, excluding pseudo nests as congeneric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_ps_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, including pseudo nests as congeneric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   Abandoned_inner_wall: Binary of whether a nest was abandoned after only an inner wall was partially or completely built, before provisions were collected. Nests with a partial inner wall (less than 2/3 completed) were considered empty for the rest of the analyses because the mother put only a minute amount of investment into the nest. However, partially completed inner walls were counted in this column and in the analyses for predictions 3d. Abandoned inner wall = 1, inner walls that had subsequent provisions = 0. Nests after provisions have been collected, pseudo nests and empty nests have NA.
