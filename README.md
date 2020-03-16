# FNAL DL-ana Scripts

These are scripts to sheppard the DL reco files (typically begins with `merged_dlreco`) through the Analysis chain.

The analysis chain includes:

* (optional) run filter, making reduced dlreco files
* run MPID on the dlreco files
* run shower code on dlreco files
* make final file
* mangle final file name with unique hex tag
* produce `json` file with SAM metadata

The SAM metdata is crucial to help with book-keeping. This should include:

* dl ana filename (with hex tag)
* parents list
* if MC, MC POT

# Workflow

Running a sample includes these steps

* Use scripts to query SAM and make an input filelist with all files
* Split the total list into digestable chunks, about 2K files each
* Prepare folder on reslilient with needed scripts, config files, and the input filelists
* Submit a condor jobs for each splits
* Collect list of output files and json files
* Register files to SAM

Below are instructions

(to do)

