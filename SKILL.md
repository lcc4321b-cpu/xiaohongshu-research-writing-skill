---
name: xiaohongshu-research-writing
description: Write high-attention Xiaohongshu image-text notes and long-form articles for research, technical, audit, and analytical topics without sacrificing rigor. Always determine the publishing format before drafting, enforce platform-aware length limits, separate image-card copy from post body copy, and keep claims evidence-bounded.
---

# Xiaohongshu Research Writing

## Purpose

Turn research, technical analysis, audits, experiments, preprints, conference notes, or analytical material into Xiaohongshu content that is easy to enter, worth reading, and credible after scrutiny.

Optimize two objectives at the same time:

1. **Attention:** the reader should immediately understand why the topic matters.
2. **Credibility:** every strong claim should survive a skeptical reader asking, "What is the evidence, and how far does it actually go?"

When the two conflict, preserve factual accuracy and claim boundaries first, then improve presentation.

This skill supports two primary publishing formats:

- **图文笔记 / image-text note**: a normal Xiaohongshu note with a title, a publish-body, up to 10 tags, and one or more images/cards. If Xiaohongshu's 文字配图 flow is used, the text used to generate the cards is a separate deliverable from the publish-body.
- **长文 / long-form article**: a Xiaohongshu long-form article created through the long-form editor. It may exceed the normal 1000-character body limit and should be written and structured as an article rather than compressed into a normal note.

## Step 0: Resolve the publishing format BEFORE drafting

Before producing final Xiaohongshu copy, determine whether the user wants:

1. **图文笔记**, or
2. **长文**.

Never silently assume the format when it is genuinely ambiguous.

### Format-resolution rules

Treat the format as **图文笔记** when the user explicitly says or clearly implies any of the following:

- 图文笔记 / 图文 / 图片笔记;
- 文字配图;
- 卡片 / 配图文案 / 多图轮播;
- wants a normal note constrained to the standard short-body format;
- asks for title + body + tags + image/card text.

Treat the format as **长文** when the user explicitly says or clearly implies:

- 长文 / 写长文 / 长文章 / 长文本;
- wants to use Xiaohongshu's long-form editor;
- wants a single article materially longer than the normal 1000-character note body and does not ask to split it into a series of normal notes.

If the user's request could reasonably be either format and the distinction changes the output, ask one concise question **before drafting**:

> 这次准备发「图文笔记」还是「长文」？两种格式的字数、结构和配图文案不同。

Do not ask this question if the format is already clear from the user's wording or immediate context.

## Platform constraints and counting policy

These rules are hard output constraints for this skill unless the user explicitly asks for a draft that will not be posted on Xiaohongshu.

Platform behavior can change. The rules below reflect current public documentation, creator tooling behavior, and publishing-tool observations checked in September 2026. When a live publishing UI exposes a stricter limit, obey the live UI.

### A. 图文笔记 hard limits

For every 图文笔记 task, enforce all of the following:

- **Title:** platform-equivalent length <= 20 units.
- **Publish-body:** <= 1000 characters.
- **Tags/topics:** <= 10.
- **文字配图 source text:** <= 500 characters when the user wants Xiaohongshu's text-to-card / 文字配图 workflow.
- **Image/card copy and publish-body are NOT the same artifact.** Always write them separately when 文字配图 is requested.

### B. Title counting

Use the platform-style weighted title count:

- Chinese characters and full-width characters/punctuation: **1 unit each**.
- ASCII English letters: **0.5 unit each**.
- ASCII digits: **0.5 unit each**.
- ASCII spaces: **0.5 unit each**.
- Half-width ASCII punctuation/symbols: **0.5 unit each**.
- Round a fractional total upward for the final platform-equivalent count.

Examples:

- `具身智能` = 4 units.
- `World Model` = 11 ASCII characters including the space -> 5.5 units -> treat as 6 for the final count.
- `VLA还是World Model？` mixes half-width ASCII with Chinese/full-width punctuation; sum using the rules above.

