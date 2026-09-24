## AI Usage Transparency
### Prompt 1

**Model:** ChatGPT
**Error:**
```
Error in format.default(messy_sample$dob, "%Y/%m/%d") : invalid 'trim' argument
```
I first asked ChatGPT what this error meant, then asked how to fix it. 

**ChatGPT response:** The use of `case_when()` expression returns a character vector, so `format()` applied was used incorrectly to the result.

**ChatGPT suggested fix** Put the `format()` operation inside each `case_when` condition so that each date is converted and formatted within its respective branch.

**My edit:** Based on those replies from ChatGPT when dealing with the mass variations in dates formats, I learned that the script I developed cannout all be sumarrised and run through `format()` in one go. There may be a different package that can utalise this to get the year-month-date format. So I followed the suggestion by adding the format line within each branch to apply it through. This had worked.

================================================
### Prompt 2

**Model:** ChatGPT
**Error:**
```
Warning message: NAs introduced by coercion
```
I first asked ChatGPT what this error meant, then asked how to fix it.  

**ChatGPT response:** R trying to convert a value to numric, but some glucose values contained non-numeric characters or missing-value text, causing R to produce `NA`. 

**ChatGPT suggested fix** Identify the values that could not be converted and determine how the missing or annotated values should be handled before numerical analysis.

**My edit:** This help point out important information involed with my decision in how to standardize my glucose values/units. I ended up reversing and left the `glucose` values unchanged. Then for the units, standardized them to the same unit (mg/dl) with the plan to explain that as a next step, idetify the values where the scale from unit change needs to be added/converted. 

================================================
### Prompt 3

**Model:** ChatGPT
**Error:**
```
error: 'lab4/' does not have a commit checked out
error: unable to index file 'lab4/'
fatal: adding files failed
```
I first asked ChatGPT what this error meant, then asked how to fix it.  

**ChatGPT response:** `lab4/` was being treated as a nested Git repository when tried to add from the parent directory.

**ChatGPT suggested fix** Work from inside the `lab4` repository rather than trying to add the repository itself from its parent directory.

**My edit:** When i saw the emphasis placed on `lab4` I took a step back and went into Git Hub and made a repository where it was named `lab3` and reset orgion with a new link. Once that was done, I was able to commit the folders I wanted into GitHub effectively. It was not exactly the suggested fix, but made me realise why the error had occured. 

================================================

## AI cleaned data

### Promt 1
**Generative AI Model:** ChatGPT

**My resonse:** Here I attached two files. One is a 60-line sample and the second is a series of sequences. I want you to clean these files one at a time. Prcess these files first.

**My response cnt:** For the sample (csv) data, please standardize the data within each column to your prefered format, as long as it is consistant. Then produce the product as sample x features x metadata table. This is all for now. 

**ChatGPT Response:** "Done. I standardized the CSV while preserving the original measurements rather than silently converting glucose units. Change include:   
> Sample IDs -> `S001` format  
> Names -> consistent capitalization  
> DOB -> `YYYY-MM-DD`  
> Sex -> `Female`, `Male`, `Unknown` or `Missing`  
> Enrollment sites -> `Site A`, `Site B`, or `Site C`  
> Glucose units -> consistent `mg/dL` / `mmol/L` formatting  
> Removed `*` from glucose values and preserved it as `glucose_flag = Flagged`  
> Standardized notes  
> Organized the table as sample -> feature -> metadata  

Presented .csv output as `cleaned_samples.csv` and attached a screenshot bellow:
<img width="355" height="322" alt="image" src="https://github.com/user-attachments/assets/8ba4520e-6b9e-4149-8d42-4347818bb166" />

### Promt 2
**Generative AI Model:** ChatGPT

**My resonse:** I want you to clean the messy sequence file by seperating the headers and give each their respective columns based on pulled information.

**ChatGPT Response:** "Done. I standardized the messy FASTA headers into consistent columns based only on information present in the headers. The cleaned table contains:  
> `sequence_id`  
> `organism`  
> `gene`  
> `header_length_bp` (length stated in the header, when present)  
> `sequence_length_bp` (length calculated from the actual sequence)  
> `notes`  
> `sequence`

I kept header-reported length separate from calculated sequence length because some records disagree (for example, sample-003 reports 150 bp while the actual sequence is 157 bp). I did not silently change either value.

Presented .csv output as `cleaned_sequences.csv` and attached a screenshot bellow:
<img width="391" height="149" alt="image" src="https://github.com/user-attachments/assets/dbec8d4e-e8b8-4634-a81e-d51d3ec2597a" />
