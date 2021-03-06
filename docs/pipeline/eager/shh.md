# nf-core/configs: shh eager specific configuration

Extra specific configuration for eager pipeline

## Usage

To use, run the pipeline with `-profile shh`.

This will download and launch the eager specific [`shh.config`](../../../conf/pipeline/eager/shh.config) which has been pre-configured with a setup suitable for the shh cluster.

Example: `nextflow run nf-core/eager -profile shh`

## eager specific configurations for shh

Specific configurations for shh has been made for eager.

* If running with the MALT module turned on, the MALT process by default will be sent  to the long queue with a resource requirement minimum of 725GB and 64 cores. If this fails, the process will be tried once more only and sent to the supercruncher queue. The module will not retry after this, and pipeline will fail.
* Modifies the bwa aln `-n` parameter to 0.01, rather than typical default of 0.04, and `-l` to 32 (rather than 1024) to syncronise the (unpublished) parameter with EAGER1 and typical/expected usage within the department.
