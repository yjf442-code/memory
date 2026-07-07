# Attention Is All You Need

> **"Attention Is All You Need"** — Vaswani et al., 2017  
> Original paper introducing the **Transformer** architecture.

[![arXiv](https://img.shields.io/badge/arXiv-1706.03762-b31b1b.svg)](https://arxiv.org/abs/1706.03762)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)
[![NeurIPS 2017](https://img.shields.io/badge/NeurIPS-2017-blue.svg)](https://papers.nips.cc/paper/2017/hash/3f5ee243547dee91fbd053c1c4a845aa-Abstract.html)

---

## 📄 Abstract

The dominant sequence transduction models are based on complex recurrent or convolutional neural networks that include an encoder and a decoder. The best performing models also connect the encoder and decoder through an attention mechanism. We propose a new simple network architecture, the **Transformer**, based solely on attention mechanisms, dispensing with recurrence and convolutions entirely.

Experiments on two machine translation tasks show these models to be superior in quality while being more parallelizable and requiring significantly less time to train.

---

## 👥 Authors

- Ashish Vaswani (Google Brain)
- Noam Shazeer (Google Brain)
- Niki Parmar (Google Research)
- Jakob Uszkoreit (Google Research)
- Llion Jones (Google Research)
- Aidan N. Gomez (University of Toronto)
- Łukasz Kaiser (Google Brain)
- Illia Polosukhin

---

## 🗂️ Repository Structure

```
attention-is-all-you-need/
├── README.md               # This file
├── CITATION.bib            # BibTeX citation
├── LICENSE                 # CC BY 4.0
├── latex/                  # Full LaTeX source (from arXiv)
│   ├── ms.tex              # Main paper source
│   ├── introduction.tex
│   ├── model_architecture.tex
│   ├── background.tex
│   ├── why_self_attention.tex
│   ├── training.tex
│   ├── results.tex
│   ├── visualizations.tex
│   ├── parameter_attention.tex
│   ├── sqrt_d_trick.tex
│   ├── nips_2017.sty       # NeurIPS 2017 style file
│   ├── figures/            # Paper figures (PNG)
│   └── visualizations/     # Attention visualization figures (PDF)
└── assets/                 # Additional resources
```

---

## 🔑 Key Contributions

| Contribution | Description |
|---|---|
| **Transformer Architecture** | Encoder-decoder architecture using only self-attention |
| **Multi-Head Attention** | Attend to information from different representation subspaces |
| **Positional Encoding** | Inject sequence order information without recurrence |
| **Scaled Dot-Product Attention** | Efficient attention mechanism: `softmax(QK^T / √d_k)V` |

---

## 🏗️ Model Architecture

The Transformer follows an encoder-decoder structure:

- **Encoder**: Stack of N=6 identical layers, each with multi-head self-attention + feed-forward sublayers
- **Decoder**: Stack of N=6 identical layers with additional encoder-attention sublayer
- **Attention**: `Attention(Q, K, V) = softmax(QK^T / √d_k)V`
- **Multi-Head**: `MultiHead(Q,K,V) = Concat(head_1,...,head_h)W^O`

---

## 📊 Results

| Model | EN-DE BLEU | EN-FR BLEU | Training Cost (FLOPs) |
|---|---|---|---|
| Transformer (big) | **28.4** | **41.0** | 2.3 × 10^19 |
| ByteNet | 23.75 | — | — |
| Deep-Att + PosUnk | — | 39.2 | 1.0 × 10^20 |

---

## 📖 How to Compile the Paper

### Requirements
- TeX Live or MiKTeX
- Required packages: `natbib`, `amsmath`, `graphicx`, `hyperref`

### Build

```bash
cd latex
pdflatex ms.tex
bibtex ms
pdflatex ms.tex
pdflatex ms.tex
```

---

## 📚 Citation

```bibtex
@inproceedings{vaswani2017attention,
  title={Attention is all you need},
  author={Vaswani, Ashish and Shazeer, Noam and Parmar, Niki and
          Uszkoreit, Jakob and Jones, Llion and Gomez, Aidan N and
          Kaiser, {\L}ukasz and Polosukhin, Illia},
  booktitle={Advances in Neural Information Processing Systems},
  volume={30},
  year={2017}
}
```

---

## 📜 License

This paper is made available under [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

> **Source**: LaTeX source obtained from [arXiv:1706.03762](https://arxiv.org/abs/1706.03762)
