
# VirusFriends: discover viral sequences in the NCBI SRA!
## Please cite our work!
### DOI:DOI 10.17605/OSF.IO/Z4BCN 
### https://osf.io/4cn3j/

![Phage Friends!](images/friends.png =250x250)

## It's always sunny when you have phage friends, too

![virus friends](images/phagefriends2.png)

## VirusFriends is an implementation to discover viruses that are slightly related to already known ones. The idea is to use the genomes of known viruses as anchors to expand the viral sequence space. 

## What's the problem?
It's being estimated that there are 3x10^31 viral particles in the world, but only ~9,500 viral genomes have being described at a genomic level. This means there is a hughe amount of viruses to be discovered! 

## Why should we solve it?

# What is VirusFriends?

This is an implementation that is inpired on work developed on previous NCBI-hackatons as part of the Virus Discovery Project, the natural histor of this work is: SIDEARM --> Virome Sniff --> ViruSpy --> EndoVir --> VirusFriends
VirusFriends is the latest stage of the [Virus Discovery Project] (https://osf.io/4cn3j/) developed at several NCBI-sponsored hackathons 


Overview Diagram
![VirusFriends Pipeline](images/Workflow.png)
Step 1. Screen a set of SRA datasets for viral reference genomes and keep the "very good" hits and "weak hits"

Input: [a list of SRA ids] [a fasta file with the viral database]
Output: sam files, fasta files for weak viral hits, stats about number of hits,identity, etc ... for strong and weak hits

Step 2: Weak hits go into denovo assembly, viral motifs search and extension of the contigs
Input: [fasta file of weak hits]
Output: enriched contigs, weakly related to known viruses

# How to use <this software>

## Installation options:

We provide two options for installing <this software>: Docker or directly from Github.

### Docker

The Docker image contains <this software> as well as a webserver and FTP server in case you want to deploy the FTP server. It does also contain a web server for testi
ng the <this software> main website (but should only be used for debug purposes).

1. `docker pull ncbihackathons/<this software>` command to pull the image from the DockerHub
2. `docker run ncbihackathons/<this software>` Run the docker image from the master shell script
3. Edit the configuration files as below

### Installing <this software> from Github

1. `git clone https://github.com/NCBI-Hackathons/<this software>.git`
2. Edit the configuration files as below
3. `sh server/<this software>.sh` to test
4. Add cron job as required (to execute <this software>.sh script)

### Configuration

```Examples here```

# Testing

We tested four different tools with <this software>. They can be found in [server/tools/](server/tools/) .

# Additional Functionality

### DockerFile

<this software> comes with a Dockerfile which can be used to build the Docker image.

  1. `git clone https://github.com/NCBI-Hackathons/<this software>.git`
  2. `cd server`
  3. `docker build --rm -t <this software>/<this software> .`
  4. `docker run -t -i <this software>/<this software>`

### Website

There is also a Docker image for hosting the main website. This should only be used for debug purposes.

  1. `git clone https://github.com/NCBI-Hackathons/<this software>.git`
  2. `cd Website`
  3. `docker build --rm -t <this software>/website .`
  4. `docker run -t -i <this software>/website`


