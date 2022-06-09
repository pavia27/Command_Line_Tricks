# Command_Line_Tricks
### Setting a global variable (makes large chunks of data slightly more readable)
***
`export variable=/Full/path`

`cd $variable` 

`export mgs=/home/mpavia/Tres_Rios/qc_metagenomes`

`cd $mgs`

### Convert csv to tsv
***
`perl -pe "s/,/\t/g;" CSV_file.csv > output_TSV_file.tsv`

### Count number of specific file types in a directory
***
`find *fa -type f | wc -l`

### Clean up gene names from prodigal output
***
`awk 'BEGIN{FS="#"}{if(/^>/){print ">"$1}else{print $0}}' prodiga_output.faa > clean_prodiga_output.faa`

### MOD to bash profile which allows you to search history (paste in .bash_profile
*** 
`bind '"\e[A": history-search-backward'`

`bind '"\e[B": history-search-forward'`

### Generate a contig to bin bin 
*** 
```for i in bin_directory/*.fa; do <br />
  bid=$(basename ${i%.fa}); <br />
  cat $i | grep ^'>' | cut -f1 -d' ' | tr -d '>' | sed 's/$/\t'$bid'/' >> output_name.map; <br />
  done```