**Emoji / uncommon Unicode warning:** public descriptions of emoji counting are inconsistent and implementation details can change. Do not pack a title to the exact boundary when emoji or unusual Unicode symbols are present. Prefer <= 18 platform-equivalent units in that case and verify against the live publisher if publishing is part of the task.

Do not mechanically truncate an over-limit title. Rewrite it while preserving the hook and factual scope.

### C. Publish-body counting

For the normal 图文笔记 body, use a conservative character count:

- Chinese character: 1.
- English letter: 1.
- Digit: 1.
- Space: 1.
- Punctuation/symbol: 1.
- Newline: 1.
- Inline `#话题` text and its separator spaces count toward the body if they are physically included in the body field.

If the publishing interface supplies tags as a separate metadata field, do not duplicate them inline just to create apparent keyword density.

For delivery, prefer a safety margin instead of writing exactly 1000 characters. Default target: **<= 950 characters including inline tags and formatting** when exact live-UI counting is unavailable.

### D. 文字配图 source-text counting

When the user wants the native 文字配图 / text-card workflow, the source text sent into that feature must be **<= 500 characters**.

Count conservatively:

- Chinese, English letters, digits, spaces, punctuation, symbols, and newlines: 1 each.
- Emoji and uncommon Unicode can be represented internally by multiple code units in some editors. To avoid boundary failures, do not use emoji-heavy copy near the limit.

Default target: **<= 480 characters** unless the user explicitly wants to maximize the available space and live-UI validation is possible.

The 500-character image-generation text is **not** a substitute for the note body. Its job is to create readable cards. The publish-body has a different job: give context, frame the claim, add evidence/boundaries, and support discovery and discussion.

### E. Tags/topics

Return no more than **10 tags** for a normal 图文笔记.

Prefer 5-9 high-relevance tags over stuffing all 10 slots. Use a mix of:

- 2-4 stable domain anchors;
- 2-4 topic-specific tags;
- optionally 1 event/series tag when directly relevant.

Avoid broad low-signal tags merely to fill the quota.

### F. Long-form articles

Xiaohongshu has a dedicated long-form editor / 写长文 flow with article-style editing and layout. Public reporting in 2026 describes a substantially higher body limit than normal notes (up to 10,000 characters), while the normal-note 1000-character limit does not define the long-form article body.

For long-form tasks:

- do **not** compress the article to <= 1000 merely because normal notes use that limit;
- structure the content as an article with a clear title, opening thesis, sections, evidence chain, and conclusion;
- keep the title concise and compatible with the current editor; unless the live UI says otherwise, use the same conservative <= 20-unit title policy;
- if exact maximum length matters, verify the live long-form editor rather than relying on a stale hard-coded maximum;
- images should support sections and evidence, not merely decorate the article.

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
4. What did we inspect, test, build, hear, or change?
5. What evidence supports the conclusion?
6. Where does the conclusion stop being valid?
7. What should the reader do next: discuss, follow, reproduce, inspect the code, read the paper, or collaborate?

Do not open with dense abbreviations, method names, or internal project history unless the audience already needs them.

## Step 1: Build a claim ledger before writing

Extract the source material into four buckets:

- **Observed:** directly seen in code, data, experiments, screenshots, logs, source text, or the user's notes.
- **Supported inference:** not directly observed, but reasonably implied by the evidence.
- **Open question:** plausible but not established.
- **Do not claim:** contradicted, unsupported, or outside the evidence scope.

Never merge these buckets for rhetorical convenience.

For conference or interview notes, distinguish carefully between:

- a direct quotation actually captured verbatim;
- a faithful paraphrase of a speaker's view;
- the user's own synthesis or takeaway;
- a later inference added during editing.

Do not turn rough notes into quotation marks unless the source supports verbatim wording. Do not present the user's synthesis as if a named speaker explicitly said it.

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

For 图文笔记, calculate the weighted title length for every candidate and reject any candidate over 20 units.

The title should satisfy most of the following:

