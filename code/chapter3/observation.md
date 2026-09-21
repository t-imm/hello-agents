## N gram

Here the code multiply continuous Markov chains to find the similarity score (P(A|B)),
this is a bigram language model rather than frequency-based model.

## Word embedding

The displacement vector (difference) for vec(man)-vec(woman) is similar to vec(king)-vec(queen). 

## Byte-Pair Encoding (BPE)

It is a subword tokenization, always merge according to learned rules. Newer models moving toward SentencePiece or Unigram.

Even tokenizers may not have the best split:
```
understanding → understand + ing
understanding → underst + and + ing
```
still work because transformers operate on sequences and context.

The data structure is a merge ranking table, not a prefix tree, 
repeatedly merges according to the learned rankings

### Advantage

1. Does not need to store in Character level, which make need lots of token

2. Can handle unseen word which is form by sub word combination, 
```
hyperquantization -> hyper + quant + ization
```

3. Learn linguistic pieces
```
play -> play
playing -> play + ing
player -> play + er
players -> play + er +s
```