# **README**

## **Social influences and parasite avoidance during nest-site selection**

### **Files**

-   **01_Wrangling.qmd**: Quarto document created for cleaning, organizing, and inspecting the data.

-   **02_Analyses.qmd**: Quarto document used for running the statistical analyses.

-   **03_Figures.qmd**: Quarto document for creating figures.

### **Dataframes** 

-   **Aggregate_nesting_data_2023.csv** and **Aggregate_nesting_data_2024.csv**: Raw data files from our field data for 2023 and 2024, respectively.

    -   Site: Location of the nest-boxes, Conroy Pit (CP), Bruce Pit (BP), or Ottawa–Carleton Trailway (NN).

    -   Subsite: Each subsite contained one nest-box of each treatment, for a total of three next-boxes per subsite. Each site contained 6 subsites at a time.

    -   Trapnest: Synonymous with nest-box. The unique identification number for each nest-box. Each contain 18 cavities and thus 18 nests at once.

    -   Treatment: Nest-box classification as the low-, mid-, or high-occupancy treatment.

    -   Cavity_size: Classification of the cavity diameter size.

    -   Cavity_number: Cavity identification number within the nest-box.

    -   Straw_ID: Identification letter of each nest, as nests would be removed perpetually throughout the experiment and should share the same Cavity_number.

    -   Straw_length_mm: Length of the straw in mm. Empty and pseudo nests contain NA, as well as nests that did not contain cells (inner wall only), were predated upon in the field, or were in too poor of shape from mold (rare).

    -   Filled_length_mm: Length of cell contents that fill the straw in mm. Empty and pseudo nests contain NA, as well as nests that did not contain cells (inner wall only), were predated upon in the field, or were in too poor of shape from mold (rare).

    -   Occupant: Genus of the mother, and in the case for pseudo nests, the genus of the imitation nest. Empty nests contain NA. Occupants other than Osmia and Megachile will be filtered out in the wrangling.

    -   09-May – 08-Aug (Aggregate_nesting_data_2023.csv) and 05-Jun – 13-Aug (Aggregate_nesting_data_2024.csv): Dates of our field visits to log bee activity and establish a nest status. Non_existent means the nest did not exist at that time (e.g., a nest is built then removed and replaced with an empty straw, so the first nest will become non-existent once it is removed). No-visit means that field site was not visited that day. The remaining statuses are bee activity (inner walls, cells with provisions and eggs, end caps), pseudo nest (imitation nest that appears completed), or empty.

    -   Notes: Noteworthy observations taken while collecting data.

-   **Emergence_data_2023.csv** and **Emergence_data_2024.csv**: Raw data files for the nesting data from occupant emergence for 2023 and 2024, respectively.

    -   Site: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Subsite: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Trapnest: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Treatment: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Cavity_size: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Cavity_number: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Straw_ID: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Nest_ID: Unique code to identify each nest created from the nest-box number, cavity number, and straw ID. Can have nesting activity (inner walls, cells with provisions and eggs, end caps), be a pseudo nest (imitation nest that appears completed), or is empty. Nests in the emergence data have nesting activity.

    -   Cell_number (Emergence_data_2023.csv): Number to indicate the order of the cells within the nest, with number 1 corresponding to the first cell built and highest number to the last cell built.

    -   Cell_position: Whether the cell was the last built before the mother sealed the nest, or it was not the last cell.

    -   Date: Date the cell was constructed.

    -   Cell_occupant: Occupant inside the cell that emerged or failed to emerge. Identified as the genus for bees, 'parasite' for all parasites, larva (unable to be distinguished as bee or parasitic wasp larva), or if the cell was not developed, it was identified as empty, a pollen mass, or mold.

    -   Species_or_subtype: Species of Osmia or Megachile occupants, subtype of parasites, and NA for the non-target bee genera or undeveloped cells.

    -   Collection: If the occupant from that nest is kept as a voucher for the collection. NA for occupants not collected.

    -   Sex: Sex of the vouchers and emerged occupants. NA for occupants not collected or their sex was not identified.

    -   Comments: Noteworthy comments about the emergence data.

-   **Empty_data_2023.csv**: Empty data with identical columns to Aggregate_nesting_data_2023.csv, used in the wrangling file. Raw data for 2024 contained the empty rows directly in the document.

