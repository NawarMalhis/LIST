# LIST
Local Identity and Shared Taxa

LIST 0.1 beta

LIST 0.1 beta generates Position Conservation Matrixes for human protein sequences in fasta format.
- First, input sequences are aligned to the UniProt Swiss-Prot/TrEMBL
- Then, it computes a deleteriousness value for every possible AA mutation in the sequence based on the LIST algorithm.

Minimum hardware requirement:
Ubuntu platform running on a desktop computer with at least 16G RAM, and a 4 cores CPU. Disk IO is the main performance bottleneck, thus SSD is recommended.

To install and test LIST 0.1 beta

Install the blast alignment tools, please type:
 sudo apt-get install ncbi-blast+

Unzip the LIST.zip file.

from: https://www.uniprot.org/downloads/ Download into the UniProt directory:
Reviewed (Swiss-Prot) fasta and Unreviewed (TrEMBL) fasta

from: ftp://ftp.ncbi.nlm.nih.gov/pub/taxonomy/ Download into the Taxa directory:
taxdump.tar.gz

To compile source code, please type:
make

To unpack and format downloaded data files, type
make unpack
               processing time is 1~3 hours

To run the test sequences in the data directory, please type:
./list data

Running LIST 0.1
LIST 0.1 processes all fasta sequences in the target directory. Each sequence must be in a fasta format in a separate file with the extension ‘.fast’.

NCBI blastp is used for alignment using m threads (default m = 4). To use different n and m values, include these values in the command line:
./list dir [threads_cnt]

Example:
./list data 2
Process all sequences in the data directory using 2 threads.

This software is distributed on an as is basis, without any kind of warranties. This software is for academic not for profit research only. Not for commercial purposes. Incorporating any part of this software in other applications should preserve the author copyright message. Appropriate citation when using LIST in publication of scientific results. These UBC Terms of Use set out the terms and conditions that will govern your relationship with UBC, through your use of LIST.
