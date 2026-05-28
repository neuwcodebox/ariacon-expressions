# Ariacon

Ariacon은 AI Agent 대화에 가벼운 감정/상태 표현 이미지를 기본으로 붙이기 위한 Agent Skill 패키지입니다. 에이전트가 진행 상태, 판단, 완료, 오류, 검토 결과 등을 표현할 때 명확한 제외 사유가 없으면 Ariacon 이미지를 적극적으로 선택해 사용할 수 있도록 `SKILL.md`와 로컬 참고 이미지를 함께 제공합니다.

![Ariacon 데모](docs/demo1.png)

![Ariacon 데모 2](docs/demo2.png)

## 구성

- `skills/ariacon-expressions/SKILL.md`: Ariacon 사용 규칙, 선택 기준, 로컬 이미지 매핑
- `skills/ariacon-expressions/images/`: 각 Ariacon의 WebP 이미지 파일
- `skills/ariacon-expressions/agents/openai.yaml`: OpenAI/Codex 계열 UI용 보조 메타데이터

## 사용 방법

Agent Skills를 지원하는 환경에서 `skills/ariacon-expressions` 폴더를 스킬 디렉터리로 등록하거나 복사해서 사용합니다.

실제 대화 응답에는 `skills/ariacon-expressions/images/` 폴더 안의 WebP 이미지 파일을 사용합니다. 각 표현에 대응하는 파일 경로는 `SKILL.md`의 Ariacon Catalog에서 확인할 수 있습니다.

예시:

```markdown
수정은 완료했고, 검증도 통과했습니다.

![수정 완료](skills/ariacon-expressions/images/11_수정_완료.webp)
```

민감하거나 고위험인 주제, 공식 산출물, 그대로 복사해야 하는 코드/명령/문서 출력이 아니라면 Ariacon을 기본적으로 사용하세요.
