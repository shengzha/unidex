# unidex
Universal demultiplexer for Adey Lab

Adjust default parameters in the unidex.cfg file to reflect paths and excutables to match your system.

Next, create a line in the config file for your application. Details are in the header for the file for how to set up a mode.


## Usage:
```
unidex [options]
```
### Info Options:
```
  -L          List modes present in the mode config file
              Can specifiy a different mode file with -m and it will list modes in that file.
  -I  [MODE]  Provide info on one or more comma separated modes as detailed in the specified
              modes file (-m or default).
```
### Run Options:
```
  -R  [STR]   Run Folder (where fastq files are present)
  -M  [LIST]  Mode list - modes must be specified in the modes.cfg file
              Modes must be comma separated and will demultiplex in specified order listed.
  -l          Delayed mode. Will wait until fastq files are propagated
              in the specified fastq directory (-r), then will run.
              Only works when specifying run name, not individual fastq files.
```
### Default Options:
```
  -O  [STR]   Output folder (def = run name, -R)
  -d  [INT]   Max allowed hamming distance (def = 2)
```
### Default Locations:
Defaults are specified in unidex.cfg, can be overridden here.
```
  -r  [PATH]  Fastq folder full path
  -o  [PATH]  Output folder
  -m  [STR]   Mode config file
```
### Fastq Input (default = auto detect):
```
  -1  [STR]   Read 1 fastq
  -2  [STR]   Index 1 fastq
  -3  [STR]   Index 2 fastq
  -4  [STR]   Read 2 fastq
```
### Other Options:
```
  -A  [STR]   Annotation file(s), comma separated with mode specified
              If only one mode is specified, then it will default to that mode
              [mode1]=[annot_file1],[mode2]=[annot_file2],etc... OR
                          First column of annot file designates mode for thast annot
  -u          Only report a read to the first mode that it matches (def = all)
  -n  [INT]   Only process the first n reads of the input fastq (def = all)
  -c  [STR]   File for compressing base triplets in reads names. (def = in unidex.cfg file)
              It is strongly discouraged to use a different file for this.
  -g  [STR]   Gzip command (def = in unidex.cfg file)
  -z  [STR]   Zcat command (def = in unidex.cfg file)
  -V          Verbose / debug mode (outputs to STDERR)
```
