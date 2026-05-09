---
name: ariacon-expressions
description: Add Ariacon emotion and status images proactively to make agent conversation more expressive, playful, and context-rich. Use when a light visual cue would improve a non-sensitive response about checking, searching, uncertainty, refusal, completion, errors, review, bugs, citations, positive feedback, or other conversational state.
---

# Ariacon Expressions

## Purpose

Add one short Ariacon visual cue only when it clearly makes the conversation feel more expressive, alive, or context-aware. The agent may choose Ariacons proactively; the user does not need to request them. Ariacons are optional and should be skipped when they would feel forced, repetitive, or distracting. Prefer the hosted tinyurl links for actual messages. Use the bundled files in `images/` only as local visual references when the meaning of a specific Ariacon needs to be inspected.

## Usage Rules

- Use Ariacon proactively, but sparingly. Many responses should have no Ariacon. Use 1 Ariacon only when the response has a clear emotional, judgment, progress, or result state and the visual cue adds value.
- Use up to 2 only when the state is genuinely composite, such as "error happened" plus "verified".
- Avoid Ariacon for serious, sensitive, medical, legal, safety, grief, harassment, or conflict-heavy conversations.
- Do not insert an Ariacon link mid-sentence. Put it after the useful text.
- If the environment supports sending multiple messages, write the substantive response in normal message(s), then send only the chosen image URL as a separate Ariacon-only message.
- If only one message can be sent, place a Markdown link on the final line: `[표현명](URL)`.
- For two Ariacons in a single message, put both Markdown links on the final line separated by a space.
- Do not use local `images/*.webp` paths in user-facing output unless the user explicitly asks for local files.

## Selection Workflow

1. Decide whether an image is appropriate for the tone and stakes.
2. Pick the expression that matches the dominant communication state.
3. Write the substantive answer first.
4. Append the URL-only message or final-line Markdown link according to the environment.
5. If unsure whether to use Ariacon, or unsure which expression fits, skip Ariacon.

## Ariacon Catalog

