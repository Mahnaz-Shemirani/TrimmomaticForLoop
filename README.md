# TrimmomaticForLoop
How to use trimmomatic for serial iteration


# save path of trimmomatic in a variable fo reasiest use
Trim='/PATH TO DIRECTORY/trimmomatic.jar'


let i=1
for file in /PATH TO FOLDER CONTANING RAW DATA/*.fastq.gz  # Loop over the number of sample files   
do   
	#Run trimmomatic
	java -jar "$Trim" PE -phred33 NAME${i}_R1.fastq.gz NAME${i}_R2.fastq.gz -baseout out/NAME${i}.fastq ILLUMINACLIP:Nextera.fa:0:20:6 HEADCROP:12 SLIDINGWINDOW:4:20 MINLEN:30
	let i=$i+1
done
rm out/*U.fastq # Remove Unpaired Files


#EAMPLE
# save path
Trim='/home/mahnaz/Downloads/program/Bioinformatic/Trimmomatic/trimmomatic.jar'


let i=1
for file in /HOME/MAHNAZ/merged/*.fastq.gz  # Loop over the number of sample files   
do   
	#Run trimmomatic
	java -jar "$Trim" PE -phred33 EC${i}_R1.fastq.gz EC${i}_R2.fastq.gz -baseout out/EC${i}.fastq ILLUMINACLIP:Nextera.fa:0:20:6 HEADCROP:12 SLIDINGWINDOW:4:20 MINLEN:30
	let i=$i+1
done
rm out/*U.fastq # Remove Unpaired Files
