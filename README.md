### Dependencies

This script needs the [biogl](https://github.com/glarue/biogl) module to function properly. If you use (or can get) `pip`, you can simply do

```python3 -m pip install biogl```

to add the package to a location reachable by your Python installation. 

Otherwise, you can clone the `biogl` repo and source it locally (to run from anywhere, you'll need to add it to your PYTHONPATH environmental variable, a process that varies by OS):

```git clone https://github.com/glarue/biogl.git```

### Usage info

```
usage: cdseq [-h] [-t] [-e] [-i] [-c] [-m] [--tag tag] [-n] [-l]
             [--introns] [--truncate_introns int_length] [--print_arg_info]
             genome annotation

Extract transcript/coding sequences from a genome using an annotation file

positional arguments:
  genome                genome file in FASTA format
  annotation            annotation file in GFF[3]/GTF format

optional arguments:
  -h, --help            show this help message and exit
  -t, --translate       translate the output sequence (default: False)
  -e, --exon            use exons instead of CDS entries to define coding
                        sequence (default: False)
  -i, --isoforms        allow multiple isoforms per gene, instead of only
                        longest (default: False)
  -c, --coord_based_isoforms
                        detect isoforms by overlapping coordindates in
                        addition to shared parent (useful for annotations
                        without gene entries) (default: False)
  -m, --minimal_headers
                        omit detailed coordinate information from output
                        headers (default: False)
  --tag tag             prepend headers with specified <tag> (default:
                        None)
  -n, --non_coding      include non-coding (intronic, UTR, etc.) sequence;
                        uses only the coordinates of the transcript itself
                        (incompatible with --introns) (default: False)
  -l, --leave_lowercase
                        leave lowercase genomic sequence intact in output
                        (ignored if --introns) (default: False)
  --introns             include intron sequences in lowercase (incompatible
                        with -n) (default: False)
  --truncate_introns int_length
                        truncate intron sequences to length {int_length}
                        (or {int_length} -1 if odd) (default: None)
  --print_arg_info      print commented argument information before
                        sequence records (default: False)
```
