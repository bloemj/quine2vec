# Paper data and code

This is the project page for the paper "Evaluating the consistency of word embeddings from small data". You can find the datasets used in the paper here.

UPDATE: Unfortunately, it does not appear that it's possible for us to release most of these datasets for copyright reasons, as the books from the Quine corpus are copyrighted, so the Quine-based sets have been made private. If you do own Word and Object and/or System of Logistic, contact us for the derived data sets. For other cases, rough corpus reproduction instructions are provided below.

Sentences randomly sampled from full corpus:

[Quine-all-rnd](https://github.com/bloemj/Quine-all-rnd)

Sentences from book halves of Word and Object:

[Quine-WordObject-halves](https://github.com/bloemj/Quine-WordObject-halves)

Sentences randomly sampled from Word and Object:

[Quine-WordObject-rnd](https://github.com/bloemj/Quine-WordObject-rnd)

Sentences from book halves of System of Logistic:

[Quine-Logistic-halves](https://github.com/bloemj/Quine-Logistic-halves)

Sentences randomly sampled from System of Logistic:

[Quine-Logistic-rnd](https://github.com/bloemj/Quine-Logistic-rnd)

Sentences randomly sampled from a Wikipedia snapshot:

[Wiki-rnd](https://github.com/bloemj/Wiki-rnd)

The next two datasets were only used for the domain comparison experiment summarized in Table 5 of the paper.

Sentences from book halves of Word and Object, with a different set of frequency-balanced words as target terms:
[Quine-WordObject-freqdata](https://github.com/bloemj/Quine-WordObject-freqdata)

Sentences from book halves of System of Logistic, with a different set of frequency-balanced words as target terms:
[Quine-Logistic-freqdata](https://github.com/bloemj/Quine-Logistic-freqdata)


## The Quine in Context corpus, v0.4
The Quine in Context dataset contains all philosophical texts written by W. V. Quine (228 books and articles from between 1932 and 2008) in plaintext format. Every file in the dataset corresponds to one single article or one section, chapter or essay of a book, resulting in a total of 818 files. The dataset has been produced from pdf files, which have been first OCR-ed, and then manually cleaned by the Quine in Context Project team (Katjoesja Kruiger, Suze van Scheers, Lisa Dondorp, Thijs Ossenkoppele, Maud van Lier, Yvette Oortwijn) and by the student cohorts of Arianna Betti's slow-reading class on Quine's Word and Object in 2015/16 and 2016/17 at the University of Amsterdam (https://quine1960.wordpress.com/about/), supervised by the project team. All data that is irrelevant to the content of the article or section has been removed. This includes information on the institution the article or book was published at, repeating headers with the title of the chapter and metadata. Some of the texts are formula-rich and/or symbol-rich: formulas and symbols were replaced by short codes (XfZ and XsZ), which function as place-holders. For precise instructions for cleaning, one can find the manual that was used [here]( https://docs.google.com/document/d/1UOEPdWxEmNs73N7nO2p2McfISfTryMzMSZw0e-VM_XM/edit?usp=sharing). This document contains all the settings to be used in the OCR software ABBYY Finereader, and all the steps for manual correction after processing by ABBYY. Subsequently, paragraph structure was detected and restored using purpose-built normalization scripts geared towards batches of texts displaying ranges of similar shortcomings, ad-hoc command lines and finally visual inspection - at times involving comparison to the book images - and manual editing by means of a good editor.

As described in the paper, the texts were then preprocessed with NLTK for sentence splitting and tokenization. A less common preprocessing step we took was to remove one-character tokens from the texts. These works contain many one-letter variable names, logical symbols and other formal language that a model might otherwise use to position vectors of Quine terminology in particular areas of the semantic space, as these tokens are highly infrequent in the general domain. For the books Word and Object and A System of Logistic, the book indexes were also OCR'd and manually corrected, in order to obtain the target terms used in the experiment.