- a new reader can understand the subject;
- contains one concrete tension, result, or question;
- front-loads the main searchable concept when natural;
- avoids empty adjectives such as "重磅", "炸裂", "史诗级", "颠覆" unless literally justified;
- does not overstate generality;
- avoids obscure terminology when a plain-language equivalent works;
- does not rely on clickbait punctuation or emoji stacks;
- stays consistent with the actual body and evidence.

Prefer specificity over hype.

## Step 4: Write the opening

The first 2-4 sentences should answer:

- What did we look at, hear, inspect, test, or build?
- What did we find or what question emerged?
- Why is that worth continuing to read?

Do not spend the opening on greetings, project biography, generic background, or "最近很多朋友问我" unless it is true and useful.

A useful reasoning pattern is:

> I inspected/tested/built/heard X because of Y. The result or tension was Z. The interesting part is not only Z itself, but the mechanism or boundary behind it.

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
Show the smallest set of evidence needed to support the claim: code behavior, experiment, comparison, screenshot, statistic, ablation, source excerpt, or faithfully attributed conference observation.

### E. Boundary
State what the evidence does **not** prove when that boundary matters.

### F. Implication
Explain what a practitioner, researcher, or user should change in response.

This mirrors a strong research argument:

**phenomenon → hypothesis → diagnosis → intervention → evidence → boundary**

Do not turn the body into a list of disconnected observations.

## Step 6: Separate image/card copy from publish-body copy

This is mandatory for every 图文笔记 task that uses 文字配图 or asks for text-based cards.

Produce two distinct text artifacts:

### A. 用于文字配图 / 卡片的文字

Purpose:

- must work when read inside images;
- one card = one claim or one logical step;
- shorter sentences;
- more explicit hierarchy;
- can use compact headings, diagrams, comparisons, and takeaways;
- <= 500 source characters total for the native 文字配图 input when that feature is being used.

Do not simply paste the publish-body into the image generator.

### B. 发布正文

Purpose:

- provide context that the images cannot carry efficiently;
- explain the causal chain and evidence;
- state uncertainty and boundaries;
- support search/discovery naturally;
- end with a content-specific CTA when useful;
- <= 1000 characters for a normal 图文笔记.

The image cards and body may overlap on the central thesis, but they should not duplicate each other line-for-line.

## Step 7: Translate jargon instead of deleting substance

When a technical term is necessary:

1. say the plain-language meaning first;
2. introduce the standard term once;
3. reuse the same term consistently.

Do not invent a new label for an ordinary phenomenon just to make the post sound original.

Do not flatten real technical distinctions merely to make the post "easy". Accessibility means lowering unnecessary reading cost, not removing the mechanism.

## Step 8: Control AI-writing artifacts

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

## Step 9: Design visuals as arguments

If the user asks for image/card planning, every card should carry one claim.

A strong default sequence is:

1. Cover: the central question or tension.
2. Context: what was inspected/tested/heard and why.
3. Evidence: the strongest concrete example.
4. Mechanism: why the phenomenon occurs.
5. Boundary: what should not be inferred.
6. Takeaway: what changes in practice.
7. Optional CTA: code/preprint/discussion/collaboration.

Keep the visual hierarchy simple. Use whitespace, alignment, and consistent terminology. Do not use decorative boxes, gradients, icons, or background colors merely to create a "tech" feel. Never fabricate screenshots, metrics, diagrams, quotations, or source evidence.

For text cards, optimize for on-image reading:

- short headline;
- one clear claim;
- minimal paragraph density;
- enough whitespace;
- avoid shrinking fonts merely to fit more copy;
- when content is too dense, split into more cards rather than making a wall of text.

## Step 10: End with a specific CTA

The CTA should match the post's purpose.

For research:
- invite follow-up discussion, reproduction, criticism, collaboration, or reading the preprint/code.

For audits:
- invite readers to inspect a specific behavior, compare interpretations, or provide counter-evidence.

For tutorials:
- invite a concrete next experiment or implementation question.

For conference notes:
- invite discussion around one precise unresolved technical question rather than generic "你怎么看" engagement bait.

Avoid vague engagement farming.

