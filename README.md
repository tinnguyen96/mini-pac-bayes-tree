# mini-pac-bayes-tree

Essential files to construct the pac-bayes-tree and compare its test-set performance to that of some common tree-pruning approaches. Please refer to https://papers.nips.cc/paper/8158-pac-bayes-tree-weighted-subtrees-with-guarantees.pdf for details on definitions of penalty and priors. 
  
## Example uses 

### pac-bayes-tree: 
#### Example call and meaning of arguments 
python dataMaster_[ADDT_nS_master]_[eTS,MD].py 0 0 leakyAda effInt penFirst spam

1st argument: index into array of training sizes
2nd argument: index into array of training/testing splits 
3rd argument: penalty type 
4th argument: prior type
5th argument: order of optimization to tune hyper-parameters  
6th argument: dataset to experiment on 

#### Where are results saved?
For instance, "eTS/each experiment, each train size/spam-ADDT_nS_leakyAda_effInt-ex0tr0.npy" will store the test error of the pac-bayes-tree.

### tree-pruning 
#### Example call and meaning of arguments 
python dataMaster_[PkdDT_master]_[eTS,MD].py 0 0 effInt spam

1st argument: index into array of training sizes
2nd argument: index into array of training/testing splits 
3rd argument: prior type
4th argument: dataset to experiment on 

#### Where are results saved?
For instance, "eTS/each experiment, each train size/spam-PDDT_effInt-ex0tr0.npy" will store the test error of the tree-pruning. 

## Remarks
### Computational efficiency
pac-bayes-tree approaches have the same complexity as tree-pruning in the sense that the number of internal nodes visited at training/test time are roughly the same. The current implementation of pac-bayes-tree is slower than tree-pruning because of the extra precision necessary to compute weights for pac-bayes-tree. 
