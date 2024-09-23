## Problem with the RNN

### Task to predict the next word
The color of the sky is _______ . output => blue

Here the blue only depends on the sky and color word . The dependency of blue word is not that much long. THis type of problem can be solved using simple RNN.

but

"I grew up in India  ..... I speak fluient _________" 

suppose this sentence is too long. the langaue depends on the country name here the country name is india. Since the sentence is too long . so we need long term dependency on language and country name. 

This type of sentence can not be slove using Simple RNN. We need long term depencency model. => long term dependency


### LSTM RNN
- Long Term Memory
- Short Term Memory

- Ht-1 => Hidden State of the previous time Stamp
- Xt => Word as passed as an input in the current time stamp.

## Forget Gate

-       Text                Next Word
-       x11, x12

Based on the some context, Forget Gate will let go some information or will not let go some infomation.

#### NOTE
    dimension of the Xt != or == dimension of the Ht-1 = dimension of the Ct-1

## Input Gate and  Candidate Memory
- If any information needed to be added it the memory then Ct-1 => The Information will be added
- we are adding some information. But in forget gate we are forgeting some of the information. 

## Output Gate
Its as short term memory.


## Training Data With LSTM
 1. word -> Vectors ->  Layer (word2vec)
 2. Embedding

## Varients of LSTM RNN
1. LSTM RNN - year 1970 to 1980
2. LSTM RNN varient by Gers & Schmidhuber - year 2000
3. Another Varient -> Coupling Forget amd I/P Gate
4. GRU -> Gated Recurrent Unit - 2014

## LSTM RNN varient by Gers & Schmidhuber
     Peephole Connection => The connection from memory cell to forget gate ,i/p Gate and O/p Gate. We let the agte layers look at the cell state.
## Another Varient -> Coupling Forget amd I/P Gate
    Instead of seperately deciding what to forget and what we should add new infomation, we make this decision together.

    GOAL : WE only forget when we are going to i/p something in its place.


   
## GRU -> Gated Recurrent Unit - 2014

 LSTM : it has 3 different gate ; Forget GATE, Input GATE + Candidate Memory, Output GATE Which is complex Architecture. Because of that traininig time increase.

Because of athat in GRU long term memory and short term memory get combined.

In GRU there are 3 
1. Update Gate
2. Reset Gate
3. Temporary Hidden State

    Update Gate => What context info needs to be Added 
                || depends on 
    Temporary hidden State => Current State


    if the current state is important then it will take less information from update Gate.