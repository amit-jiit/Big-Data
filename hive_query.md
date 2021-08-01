                                   -- create table in hive --
create external table if not exists data_may(cord_uid string, sha string, source_x string, title string, doi string, pmcid string, pubmed_id string, license string, abstract varchar(65355), publish_time string, authors string, journal string, microsoft_academic_paper_id string,who_covidence string, arxiv_id string, has_pdf_parse string, has_pmc_xml string, full_text_file string, url string) comment 'data_may' row format serde 'org.apache.hadoop.hive.serde2.OpenCSVSerde' with serdeproperties ( "sepraterChar"=",", "quoteChar"="\"", "excapeChar"=",,,")  location 'may/' tblproperties("skip.header.line.count"="1");

                               ----Query Execution in hive--

Query 1- Find the 5 most common journals, list them along with their frequencies.

select journal , count('journal') as frequency from data_may group by journal order by frequency desc limit 6;

Query 2- The top 5 average abstract lengths (number of words) per journal.

select journal, avg(size(split('abstract', " "))) as abstract_length from data_may where journal is not null group by journal sort by abstract_length desc limit 5;

Query 3- Titles of the 5 papers with the highest numbers of authors. Both the numbers of authors
and the corresponding titles need to be output.

select title, count('authors') as total_authors from data_may where title is not null group by title limit 5; 
