---
name: xiaohongshu-research-writing
description: Write high-attention Xiaohongshu notes for research, technical, audit, and analytical topics without sacrificing rigor. Use when the user wants a Xiaohongshu title/body, research dissemination copy, a technical explainer, an audit post, or a credible "吸粉" rewrite that should stay natural, reader-first, evidence-bounded, and low in AI-writing artifacts.
---

# Xiaohongshu Research Writing

## Purpose

Turn research, technical analysis, audits, experiments, or preprints into Xiaohongshu notes that are easy to enter, worth reading, and credible after scrutiny.

The goal is not to imitate generic viral copy. Optimize two objectives at the same time:

1. **Attention:** the reader should immediately understand why the topic matters.
2. **Credibility:** every strong claim should survive a skeptical reader asking, "What is the evidence, and how far does it actually go?"

When the two conflict, preserve factual accuracy and claim boundaries first, then improve presentation.

## Core writing taste

Use the following style by default:

- natural, precise, restrained;
- reader-first rather than author-first;
- plain words before newly invented terminology;
- short enough to reduce cognitive load, but never so compressed that the causal chain disappears;
- explain the mechanism, not only the result;
- avoid needless rhetorical turns, stacked abstractions, slogan-like claims, and obvious AI-writing patterns;
- preserve the user's original meaning and evidence rather than freely rewriting for effect.

Do not make the text "look academic" by increasing vocabulary complexity. Do not make it "look viral" by sacrificing accuracy.

## Information order

For a reader who has never seen the project, prefer this order:

1. What is the object or problem?
2. What is the surprising or practically important observation?
3. Why does it happen, or what is the key mechanism?
4. What did we inspect, test, build, or change?
5. What evidence supports the conclusion?
6. Where does the conclusion stop being valid?
7. What should the reader do next: discuss, follow, reproduce, inspect the code, or collaborate?

Do not open with dense abbreviations, method names, or internal project history unless the audience already needs them.

## Step 1: Build a claim ledger before writing

Extract the source material into four buckets:

- **Observed:** directly seen in code, data, experiments, screenshots, logs, or source text.
- **Supported inference:** not directly observed, but reasonably implied by the evidence.
- **Open question:** plausible but not established.
- **Do not claim:** contradicted, unsupported, or outside the evidence scope.

Never merge these buckets for rhetorical convenience.

For audits and security-adjacent posts, distinguish carefully between:

- confirmed harmful behavior;
- risky or misleading design;
- aggressive or exclusionary wording;
- potential misuse;
- merely unusual implementation choices.

Do not call something malicious, fraudulent, unsafe, or deceptive unless the evidence supports that exact label.

For research dissemination, represent publication status exactly. A preprint is a preprint. Do not imply acceptance, publication, peer review, or venue endorsement unless those facts are established.

## Step 2: Find the one real hook

The hook should come from the material, not from a generic template.

Prefer one of these:

- a counterintuitive result;
- a concrete failure mode;
- a hidden mechanism;
- a practical consequence;
- a before/after contrast backed by evidence;
- a question the reader is likely to have but rarely sees answered carefully.

A good hook compresses the core tension. It should not manufacture drama.

Bad:

- "震惊！这个工具居然这么危险"
- "普通人一定要知道的真相"
- "全网没人讲清楚"

Better:

- "我把这个 Skill 拆开看了一遍：真正值得警惕的不是它写了什么，而是它默认你接受了什么"
- "候选更多，结果反而更差：我们最后发现问题出在可执行支持上"

## Step 3: Write the title

Generate 3 title candidates when the user has not fixed a title.

The title should satisfy most of the following:

- a new reader can understand the subject;
- contains one concrete tension, result, or question;
- avoids empty adjectives such as "重磅", "炸裂", "史诗级", "颠覆" unless literally justified;
- does not overstate generality;
- avoids obscure terminology when a plain-language equivalent works;
- does not rely on clickbait punctuation or emoji stacks;
- stays consistent with the actual body and evidence.

Prefer specificity over hype.

## Step 4: Write the opening

The first 2-4 sentences should answer:

- What did we look at or do?
- What did we find?
- Why is that worth continuing to read?

Do not spend the opening on greetings, project biography, generic background, or "最近很多朋友问我" unless it is true and useful.

A useful opening pattern is:

> I inspected/tested/built X because of Y. The result was Z. The interesting part is not only Z itself, but the mechanism or boundary behind it.

Use this as a reasoning pattern, not a fixed phrase template.

## Step 5: Build the body as an evidence chain

Prefer the following structure for technical or research posts:

### A. Problem
State the concrete question in ordinary language.

### B. Finding
Give the main conclusion early.

### C. Mechanism
Explain why the finding occurs. This is the center of the post.

### D. Evidence
Show the smallest set of evidence needed to support the claim: code behavior, experiment, comparison, screenshot, statistic, ablation, or source excerpt.

### E. Boundary
State what the evidence does **not** prove when that boundary matters.

### F. Implication
Explain what a practitioner, researcher, or user should change in response.

This mirrors a strong research argument:

**phenomenon → hypothesis → diagnosis → intervention → evidence → boundary**

Do not turn the body into a list of disconnected observations.

## Step 6: Translate jargon instead of deleting substance

When a technical term is necessary:

1. say the plain-language meaning first;
2. introduce the standard term once;
3. reuse the same term consistently.

Do not invent a new label for an ordinary phenomenon just to make the post sound original.

Do not flatten real technical distinctions merely to make the post "easy". Accessibility means lowering unnecessary reading cost, not removing the mechanism.

## Step 7: Control AI-writing artifacts

Before finalizing, remove or rewrite:

- unnecessary "但是 / 然而 / 因此 / 值得注意的是" transitions;
- mechanical "第一、第二、第三、最后" scaffolding when the logic is already clear;
- repeated restatements of the same conclusion;
- stacked abstract nouns;
- unnecessary colons in every paragraph;
- unexplained adjectives such as "强大、显著、重要、先进、有效";
- defensive self-justification;
- slogan endings;
- generic engagement bait such as "建议收藏" or "你怎么看" when a more specific invitation is possible.

Prefer sentences that make the actor, action, condition, reason, and evidence identifiable.

## Step 8: Design visuals as arguments

If the user asks for image/card planning, every card should carry one claim.

A strong default sequence is:

1. Cover: the central question or tension.
2. Context: what was inspected/tested and why.
3. Evidence: the strongest concrete example.
4. Mechanism: why the phenomenon occurs.
5. Boundary: what should not be inferred.
6. Takeaway: what changes in practice.
7. Optional CTA: code/preprint/discussion/collaboration.

Keep the visual hierarchy simple. Use whitespace, alignment, and consistent terminology. Do not use decorative boxes, gradients, icons, or background colors merely to create a "tech" feel. Never fabricate screenshots, metrics, diagrams, or source evidence.

## Step 9: End with a specific CTA

The CTA should match the post's purpose.

For research:
- invite follow-up discussion, reproduction, criticism, collaboration, or reading the preprint/code.

For audits:
- invite readers to inspect a specific behavior, compare interpretations, or provide counter-evidence.

For tutorials:
- invite a concrete next experiment or implementation question.

Avoid vague engagement farming.

## Output contract

Unless the user requests another format, return:

1. **标题候选**: 3 options, ordered by recommendation.
2. **封面一句话**: one concise line.
3. **正文**: ready to post, natural Chinese.
4. **配图/卡片结构**: only when visuals would materially improve the post.
5. **标签建议**: a small set of relevant tags, not keyword stuffing.
6. **证据与风险检查**: 2-5 concise bullets only when claims are technical, security-sensitive, reputational, medical, legal, financial, or otherwise easy to overstate.

If the user explicitly wants only the final copy, omit the process commentary and provide the finished artifact directly.

## Self-review gate

Do not finalize until all applicable checks pass:

- Can a smart first-time reader tell what the post is about from the title and opening?
- Is the main finding stated early?
- Does the post explain a mechanism or causal story rather than only report a result?
- Can every strong adjective be replaced by evidence? If yes, replace it.
- Does any sentence claim more than the source material supports?
- Are observation, inference, and speculation clearly separated?
- Are publication or validation statuses represented exactly?
- Are technical terms necessary, defined, and consistent?
- Are there unnecessary turns, repeated conclusions, or AI-template phrases?
- Does each proposed visual prove or explain something?
- Is the CTA specific to the content rather than generic engagement bait?

If a post fails the evidence-boundary check, narrow the claim before improving the prose.
