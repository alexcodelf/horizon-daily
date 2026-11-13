---
layout: default
title: "Horizon Summary: 2026-11-13 (EN)"
date: 2026-11-13
lang: en
---

> From 42 items, 15 important content pieces were selected

---

**Technology News**
1. [Rust 1.100 stabilizes never type, custom allocators, dependency cooldowns](#item-tech-news-1) ⭐️ 8.0/10
2. [Google releases Gemini 4 Hydrogen, reportedly replacing 3.8 Flash](#item-tech-news-2) ⭐️ 8.0/10
3. [Chips and Cheese Interviews AMD Designer Mike Clark on Zen 6](#item-tech-news-3) ⭐️ 8.0/10
4. [UMAP 0.6 adds recursive initialization and new optimizers](#item-tech-news-4) ⭐️ 8.0/10
5. [2016 Essay on Why Correct Software Is Hard Resurfaces](#item-tech-news-5) ⭐️ 7.0/10
6. [smolmaxxing claims 16B LLMs on sub-1GB legacy hardware](#item-tech-news-6) ⭐️ 7.0/10
7. [Microsoft 365 email outage drags on as Microsoft applies recovery fix](#item-tech-news-7) ⭐️ 7.0/10
8. [PostgreSQL type-confusion writeup claims CVE-2026-6460 RCE chain](#item-tech-news-8) ⭐️ 7.0/10
9. [Independent audit reports no retinotopy or tonotopy in Meta&\#x27;s TRIBE v2](#item-tech-news-9) ⭐️ 7.0/10
10. [Survey of NeurIPS, ICML, ICLR Desk-Rejection Rules Since 2013](#item-tech-news-10) ⭐️ 7.0/10
11. [Google launches Gemini Decisions API for fast multimodal decisions](#item-tech-news-11) ⭐️ 7.0/10
12. [US Commerce Department finalizing rule to block Chinese AI firms&\#x27; remote chip access](#item-tech-news-12) ⭐️ 7.0/10
13. [Apple details Secure Exclaves and iPhone 18 Pro indicator checks](#item-tech-news-13) ⭐️ 7.0/10

**Financial News**
1. [NVIDIA CEO 黄仁勋 resigns; CFO Colette Kress named interim CEO](#item-finance-news-1) ⭐️ 9.0/10
2. [China approves Eli Lilly&\#x27;s oral weight-loss drug, its first oral GLP-1](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Rust 1.100 stabilizes never type, custom allocators, dependency cooldowns](https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/) ⭐️ 8.0/10

Rust 1.100 has been released, stabilizing the never type and custom allocators. Cargo now supports a minimum publish age for dependency cooldowns \(RFC 3923\), reports unused dependencies by default with the \`cargo::unused\_dependencies\` lint set to warn, and makes \`cargo install\` use the lockfile inside the \`.crate\` tarball by default, turning \`--locked\` into a no-op.

hackernews · mbStavola · Nov 12, 18:39 · [Discussion](https://news.ycombinator.com/item?id=50472038)

**「Background」** Rust&\#x27;s release train delivers a new stable toolchain on a regular cadence, with Cargo shipped alongside the compiler. Cargo resolves crate versions and records the chosen ones in \`Cargo.lock\`; that lockfile keeps subsequent builds pinned, while resolver settings determine which published versions are eligible in the first place. The never type \`\!\` denotes an expression that never produces a value, such as a diverging function or \`panic\!\`, and stabilizing it lets stable Rust code use it as a normal type.

**「Impact」** Projects that set Cargo&\#x27;s minimum publish age will ignore dependency versions newer than that threshold unless they are already recorded in \`Cargo.lock\`, so maintainers can delay adoption of newly published dependency versions without rewriting lockfiles.

**「Community discussion」** Hacker News commenters highlighted dependency cooldowns, unused-dependency warnings, and the \`cargo install\` lockfile change as practical improvements, and some pointed to stabilized APIs omitted from the post such as \`bool::toggle\(\)\`, \`Box::map\(\)\`, and \`trim\_prefix\`/\`trim\_suffix\`. One commenter described \`DropGuard\` as similar to Go&\#x27;s \`defer\`.

**Tags**: `#Rust`, `#Cargo`, `#language features`, `#dependency management`, `#custom allocators`

---

<a id="item-tech-news-2"></a>
### [Google releases Gemini 4 Hydrogen, reportedly replacing 3.8 Flash](https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/) ⭐️ 8.0/10

Google&\#x27;s blog published a post introducing Gemini 4 Hydrogen, a new model in its Gemini lineup, but the post text was not available for review, so the model&\#x27;s capabilities, context limits, and availability terms remain unconfirmed. Hacker News users report the model replaced Gemini 3.8 Flash in the Gemini app immediately on release, and one commenter deduced from its placement in Search and a stated 2.5x speed advantage over 3.8 Flash that Hydrogen is the new entry-level model intended to replace 3.5 Flash Lite. That same commenter says Hydrogen is priced at the same rate as undiscounted 3.8 Flash, considerably above what users currently pay for 3.8 Flash or 3.5 Flash Lite — a pricing claim that comes from the discussion rather than verified source material.

hackernews · dvaplima · Nov 12, 18:01 · [Discussion](https://news.ycombinator.com/item?id=50471431)

**「Background」** Google&\#x27;s model card describes Gemini 4 Hydrogen as aimed at &quot;everyday coding and agentic workflows&quot;—multi-step tasks in which a model calls tools and takes actions. OpenRouter lists the model as released on Nov. 12, 2026, and Google&\#x27;s announcement frames it as fast and cost-efficient.

**「Migration and cost checks for 3.8 Flash users」** Teams currently on Gemini 3.8 Flash face an in-place substitution: Google&\#x27;s own post frames Hydrogen as a standalone upgrade for those migrating from 3.8 Flash, claiming tasks finish about 2.5x faster, so existing prompts and evaluations tuned to 3.8 Flash should be re-run rather than assumed to carry over. Cost is the second concern — the model appeared in Google Cloud&\#x27;s billing catalogue, and a commenter reports it is priced at the non-discounted 3.8 Flash rate, well above the discounted rates teams report paying today, so budgets should be rechecked before switching production traffic.

**「Community discussion」** Commenters criticized the element- and molecule-based naming scheme, arguing that names like Hydrogen and Argon carry no intuitive sense of relative capability and make it harder to compare models that are meant to be alternatives. Others questioned the pricing, asking whether Google is abandoning its &quot;fast and cheap&quot; tier, while a separate thread reported account suspensions with no stated reason for command-line tool use and listed reliability and feature gaps versus OpenAI&\#x27;s offerings.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/">Introducing Gemini 4 Hydrogen for Agentic Workflows</a></li>
<li><a href="https://openrouter.ai/google/gemini-4-hydrogen">Gemini 4 Hydrogen - API Pricing &amp; Providers | OpenRouter</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-4-hydrogen/">Gemini 4 Hydrogen - Model Card — Google DeepMind</a></li>
<li><a href="https://www.youtube.com/watch?v=ufOH8dSzfPM">GEMINI 4 HYDROGEN IS ALMOST HERE?! Gemini ... - YouTube</a></li>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/introducing-gemini-4-hydrogen/">Introducing Gemini 4 Hydrogen for Agentic Workflows</a></li>

</ul>
</details>

**Tags**: `#Gemini`, `#Google AI`, `#large language models`, `#model release`, `#AI pricing`

---

<a id="item-tech-news-3"></a>
### [Chips and Cheese Interviews AMD Designer Mike Clark on Zen 6](https://chipsandcheese.com/p/talking-zen-6-with-mike-clark-at) ⭐️ 8.0/10

Chips and Cheese published an in-depth interview with AMD CPU designer Mike Clark centered on Zen 6. The piece is aimed at readers interested in processor architecture and hardware engineering, according to the available summary. The supplied material does not include specific Zen 6 technical details, timelines, or product claims, so the interview&\#x27;s concrete findings cannot be assessed here.

hackernews · dverlaeckt80 · Nov 12, 14:12 · [Discussion](https://news.ycombinator.com/item?id=50467460)

**「Background」** Zen 6 is AMD&\#x27;s successor to the Zen 5 core line, and this interview centers on how the design evolved from Zen 5 and on what separates Zen 6 from the smaller Zen 6c variant. Chips and Cheese has interviewed the same AMD architect before; its July 2024 video interview with him, published as a transcript, discussed his work as chief architect of Zen. The new piece follows that transcript format, with the published conversation edited for readability and conciseness.

**「Community Discussion」** Commenter koutakun described the interview as a rare instance of a CPU designer going into unusual depth. That is a reader reaction, not independent confirmation of the interview&\#x27;s technical claims.

<details><summary>References</summary>
<ul>
<li><a href="https://chipsandcheese.com/p/talking-zen-6-with-mike-clark-at">Talking Zen 6 with Mike Clark at AMD In-Depth</a></li>
<li><a href="https://chipsandcheese.com/p/a-video-interview-with-mike-clark-chief-architect-of-zen-at-amd">A Video Interview with Mike Clark, Chief Architect of Zen at AMD</a></li>

</ul>
</details>

**Tags**: `#AMD Zen 6`, `#CPU architecture`, `#hardware engineering`, `#semiconductor industry`, `#technical interview`

---

<a id="item-tech-news-4"></a>
### [UMAP 0.6 adds recursive initialization and new optimizers](https://www.reddit.com/r/MachineLearning/comments/1xudaah/umap_06_new_initialization_new_optimizers_and/) ⭐️ 8.0/10

UMAP 0.6 is released with a recursive initialization scheme that uses UMAP itself, new optimizers built around more effective hard-negative mining, and nearest-neighbor search reported about 4x faster through better use of PyNNDescent. The maintainer reports that a 3-million-paper arXiv dataset finishes in under five minutes, while a seeded UMAP 0.5 run was single-threaded and took 52 minutes, described as 12x longer; the new optimizers also allow reproducible seeded runs while using every core. The new initialization and optimizers are opt-in in this version and change the output; users enable them with compatibility\_layout=False, and they are slated to become the default in future versions.

reddit · r/MachineLearning · /u/lmcinnes · Nov 12, 13:51

**「Background」** UMAP is a dimensionality reduction library that lays out high-dimensional data in a lower-dimensional space while preserving neighborhood structure. Before version 0.6, UMAP used spectral or PCA initialization and an optimizer designed around a narrow portion of the attraction-repulsion spectrum; a seeded version 0.5 run was also single-threaded.

**「Impact」** Practitioners testing the new behavior must set compatibility\_layout=False and should expect different embeddings from previous UMAP versions. Users who need the existing output can keep the default in 0.6, while those working with million-scale datasets can try the release&\#x27;s improved large-scale layout quality and faster nearest-neighbor search.

**Tags**: `#UMAP`, `#dimensionality reduction`, `#machine learning`, `#open-source software`, `#performance optimization`

---

<a id="item-tech-news-5"></a>
### [2016 Essay on Why Correct Software Is Hard Resurfaces](https://pron.github.io/posts/correctness-and-complexity) ⭐️ 7.0/10

A 2016 essay titled Why writing correct software is hard and why math \(alone\) won’t help us resurfaced on Hacker News, arguing that mathematical correctness is not sufficient for reliable software because acceptable behavior and real-world inputs still have to be defined. The repost drew 348 points and 166 comments debating formal specification, Rice’s Theorem, and the difficulty of specifying acceptable inputs, outputs, and intermediate states. No new version, tool, or implementation is announced; the item is a renewed discussion of the earlier essay.

hackernews · AriFordsham · Nov 12, 10:28 · [Discussion](https://news.ycombinator.com/item?id=50465352)

**「Background」** The piece originated as a 2016 Curry On talk by Ron Pressler and was published that July as an essay reviewing results from computability theory and complexity theory to argue that programs and complete understanding—the precondition for correctness—are fundamentally at odds. Its November 2026 appearance on Hacker News is a resurfacing of that 2016 write-up, not a new publication.

**「Impact」** For developers weighing formal verification, the practical consequence is that proof work depends on a prior specification decision: a verifier can check a stated property, but it cannot establish that the chosen inputs and outputs are the right ones.

**「Community discussion」** Commenters disagreed over what formal correctness can deliver: turbobutton argued mathematical correctness must be separated from real-world operation, while mpweiher asked how one knows a specification is itself correct. johnbender disputed the essay’s reading of Rice’s Theorem, saying it rules out a general method for all programs, not one-off proofs about a specific program.

<details><summary>References</summary>
<ul>
<li><a href="https://pron.github.io/posts/correctness-and-complexity">Why Writing Correct Software Is Hard - Ron Pressler</a></li>
<li><a href="https://upstract.com/x/72ef0f8da3aa6cdc">Why Writing Correct Software Is Hard - upstract.com</a></li>

</ul>
</details>

**Tags**: `#formal verification`, `#software correctness`, `#complexity`, `#specification`, `#programming languages`

---

<a id="item-tech-news-6"></a>
### [smolmaxxing claims 16B LLMs on sub-1GB legacy hardware](https://github.com/hyperionaidev/smolmaxxing/) ⭐️ 7.0/10

An open-source project called smolmaxxing claims it can run models with up to 16 billion parameters on a first-generation iPad Air and a Xiaomi TV box, each with less than 1 GB of usable memory. The author, mrashad74, says the effort includes custom kernels, modified model weights published on Hugging Face, and results intended for reproduction, with “decent speeds given the hardware.” The performance figures are self-reported and have not been independently verified.

hackernews · mrashad74 · Nov 12, 15:23 · [Discussion](https://news.ycombinator.com/item?id=50468888)

**「Why a 16B model can fit in 1 GB」** The approach relies on mixture-of-experts models: rather than loading all weights into RAM, the project keeps only the experts needed for a given step in memory and reads the remainder from flash storage as required. That distinction explains how a 16B-parameter model can be described as running on devices with about 1 GB of usable memory even though its full weights do not fit there.

**「Impact」** Developers working on local inference can try to reproduce the kernels and modified weights on similarly constrained hardware, but should treat the 16B result as an unverified benchmark until memory use, speed, and output quality are independently measured.

**「Community discussion」** Commenters were split: one argued that coding agents can now produce inference engines for arbitrary old hardware from a single prompt, so the engineering novelty is limited, while others welcomed the small-model optimization trend and shared their own work on much smaller locally trained models. A separate thread questioned whether such small models are useful for practical tasks.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/hyperionaidev/smolmaxxing/">GitHub - hyperionaidev / smolmaxxing : maxxing the ability to run...</a></li>

</ul>
</details>

**Tags**: `#local LLM inference`, `#edge devices`, `#model optimization`, `#open source`, `#low-memory computing`

---

<a id="item-tech-news-7"></a>
### [Microsoft 365 email outage drags on as Microsoft applies recovery fix](https://status.cloud.microsoft/) ⭐️ 7.0/10

Microsoft 365 customers reported prolonged email outages on November 12–13, while Teams chat and meetings and Azure infrastructure appeared largely unaffected, according to commenters. Microsoft said it had validated an alternative health-check method on a subset of affected infrastructure, bringing those servers back into service, and was applying the change more broadly. It was also preparing an automated recovery process to continually detect and restart unresponsive servers. The Microsoft status page itself was not working well, and at least one commenter relied on its RSS feed for updates.

hackernews · dkpk · Nov 12, 18:20 · [Discussion](https://news.ycombinator.com/item?id=50471731)

**「Context」** Microsoft 365 bundles Outlook, Teams, Word, Excel, PowerPoint and Copilot, and users reported problems reaching all of them on Thursday, Nov. 12; the outage-tracking site Down Detector logged nearly 130,000 reports of Microsoft 365 issues. Amazon Web Services said it was &quot;operating normally&quot; and disputed inaccurate reports of outages on its own platforms, indicating the disruption was specific to Microsoft rather than a broader cloud-provider failure.

**「Impact」** For affected organizations, email was unavailable for hours while Teams remained usable, forcing incident response onto other channels; the degraded status page also meant at least one admin had to use Microsoft&\#x27;s RSS feed to follow recovery updates.

**「Community Discussion」** Commenters reported receiving no email for about 5.5 hours and called it their organization&\#x27;s worst Microsoft 365 outage since adopting the service in 2019. One user also said Outlook desktop could not reach a self-hosted mail account because Microsoft acts as the relay when the account is added.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/12/microsoft-outage-outlook-aws-google.html">Widespread Microsoft outage takes down Outlook and other 365 ...</a></li>
<li><a href="https://www.theguardian.com/technology/2026/nov/13/microsoft-outage-outlook-teams-word-excel-reports">Global Microsoft outage affects Outlook and Teams users, with ...</a></li>

</ul>
</details>

**Tags**: `#Microsoft 365`, `#cloud outage`, `#service reliability`, `#sysadmin`, `#incident response`

---

<a id="item-tech-news-8"></a>
### [PostgreSQL type-confusion writeup claims CVE-2026-6460 RCE chain](https://mehmetince.net/part-3-6-how-i-ended-up-turning-a-22-year-old-postgresql-type-confusion-primitive-into-rce-cve-2026-6460/) ⭐️ 7.0/10

A technical writeup describes turning a 22-year-old PostgreSQL type-confusion primitive into an exploit chain tracked as CVE-2026-6460, which the author frames as remote code execution. The supplied material does not include affected PostgreSQL versions, patch status, or independent validation, so the RCE characterization remains a research claim rather than a confirmed, broadly applicable vulnerability assessment.

hackernews · ozirus · Nov 12, 18:22 · [Discussion](https://news.ycombinator.com/item?id=50471761)

**「Background」** PostgreSQL&\#x27;s fixes for CVE-2026-6460 landed in a security release carrying 52 new CVEs, six of them connected to this research, according to the writeup; Phoronix&\#x27;s roundup lists CVE-2026-6460 as a type-confusion issue involving ALTER ... SET DATA TYPE with a CVSS score of 8.8. The writeup says the umbrella fix introduces versioning for composite attributes, addressing the conditions under which an attribute could be interpreted using the wrong type layout.

**「Who is actually exposed」** The exposure is bounded by DDL privileges rather than network reach: Red Hat&\#x27;s advisory describes an authenticated user with permission to create or alter database objects triggering the type confusion through commands such as altering a column&\#x27;s data type, and PostgreSQL&\#x27;s own entry says the flaw lets an object creator execute arbitrary code as the operating system user running the database. That makes privilege review as important as patching — any role granted CREATE or ALTER rights on a shared instance, including multi-tenant deployments where tenants can define their own objects, should be treated as able to reach the host account. The advisory also notes other DDL routes besides ALTER ... SET DATA TYPE, such as ALTER TABLE ... ADD COLUMN followed by ROLLBACK and another ADD COLUMN, so filtering a single statement is not sufficient mitigation; the CVSS score published for the CVE is 8.8.

**「Community discussion」** Commenters disputed the RCE label, arguing that the described exploits require an authenticated database account and are better classified as privilege escalation; one said the issue mainly affects multi-tenant databases. Another commenter focused on the underlying design, calling the handling of a PostgreSQL Datum and its separately stored type ID worse than a code smell.

<details><summary>References</summary>
<ul>
<li><a href="https://www.phoronix.com/news/PostgreSQL-52-CVEs">PostgreSQL Sees New Releases For 52 Security... - Phoronix</a></li>
<li><a href="https://mehmetince.net/part-3-6-how-i-ended-up-turning-a-22-year-old-postgresql-type-confusion-primitive-into-rce-cve-2026-6460/">Part 3/6 | How I Ended Up Turning a 22-Year-Old PostgreSQL ...</a></li>
<li><a href="https://www.postgresql.org/support/security/CVE-2026-6460/">PostgreSQL: CVE-2026-6460: PostgreSQL type confusion after ...</a></li>
<li><a href="https://cvetodo.com/cve/CVE-2026-6460">CVE-2026-6460: PostgreSQL Type Confusion (CVSS 8.8) | CVETodo</a></li>
<li><a href="https://access.redhat.com/security/cve/cve-2026-6460">CVE-2026-6460 - Red Hat Customer Portal</a></li>

</ul>
</details>

**Tags**: `#PostgreSQL`, `#security vulnerability`, `#CVE-2026-6460`, `#exploit research`, `#privilege escalation`

---

<a id="item-tech-news-9"></a>
### [Independent audit reports no retinotopy or tonotopy in Meta&\#x27;s TRIBE v2](https://www.reddit.com/r/MachineLearning/comments/1xuillf/does_metas_brainresponse_model_tribe_v2_actually/) ⭐️ 7.0/10

An independent, self-funded audit of Meta&\#x27;s TRIBE v2, a model that predicts fMRI responses from video, audio, and text, reported no recovered retinotopic maps \(d=0.05, not significant\) or tonotopic maps \(rho=-0.07, not significant, even with loudness controlled\), but strong motion selectivity in MT+ \(d=4.31, 52x enrichment over chance\). The author says an apparent eccentricity effect became significant and &quot;correct&quot; only under three stimulus-geometry controls, indicating an image-statistics confound rather than a positional code. The findings are a single-author Reddit post and have not been peer reviewed or independently verified; the post links code and a paper, but the supplied excerpt does not include figures or full results.

reddit · r/MachineLearning · /u/Own\_Tank1283 · Nov 12, 17:16

**「Background」** TRIBE v2 is Meta&\#x27;s tri-modal brain-encoding model, released in March 2026 with its codebase, paper, and demo, that predicts fMRI responses to naturalistic video, audio, and text by mapping multimodal representations onto the cortical surface. Retinotopy and tonotopy—the orderly visual and auditory maps of space and frequency—are classically probed with controlled checkerboard, hemifield, and tone-sweep stimuli rather than the naturalistic inputs TRIBE v2 targets.

**「Impact」** For neuro-AI researchers, the audit implies TRIBE v2 should not be used as a stand-in for retinotopic or tonotopic mapping, and apparent eccentricity effects need stimulus-geometry controls before being read as positional coding; its reported motion selectivity in MT+ is the one topographic signature the author says was recovered.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/facebookresearch/tribev2">GitHub - facebookresearch/tribev2: This repository contains ...</a></li>
<li><a href="https://ai.meta.com/blog/tribe-v2-brain-predictive-foundation-model/">Introducing TRIBE v2: A Predictive Foundation Model Trained ...</a></li>

</ul>
</details>

**Tags**: `#neuro-AI`, `#model validation`, `#fMRI encoding models`, `#reproducibility`, `#TRIBE v2`

---

<a id="item-tech-news-10"></a>
### [Survey of NeurIPS, ICML, ICLR Desk-Rejection Rules Since 2013](https://www.reddit.com/r/MachineLearning/comments/1xu08e7/how_to_get_deskrejected_at_neuripsicmliclr_d/) ⭐️ 7.0/10

A Reddit post by /u/martincsweiss presents the author&\#x27;s own review of every NeurIPS, ICML, and ICLR call for papers, author guide, and ethics/LLM policy page since 2013, using Wayback snapshots taken near each deadline, to compile reasons a paper can be rejected without review. The author reports that until 2023 all such rules concerned the paper itself — page limits, anonymity, dual submission — whereas current rules also cover author behavior: lacking reciprocal reviewing, a co-author&\#x27;s negligent reviewing, LLM use in some cases, false conflict declarations, collusion, and an out-of-date OpenReview profile. The post links to an ICML blog post on violations of LLM review policies as supporting material. This is a community-compiled survey rather than an independently verified or conference-endorsed accounting, and no per-conference breakdown of the rules is included in the post.

reddit · r/MachineLearning · /u/martincsweiss · Nov 12, 01:51

**「Background」** Desk rejection is rejection without peer review, historically used for paper-level violations such as page limits, anonymity, or dual submission. ICML&\#x27;s January 8, 2026 peer-review policy said LLM-use violations could lead to desk rejection of the submission or all submissions by the authors; its March 18, 2026 post reported 497 desk rejections, about 2% of submissions, tied to 398 reciprocal reviewers who violated those rules.

**「Impact for authors」** The practical consequence for authors is that compliance now extends beyond the manuscript: submission-time obligations include keeping OpenReview profiles current, declaring conflicts accurately, and ensuring co-authors meet reviewing duties, since the post says a co-author&\#x27;s negligent reviewing can itself trigger desk rejection. Researchers submitting to these venues should check each conference&\#x27;s current author guide and ethics/LLM policy rather than relying on the paper-format rules that dominated before 2023.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.icml.cc/2026/03/18/on-violations-of-llm-review-policies/">On Violations of LLM Review Policies – ICML Blog</a></li>
<li><a href="https://blog.icml.cc/2026/01/08/whats-new-in-icml-2026-peer-review/">What’s New in ICML 2026 Peer Review – ICML Blog</a></li>

</ul>
</details>

**Tags**: `#peer review`, `#ML conferences`, `#academic publishing`, `#research ethics`, `#LLM policy`

---

<a id="item-tech-news-11"></a>
### [Google launches Gemini Decisions API for fast multimodal decisions](https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/) ⭐️ 7.0/10

Google announced the Gemini Decisions API, built on a new Gemini Decision 1 model, for closed-ended multimodal decisions such as tool selection, policy checks, and model routing, and said it is available in Google AI Studio. It accepts text, image, audio, video, and PDF inputs, can score up to 1,000 questions per call, returns probabilities and confidence, and targets roughly 150–250 ms end-to-end latency. Pricing is $0.10 per million input tokens with no output-token charge, and Google claims it is nearly five times cheaper than a Gemini 3.5 Flash-Lite approach—a vendor figure not independently verified in the supplied source.

telegram · zaihuapd · Nov 12, 00:28

**「Background」** Developers building agents typically handle tool selection, policy checks and model routing by prompting a general-purpose model to emit a label, which consumes output tokens and adds text-generation latency. The Gemini Decision 1 model behind this API targets that narrower job instead: per its OpenRouter listing, it answers true/false, multiple-choice \(up to 255 options\) and scored questions and returns a confidence value for each answer rather than free-form text.

**「Cost trade-off for routing workloads」** For teams running high-volume tool selection or policy checks, the $0.10-per-million-input-token price with no output charge lowers the cost of each decision call; Gemini 3.5 Flash-Lite is listed by third-party trackers at $0.30 per million input and $2.50 per million output tokens, so savings are largest where output volume would otherwise dominate. The trade-off is scope: the endpoint returns scored closed-ended decisions rather than free-form text, so it can replace Flash-Lite for routing and guardrail checks but not for open-ended generation.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/gemini-decisions-api/">Gemini Decisions API : Fast multimodal decisions</a></li>
<li><a href="https://openrouter.ai/google/gemini-decision-1">Gemini Decision 1 - API Pricing &amp; Providers | OpenRouter</a></li>
<li><a href="https://langcopilot.com/llm-pricing/google/gemini-3.5-flash-lite">Google Gemini 3.5 Flash-Lite Pricing (2026) — Cost per 1K/1M ...</a></li>
<li><a href="https://whatisamilliontokens.com/models/gemini-3-5-flash-lite">Gemini 3.5 Flash-Lite Pricing — Cost Per Token, Input vs ...</a></li>

</ul>
</details>

**Tags**: `#Gemini API`, `#multimodal AI`, `#model routing`, `#inference cost`, `#Google`

---

<a id="item-tech-news-12"></a>
### [US Commerce Department finalizing rule to block Chinese AI firms&\#x27; remote chip access](https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule) ⭐️ 7.0/10

The US Commerce Department is reportedly finalizing a rule that would stop Chinese AI companies from remotely using advanced AI chips hosted in overseas data centers, with publication possible as early as this month. The controls would extend existing semiconductor export restrictions to Malaysia, Singapore, Thailand and four other countries — seven in total — to close remote-access and chip-smuggling routes, according to the report. Commerce is still consulting other government agencies before finalizing the text, so the rule is not yet published or in effect. The White House has asked Congress to legislate that Commerce write this rule, and Nvidia has lobbied against closing the remote-access gap, arguing that US AI infrastructure needs to win globally.

telegram · zaihuapd · Nov 12, 03:42

**「Existing controls and the legal gap」** Existing US semiconductor export restrictions, administered by Commerce&\#x27;s Bureau of Industry and Security, limit shipments of advanced AI chips to China but do not clearly reach Chinese firms that rent compute in third-country data centers — the remote-access gap this rule is meant to close. The House passed the Remote Access Security Act by 369 to 22 in January, but the Senate has not taken it up, and critical commentary cited in trade coverage argues Commerce lacks clear statutory authority to regulate remote access on its own.

**「Compute access at risk」** Chinese AI developers that depend on rented GPU capacity in Singapore, Malaysia, Thailand, or the other newly covered countries would need to move training and inference workloads to compliant domestic or non-restricted infrastructure, or risk losing access once the rule is finalized. Because the rule is still being drafted and could be published as soon as this month, teams should treat existing overseas capacity arrangements as conditional rather than durable.

<details><summary>References</summary>
<ul>
<li><a href="https://www.theinformation.com/articles/commerce-department-finalizing-long-awaited-ai-remote-access-rule">Commerce Department Finalizing Long-Awaited AI Remote Access Rule</a></li>
<li><a href="https://aiweekly.co/alerts/commerce-readies-rule-to-block-chinas-remote-ai-chip-access">Commerce Readies Rule to Block China&#x27;s Remote AI Chip Access</a></li>

</ul>
</details>

**Tags**: `#AI chips`, `#export controls`, `#US-China tech`, `#data centers`, `#semiconductor policy`

---

<a id="item-tech-news-13"></a>
### [Apple details Secure Exclaves and iPhone 18 Pro indicator checks](https://security.apple.com/blog/secure-exclaves/) ⭐️ 7.0/10

Apple published a November 12 blog post detailing Secure Exclaves, an isolated environment for audio and video processing that lets the main system and apps in an environment-aware mode receive only necessary recognition results rather than raw data. Apple says the architecture is used in HomeView face and sound recognition and in the iPhone 18 Pro privacy indicator. On that phone, according to the post, dedicated hardware checks the microphone indicator dot&\#x27;s color, brightness, and visibility before audio can enter the main system; Siri audio sessions must keep the dot visible continuously and for at least three seconds total to prevent blocking or spoofing. The source is a brief summary of Apple&\#x27;s post and offers no independent verification of these claims.

telegram · zaihuapd · Nov 12, 09:13

**「Background」** An enclave is a separated execution environment that keeps sensitive processing and data away from the main operating system, with apps receiving narrow results rather than raw inputs. The recording indicator is a visible signal that a microphone is active, which is why Apple&\#x27;s new design treats its verified visibility as a condition for admitting audio.

**「Impact」** On iPhone 18 Pro, microphone audio is blocked from reaching the main system until dedicated hardware verifies that the recording indicator is visible and meets Apple’s color and brightness requirements, so covering or disguising the indicator prevents capture rather than merely hiding a light. Apple also requires the indicator to remain displayed during Siri audio sessions and for at least three seconds total, leaving developers no software-only way to bypass the check.

**Tags**: `#Apple`, `#Secure Exclaves`, `#privacy`, `#audio/video security`, `#recording indicators`

---

## Financial News

<a id="item-finance-news-1"></a>
### [NVIDIA CEO 黄仁勋 resigns; CFO Colette Kress named interim CEO](https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition) ⭐️ 9.0/10

According to a Telegram post citing an NVIDIA announcement, CEO 黄仁勋 resigned as president, CEO and director effective immediately, and CFO Colette Kress will serve as interim CEO while continuing as CFO as the board searches for a permanent successor. The report says NVIDIA&\#x27;s third-quarter results remain scheduled for Nov. 17 and that the board also named Harvey C. Jones as its first board chair; the names are placeholders in the relayed item and independent confirmation is limited.

telegram · zaihuapd · Nov 12, 13:52

**「Background」** CNN reported that NVIDIA’s board is considering both internal and external candidates for a permanent CEO, a search running alongside CFO Colette Kress’s interim appointment.

**「Impact」** NVIDIA investors and the AI-hardware customers that depend on its product roadmap face a period of leadership uncertainty until a permanent CEO is appointed, though the company said operations, customer commitments and its roadmap will not be interrupted.

<details><summary>References</summary>
<ul>
<li><a href="https://nvidianews.nvidia.com/news/nvidia-announces-ceo-transition">NVIDIA Announces CEO Transition | NVIDIA Newsroom</a></li>
<li><a href="https://edition.cnn.com/2026/11/12/tech/jensen-huang-nvidia-resigns">CFO Colette Kress to serve as interim leader after Nvidia CEO ...</a></li>

</ul>
</details>

**Tags**: `#NVIDIA`, `#CEO transition`, `#corporate governance`, `#semiconductor industry`, `#AI hardware`

---

<a id="item-finance-news-2"></a>
### [China approves Eli Lilly&\#x27;s oral weight-loss drug, its first oral GLP-1](https://www.reuters.com/business/healthcare-pharmaceuticals/china-approves-eli-lillys-weight-loss-pill-orforglipron-2026-11-12/) ⭐️ 8.0/10

China&\#x27;s National Medical Products Administration on Nov 12 approved Eli Lilly&\#x27;s once-daily oral GLP-1 weight-loss drug orforglipron \(brand name Muyouda\) as a Class 1 new drug, for adults who are obese or overweight with at least one weight-related condition — the first oral GLP-1 cleared for weight loss in the country. The company has not announced pricing or a launch date, and a separate application for type 2 diabetes is still under review.

telegram · zaihuapd · Nov 12, 10:09

**「Background」** Orforglipron is a once-daily pill, giving patients in China an oral alternative to the once-weekly injectable GLP-1 weight-loss drugs from rivals such as Novo Nordisk, Pfizer and Innovent. It was approved for weight loss in the U.S. in April 2026 under the brand Foundayo.

**「Who is affected」** The approval gives Chinese adults who are obese or overweight with at least one weight-related condition a once-daily oral alternative to weekly injections, adding competitive pressure in a market bracing for price competition after semaglutide&\#x27;s patent expiry.

<details><summary>References</summary>
<ul>
<li><a href="https://www.drugs.com/article/prescription-weight-loss-drugs.html">Weight Loss Drugs &amp; Injections: What Are Your Options?</a></li>
<li><a href="https://global.chinadaily.com.cn/a/202604/02/WS69ce1a08a310d6866eb416e6.html">Price war looms in China&#x27;s booming weight-loss drug market</a></li>

</ul>
</details>

**Tags**: `#Eli Lilly`, `#China drug approval`, `#oral GLP-1`, `#obesity treatment`, `#pharmaceuticals`

---