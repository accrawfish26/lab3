# Graduate Addenum

## Comparing the two outputs

### Question 1: Where did they agree/disagree?
I think there are some interesting observations here. I think the inital thing was that it seemed ChatGPT had used pandas package during alysis which naturally presents a different set of tools compared to my choice in using RStudio. Some differences I saw was that `sequence_id` still had variations while mine was consistant in relation to capitalization. ChatGPT had addressed the length issue by keeping the length presenter in heading then adding the full calcuated length. I had only included information that was given in the header. With the samples data, I thought it was interesting ChatGPT had formatted dates with `-` while I used `/`, had `Female` while I had `F` and used `Site A` while I had `A`. They are minor differences, but something worth mentioning was that variations with glucose was changed by leaving values alone, change all units to lowercase, then add a column for rows that was marked with `*` symbol. 

## Question 2: Which caught edge causes the other missed?
I think the AI had done better with the dates because it caught the differences in years. Because some years are only 2 digits instead of all 4, it was able to catch and assign the correct decade (56 -> 1956 not 2056). I think my produce a 'false success' in that my script works but does not catch these slight variations as accurately. One thing I had caught better was diving the sequences more accuare to what in the sequence and kept integrety to the columns in given data by not adding additional information and maintaining their respective orders. 

## Question 3: Time/effort comparison: which was faster to get right?
Unfortunatly, I think that AI had the better advantage. It shown through this assignment that AI had arrived to the point that if provided a well enough promt will generate data that near to what I had manually done through coding over a few hours into a few minutes. I would take their outputs and modify that outcome to ensure accuracy would be the most effient process than all manual or all AI generated. 

## Question 4: Find at least 2 specific records where one or both approaches got something wrong (or ambiguous) and explain why.
For mine, I breifly mention in prior question. But I had a hard time with standardizing dates. There are not only variations in symbols used (./-) as seperators, but the order in years/month/dates vs dates/month/years and that years itself was presented as 95 and 1995. The same applied to moths with 05 vs MAY. I done the best to capture as many options but I could not get the chance to address the 95 to 1995 without breaking other elements. This is one place I got wrong. 
The second record was that AI had done was having some ambiguous/assumptions with the sequence dataset. This is from the `sequence ID` having the correct seperation, but was left as `sample_001`, `Sample_002`...`SAMPLE_004`...`seq6` in addition to `organisms` column all being labled as `Homo sapians`. I think it was interesting that it did not standardize the `sequence ID` but did for the `organisms`. I wonder what part of it decision to perform that action. 
Another note for the AI was leaving the `glucose_value` that had no measurements as fully blank. It did not input any `NA` characters/text to signify its missing input. This could impact any analysis done on this column. 

## Additional queestion about samples x features x metadata table
The `messy_sample.csv` was turned into a table. The sample was each given its own row with each column having its own observation point (features) to create the metadata table. However there are still important things worth noting about being analytic readiness. Due to limitation of must be reproducible through codes, it increase difficulty to catch every variation for each observation. Some thing that would ned to be addressed are `date_of_birth` to ensure that the years are accurate (no 2053 instead of 1953). Conversion for `glucose_values` where its unit was changed to ml/dl for sake of standardizing the units column. 

