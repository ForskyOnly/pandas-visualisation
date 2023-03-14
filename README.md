# pandas-visualisation
file_list = ['eastern_africa.csv', 'middle_africa.csv', 'northern_africa.csv',
             'southern_africa.csv', 'western_africa.csv', 'northern_america.csv',
             'central_america.csv', 'caribbean.csv', 'south_america.csv', 'central_asia.csv',
             'eastern_asia.csv', 'southern_asia.csv', 'south_eastern_asia.csv',
             'western_asia.csv', 'eastern_europe.csv', 'northern_europe.csv',
             'southern_europe.csv', 'western_europe.csv', 'australia_new_zealand.csv',
             'melanesia.csv', 'micronesia.csv', 'polynesia.csv']

import pandas as pd

def read_and_clean_csv_files(*files, columns_to_drop=None):
    data_list = []
    for file in files:

        data = pd.read_csv(file)

        data.columns = [col.replace(' ', '_') for col in data.columns]

        if columns_to_drop:
            data = data.drop(columns_to_drop, axis=1)
     
        data_list.append(data)
    return data_list



file_list = ['fichier1.csv', 'fichier2.csv', 'fichier3.csv']
columns_to_drop = ['colonne1', 'colonne2', 'colonne3']
data_list = read_and_clean_csv_files(*file_list, columns_to_drop=columns_to_drop)

