# stm32-data

`stm32-data` is a project aiming to produce clean machine-readable data about the STM32 microcontroller
families, including:

- :heavy_check_mark: Base chip information
    - RAM, flash
    - Packages
- :heavy_check_mark: Peripheral addresses and interrupts
- :heavy_check_mark: Interrupts
- :heavy_check_mark: GPIO AlternateFunction mappings (except F1)
- :construction: Register blocks for all peripherals
- :construction: DMA stream mappings
- :x: Per-package pinouts
- :heavy_check_mark: Links to applicable reference manuals, datasheets, appnotes PDFs.

:heavy_check_mark: = done, :construction: = work in progress, :x: = to do

## Data sources

These are the data sources currently used.

- STM32Cube database: describes all MCUs, with useful stuff like GPIO AF mappings, DMA stream mappings, pinouts...
- stm32-rs SVDs: register blocks. YAMLs are extracted and manually cleaned up.

## Install pre-requisites

In order to run the generator, you will need to install the following tools:

* `wget`
* `git`
* `jq`
* `svd` – `pip3 install svdtools` 

## Generating the YAMLs

- Run `./d download-all`
- Run `python3 parse.py`

This generates all the YAMLs in `data/` except those in `data/registers/`, which are manually extracted and cleaned up.

## Extracting new register blocks

TODO document