-   **Weather_2023_data.csv** and **Weather_2024_data.csv**: Weather data used to calculate the number of days with weather appropriate for bee activity between our field visits.

    -   Date: Date of every day during the 2023 field season.

    -   Max_temp (Weather_2023_data.csv): Maximum temperature during the day.

    -   Rain (Weather_2023_data.csv): Amount of rain in mm or 'trace' if minimal precipitation but not zero.

    -   Sun_at_noon (Weather_2023_data.csv): Cloud cover at noon.

    -   Scale_to_3 (Weather_2023_data.csv): How many of the conditions (temperuature, rain, and cloud cover) met the threshold for appropriate weather for bee activity.

    -   Visit_NN, Visit_BP_Os, Visit_BP_Meg, Visit_CP, Visit_BP: If we visited the site that day. NA for when the site did not exist.

    -   Weather: If the weather was good or bad for bee activity.

    -   Good_days_NN, Good_days_BP_Os, Good_days_BP_Meg, Good_days_CP, Good_days_BP: The number of days with good weather between our field visits. NA for when we did not visit the field, or when the site did not exist.

-   **nesting_cleaned_osmia.csv** and **nesting_cleaned_megachile.csv**: Cleaned and organized dataframes containing nest-level data for Osmia and Megachile bees, respectively. Each row is a unique date and Nest_ID combination.. Below, the "X" in the column names is a stand-in for Osmia in the nesting_cleaned_osmia.csv dataframe and Megachile in the nesting_cleaned_megachile.csv dataframe. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes.

    -   Site: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Subsite: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Trapnest: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Treatment: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Nest_ID: See explanation from columns in Emergence_data_2023.csv and Emergence_data_2024.csv.

    -   Date: Date of the data collection and thus nesting activity from previous date of data collection.

    -   Day_of_year: Day of the year, better fit for the GLMMs.

    -   Year: Year of the nest construction.

    -   Status: Status of the nest, which could be nesting activity, or be a pseudo nest or empty nest.

    -   Occupant: Genus of the mother, and in the case for pseudo nests, the genus of the imitation nest. Empty nests contain NA.

    -   Sealed: Indicates if the nest is sealed an end cap, or remains active with mothers building the nests, with the exception of abandoned nests. Empty and pseudo nests contain NA.

    -   Nest_parasitized: Indicates if the nests are parasitized or not. Empty and pseudo nests contain NA.

    -   Good_days: Number of weather days appropriate for bee activity between our field visits.

    -   Bee_choice: Binary of whether a new nest was built in a previously empty straw, yes = 1, no (remains empty) = 0. Pseudo nests or nests already established receive an NA.

    -   Available_post: Number of available cavities for each nest-box and date combination after the new nests for that visit have been started, i.e., how many available cavities that the experiments saw when arriving to the nest.

    -   New_nests_X: Number of new bee nests, for each nest-box and date combination.

    -   New_nests_sum: Sum of the new Osmia and Megachile nests for each nest-box and date combination.

    -   Available_cavities_prior: Number of available cavities prior to the new nesting activity since our previous field visit for each nest-box and date combination, e.g., the number of available cavities that could have had a new nest built between visits.

    -   X_ps_prior: Number of existing bee nests in each nest-box and date combination, including pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_no_ps_prior: Number of existing bee nests in each nest-box and date combination, excluding pseudo nests as congeneric occupants, prior to the new mothers building nests in that nest-box. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   X_active_mothers: Number of unsealed bee nests that are not abandoned, meaning the mother is actively building the nest, in each nest-box and date combination.

    -   Sum_unsealed_X: Number of bee nests that are not sealed in each nest-box and date combination. These columns are for testing an attraction of parasites to bees, so NAs occur when there are no parasite attacks.

    -   DP_X_prior: Number of bee nests that are unsealed and parasitized, considered as nests with detectable parasites, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, excluding pseudo nests as congeneric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   NDP_ps_X_prior: Number of bee nests that are sealed (parasitized or not) considered as nests with no detectable parasites, including pseudo nests as congeenric occupants, in each nest-box and date combination. When more than one new nest was built between our field visits, we averaged the number of neighbouring congeneric occupants existing in the nest-box, resulting in several half numbers. See the methods section for details.

    -   Abandoned_inner_wall: Binary of whether a nest was abandoned after only an inner wall was partially or completely built, before provisions were collected. Nests with a partial inner wall (less than 2/3 completed) were considered empty for the rest of the analyses because the mother put only a minute amount of investment into the nest. However, partially completed inner walls were counted in this column and in the analyses for predictions 3d. Abandoned inner wall = 1, inner walls that had subsequent provisions = 0. Nests after provisions have been collected, pseudo nests and empty nests have NA.

