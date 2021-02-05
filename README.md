# academic-publishers

## Purpose

A list of academic publishers and their scholarly journals — the main result is contained in the `Output`-folder.

## Data Sources

### Publishers
The compilation of publishers was generated by drawing from the following four sources:

* [DOAJ](https://doaj.org/) (using the data dump)
* [Publons](https://publons.com/about/home/) (using webscraping)
* [Scopus](https://www.scopus.com/) (using the csv-formatted source list from Oct. 2020)
* [Sherpa Romeo](https://v2.sherpa.ac.uk/view/publisher_list/1.html) (using webscraping)

### Journals
The list of journals was scraped from every respective publisher's website; see the urls in `Data\04_publishers.csv`.

## Methodical Approach

### Publishers

The data extraction regarding the publishers occurs in the files 01 to 04 in the `Script`-folder, mainly using R's `rvest`-package.

Using the information from the four data sources, the script takes each publisher's highest journal count as assigned by these data sources (so that each publisher has up to four, often differing, journal counts). It then orders the list by each publisher's respective highest journal count. This is done in file 05 in the `Script`-folder.

In a further step, the script harmonizes duplicated names of publishers (based on the data in `Data\03_publishers_harmonization.txt`). 

The full (harmonized) list of the publishers and their journal counts is visible in `Output\allpublishers-FINAL-2021-02-05.csv`.

### Journals

Finally, the publishers' websites are accessed via a uniform webscraping function (but with differing css selectors) so as to extract all of the publishers' journal names, including the URL to each journal. This is done in file 06 in the `Script`-folder. 

The various css selectors for each publisher is saved in `Data\04_publishers.csv`.

The outcome of this is visible in `Output\alljournals.csv` soon.
