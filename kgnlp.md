<!-- TITLE: ELS Knowledge Graphs -->
<!-- SUBTITLE: NLP pipeline -->

# Overview
The current flow chains the following sub-processes:
1. [Tokenization](kgtkenization)
2. [PoS Tagging](PosTag)

# Postprocessing and patches
The postprocessing is a patch system that aims at fixing some errors that occurred during the main flow. As such it consiste of additional computing devices that are experimentally tested, and ultimately integrated in the regular flow when they are though to be valuable and stable enough.
Currently there are only one such patch, that aims at fixing some PoS issues.
## PoS patching
Very often no predicate could be extracted because of PoS errors. Such situations can be recognized when an HL does not contain any verbal chunk or phrase: for example a token that should have been tagged as VBP is instead tagged NN (this seems to happen quite frequently with termes such as *increase*, for instance).

The first attempt to tackle this problem is data driven, based on statistics extracted from most probably good taggings. 