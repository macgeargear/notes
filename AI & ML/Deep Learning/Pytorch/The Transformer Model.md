[resource](https://towardsdatascience.com/illustrated-guide-to-transformers-step-by-step-explanation-f74876522bc0)
###### Outline
> Transformer Architecture
> 	The Encoder
> 	The Decoder
> Comparison to RNN and CNN

## The Transformer Architecture
- follows an **encoder-decoder** structure but does **not rely** on **RNN and CNN** to   generate an output.

- Maps an input sequence into abstracut continuous representation that holds all the learned information of that input. 


- Input Embeddings
- Positional Encoding 
- Encoder Layer
- Multi-Headed Attention
- Query, Key, and Value Vectors
- Dot Product of Query and Key
- Scaling Down the Attention Scores
- Softmax of the Scaled Scores
- Multiply Softmax Output with Value vector
- Computing Multi-headed Attention
- The Residual Connections, Layer Normalization, and Feed Forward Network
- Encoder Wrap-up
- Decoder Layer