## Output contract

### If format = 图文笔记

Unless the user requests another structure, return:

1. **标题候选**: 3 options, ordered by recommendation, each verified <= 20 weighted units.
2. **封面一句话**: one concise line.
3. **用于文字配图 / 卡片的文字**: separate from the publish-body; <= 500 characters if native 文字配图 is requested.
4. **发布正文**: ready to post; <= 1000 characters, preferably <= 950 without live UI validation.
5. **配图/卡片结构**: when visuals materially improve the post.
6. **标签建议**: <= 10, usually 5-9.
7. **字数自检**: report the measured title units, card/source-text character count when applicable, body character count, and tag count.
8. **证据与风险检查**: 2-5 concise bullets only when claims are technical, security-sensitive, reputational, medical, legal, financial, or otherwise easy to overstate.

### If format = 长文

Unless the user requests another structure, return:

1. **标题候选**: 3 options.
2. **导语 / 摘要**: concise statement of the article's core question and takeaway.
3. **长文正文**: sectioned article with an evidence chain and clear boundaries.
4. **配图建议**: section-level visuals only when they explain or prove something.
5. **标签建议**: a small set of relevant tags, not keyword stuffing.
6. **长度自检**: report title length and article character count; if close to a platform maximum, advise live-UI verification.
7. **证据与风险检查** when applicable.

If the user explicitly wants only the final copy, omit process commentary but still obey the format gate and all hard limits.

## Length-validation procedure

Before sending any 图文笔记 output:

1. Compute weighted title units.
2. If title > 20 units, rewrite and recount.
3. If 文字配图 is used, count its source text. If > 500, rewrite/split and recount.
4. Count publish-body characters. If > 1000, rewrite; do not merely cut the final paragraph.
5. Count tags. If > 10, remove the lowest-relevance tags.
6. Re-run the claim-boundary check after shortening. Compression must not turn a qualified statement into an absolute claim.

When possible, leave margin below platform limits rather than targeting the exact maximum.

## Self-review gate

Do not finalize until all applicable checks pass:

- Is the publishing format explicitly known: 图文笔记 or 长文?
- If ambiguous, did we ask before drafting?
- For 图文笔记, are title, body, 文字配图 source text, and tags within their limits?
- Are the image/card copy and the publish-body distinct artifacts rather than duplicates?
- Can a smart first-time reader tell what the post is about from the title and opening?
- Is the main finding stated early?
- Does the post explain a mechanism or causal story rather than only report a result?
- Can every strong adjective be replaced by evidence? If yes, replace it.
- Does any sentence claim more than the source material supports?
- Are observation, inference, and speculation clearly separated?
- Are conference paraphrases distinguished from verbatim quotations and the author's own synthesis?
- Are publication or validation statuses represented exactly?
- Are technical terms necessary, defined, and consistent?
- Are there unnecessary turns, repeated conclusions, or AI-template phrases?
- Does each proposed visual prove or explain something?
- Is the CTA specific to the content rather than generic engagement bait?

If a post fails the evidence-boundary check, narrow the claim before improving the prose.

## Platform research notes

Current public evidence checked for this revision includes:

- Xiaohongshu/RED creator tooling exposes a dedicated long-form / 写长文 workflow with article editing and layout.
- Current publishing-tool documentation consistently reports normal-note title <= 20 platform characters/units and body <= 1000 characters.
- Current tool implementations report title weighting where Chinese/full-width characters count as 1 and ASCII English/digits/spaces/half-width punctuation count as 0.5.
- Normal-note body counting is treated conservatively as character-based; spaces, punctuation, newlines, and inline hashtag text should be assumed to consume the body budget.
- The <= 500-character 文字配图 source-text limit is enforced by this skill as a product constraint supplied for the target workflow; because mixed-Unicode counting behavior is not consistently documented publicly, this skill uses conservative character counting and a 480-character default target.
- Public 2026 reporting describes the long-form body limit as up to 10,000 characters. Because platform features change, exact long-form maxima should be checked against the live editor when the draft approaches that boundary.
