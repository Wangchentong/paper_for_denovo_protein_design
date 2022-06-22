# paper_for_denovo_protein_design
a paper list for denovo preotein design, incluede various field, some new progress and some classcial review, to help people who is newcomer for protein design

## About this repository

ths repo is not highly recommended for the latest progress in denovo design but mainly to introduce basic concept of it by list some classical and not too hard-reading paper, though we also list some new paper within it, i recommend that first read a few reviews and classical papers then jump into others. this repo will continuely update as soon as how often i read papers, every one is encouraged to edit this repo. the most important thing is i hope every paper in the list will be greate helpful to every new comer rather than very trival and uninovational.

## Menu

- [List of papers about Proteins Design](#paper_for_denovo_protein_design)
  - [About this repository](#about-this-repository)
  - [1. Reviews](#1-reviews)
  - [2. Scaffold generation](#2-scaffold-generation)
  - [Extra](#extra)

## 1. Reviews

### 1.1 **The coming of age of de novo protein design**  

Po-Ssu Huang, Scott E. Boyken & David Baker   [Nature](https://www.nature.com/articles/nature19946) || 2016

intro: ***author give a brief intro to denovo design, including physical principal and design strategy. A paper tell you what this field can do and what has been done. you can find a lot of progress here mainly made by traditional compuational design,notice that this paper published at 2016, when deep learning method hasn't show the great power but soon***  

### 1.2 **Recent advances in de novo protein design: Principles, methods, and applications**  

Xingjie Pan & Tanja Kortemme   [JBC Review](https://www.sciencedirect.com/science/article/pii/S0021925821003367) || 2021

intro: ***this paper gives a systematic introduction to diffrent subfield or pipeline of denovo protein design: backbone generation,sequence design,scoring function. Also introduce different ways denovo protein perform function like binding ligand,self assemble,membrane proteins and dynamic proteins, more close to the mainstream research direction***  

## 2. Scaffold generation 

### 2.1 **Sampling of Structure and Sequence Space of Small Protein Folds**

Linsky T*, Noble K* & Baker D, Strauch EM [bioarxiv](https://www.biorxiv.org/content/10.1101/2021.03.10.434454v1) || 2021

intro: ***a convenient tool for scaffold generation of specific topology, you only need to define the length variance and ss type with connection way, a great step to avoid define blueprint for each length and each abego to enumarately explore parameter space. Dynamic parameter sampling and sequential segment folding makes it more efficient than blueprint. There's some similarity between FoldArchitect(this paper) and topobuilder. Latter can accomodate motifs by using Funfoldes Mover, but former seems more intelligent when it comes to scaffold generation. very helpful if you need generate some simple topology scaffold(leave more complex one to deep learning method). blueprint and FoldArchitect,Topobuilder,rosetta remodel, i guess this is all you need for scaffold generation.***




## Extra
Computational design of self-assembling cyclic protein homo-oligomers [Nature](https://www.nature.com/articles/nchem.2673)  
***slide into contact and orginal rpx application***   
  
Rosetta FunFolDes – A general framework for the computational design of functional proteins [Plos](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1006623)  
***motif into scaffold, code might help?***    

The landscape of bispecific T cell engager in cancer treatment [BMC](The landscape of bispecific T cell engager in cancer treatment)  
***CART and BiTE, read to understand why CD3 is so important***    

Tertiary Structural Motif Sequence Statistics Enable Facile Prediction and Design of Peptides that Bind Anti-apoptotic Bfl-1 and Mcl-1 [Cell](https://www.cell.com/structure/fulltext/S0969-2126(19)30008-5?_returnURL=https%3A%2F%2Flinkinghub.elsevier.com%2Fretrieve%2Fpii%2FS0969212619300085%3Fshowall%3Dtrue)   
***might be useful***  
 
 
 
