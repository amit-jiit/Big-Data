# Big-Data
## Analysis of COVID-19 Open Research Dataset
### Main Overview
In response to the COVID-19 pandemic, the Allen Institute for AI has partnered with leading research groups to prepare and distribute the COVID-19 Open Research Dataset (CORD-19), a free resource of over 44,000 scholarly articles, including over 29,000 with full text, about COVID-19 and the coronavirus family of viruses for use by the global research community.
### Data Sources

This resource includes the metadata.csv file released weekly by the Allen Institute for AI, which documents COVID-19 updates and new research published in peer-reviewed publications. The columns of the dataset are:

cord_uid, sha,source_x, title,doi, pmcid, pubmed_id, license, abstract, publish_time, authors, journal, microsoft_academic_paper_id, who_covidence, has_pdf_parse, has_pmc_xml_parse, full_text_file, url

you can obtain a historical CORD-19 dataset by requesting:
https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/<date_iso_str>/<file_name>

where <date is str> is in the format YYYY-MM-DD and <file name> is metadata.csv. 
So e.g. for the 2020-05-01 dataset, the link would be
https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/2020-05-01/metadata.csv

  
Detailed description of the CORD-19 dataset is available at
https://github.com/rearc-data/covid-19-open-research
  https://www.semanticscholar.org/cord19
  https://www.scimagojr.com/journalrank.php.
  
### Problem statements
I have analysed dataset using different Big Data tools like Pyspark,Hive.
1. Find the 5 most common journals, list them along with their frequencies.
2. The top 5 average abstract lengths (number of words) per journal.
3. Titles of the 5 papers with the highest numbers of authors. Both the numbers of authors and the corresponding titles need to be output.
4. The top 5 most prolific authors along with the number of papers they have contributed to.
5. If an author’s H index is computed by summing all the H indexes of the journals they’ve published in (as included in the scimagojr dataset), list the 5 people with the top author H index values.
6. Plot the number of papers per month since 2020-01. You need to include your visualization as well as a table of the values you have plotted for each month.
