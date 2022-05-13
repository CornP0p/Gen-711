# Gen 711

# Building a Phyogentic Tree From New Hampshire SARS-CoV-2 Surface Glycoprotein sequences collected at different times

## Background

SARS-CoV-2 was first discovered and sequenced in Wuhan in december 2019. Since then, it has quicly spread across the globe and mutated into many variants with differing virulences. It is a postive sense single stranded RNA virus and has a very high mutation rate due to the instability of single stranded RNA. This higher rate of mutation correlates to enhanced evolvability and virulence. Many of these mutations, which have altered it's ability to infect host cells, have occurred on the surface glycoprotein, or S protein. The S protein is made up of 2 subunits. The S1 subunit recognizes and attaches to the host angiotensin-converting enzyme 2 (ACE2). The S2 subunit is responsible for membrane fusion of the virus so its genetic informaton can invade the host cells and replicate. Becasue this protein is so important to the viruses success in invading host cells, it is under high selective pressure as well as a target for antiviral drugs and vaccines. My aim is to visualize New Hampshire surface glycoprotein nucleotide sequences from different points in time, using a phylogentic tree, to see if there is a clear distiction due to mutational change between the two times.

## Methods

The first step I took was to set up the conda environment to make insatlling the program packages I would need simpler. I downloaded 201 sequences of the coding region of the surface glycoprotien of SARS-CoV-2 from the NCBI data base: 100 from January in New Hampshire, 100 from april in New HAmpshire, and the original Wuhan strain. All the sequences were in FASTA format. I grouped the three files together in commandline and got rid of the spaces and "|" between the accession number and collection date so the collection date would be perserved when alinging and bootstrapping. I then installed the multiple sequence alignment program, MAFFT, and ran the command to align the sequences. I used AliView to visualize the the aligned sequences. With all the sequences aligned in a .ali file, I was ready to do the bootstraps to build the tree. I installed the packages for RAxML and ran the command to perform 20 bootstraps on the sequences which took 447 seconds. This gave me a file containing the best tree in a .tre file as well as a file for each bootstrap and information on the bootstraps. I then uploaded the besttree file to the free to use website, Interactive Tree of Life (ITOL), which gave me a visulaization of the tree and options to edit it's appearance. 

## Findings


![aliview.png](https://github.com/CornP0p/Gen-711/blob/main/Cringe/AliViewSpike.png) 
When visualizing the aligned sequnces with AliView there were mutiple deletions present distinct to the months. There were also nucleotide changes that were within the same month as well as ones that were distict to the individual months. THere were some sections of ambigious bases as well, and some of the sequences looked enitely identical and this was confirmed during the bootstrapping which noted that there were some sequences that had no differences which would regularly be removed. 

![branch.png](https://raw.githubusercontent.com/CornP0p/Gen-711/main/Cringe/SARS-CoV-2Spikebranch.png)

The tree with branch lenghths included shows a clear distiction between the two months with the sequences for april clustering in the top and the sequences from JAnuary spaced out on the bottom. The short branch lenghths for the April sequences indicate little genetic change as well as identical sequences being present. The more spaced JAnusary branches indicate more genetic change and less identical sequences. I am unsure exactly why this is, but from my knowledge there may have been a selective sweep that decreased the diversity of the virus between January and April.

![noBranch.png](https://raw.githubusercontent.com/CornP0p/Gen-711/main/Cringe/SARS-CoV-2Spike.png)

The tree with branch lenghths ingnored shows the sequences without the clustering. The Wuhan sequence is located near the right middle of the circular tree with its most closely related sequence being one collected on January 14th. It also shows that all the January sequences share a most recent common ancestor with a sequence collected on April 22nd which I cannot explain. It may be that there was not enough sequence informtion from the spike protein alone to make an acucrate tree. 


## Challenges

I did not figure out how to download the data sets, containing the collection dates for my sequences, through NCBI. When I tried downloading the sequences with the collection dates as the title, the bootstraps did not work because it does not allow the same title for multiple sequences. I downloaded the sequences with the accession number as well as the collection date, but the collection date would get removed during the alignment. To remidy this, I removed the " | " between the accession number and the collection date, but this made them connected and does not look nice on the tree. I would have like to figure out how to upload the data from NCBI to ITOL and annote the tree with it. There were also identical sequences that were used while making the tree and it would have been better to get 100 unique sequences for each month, so the same sequence wasnt assigned twice to the tree leading to the clustering. 