<!-- -->

-   **nesting_cells_cleaned_osmia.csv** and **nesting_cells_cleaned_megachile.csv**: Cleaned and organized dataframes containing cell-level data for Osmia and Megachile bees, respectively. Each row is a unique cell from within a Nest_ID. Below, the "X" in the column names is a stand-in for Osmia in the nesting_cleaned_osmia.csv dataframe and Megachile in the nesting_cleaned_megachile.csv dataframe. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes.

Nest_ID

Date

Site

Subsite

Trapnest

Treatment

Cavity_size

Cavity_number

Straw_ID

Cell_number

Cell_ID

Cell_position

Cell_occupant

Species_or_subtype

Cell_parasitized: Whether the cell is parasitized or not, 1 = parasitized, 0 = not parasitized.

Cumulative_par: The cumulative number of parasites in the nest up until that date.

Number_of_cells: The number of cells in the nest up until that date.

Filled_length_mm

Straw_length_mm

Cavity_ID

Status

Contains_cells: Whether the nest contains cells...

Occupant

Good_days

Bee_choice

Available_post

New_nests_os

New_nests_meg

Osmia_ps

Osmia_no_ps

Meg_ps

Meg_no_ps

Osmia_ps_prior

Osmia_no_ps_prior

Meg_ps_prior

Meg_no_ps_prior

New_nests_sum

Available_cavities_prior

Sealed: If the nest was sealed or not in that date.

After_inner_wall: ...

Before_cells: ...

Nest_parasitized

Active_bin: ...

Osmia_active_mothers

Meg_active_mothers

Sum_unsealed_os

Total_cells_per_date:...

Sum_cell_parasitized:...

Sum_cell_not_parasitized:...

Day_of_year

Year

Cell_position_bi:...

-   **investment_cleaned_osmia.csv** and **investment_cleaned_megachile.csv**: Cleaned and organized dataframes containing nest-level data for Osmia and Megachile bees, respectively. Each row is unique nest that has a measured filled_length and straw_length for the nest investment prediction (3b). Below, the "X" in the column names is a stand-in for Osmia in the nesting_cleaned_osmia.csv dataframe and Megachile in the nesting_cleaned_megachile.csv dataframe. Accordingly, the "number of bee nests" in the descriptions refers to the number of Osmia or Megachile nests, respective to their dataframes.

    -   Site

    -   Subsite

    -   Trapnest

    -   Treatment

    -   Straw_ID: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Date

    -   Day_of_year

    -   Nest_ID

    -   Status

    -   Sealed

    -   Nest_parasitized

    -   Occupant

    -   Good_days

    -   Bee_choice

    -   Available_post

    -   New_nests_os

    -   New_nests_meg

    -   Available_cavities_prior

    -   New_nests_sum

    -   Osmia_ps_prior

    -   Osmia_no_ps_prior

    -   Meg_ps_prior

    -   Meg_no_ps_prior

    -   X_active_mothers: See explanation from columns in nesting_cleaned_osmia.csv and nesting_cleaned_megachile.csv.

    -   Sum_unsealed_os

    -   Sum_unsealed_meg

    -   DP_os_prior

    -   NDP_os_prior

    -   NDP_ps_os_prior

    -   DP_meg_prior

    -   NDP_meg_prior

    -   NDP_ps_meg_prior

    -   Abandoned_inner_wall

    -   Year

    -   Straw_length: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

    -   Filled_length: See explanation from columns in Aggregate_nesting_data_2023.csv and Aggregate_nesting_data_2024.csv.

-   **trapnesting** data: next-bost level data, unique combo for nest box and date.
