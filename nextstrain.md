
Execute the following commands to build the tree:  
```
nextstrain shell .
augur tree -a {{ fasta-file }} -o tree_raw.nwk --nthreads N
augur refine --tree tree_raw.nwk --alignment {{ fasta-file }} --metadata {{ metadata.tsv }} --output-tree tree.nwk --output-node-data {{ nodes.json }} 
```

Execute the following commands to view the tree and follow the generated link:

```
export AUGUR_RECURSION_LIMIT=10000  
augur export v2 --tree tree_raw.nwk --metadata {{ metadata.tsv }} --output {{ output.json }}--node-data {{ nodes.json }} --colors colors.tsv
```