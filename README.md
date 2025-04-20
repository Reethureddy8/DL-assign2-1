Given an input embedding dimension of 256, a hidden state size of 256 for both the encoder and decoder, a sequence length of T = 20, and a vocabulary size of V = 60 (which is the same for both source and target), utilizing a 1-layer LSTM for both encoder and decoder along with greedy decoding during inference, the total number of operations conducted by the network is roughly 21.28 million. This is obtained using the formula:

Total Computations = T × [8k(m+k) + kV] = 20 × [8 × 256(256 + 256) + 256 × 60] = 21,278,720.

The overall count of trainable parameters present in the network is approximately 1.10 million, calculated using the formula:

Total Parameters = 2Vm + 8k(m + k + 1) + kV + V = 2 × 60 × 256 + 8 × 256 × (256 + 256 + 1) + 256 × 60 + 60 = 1,100,464.

For the training process, the top-performing model was trained with an embedding size of 256, hidden size of 256, and a 1-layer LSTM for both encoder and decoder, using a batch size of 64 and spanning 100 epochs. The model exhibited excellent transliteration results, achieving character-level accuracy of approximately 94% on the validation dataset. It successfully transliterated  Latin-script Hindi inputs into accurate Devanagari representations.
