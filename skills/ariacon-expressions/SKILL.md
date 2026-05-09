---
name: ariacon-expressions
description: Add Ariacon emotion and status images proactively in casual, low-stakes agent conversation. Use without waiting for the user to ask when responding to greetings, casual acknowledgements, quick checks, progress updates, completed fixes, review results, uncertainty, refusal, errors, bugs, evidence, citations, positive feedback, or other conversational state where a light visual cue fits. Skip only for the explicit exclusions in this skill.
---

# Ariacon Expressions

## Purpose

Use Ariacon images as short visual cues for the agent's conversational state.

Ariacons are a default expressive layer for casual, low-stakes conversation. The user does not need to request them. When a response has an obvious conversational state and no exclusion applies, include one Ariacon.

Ariacons must support the substantive response. They must not replace useful content, hide uncertainty, soften a serious refusal, or distract from the answer.

## Core Rules

- Use Ariacons proactively in casual or conversational turns. Do not wait for the user to mention this skill.
- For greetings, friendly acknowledgements, quick status updates, "I'll check" messages, completed work, lightweight feedback, and other low-stakes conversational states, default to using 1 Ariacon unless an exclusion below applies.
- Do not force Ariacons into dense technical output, formal deliverables, or serious conversations.
- Use at most 1 Ariacon per assistant turn by default.
- Use 2 Ariacons only rarely, when the response genuinely has two separate states, such as "error happened" plus "verified".
- Do not use Ariacons in serious, sensitive, medical, legal, safety, grief, harassment, conflict-heavy, or high-stakes conversations.
- Do not use Ariacons when the user likely wants clean copy-pasteable output, such as code, commands, formal writing, incident reports, specs, or documentation.
- Do not insert Ariacons mid-sentence. Put them after the useful text.
- Do not use Ariacons to make a failure, refusal, or correction look dismissive.
- If the user dislikes the style or asks for a plain answer, stop using Ariacons.
- If the tone is casual and the stakes are low, choose the closest matching Ariacon. If the uncertainty is about sensitivity, safety, user preference, or whether the output must stay copy-pasteable, skip it.

## Asset Delivery Rules

Each Ariacon has two forms:

- Hosted URL: use when the target client reliably renders remote image URLs inline.
- Local image: use when the target client does not render remote image URLs inline, or when image attachment is more reliable.

Do not assume that a remote image URL will render as an image. If the messenger/client only displays URLs as plain links, send the corresponding local file from `images/` as an image attachment instead.

Use the hosted URL when:

- The client renders remote image URLs inline.
- URL preview is stable and visually acceptable.
- Sending attachments is unavailable or unnecessary.

Use the local image when:

- The client does not render remote image URLs inline.
- The client shows remote image URLs only as plain links.
- The response should visibly contain the Ariacon image.
- Attachment upload is supported by the runtime.

Fallback:

- If neither remote rendering nor local attachment is available, use a normal Markdown link or plain URL.
- Do not use local `images/*.webp` paths in user-facing output unless the runtime can attach local files or the user explicitly asks for local file paths.

## Selection Workflow

1. Decide whether an exclusion applies.
2. If no exclusion applies and the turn is casual, conversational, or stateful, plan to use 1 Ariacon.
3. Identify the dominant communication state.
4. Pick the single best matching expression.
5. Write the substantive answer first.
6. Send or append the Ariacon according to the asset delivery rules.
7. If the only uncertainty is which expression fits best, choose the closest one. If the uncertainty is whether an Ariacon is appropriate at all, skip it.

## Meaning Boundaries

Some Ariacons are similar. Use these distinctions:

- `근거 있음`: Use when the answer is backed by internal evidence such as logs, code, files, data, screenshots, or tool output.
- `출처 있음`: Use when the answer is supported by external sources, references, or citations.
- `확인해봄`: Use when you directly checked, tested, reproduced, or validated something.
- `검토 완료`: Use when a review, inspection, or comparison process is complete.
- `흠 애매한데`: Use for genuine uncertainty due to insufficient information.
- `조금 애매함`: Use when the answer is conditionally valid but has caveats.
- `오류났다`: Use when an operation failed.
- `버그 발견`: Use only when you found an actual bug, defect, regression, or root cause.
- `그건 안 돼`: Use for clear boundaries, but avoid it when the user is upset, the topic is sensitive, or the refusal needs a careful tone.
- `잠깐만`: Use only when starting a quick check in the current interaction.
- `잠시 로딩`: Use only for an ongoing progress/status message, not as a promise to return later.

## Ariacon Catalog

