## Paper reading 
I have been reading the main parts of this paper：**The Power of Contrast for Feature Learning: A Theoretical Analysis**  And I am currently working on the proof parts of this paper. Here is the summary of what I have read:

### Review of contrasive learning
There are two common approaches for feature extraction I am not familar with contrasive learning. So I read the SimCLR work.
![[Pasted image 20240618213000.png]]
1. A stochastic data augmentation that transforms the data into a positive pair
2. A neural network base encoder f (·) that extracts representation vectors from augmented data examples
3. A small neural network projection head g(·) that maps representations to the space (smaller dimension)
4. A contrastive loss function defined for a contrastive prediction task
In this paper, the second part is based on ResNet (He et al., 2016).

The Learning process
![[Pasted image 20240619003346.png]]
## Theoretical 