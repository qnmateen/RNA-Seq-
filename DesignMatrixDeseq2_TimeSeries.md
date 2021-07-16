# Design Matrix

Columns are- 

## Sample id Gender Genotype  

**dds$group <- factor(paste0(dds$Gender, dds$Genotype))
design(dds) <- ~ group**
dds <- DESeq(dds)
resultsNames(dds)   

#e.g. for condition KO Male vs KO female
results(dds, contrast=c("group","MKO","FKO"))   

#e.g. for Male KO vs WT
results(dds, contrast=c("group","MKO","MWT")) 
