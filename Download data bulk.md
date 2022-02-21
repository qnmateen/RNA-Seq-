## Bulk download using SRA

import subprocess

# samples correspond to 61 samples
sra_numbers = [
    "SRR9036307", "SRR9036308", "SRR9036309", "SRR9036310", "SRR9036311", "SRR9036312", "SRR9036313", "SRR9036314", "SRR9036315", "SRR9036316","SRR9036317",
    "SRR9036318","SRR9036319","SRR9036320","SRR9036321","SRR9036322","SRR9036323","SRR9036324","SRR9036325","SRR9036326","SRR9036327","SRR9036328","SRR9036329","SRR9036330","SRR9036331","SRR9036332","SRR9036333","SRR9036334","SRR9036335","SRR9036336","SRR9036337","SRR9036338","SRR9036339","SRR9036340","SRR9036341","SRR9036342","SRR9036343","SRR9036344","SRR9036345","SRR9036346","SRR9036347","SRR9036348","SRR9036349","SRR9036350",
    "SRR9036351", "SRR9036352", "SRR9036353", "SRR9036354", "SRR9036355", "SRR9036356", "SRR9036357", "SRR9036358", "SRR9036359", "SRR9036360", "SRR9036361", "SRR9036362", "SRR9036363", "SRR9036364", "SRR9036365", "SRR9036366", "SRR9036367", "SRR9036368", "SRR9036369", "SRR9036370", "SRR9036371", "SRR9036372", "SRR9036373", "SRR9036374", "SRR9036375", "SRR9036376", "SRR9036377", "SRR9036378", "SRR9036379", "SRR9036380", "SRR9036381", "SRR9036382", "SRR9036383", "SRR9036384"
    ]

# this will download the .sra files to ~/ncbi/public/sra/ (will create directory if not present)
for sra_id in sra_numbers:
    print ("Currently downloading: " + sra_id)
    prefetch = "prefetch " + sra_id
    print ("The command used was: " + prefetch)
    subprocess.call(prefetch, shell=True)

# this will extract the .sra files from above into a folder named 'fastq'
for sra_id in sra_numbers:
    print ("Generating fastq for: " + sra_id)
    fastq_dump = "fastq-dump --outdir fastq --gzip --skip-technical  --readids --read-filter pass --dumpbase --split-3 --clip ~/ncbi/public/sra/" + sra_id + ".sra"
    print ("The command used was: " + fastq_dump)
    subprocess.call(fastq_dump, shell=True)
