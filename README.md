# EuPathDB<br>Eukaryotic Pathogen Database Project  

EuPathDB-Clean is a set of eukaryotic pathogen genomes originally downloaded from the 
[EuPathDB Resource Project](https://veupathdb.org/veupathdb/app) established by the National Institute of Allergy
and Infectious Disease (NIAID/NIH). These draft genomes were processed to remove all contaminating
and low-complexity sequences.  
  
Here we provide the cleaned eukaryotic pathogen genome FASTA files that can be used with any
metagenomics classification/analysis programs. For use, download each of the .tgz files and untar
the FASTA files using:  

```bash
for file in *.tgz
  do tar -xvzf $file -C my_eupathDB_folder/
done
```

## EuPathDB46 vs. EuPathDB26

As of December 1, 2020, we are releasing **EuPathDB46-Clean**. As compared to EuPathDB-28 (245
genomes), this database is larger (388 genomes) with fewer contaminating sequences. The database
underwent the same contamination/low-complexity removal process with updated reference bacterial,
archaeal, viral, vertebrate, and plant sequences.

## EuPathDB-46 Downloads

**EuPathDB-46: [Kraken 2 Database](https://genome-idx.s3.amazonaws.com/kraken/k2_eupathdb48_20201113.tar.gz)**  
At the link above, we provide the pre-built Kraken 2 database along with the relevant Bracken files.
The database is built from ONLY EuPathDB-46 genomes. In order to add EuPathDB-46 to an existing
database, users will need to download the genomes themselves and build a new database.  
  
[EuPathDB46_Contents.txt](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/EuPathDB46_Contents.txt) lists
all genomes in the database, including details about the filename, type, genus, species, and
strain.  
  
To build a database containing these genomes:

1.  Make a folder for the database:  
  `mkdir my_db`
2.  Change directory to the database folder:   
  `cd my_db`
3.  Download the NCBI taxonomy:  
  `kraken2-build --download-taxonomy --db .`
4.  Download the [**`seqid2taxid.map`**](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/seqid2taxid.map) file for EuPathDB46:   
  `wget ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/seqid2taxid.map`
5.  Make a libarary folder:  
  `mkdir library`
6.  Move to the library folder:   
  `cd library/`
7.  Download all of the genomes using the links below:  
  `wget ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/AmoebaDB46.tgz`
8.  Uncompress all of the genome folders:  
  ` tar -xzvf AmoebaDB46.tgz`
9.  Move back to the database folder:  
  `cd ../`
10. Build the Kraken/Kraken 2 database:  
  `kraken2-build --build --db . `


| Class                       | Genus Composition *                                                                                                                                                     | Number of EuPathDB-48 Files | Download                                                                                               | Uncompressed |
| --------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- | --------------------------: | ------------------------------------------------------------------------------------------------------ | -----------: |
| **AmoebaDB**                | Acanthamoeba, Entamoeba, Naegleria                                                                                                                                      |                          30 | [AmoebaDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/AmoebaDB46.tgz) (360 Mb)              |      1.39 Gb |
| **CryptoDB**                | Chromera, Cryptosporidium, Gregarina, Vitrella                                                                                                                          |                          18 | [CryptoDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/CryptoDB46.tgz) (98 Mb)               |       345 Mb |
| **FungiDB**                 | Allomyces, Aspergillus, Candida, Clavispora, Coccidioides, Coprinopsis, Histoplasma, Malassezia, Melampsora, Mucor, Penicillium, Pythium, Saccharomyces, Yarrowia, etc. |                         164 | [FungiDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/FungiDB46.tgz) (1.8 Gb)                |       6.2 Gb |
| **GiardiaDB**               | Giardia, Monocercomonoides, Spironucleus                                                                                                                                |                          10 | [GiardiaDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/GiardiaDB46.tgz) (50 Mb)             |       179 Mb |
| **MicrosporidiaDB**         | Anncaliia, Edhazardia, Enterospora, Hepatospora, Mitosporidium, Nematocida, Spraguea, Vittaforma, etc.                                                                  |                          35 | [MicrosporidiaDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/MicrosporidiaDB46.tgz) (62 Mb) |       245 Mb |
| **PiroplasmaDB**            | Babesia, Cytauxzoon, Theileria                                                                                                                                          |                          10 | [PiroplasmaDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/PiroplasmaDB46.tgz) (29 Mb)       |       101 Mb |
| **PlasmoDB**                | Plasmodium                                                                                                                                                              |                          45 | [PlasmoDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/PlasmoDB46.tgz) (185 Mb)              |       1.1 Gb |
| **ToxoDB**                  | Cyclospora, Cystoisospora, Eimeria, Hammondia, Neospora, Sarcocystis, Toxoplasma                                                                                        |                          33 | [ToxoDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/ToxoDB46.tgz) (550 Mb)                  |       2.1 Gb |
| **TrichDB**                 | Trichomonas                                                                                                                                                             |                           1 | [TrichDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/TrichDB46.tgz) (50 Mb)                 |       180 Mb |
| **TriTrypDB**               | Blechomonas, Bodo, Leishmania, Leptomonas, Paratrypanosoma, Trypanosoma                                                                                                 |                          42 | [TriTrypDB46_Clean.tgz](ftp://ftp.ccb.jhu.edu/pub/data/EuPathDB46/TriTrypDB46.tgz) (406 Mb)            |       1.5 Gb |
| **Total EuPathDB-46-Clean** |                                                                                                                                                                         |                     **388** |                                                                                                        |  **13.4 GB** |
  
## EuPathDB-28 Downloads

**EuPathDB-28 Library: [eupathDB.tar.gz](dl/eupathDB.tar.gz)** (2.2 GB)  
This file contains all 245 genomes in a single folder. Each genome is a multi-fasta file with
[Kraken](http://ccb.jhu.edu/software/kraken) and
[Kraken2](http://ccb.jhu.edu/software/kraken2)-compatible headers. To build a Kraken/Kraken2
database with these files, unzip the folder and place it directly within the `library/` folder.  

**For example, to build a database with human, bacteria, and eupathDB:**
```bash
tar -xzvf eupathDB.tar.gz
mv library/ $DBNAME/library/ 
kraken2-build --download-library bacteria --db $DBNAME
kraken2-build --download-library human --db $DBNAME
kraken2-build --build --db $DBNAME
```

(It is NOT required to use `kraken2-build --add-to-library` for these files.)

**EuPathDB-28 Kraken2 Database: [eupathDB_kraken2.tar.gz](dl/eupathDB_kraken2.tar.gz)** (5.6 GB)  
This folder is a pre-built Kraken2 database of the 245 eupathDB genomes. It contains three files:
`hash.k2d, opts.k2d,` and `taxo.k2d`.  

**For example, to use this pre-built database:**

```bash
tar -xzvf eupathDB_kraken2.tar.gz
kraken2 --db eupathDB_kraken2 MYSAMPLE.FNA > MYSAMPLE.KRAKEN2
```

(Do not run `kraken2-build --build` on this folder.)  
(This database is NOT compatible with Kraken 1)

*For more information on Kraken and Kraken 2, see:* 
[Kraken's Website](http://ccb.jhu.edu/software/kraken) and   
[Kraken2's Website](http://ccb.jhu.edu/software/kraken2)  

| Class                    | Genus Composition *                                                                                          | Number of EuPathDB-28 Files | Download                                                                                           | Uncompressed |
| ------------------------ | ------------------------------------------------------------------------------------------------------------ | --------------------------: | -------------------------------------------------------------------------------------------------- | -----------: |
| **AmoebaDB**             | Acanthamoeba, Entamoeba, Naegleria                                                                           |                          29 | [AmoebaDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/AmoebaDB_Clean.tgz) (326 MB)              |      1.37 GB |
| **CryptoDB**             | Chromera, Cryptosporidium, Gregarina, Vitrella                                                               |                          11 | [CryptoDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/CryptoDB_Clean.tgz) (86.5 MB)             |       359 MB |
| **FungiDB**              | Ajellomyces, Aspergillus, Candida, Coccidioides, Cryptococus, Fusarium, Rhizopus, Saccharomyces, Trichoderma |                          87 | [FungiDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/FungiDB_Clean.tgz) (931 MB)                |       3.5 GB |
| **GiardiaDB**            | Giardia, Spironucleus                                                                                        |                           6 | [GiardiaDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/GiardiaDB_Clean.tgz) (21 MB)             |        72 MB |
| **MicrosporidiaDB**      | Anncaliia, Encephalitozoon, Mitosporidia, Nematocida                                                         |                          25 | [MicrosporidiaDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/MicrosporidiaDB_Clean.tgz) (35 MB) |       199 MB |
| **PiroplasmaDB**         | Babesia, Cytauxzoon, Theileria                                                                               |                           8 | [PiroplasmaDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/PiroplasmaDB_Clean.tgz) (21 MB)       |        76 MB |
| **PlasmoDB**             | Plasmodium                                                                                                   |                           9 | [PlasmoDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/PlasmoDB_Clean.tgz) (27 MB)               |       216 MB |
| **ToxoDB**               | Cyclospora, Eimeria, Hammondia, Neospora, Sarcocystis, Toxoplasma                                            |                          30 | [ToxoDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/ToxoDB_Clean.tgz) (456 MB)                  |       1.8 GB |
| **TrichDB**              | Trichomonas                                                                                                  |                           1 | [TrichDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/TrichDB_Clean.tgz) (43 MB)                 |       180 MB |
| **TriTrypDB**            | Leishmania, Leptomonas, Trypanosoma                                                                          |                          39 | [TriTrypDB_Clean.tgz](http://ccb.jhu.edu/data/eupathDB/dl/TriTrypDB_Clean.tgz) (336 MB)            |       1.3 GB |
| **Total EuPathDB-Clean** |                                                                                                              |                     **245** | **2.3 GB**                                                                                         |   **9.1 GB** |

*The genuses listed for FungiDB and MicrosporidiaDB are a subset of all genuses represented. For full list of genuses contained in these classes, see the publication supplementary table.  

## Publications

The publication associated with the data is located at:  
J. Lu, S.L. Salzberg. (2018). "Removing contaminants from databases of draft genomes." 
*PLoS Comput Biol* <https://doi.org/10.1371/journal.pcbi.1006277>  

## Authors/Contributors

[Jennifer Lu, Ph.D.](http://ccb.jhu.edu/people/jennifer.lu/)  
[Steven Salzberg, Ph.D.](https://salzberg-lab.org/)    
