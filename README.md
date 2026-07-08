### DS-Dataset-Catalogue

This is the AITIS Dataset Catalogue Repository.

The top level index file `index.md` servers as a table of contents that links to each dataset folder.

To contribute to this repository, please find the templates in the `templates` folder in this directory. The `overview_template.md` file contains the empty data overview template that can be copied and filled out for each dataset. The `overview_example.md` file contains pre-filled example of how the this template should be filled out. This is similary for the `dictionary_example.md` and `dictionary_template.md` files.



### Repository Structure

```zsh
.
├── index.md                            # top level data index
├── mymonx                              # product directory
│   └── Dexcom                          # dataset sub-directory
│       ├── data_overview.md            # data overview 
│       ├── data_dictionary.md          # data dictionary of variables
│       └── data_analysis.ipynb         # existing data analysis on dataset
├── skincancer
│       ├── data_overview.md
│       └── data_dictionary.md
├── templates
│   ├── dictionary_example.md
│   ├── dictionary_template.md
│   ├── overview_example.md
│   └── overview_template.md
├── ...
└── README.md
```

