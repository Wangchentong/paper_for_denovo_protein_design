# paper_record


###  **Exploring evolution-based & -free protein language models as protein function predictors**  

Mingyang Hu & Fajie Yuan   [arxiv](https://arxiv.org/abs/2206.06583) || 2022

intro: ***treat af2 evofomer as a language model since traning with bert-like msa mask, do lots of benchmarking with funtion prediction, structure prediction and zeroshot,take out a view that evoformerblock is not SOTA for function task but esm-1b, which is not quite fair since different traning set. one curious is that why evofomer is so bad at zeroshot prediction? why as same class with msa transformer as defined by authour but got huge gap at zeroshot learning? whats logic behind that?     anyway,seems there's some gap at structure predcition and function prediction and not fixed by adding seq mask traning to structure predcition model***  
idea: ***pretraning evoformer at uniref like msa transfomer may be more properly to function task and may become SOTA. directly mask at 2d pair map of template is a possible way to do a strucutre pretraning or not? why af2 not use that like mask to msa? by the way, combine pretraning at seq level and structure level is definitely aa funture research direction***

###  **Protein Representation Learning by Geometric Structure Pretraining**

Zuobai Zhang & Jian Tang [arxiv](https://arxiv.org/abs/2203.06125) | 2022

intro: ***bring contrastive learning to protein graph representation,which shows to be a more useful pretraning task than mask for graph. another interesting try is multiedgetype node update method(Relational graph convolutional layer), a meaningful improvements from knn and radius-based neighbour node. thers's some difference on node update of gcn used in this and mpnn,update node by concat (node,edge,edge-twoward-node) or update node by add (updated-node-by-neighbour-ndoe and fc(edge)) which edge is updated by neighbour edge. maybe update edge by both neighbour node and edge concerned to protein mpnn may improve a litle bit? anymway,there's lots of ways to update node and edge,update edge by edge and node,update node by edge and node,update edge by edge,update node by node, need think and test more about combination.***
idea: ***pretraning by graph contrastive learning, split and update edge feature by diifferent type(which can combine position encoding to other edge by not individually present, other atom distance can be added and i think can take some advantage like protein mpnn) brings alot paper abour structure representation***
