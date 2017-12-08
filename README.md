#SimPEL

SimPEL is short for Simulation-based Power Estimation for sequencing studies of Low-prevalence conditions. SimPEL addresses the need for power estimation in low-prevalence condition studies, taking into account their inherently small sample sizes and analytical procedures. SimPEL integrates customizable parameters to realistically model study design outcomes and provide applicable information towards further refinement of experimental procedure. SimPEL is implemented as a function of the established JAWAMix5 tool (Long et al., 2013)⁠, an HDF5-based Java implementation for association mapping.

Installation

A tarball will be available for download at https://owncloud.westgrid.ca/index.php/s/s4d86JjmRXycLKZ. The archive will include all mandatory input files. MD5 hash values for each of the files are also included in the download. As Java is platform independent and the software comes “batteries-included,” there is no specific installation required. The JAWAMix5 jar file is ready for immediate use, provided that Java has been installed in the system. Through this, users can easily verify that they indeed have the correct files and that no errors have occurred during the download and extraction process.

Please note that the files in the tarball are for user convenience. This allows users to start testing the program without the burden of locating and downloading multiple files from different websites. Once users have confirmed that they are able to run the program without any issues, it is strongly encouraged to download up to date files from the original websites and cite the updated publications for each file. Should users choose to use the included files in the tarball, please cite SimPEL in the publication as well as the following papers for the tarball files:

1000 Genomes Project Consortium, Auton, A., Brooks, L. D., Durbin, R. M., Garrison, E. P., Kang, H. M., … Abecasis, G. R. (2015). A global reference for human genetic variation. Nature, 526(7571), 68–74. https://doi.org/10.1038/nature15393

Jagadeesh, K. A., Wenger, A. M., Berger, M. J., Guturu, H., Stenson, P. D., Cooper, D. N., … Bejerano, G. (2016). M-CAP eliminates a majority of variants of uncertain significance in clinical exomes at high sensitivity. Nature Genetics, 48(12), 1581–1586. https://doi.org/10.1038/ng.3703

Lek, M., Karczewski, K. J., Minikel, E. V., Samocha, K. E., Banks, E., Fennell, T., … MacArthur, D. G. (2016). Analysis of protein-coding genetic variation in 60,706 humans. Nature, 536(7616), 285–291. https://doi.org/10.1038/nature19057

Usage

All parameters are implemented as:
java -Xmx4g -jar /filepath/jawamix5.jar simpel <parameters>.

An example command line is as follows:
java -Xmx4g -jar jawamix5.jar simpel -population_genotypes g1k_all.hdf5 -out example_output.txt -causal_gene_pool HLA_ErbB.txt -population_pedigree integrated_call_samples_v2.20130502.ALL.ped -all_genes gencode.v12.genenames.gtf -mafs ExAC.r0.3.1.sites.AC.txt -pathogenicity mcap_v1_0.txt -tmp_folder tmp_chrs/ -num_cases 10 -parents 8 -compound_het

In this example, all the files are present in current working directory. The number of case-control pairings is designated as 10, of which 8 of the controls are parents of the cases. Instances of compound heterozygosity will also be considered by the program, as indicated by the inclusion of the -compound_het flag.

For all file names, the file path must be specified if the file in question is not present in the current working directory.

Please refer the Users Manual for detailed descriptions.
