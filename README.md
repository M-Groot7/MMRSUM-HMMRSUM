# MMRSUM-HMMRSUM
Beyond Text Unlocking Multimodal Magic": Harnessing New Reddit Thread Datasets for Multimodal Summarization

Overview
This project implements multimodal discourse summarization based on the MMRSUM and HMMRSUM datasets, which integrate both text and images for summarizing Reddit discussions. It uses advanced deep learning techniques to extract meaningful insights from Reddit threads, combining textual and visual elements into concise summaries.

 Key Features
 Multimodal Summarization:  Summarizes both text and images from Reddit threads.
 Codemixed Hinglish Summarization:  Includes a dataset (HMMRSUM) specifically designed for summarizing discussions in Hinglish.
 Relevant-Cluster-based Multi-stage Summarization (RCMS):  A five-step approach that clusters comments based on relevance, selects the most pertinent images, and generates comprehensive textual summaries.


1. The script is used for calculating the CLIPScore, which is essential for measuring the alignment between images and textual data in Reddit threads.
   - It processes text embeddings and image embeddings, computes the similarity score, and selects the most relevant images to be included in the final multimodal summary.

2. The script contains the main model implementation for the multimodal summarization task. It uses the RCMS approach to:
 - Cluster comments using RoBERTa-based sentence embeddings and Agglomerative Clustering.
     - Generate a textual summary using a transformer model (BART).
     - Integrate both textual and image elements for a holistic summarization of Reddit threads.
   - The model is evaluated using ROUGE and BERTScore for text, and CLIPScore for text-image alignment.

3. The research paper titled "Beyond Text Unlocking Multimodal Magic:  Harnessing New Reddit Thread Datasets for Multimodal Summarization" describes the creation and evaluation of the MMRSUM and HMMRSUM datasets. 
   - The paper introduces RCMS, discusses related work, and presents experimental results, showcasing the performance of the model compared to existing large language models (LLMs).

Prerequisites
- Python 3.x
- Libraries:
  - `transformers`
  - `torch`
  - `sentence-transformers`
  - `numpy`
  - `pandas`
  - `clip`

Datasets
 MMRSUM Dataset
- A dataset of 7130 Reddit threads that include both text and image components.
- Used for English-based multimodal summarization.

 HMMRSUM Dataset
- A codemixed (Hinglish) variant of the MMRSUM dataset for summarizing discussions in a blend of Hindi and English.

 Model Architecture
The model follows the RCMS (Relevant-Cluster-based Multi-stage Summarization) framework:
1. Clustering:  Uses agglomerative clustering with RoBERTa embeddings to group comments based on relevance.
2. Image Selection:  Uses CLIPScore to determine the most relevant images for the summary.
3. Text Summarization:  Generates concise, abstractive summaries using a BART-based model.
4. Image-Text Integration :  Combines the selected images with the generated textual summaries.
5. Evaluation:  The model is evaluated using ROUGE, BERTScore, and CLIPScore.




Results
The RCMS model  outperformed existing large language models such as GPT-3.5 and BART by approximately 6% on the ROUGE and BERTScore metrics.

 References
- [Multimodal Magic: Reddit Thread Summarization]


