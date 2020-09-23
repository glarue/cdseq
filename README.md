```
usage: cdseq [-h] [-t] [-e] [-i] [-c] [-v] [-n] [--introns]
             [--truncate_introns int_length]
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
  -v, --verbose_headers
                        include coordinate info in output headers (default:
                        False)
  -n, --non_coding      include non-coding (intronic, UTR, etc.) sequence;
                        uses only the coordinates of the transcript itself
                        (incompatible with --introns) (default: False)
  --introns             include intron sequences in lowercase (incompatible
                        with -n) (default: False)
  --truncate_introns int_length
                        truncate intron sequences to length {int_length} (or
                        {int_length} -1 if odd) (default: None)
```
