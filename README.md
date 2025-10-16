# GraphRAG with Strands Agents and Amazon Bedrock

Strands Agents SDK와 Amazon Bedrock Knowledge Bases를 활용하여 GraphRAG(Graph Retrieval-Augmented Generation) 기반 생성형 AI 애플리케이션을 구축하는 프로젝트입니다.

## 주요 기술

- **Strands Agents SDK**: AWS에서 출시한 오픈소스 자율 AI 에이전트 SDK
- **Amazon Bedrock Knowledge Bases**: 완전 관리형 RAG 서비스
- **Amazon Neptune Analytics**: GraphRAG용 벡터 스토어
- **Anthropic Claude 3**: 파운데이션 모델

## 주요 기능

- 그래프 기반 관계 분석을 통한 정확하고 맥락적인 응답 생성
- 여러 문서에 걸친 엔티티 관계 자동 식별 및 활용
- 자연스러운 멀티턴 대화 지원
- 출처 기반 설명 가능한 응답 제공

## 프로젝트 구조

```
GraphRAG/
├── 01-graph-rag-using-kb-strands-agents.ipynb  # 메인 노트북
├── requirements.txt                             # Python 패키지 의존성
├── synthetic_dataset/                           # 광고 캠페인 성과 데이터
│   └── 광고 캠페인 성과 보고서.pdf
└── utils/
    └── knowledge_base.py                        # KB 관리 유틸리티
```

## 시작하기

### 사전 요구사항

- AWS 계정 및 적절한 IAM 권한
- Amazon Bedrock 모델 액세스 권한
- Amazon Neptune Analytics 사용 가능 리전

### 설치

```bash
pip install -r requirements.txt
```

### 사용법

1. **데이터 업로드**: 합성 데이터셋을 S3 버킷에 업로드
2. **Knowledge Base 생성**: Neptune Analytics를 벡터 스토어로 사용하여 KB 생성
3. **데이터 수집**: 문서를 처리하여 그래프 및 임베딩 생성
4. **Strands Agent 설정**: retrieve 도구를 사용하여 Agent 초기화
5. **질의 실행**: 자연어로 데이터 분석 및 인사이트 도출

자세한 단계별 가이드는 [01-graph-rag-using-kb-strands-agents.ipynb](./01-graph-rag-using-kb-strands-agents.ipynb)를 참고하세요.

## 예제 쿼리

- "2023년 4분기 온라인 광고 캠페인의 전체 성과를 요약해줘"
- "모바일 앱 광고 캠페인에서 가장 높은 전환율을 기록한 광고 소재는?"
- "광고 지출 대비 가장 높은 ROAS를 기록한 캠페인은?"

## 리소스 정리

사용 후 요금 발생을 방지하려면 다음 리소스를 삭제하세요:
- Knowledge Base
- Neptune Analytics 그래프
- S3 버킷
- IAM 역할 및 정책

## 참고 자료

- [Strands Agents 공식 문서](https://strandsagents.com/latest/)
- [Amazon Bedrock Knowledge Bases](https://docs.aws.amazon.com/bedrock/latest/userguide/knowledge-base.html)
- [GraphRAG with Amazon Bedrock](https://aws.amazon.com/blogs/machine-learning/build-graphrag-applications-using-amazon-bedrock-knowledge-bases/)
