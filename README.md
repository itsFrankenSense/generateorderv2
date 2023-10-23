### Overview
This script serves as a convenient tool for generating metadata for collections, tailored for compatibility with www.generatord.io. It may not align with the requirements of other platforms. The script allows users to define trait rarities, specify traits that should not coexist, and even consider the absence of a trait ("none") as a valid option.

_I'm not a developer, but I enjoy creating tools that might simplify life for others. A large portion of this script was created by ChatGPT. Me monkey, me type._

## Features
- **Spreadsheet Creation**: Creates an organized spreadsheet that users can navigate with ease. This setup facilitates the adjustment of trait rarities and creates rules for trait compatibility.

- **Metadata Generation**: Executes the creation of metadata for a predetermined number of collection items, adhering to the user-defined rarities and rules.

- **Validation**: Aims to maintain the logical consistency of traits within each metadata item and throughout the entire collection. The process involves checking for prohibited trait pairings and aiming to adhere to the user's rarity specifications.

- **Statistics and Summary**: Offers a breakdown of trait usage throughout the collection, with distribution and occurrence frequency of each trait. It's crucial to personally verify that the output aligns with your expectations, as the script doesn't guarantee absolute accuracy.

### Requirements
- Python 3.x
- The `openpyxl` library, essential for managing Excel spreadsheets.

### How to Use
1. **Setting Up Your Environment**:
   - Confirm that Python 3 is installed on your system.
   - Install the required `openpyxl` library using the command: `pip install openpyxl`.

2. **Configuration**:
   - Specify the `ROOT_DIRECTORY` within the script (default set as 'Content'). This directory should host subdirectories, each symbolizing a different trait type, with individual files within these subfolders representing the traits.

3. **Running the Script**:
   - Initiate the script by executing `python generateorder.py` in your terminal.
   - The script kickstarts the process by creating a 'traits_info.xlsx' spreadsheet based on your folder structure.
   - Leaving the rarity field empty defaults to a random rarity assignment.
   - If opting for specific rarity percentages, ensure the collective rarity across all traits within a type equals 100%.
   - Including 'Yes' for the 'None' trait it should be added in your rarity percentages.
   - To prevent certain traits from pairing in the generated metadata, list the trait numbers in the 'Avoid Traits' column, separating multiple traits with commas.

4. **Generating Metadata**:
   - Once you've updated the 'traits_info.xlsx' file, press Enter in your terminal to prompt the script to continue.
   - Specify the quantity of items (inscriptions) for which you intend to generate metadata.
   - The script then creates the metadata generation, ensuring each item is not the same as any other already created for metadata and attempts to abide by rarity and trait avoidence. It concurrently validates the data to identify any inconsistencies or breaks in the rules. It's IMPORTANT to double-check your metadata for precision, as discrepancies may exist.

5. **Output**:
   - Upon completion, the script generates several files:
     - `metadata.json`: Houses the metadata for each collection item.
     - `traits.json`: Associates traits with their corresponding inscription IDs.
     - `trait_usage_statistics.json`: Presents a detailed account of trait usage and distribution throughout the collection.

### Handling Errors and Inconsistencies:
- Should you encounter errors or inconsistencies within the 'traits_info.xlsx' file or the generated metadata, the script will highlight these. It's advisable to rectify these based on the provided feedback and re-run the script if necessary.

### Caution
- It's important to ensure that the rules established for rarity and trait avoidance are logically sound. Conflicting or ambiguous rules could hinder the script's ability to produce the collection metadata.

*In scenarios where the script struggles to generate unique metadata for each collection item, it's worthwhile to consider introducing additional traits or tweaking the rules to accommodate a broader range of unique combinations.*