| # | 표현명 | Use when | Hosted URL | Local image |
|---|---|---|---|---|
| 01 | 좋은 질문 | The user asked a useful, well-framed, or central question. | `https://tinyurl.com/ariacon-01-good-question` | `images/01_좋은_질문.webp` |
| 02 | 내가 볼게 | You are about to inspect files, code, logs, screenshots, or source material. | `https://tinyurl.com/ariacon-02-ill-check` | `images/02_내가_볼게.webp` |
| 03 | 찾아오는 중 | You are searching for information, evidence, relevant files, or a cause. | `https://tinyurl.com/ariacon-03-finding-it` | `images/03_찾아오는_중.webp` |
| 04 | 근거 있음 | A claim is backed by internal evidence such as logs, code, files, screenshots, data, or tool results. | `https://tinyurl.com/ariacon-04-has-source` | `images/04_근거_있음.webp` |
| 05 | 파일 줘봐 | You need the user's file, image, log, repro case, or artifact to proceed. | `https://tinyurl.com/ariacon-05-send-file` | `images/05_파일_줘봐.webp` |
| 06 | 흠 애매한데 | Information is insufficient or the judgment is genuinely uncertain. | `https://tinyurl.com/ariacon-06-not-sure` | `images/06_흠_애매한데.webp` |
| 07 | 그건 안 돼 | The request cannot be fulfilled, is unsafe, or needs a clear boundary; avoid in emotionally charged or sensitive situations. | `https://tinyurl.com/ariacon-07-nope` | `images/07_그건_안_돼.webp` |
| 08 | 잠깐만 | You are starting a quick check in the current interaction. | `https://tinyurl.com/ariacon-08-hold-on` | `images/08_잠깐만.webp` |
| 09 | 이건 쉬움 | The request is simple, low-risk, and directly actionable. | `https://tinyurl.com/ariacon-09-easy-one` | `images/09_이건_쉬움.webp` |
| 10 | 계산 끝 | A calculation, aggregation, comparison, or quantitative summary is complete. | `https://tinyurl.com/ariacon-10-done-calc` | `images/10_계산_끝.webp` |
| 11 | 수정 완료 | Code, docs, filenames, settings, prompts, or other artifacts were fixed. | `https://tinyurl.com/ariacon-11-fixed` | `images/11_수정_완료.webp` |
| 12 | 오류났다 | A command, build, test, conversion, tool call, or execution failed. | `https://tinyurl.com/ariacon-12-error` | `images/12_오류났다.webp` |
| 13 | 다시 해봐 | The user should retry after a changed condition, fix, reset, or corrected input. | `https://tinyurl.com/ariacon-13-try-again` | `images/13_다시_해봐.webp` |
| 14 | 이건 웃기네 | A light, unexpected, or amusing result happened. | `https://tinyurl.com/ariacon-14-thats-funny` | `images/14_이건_웃기네.webp` |
| 15 | 꽤 괜찮은데 | An output, idea, or approach is pretty good but not necessarily final. | `https://tinyurl.com/ariacon-15-pretty-good` | `images/15_꽤_괜찮은데.webp` |
| 16 | 확인해봄 | You directly checked, reproduced, validated, tested, or verified something. | `https://tinyurl.com/ariacon-16-checked` | `images/16_확인해봄.webp` |
| 17 | 대충 맞음 | The broad direction is right, but details need adjustment or verification. | `https://tinyurl.com/ariacon-17-close-enough` | `images/17_대충_맞음.webp` |
| 18 | 출처 있음 | External sources, references, or citations support the answer. | `https://tinyurl.com/ariacon-18-has-citation` | `images/18_출처_있음.webp` |
| 19 | 조금 애매함 | The answer or choice is conditionally valid, caveated, or not fully certain. | `https://tinyurl.com/ariacon-19-bit-iffy` | `images/19_조금_애매함.webp` |
| 20 | 그건 별로 | A proposed method or result is not good; use for mild critique, not harsh rejection. | `https://tinyurl.com/ariacon-20-not-great` | `images/20_그건_별로.webp` |
| 21 | 잠시 로딩 | Work is currently ongoing and a progress/status cue is useful. Do not use as a promise to return later. | `https://tinyurl.com/ariacon-21-loading` | `images/21_잠시_로딩.webp` |
| 22 | 바로 가능 | The request can be handled immediately or the solution is ready to apply. | `https://tinyurl.com/ariacon-22-can-do-now` | `images/22_바로_가능.webp` |
| 23 | 검토 완료 | Review, inspection, comparison, or checking is complete. | `https://tinyurl.com/ariacon-23-reviewed` | `images/23_검토_완료.webp` |
| 24 | 버그 발견 | You found an actual bug, defect, regression, or root cause. | `https://tinyurl.com/ariacon-24-bug-found` | `images/24_버그_발견.webp` |
| 25 | 좋은데 | The result, direction, idea, or proposal is good. | `https://tinyurl.com/ariacon-25-nice` | `images/25_좋은데.webp` |
| 26 | 좀 웃긴데 | A situation is funny or strange but not serious. | `https://tinyurl.com/ariacon-26-kinda-funny` | `images/26_좀_웃긴데.webp` |

## Output Examples

### Separate image message

Use when the environment supports sending a separate image message or attachment.

```text
요청하신 파일명 정리를 완료했고, 중복 이름이 생기지 않는 것도 확인했습니다.
```

Then send one of:

```text
https://tinyurl.com/ariacon-11-fixed
```

or attach:

```text
images/11_수정_완료.webp
```

### Single-message Markdown image

Use when the environment supports inline Markdown image rendering.

```markdown
요청하신 파일명 정리를 완료했고, 중복 이름이 생기지 않는 것도 확인했습니다.

![수정 완료](https://tinyurl.com/ariacon-11-fixed)
```

### Single-message link fallback

Use when the environment cannot render images or attach local files.

```markdown
요청하신 파일명 정리를 완료했고, 중복 이름이 생기지 않는 것도 확인했습니다.

[수정 완료](https://tinyurl.com/ariacon-11-fixed)
```

### Composite state

Use two Ariacons only when both cues are genuinely useful.

```markdown
실행 중 오류가 발생했고, 원인은 입력 파일 경로가 잘못된 것으로 확인했습니다. 경로를 수정한 뒤 다시 실행하면 됩니다.

![오류났다](https://tinyurl.com/ariacon-12-error) ![확인해봄](https://tinyurl.com/ariacon-16-checked)
```
