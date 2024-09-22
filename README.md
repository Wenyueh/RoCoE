# Propagation and Pitfalls: Reasoning-based Assessment of Knowledge Editing through Counterfactual Tasks

## Abstract
Current approaches of knowledge editing struggle to effectively propagate updates to interconnected facts. In this work, we delve into the barriers that hinder the appropriate propagation of updated knowledge within these models for accurate reasoning.  To support our analysis, we introduce a novel reasoning-based benchmark -- **ReCoE** (**Re**asoning-based **Co**unterfactual **E**diting dataset) -- which covers six common reasoning schemes in real world. We conduct a thorough analysis of existing knowledge editing techniques, including input-augmentation, finetuning, and locate-and-edit. We found that all model editing methods show notably low performance on this dataset, especially in certain reasoning schemes. Our analysis over the chain-of-thought generation of edited models further uncover key attributors behind the inadequacy of existing knowledge editing methods from a reasoning standpoint, involving aspects on _fact-wise editing_, _fact recall_ ability, and _coherence_ in generation.



<img width="590" alt="Screen Shot 2024-09-21 at 11 47 21 PM" src="https://github.com/user-attachments/assets/c70f8c26-985d-40ce-87d1-4aadb058c282">

## ReCoE: Benchmark Introduction

### 6 sub-datasets in ReCoE:

1. _superlative_
   
3. _comparative_
  
5. _sorting_
  
7. _counting_
  
9. _aggregation_
   
11. _subtraction_
    
<img width="664" alt="Screen Shot 2024-09-21 at 11 58 00 PM" src="https://github.com/user-attachments/assets/83ce48d0-c2d7-4d88-8c21-9a8369ee2193">

### Basic dataset statistics:

<img width="317" alt="Screen Shot 2024-09-21 at 11 58 21 PM" src="https://github.com/user-attachments/assets/0fe5c1e5-15df-4dd4-a3c6-95461b07b1d3">

### Datapoint Format

Each datapoint encapsulates 5 key components:

$Q$: Question that corresponds to each of our defined reasoning schemes

$A$: Answer and aliases

$F$: Set of facts that supports the answer ($A$)

$CA$: Counterfactual answer and aliases

$CF$: Set of counterfactuals that supports the counterfactual answer ($CA$)

These components allow us to assess knowledge propagation by editing a language model with the set of counterfactuals $CF$, and testing if the edited model is able to flip its original answer ($A$) towards the counterfactual answer ($CA$) through reasoning.
