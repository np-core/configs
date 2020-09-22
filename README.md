# configs

Nextflow configuration files for deployment in specific computing environments


[`Signal`](https://github.com/np-core/containers) environments are available for `Docker` and `Singularity` containers, as for instance configured in the default configuration file [`configs/nextflow.config`](https://github.com/np-core/configs/blob/master/nextflow.config). You can specifify a `Docker` container tag or `Singularity` [tags or image files](https://www.nextflow.io/docs/latest/singularity.html) with the `--container` parameter or the native `-with-docker` or `-with-singularity` `Nextflow` command line flags.

Resources can be configured hierarchically from the `configs/` submodule by selecting a configuration file with `--config` and a process resource configuration file with `--resource_config`. Execution environment profiles defined within the configuration files are selected with the native argument `-profile`

```
--container             path to container file or docker tag to provision pipeline
--config                select a configuration from the configs subdirectory of the pipeline

                        <nextflow>  base configuration with docker or singularity profiles
                        <jcu>       base configuration for the zodiac cluster at JCU
                        <nectar>    base configuration for the nectar cluster at QCIF

--resource_config       select a resource configuration nested within the selected configuration

                        <process>   base resource configuration of processes for compute servers        

-profile                select an resource and executor profile from the config file 

                        <docker> / <docker_gpu>  - expect container to be tag format
                        <singularity> / <singularity_gpu> - expect container to be path to image

```
