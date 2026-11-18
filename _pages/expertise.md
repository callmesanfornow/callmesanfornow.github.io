---
permalink: /expertise/
title: "Expertise"
author_profile: true
---

I work where speech and language AI meets online safety. Each area below gives the problem, what I do about it, and where you can see the evidence. All examples come from my research, not from client work.

Multilingual and low-resource speech and NLP
===
**The problem:** most moderation and language tools are built for English and a handful of major languages, while many users speak low-resource languages or mix several in one sentence.

**What I do:** adapt pre-trained speech and text models (Whisper, wav2vec 2.0 / XLS-R, CLAP, multilingual transformers) to new languages with little labelled data, using few-shot learning, cross-lingual transfer and leave-one-language-out evaluation.

**Evidence:** [few-shot audio abuse detection across 10 Indian languages](/publication/sankaran2025towards) (COLING 2025); [few-shot contrastive adaptation with CLAP](https://arxiv.org/abs/2604.09094) (preprint); work under review on how language families shape cross-lingual transfer in speech encoders.

Content moderation and Trust & Safety
===
**The problem:** abuse increasingly arrives as voice notes, audio rooms and short videos, and transcribing it first loses tone and fails on informal or profane speech.

**What I do:** build and evaluate detection pipelines for abusive speech and text, analyse where and why they fail, and prototype monitoring tools quickly.

**Evidence:** abusive speech detection on the ADIMA benchmark across 10 Indian languages; a racist-narrative tracking pipeline built at the [Hack the Feed](/hack-the-feed/) hackathon.

Responsible AI and bias evaluation
===
**The problem:** a model can look accurate on average while failing badly for particular languages or groups, and content itself can carry stereotypes.

**What I do:** per-language and per-group error audits, bias detection, and LLM-based rewriting checked against human experts.

**Evidence:** [identifying and rectifying gender stereotypes in rhymes and poems](/publication/sankaran2024revisiting) (LREC-COLING 2024); ongoing work on how moderation errors are distributed across languages.

Choosing models and architectures
===
**The problem:** teams have to decide between transcribe-then-classify pipelines and models that work on the audio directly, and between many possible encoders, often without a fair comparison.

**What I do:** controlled, budget-matched comparisons with ablations that rule out the obvious confounds, turned into a recommendation that accounts for cost and language coverage.

**Evidence:** work under review comparing speech-to-text pipelines with direct audio classifiers across 10 Indian languages; in our tests, direct audio models came out ahead.

Generative AI and LLM prototyping
===
**The problem:** organisations want to know what LLMs can safely do for them before committing to a build.

**What I do:** rapid prototypes with LLMs and agents, evaluated against clear baselines and human judgement.

**Evidence:** LLM rewriting of stereotyped text benchmarked against educators ([LREC-COLING 2024](/publication/sankaran2024revisiting)); LLM agent tooling for automating my own experiments; hackathon builds.

Digital humanities and media analytics
===
**The problem:** media and cultural organisations want to understand language use in content and audiences at scale.

**What I do:** combine NLP with statistical analysis to study language choice, style and their link to audience success.

**Evidence:** [code-switching in K-pop hits on Billboard charts](/publication/sankaran2025global) (CHR 2025); [talks](/talks/) including one at TotalEnergies, Paris.

Teaching and training
===
I teach unsupervised learning sessions in a data science course at Télécom SudParis ([teaching](/teaching/)), and I enjoy explaining technical results to non-specialist audiences.

Get in touch
===
If you are working on multilingual moderation, Trust & Safety or Responsible AI, I would be glad to talk. Email me at [aditya-narayan.sankaran@telecom-sudparis.eu](mailto:aditya-narayan.sankaran@telecom-sudparis.eu) or connect on [LinkedIn](https://www.linkedin.com/in/aditya-narayan-san).
