Datasets and codes for analyses and pre-processing of metabarcoding data from the Meloloepel experiment.

Create Bacteria phyloseq for pre-processing:
load ("./Bacteria/Bacteria_phy.RData")
load ("./Bacteria/Bacteria_phy_updated_taxa.RData")
bacteria_phy
sample_names_bact <- sample_names(bacteria_phy)
data <- read.csv("./Bacteria/metadata_DNA-RNA - CorrMc-final.csv", sep =';', row.names = 1)
sample_data(bacteria_phy) <- sample_data(data)

Or use the pre-processes bacterial phyloseq : ps.bact
load (file = 'ps-selected-only-bact-filt-lowabd-no-neg-norep2.RData')

create fungal phyloseq:
load ("./ITS/ITS_phy_meta.RData")
ITS_phy
sample_names_ITS <- sample_names(ITS_phy)
write.csv(sample_names_ITS, "ITS/sample_names_ITS.csv", row.names=TRUE)

#change metadata with the metadata with the right Mc counts
data <- read.csv("./ITS/metadata_DNA-RNA - CorrMc-final.csv", sep =';', row.names = 1)
sample_data(ITS_phy) <- sample_data(data)

Or use the pre-processes fungal phyloseq : ps.ITS
load (file = 'ps-selected-only-ITS-filt-lowabd-no-neg-norep.RData')
