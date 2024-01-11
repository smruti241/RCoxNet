# Survival-Analysis

![proposed](https://github.com/sakshig26/Survival-Analysis/assets/104989737/a72d0271-2520-4475-b95b-fe4fdad047e5)




**Usage:**

The **CoxRwrNet** package is for Survival analysis based on mutation data of TCGA Breast Invasive Carcinoma(BRCA) patients, the user can perform:

Preprocessing of TCGA BRCA patient,clinical and mutation data.
Calculate Prognostic index of each patients using model.
Visualize survival results and Rwr score patterns.

It looks like you have a Python script that involves data loading, cleaning, merging, and running an R script for further analysis. Here's a description of each function in your script:


2. **load_data():**
   - Reads clinical patient, clinical sample, and mutation data from three different files (`data_clinical_patient.txt`, `data_clinical_sample.txt`, and `data_mutations.txt`).
   - Returns the loaded dataframes.

3. **clean_data(df_data_mut):**
   - Cleans mutation data by extracting the prefix from the 'Tumor_Sample_Barcode' column and saving it to a new CSV file named "clean_tcga.csv".
   - Modifies the 'Tumor_Sample_Barcode' column in the original dataframe.
   - Returns the cleaned dataframe.

4. **merge_data(df_clinical_patient, df_clinical_sample, df_data_mut_final):**
   - Merges clinical patient, clinical sample, and cleaned mutation data based on specified column names.
   - Filters the resulting dataframe to include only records related to 'Breast Cancer'.
   - Returns the merged and filtered dataframe.

5. **get_all_mutated_genes(df_data_mut):**
   - Groups mutation data by 'Tumor_Sample_Barcode' and returns a dataframe with unique mutated genes for each sample.

6. **get_deleted_genes(df_data_mut):**
   - Reads data from "output_9606.protein.links.full.v11.5.txt" and identifies deleted genes.
   - Returns a list of deleted genes and the original list of genes.

7. **remove_items(test_list, item):**
   - Removes specified items from a list.

8. **calculate_seed(df_data_mut_patient_all_mutated, df_new, del_genes_all):**
   - Filters out deleted genes from the mutation data and saves the result to "patient_id_updated.csv".
   - Groups the updated mutation data by 'Tumor_Sample_Barcode' and returns a dataframe.
   - Displays the resulting dataframe.

9. **calculate_sg_score(list_of_genes, list_of_mutated_genes):**
   - Calculates a score for each gene based on its presence in the mutation data.
   - Saves the results to "score_sg_all_tcga_brca_all.csv".
   - Returns lists of mutated genes and their scores.

10. **run_r_script(input_csv_sg, input_csv_seed, output_csv):**
    - Executes an R script using rpy2, performing calculations based on input CSV files and saving the results to an output CSV file.
    - Returns the path of the generated CSV file.

11. **Extract(lst):**
    - Extracts the first element from each list in the provided list of lists.

12. **process_and_clean_data(df_data_mut_patient_all_mutated, df_data_mut_patient_all_data_new, csv_output_path, data):**
    - Processes and cleans additional columns from the mutation data, adds new columns, and saves the cleaned data to a CSV file.
    - Returns the cleaned dataframe.

13. **split_data(data, train_ratio, test_ratio, validation_ratio, random_state):**
    - Splits the data into training, testing, and validation sets based on specified ratios.
    - Prints the size of each set and returns the sets.

14. **save_data_to_csv(data, filename):**
    - Saves the provided dataframe to a CSV file.

15. **cll_funs():**
    - Calls all the defined functions in sequence to load, clean, merge, calculate, and process data.
    - Saves the training, testing, and validation sets to CSV files.





This repository contains code, data and results in BRCA, OV, GBM and Lung cancer folders & results for COX-RWRnet model for various conditions. We have compared our model COX-RWR net with existing models and those results are present in these repository.

BRCA, GBM, Lung, OV -> Contains code, data and results

CoxPasnet_without_age -> Contains results

Final Results -> Contains results for all cancers

Comparative result.jpeg, Comparative_result_with_msi_tmb.pdf, Comparativeresult_with_msi_tmb.jpeg -> Results for Comparative methods 
