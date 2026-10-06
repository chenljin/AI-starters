# AI from First Principles

**Live site: https://chenljin.github.io/AI-starters/**

An interactive, single-page course that takes you from fitting a straight line to how Transformers, Mamba and large language models work. It is written for learners with undergraduate maths (calculus, linear algebra, basic probability) and no prior machine-learning background.

**56 concepts · 10 chapters · 40 live labs · about 13 hours of study**

Every concept page has:

- **The idea** in two sentences, and **the intuition** in plain language
- **The key formula**, typeset, with every symbol explained
- **How it works** in three steps, plus an **animated explainer** that plays those steps
- A **worked example** with real numbers you can check by hand
- A **live lab** for 40 of the 56 concepts: drag, slide and train things in the browser
- **Good to know** notes (pitfalls and practical tips), where you will meet it today, and links to the original papers

The home page groups concepts into chapters in a suggested learning order. The **Map** view shows how every concept builds on earlier ones. Mark concepts as learned to track your progress; progress is stored only in your own browser (localStorage).

## The course

1. **Learning from data** — 1 Machine learning (lab) · 2 Linear regression (lab) · 3 Gradient descent (lab) · 4 Logistic regression (lab) · 5 Maximum likelihood (lab) · 6 Overfitting & regularization (lab) · 7 Measuring performance (lab)
2. **The classic toolkit** — 8 k-nearest neighbors (lab) · 9 Decision trees & ensembles (lab) · 10 k-means clustering (lab) · 11 Principal component analysis (lab)
3. **Neural networks** — 12 The artificial neuron (lab) · 13 Multilayer perceptron (lab) · 14 Backpropagation (lab) · 15 Optimizers (lab) · 16 Initialization & normalization (lab) · 17 Dropout
4. **Seeing with convolutions** — 18 Convolution (lab) · 19 Convolutional networks (lab) · 20 Residual networks · 21 Transfer learning
5. **Sequences & language** — 22 Tokenization (lab) · 23 Embeddings (lab) · 24 Recurrent neural networks · 25 Long short-term memory (lab) · 26 Encoder–decoder with attention
6. **Transformers** — 27 Self-attention (lab) · 28 Positional encoding (lab) · 29 The Transformer block · 30 Encoders, decoders & masking · 31 Vision Transformer
7. **Beyond attention: state space models** — 32 Linear attention (lab) · 33 State space models (lab) · 34 Mamba: selective SSMs (lab)
8. **Generative models** — 35 Variational autoencoders · 36 Generative adversarial networks · 37 Diffusion models (lab) · 38 Flow matching (lab) · 39 Contrastive learning & CLIP · 40 Latent diffusion & guidance (lab)
9. **Reinforcement learning** — 41 Markov decision processes (lab) · 42 Q-learning & DQN (lab) · 43 Policy gradients (lab) · 44 Proximal policy optimization (lab)
10. **Large language models** — 45 Language modeling (lab) · 46 Pretraining & scaling laws (lab) · 47 Mixture of experts · 48 Decoding & sampling (lab) · 49 Efficient inference (lab) · 50 Prompting & in-context learning · 51 Supervised fine-tuning · 52 Low-rank adaptation (lab) · 53 Learning from human preferences · 54 Reasoning models (lab) · 55 Retrieval-augmented generation (lab) · 56 Tool use & agents

## Use it

It is one self-contained file: open `index.html` in a browser. The only external request is to Google Fonts; without it the page falls back to system fonts.

### Publish on GitHub Pages

1. Create a repository and add `index.html` (and this README) to its root.
2. In **Settings → Pages**, choose **Deploy from a branch**, branch `main`, folder `/ (root)`.
3. The course is then live at `https://chenljin.github.io/AI-starters/`. Any concept can be linked directly with its id, for example `https://chenljin.github.io/AI-starters/#attention` or `…/#mamba`.

## Edit and rebuild (optional)

`index.html` is generated from the sources in `source/`. To change a lesson:

```bash
cd source
npm install                 # MathJax (to pre-typeset formulas) and Playwright (for screenshots)
node build.mjs              # writes dist/index.html
node tools/lint-content.mjs # style checks for the lesson text
node tools/sweep.mjs        # opens every lesson, explainer slide and lab, and reports console errors
```

- `src/content/<chapter>.js`: lesson text, formulas (TeX), worked examples, references
- `src/anim/<chapter>.js`: tile art and the three-step explainer animations (Canvas 2D)
- `src/labs/<chapter>.js`: the live labs
- `src/app.js`, `src/style.css`, `src/body.html`, `src/core.js`: the site itself
- `SPEC.md`: the curriculum specification, writing style and the animation and lab APIs

Formulas are rendered to SVG at build time with MathJax, so the page needs no scripts from a CDN.

## Notes

Labs that simplify (a hand-made embedding, a fixed next-token distribution, an exact denoiser instead of a trained network) say so on screen. Reference links point to the original papers (mostly arXiv) and well-known tutorials.
