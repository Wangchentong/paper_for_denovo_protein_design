# paper_record


###  **Exploring evolution-based & -free protein language models as protein function predictors**  

Mingyang Hu & Fajie Yuan   [arxiv](https://arxiv.org/abs/2206.06583) || 2022

intro: ***treat af2 evofomer as a language model since traning with bert-like msa mask, do lots of benchmarking with funtion prediction, structure prediction and zeroshot,take out a view that evoformerblock is not SOTA for function task but esm-1b, which is not quite fair since different traning set. one curious is that why evofomer is so bad at zeroshot prediction? why as same class with msa transformer as defined by authour but got huge gap at zeroshot learning? whats logic behind that?     anyway,seems there's some gap at structure predcition and function prediction and not fixed by adding seq mask traning to structure predcition model***  
idea: ***pretraning evoformer at uniref like msa transfomer may be more properly to function task and may become SOTA. directly mask at 2d pair map of template is a possible way to do a strucutre pretraning or not? why af2 not use that like mask to msa? by the way, combine pretraning at seq level and structure level is definitely aa funture research direction***

