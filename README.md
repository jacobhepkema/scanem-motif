[![Docker Repository on Quay](https://quay.io/repository/jacobhepkema/scanem-motif/status "Docker Repository on Quay")](https://quay.io/repository/jacobhepkema/scanem-motif)

# scanem-motif
TOMTOM docker/singularity container for [**scanem**](https://github.com/jacobhepkema/scanem). Quay.io docker repo at [https://quay.io/repository/jacobhepkema/scanem-motif](https://quay.io/repository/jacobhepkema/scanem-motif) (see build status above). 

Usually this container is used in the Nextflow pipeline for [**scanem**](https://github.com/jacobhepkema/scanem). This container contains the MEME suite, which includes the Tomtom motif comparison tool<sup>1</sup>.

1. Shobhit Gupta, JA Stamatoyannopolous, Timothy Bailey and William Stafford Noble, "Quantifying similarity between motifs", Genome Biology, 8(2):R24, 2007. 

Run tools by prepending `/opt/bin` to your command, e.g. `/opt/bin/tomtom [args]`
