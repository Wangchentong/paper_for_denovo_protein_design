# paper_record


###  **Exploring evolution-based & -free protein language models as protein function predictors**  

Mingyang Hu & Fajie Yuan   [arxiv](https://arxiv.org/abs/2206.06583) || 2022

intro: ***treat af2 evofomer as a language model since traning with bert-like msa mask, do lots of benchmarking with funtion prediction, structure prediction and zeroshot,take out a view that evoformerblock is not SOTA for function task but esm-1b, which is not quite fair since different traning set. one curious is that why evofomer is so bad at zeroshot prediction? why as same class with msa transformer as defined by authour but got huge gap at zeroshot learning? whats logic behind that?     anyway,seems there's some gap at structure predcition and function prediction and not fixed by adding seq mask traning to structure predcition model. The most most most important problem here is that what kind of knowledge gap existense here stops the performance of structure pretraning model to beat seq model on function task as we naturely thought? i guess nobody knows till now. truely saying, this paper contribute to take out several question but not really answer it.***
idea: ***pretraning evoformer at uniref like msa transfomer may be more properly to function task and may become SOTA. directly mask at 2d pair map of template is a possible way to do a strucutre pretraning or not? by the way, combine pretraning at seq level and structure level is definitely a funture research direction***

###  **Protein Representation Learning by Geometric Structure Pretraining**

Zuobai Zhang & Jian Tang [arxiv](https://arxiv.org/abs/2203.06125) | 2022

intro: ***great paper. bring contrastive learning to protein graph representation,which shows to be a more useful pretraning task than mask for graph. another interesting try is multiedgetype node update method(Relational graph convolutional layer), a meaningful improvements from knn and radius-based neighbour node. thers's some difference on node update of gcn used in this and mpnn,update node by concat (node,edge,edge-twoward-node) or update node by add (updated-node-by-neighbour-ndoe and fc(edge)，oops, inital edge contains both node and distance feature) which edge is updated by neighbour edge.anymway,there's lots of ways to update node and edge,update edge by edge and node,update node by edge and node,update edge by edge,update node by node, need think and test more about combination.***  
idea: ***pretraning by graph contrastive learning, split and update edge feature by diifferent type(knn,radius-based,sequential-based) and brings a lot paper abour structure representation tips:update edge by edge might work better than update edge by node. brings full atom distance feature will absolutely give a improvement***

### **Multi-Scale Representation Learning on Proteins**
  
Vignesh Ram Somnath*, Charlotte Bunne* & Andreas Krause [NeurIPS](https://openreview.net/forum?id=-xEk43f_EO6) | 2021 [Code](https://github.com/vsomnath/holoprot)
  
intro: ***two-scale protein representation of protein, surface feature(vertices or superpixel) and structure feature, reduce surface vertices by combine them into k for each node and take out (min,max,mean,std) to represent a node. then get mean for node belong to same residue to combine with node feature to get initial structural graph representation. show great performance on ligand binding affinity with surface feature alone(perform bad on enzyme classification which resonable). two task both benefit from mutiscale graph than single scale graph alone. but to notice that structure graph alone is always better than surface graph and mostly comparable with mutiscale graph, which makes me thought that structure feature is enough for represent surface info on a properly network? since it performs well on ligand binding task like surface graph. Still,encode surface feature get some improvement in this paper.***   

### **Intrinsic-Extrinsic Convolution and Pooling for Learning on 3D Protein Structures**

Pedro Hermosilla ... & Timo Ropinski [ICLR](https://openreview.net/forum?id=l0mSUROpwY) | 2021 [Code](https://github.com/phermosilla/IEConv_proteins)  

intro : ***two major contribute: a new conv layer to aggregate neighbour node(low computation cost(fc(f_edge)*f_node),with edge of intrinsic(covalent bond,covalent bond + hydrogen bond) distance and extrinsic distance(elucidean distance)), pooling operator(not seems necessary on amino acid level) but herachichally reduce graph size to enable higher level representation(more hidden size with per node).*** pooling maybe benefit to protein level downstream task, conv layer seems too simple to handle complex far distance relationship. edge pool can get same result, check it out.  i believe conv with (elucidean distance,sequential distance) is enough to handel node relationship but only benchmark individually. encoding amino acid type with a embedding layer is better than encode directly by one hot? i guess both ok. second one can be visualized to test understand ability of network. also give some advice for other method's finetuning. Author give fair opinion about voxel-based method and GCNN-method, voxel-based:**why do need a new pool operator than just 3d conv on 3d grid?** unfortunately, grids donot scale well to fine structures or many atoms, and even more importantly, they do not consider the primary and secondary structure of proteins. GCNN approaches suffer from over-smoothing, i.e.,**indistinguishable node representations after stacking several layers**, which limits the maximum depthusable for such architectures.   

# Not very useful

***Structure-aware Protein Self-supervised Learning***   
intro: combine TransProt with GNN model to learn structure representation, not combine LM representation of seq in the initial node feature but at the end, to leverage seq info by a bi optimization step.More specificlly, create a gradient from gnn to LM to get a double loss, one from direct loss and one from LM which calculate by a liite param update by guidence of GNN. take a example, gnn tell LM to go for a way, and at next batch we see gnn's guidence is right or not, and update gnn's param from the delta theta(param change of LM). a liitle improvement(the benchmark seems not very promising) but a huge computation time up. simply update node by edge and node, again mutitype edge and all atom pair distance might work better. only predict distance(important) and dihedral angle(not very important), why not hide residue type? contrastive learning seems more desirable.   



