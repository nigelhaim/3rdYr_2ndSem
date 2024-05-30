
Introduced by Dovitsky et al. (2021) to prove that classification is not only limited to CNN, but can be performed through a transformers that is applied directly through a sequence of images patches. The model splits the image to an equal fixed-size patches that are linearly embedded and added position embeddings to be fed on a transformer encoder. Dovitsky et al. (2021) added an extra learnable "classification token" similar to the standard approach to perform classification. It is designed to follow the original transformer architecture of Vaswani et al. (2017). It's only advantage is that is scalable NLP Transformer architectures because of their efficient implementations (Dovitsky et al., 2021). 


Dosovitskiy, A., Beyer, L., Kolesnikov, A., Weissenborn, D., Zhai, X., Unterthiner, T., Dehghani, M., Minderer, M., Heigold, G., Gelly, S., Uszkoreit, J., & Houlsby, N. (2021). _An image is worth 16x16 words: Transformers for image recognition at scale_ (arXiv:2010.11929; Version 2). arXiv. https://doi.org/10.48550/arXiv.2010.11929



Vaswani, A., Shazeer, N., Parmar, N., Uszkoreit, J., Jones, L., Gomez, A. N., Kaiser, L., & Polosukhin, I. (2023). _Attention is all you need_ (arXiv:1706.03762). arXiv. https://doi.org/10.48550/arXiv.1706.03762