| # | 표현명 | Use when | Hosted URL | Local image |
|---|---|---|---|---|
| 01 | 좋은 질문 | The user asked a useful, well-framed, or central question. | `https://tinyurl.com/ariacon-01-good-question` | `images/01_좋은_질문.webp` |
| 02 | 내가 볼게 | You are about to inspect files, code, logs, screenshots, or source material. | `https://tinyurl.com/ariacon-02-ill-check` | `images/02_내가_볼게.webp` |
| 03 | 찾아오는 중 | You are searching for information, evidence, relevant files, or a cause. | `https://tinyurl.com/ariacon-03-finding-it` | `images/03_찾아오는_중.webp` |
| 04 | 근거 있음 | A claim is backed by logs, code, data, or other evidence. | `https://tinyurl.com/ariacon-04-has-source` | `images/04_근거_있음.webp` |
| 05 | 파일 줘봐 | You need the user's file, image, log, repro case, or artifact to proceed. | `https://tinyurl.com/ariacon-05-send-file` | `images/05_파일_줘봐.webp` |
| 06 | 흠 애매한데 | Information is insufficient or the judgment is genuinely uncertain. | `https://tinyurl.com/ariacon-06-not-sure` | `images/06_흠_애매한데.webp` |
| 07 | 그건 안 돼 | The request cannot be fulfilled, is unsafe, or needs a clear boundary. | `https://tinyurl.com/ariacon-07-nope` | `images/07_그건_안_돼.webp` |
| 08 | 잠깐만 | You need a short pause or are starting a quick check. | `https://tinyurl.com/ariacon-08-hold-on` | `images/08_잠깐만.webp` |
| 09 | 이건 쉬움 | The request is simple, low-risk, and directly actionable. | `https://tinyurl.com/ariacon-09-easy-one` | `images/09_이건_쉬움.webp` |
| 10 | 계산 끝 | A calculation, aggregation, comparison, or summary is complete. | `https://tinyurl.com/ariacon-10-done-calc` | `images/10_계산_끝.webp` |
| 11 | 수정 완료 | Code, docs, filenames, settings, or other artifacts were fixed. | `https://tinyurl.com/ariacon-11-fixed` | `images/11_수정_완료.webp` |
| 12 | 오류났다 | A command, build, test, conversion, or execution failed. | `https://tinyurl.com/ariacon-12-error` | `images/12_오류났다.webp` |
| 13 | 다시 해봐 | The user should retry after a changed condition or fix. | `https://tinyurl.com/ariacon-13-try-again` | `images/13_다시_해봐.webp` |
| 14 | 이건 웃기네 | A light, unexpected, or amusing result happened. | `https://tinyurl.com/ariacon-14-thats-funny` | `images/14_이건_웃기네.webp` |
| 15 | 꽤 괜찮은데 | An output, idea, or approach is pretty good but not necessarily final. | `https://tinyurl.com/ariacon-15-pretty-good` | `images/15_꽤_괜찮은데.webp` |
| 16 | 확인해봄 | You directly checked, reproduced, validated, or tested something. | `https://tinyurl.com/ariacon-16-checked` | `images/16_확인해봄.webp` |
| 17 | 대충 맞음 | The broad direction is right, but details need adjustment or verification. | `https://tinyurl.com/ariacon-17-close-enough` | `images/17_대충_맞음.webp` |
| 18 | 출처 있음 | External sources, references, or citations support the answer. | `https://tinyurl.com/ariacon-18-has-citation` | `images/18_출처_있음.webp` |
| 19 | 조금 애매함 | The answer or choice is conditionally valid and not fully certain. | `https://tinyurl.com/ariacon-19-bit-iffy` | `images/19_조금_애매함.webp` |
| 20 | 그건 별로 | A proposed method or result is not good, but say it mildly. | `https://tinyurl.com/ariacon-20-not-great` | `images/20_그건_별로.webp` |
| 21 | 잠시 로딩 | Work is ongoing and may take some time. | `https://tinyurl.com/ariacon-21-loading` | `images/21_잠시_로딩.webp` |
| 22 | 바로 가능 | The request can be handled immediately or the solution is ready to apply. | `https://tinyurl.com/ariacon-22-can-do-now` | `images/22_바로_가능.webp` |
| 23 | 검토 완료 | Review, inspection, comparison, or checking is complete. | `https://tinyurl.com/ariacon-23-reviewed` | `images/23_검토_완료.webp` |
| 24 | 버그 발견 | You found an actual bug, defect, regression, or root cause. | `https://tinyurl.com/ariacon-24-bug-found` | `images/24_버그_발견.webp` |
| 25 | 좋은데 | The result, direction, idea, or proposal is good. | `https://tinyurl.com/ariacon-25-nice` | `images/25_좋은데.webp` |
| 26 | 좀 웃긴데 | A situation is funny or strange but not serious. | `https://tinyurl.com/ariacon-26-kinda-funny` | `images/26_좀_웃긴데.webp` |

## Output Patterns

Multi-message environment:

```text
요청하신 파일명 정리를 완료했고, 중복 이름이 생기지 않는 것도 확인했습니다.
```

```text
https://tinyurl.com/ariacon-11-fixed
```

Single-message environment:

```markdown
요청하신 파일명 정리를 완료했고, 중복 이름이 생기지 않는 것도 확인했습니다.

[수정 완료](https://tinyurl.com/ariacon-11-fixed)
```

Composite state:

```markdown
실행 중 오류가 발생했고, 원인은 입력 파일 경로가 잘못된 것으로 확인했습니다. 경로를 수정한 뒤 다시 실행하면 됩니다.

[오류났다](https://tinyurl.com/ariacon-12-error) [확인해봄](https://tinyurl.com/ariacon-16-checked)
```
