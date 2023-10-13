First and foremost,I imported 'pandas' as 'pd' into workspace,then;
I loaded my file 'Energy_Indicators.xlsx' into my nootbook using 'read_excel()'.
I advanced to cleaning my data.
Doing that,I followed these steps below:

    -I dropped the irrevant rows(both the header and the footer) and columns(the 1st two cloumns) using 'data.loc[range].index,inplace = True';NOTE:inplace=True,this reflects the changes made to the original data.
    
    -Moving on from that,I renamed my columns to this specified columns names:(Country,Energy-Supply,Energy-Supply-per-Capita,Renewable%) using 'data.rename(columns={#using a dictionary},inplace=True)'.
    
    -Then I created a DataFrame named 'Energy' and converted my data to a DataFrame using 'pd.DataFrame(data)'.
    
    -Had to reset my index using 'Energy.reset_index(drop=True,inplace=True)';NOTE:drop=True,drops the original index of the dataframe.
    
    -Noticed that there were missing data-points from certain columns that are neither 'string' or 'numbers',so I solved this using 'Energy['columns with empty datapoints']=pd.to_numerical(Energy['columns with empty datapoints'],errors = 'coerce')'.NOTE:specifying 'errors ='coerce' ' turns all datapoints that isn't a numerical value to 'NaN'. And with that,I was able to convert non-numerical datapoints to 'NaN'.
    
    -NOTE:use 'pd.set_option(display.max_rows,None)' to display the data.
    -With this,I started replacing Country names with its appropriate names using 'Energy['Column'].replace({'old column-name':'new-column-name'})'.For certain columns that has extremely long name,used 'pd.set_option(max_colwidth,None)' to expand the column width.
    
    -Converted the Energy Supply originally in Petajoules to Gigajoules by creating a new column and multiplying it with 1,000,000.
    
    
    
