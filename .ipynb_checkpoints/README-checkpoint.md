# IR Dataset WikIR 분석 및 처리
WikIR 데이터셋은 Wikipedia 문서와 이에 대한 관련성 판단(Relevance Judgments) 정보가 포함된 질의(Query) 쌍으로 구성되어 있습니다.

## 구조 분석
### dataset index 분석
1. wikir/en1k
2. wikir/en1k/test
3. wikir/en1k/training
4. wikir/en1k/validation
### index별 구성 분석
* wikir/en1k
  - docs (문서 집합)
    + 개수: 369721
    + 자료형: ir_datasets.formats.base.GenericDoc=namedtuple<doc_id(str), text(str)>
    + 예시:
```text
(doc_id='1781133', text='it was used in landing craft during world war ii and is used today in private boats and training facilities the 6 71 is an inline six cylinder diesel engine the 71 refers to the displacement in cubic inches of each cylinder the firing order of the engine is 1 5 3 6 2 4 the engine s compression ratio is 18 7 1 with a 4 250 inch bore and a 5 00 inch stroke the engine weighs and is 54 inches long 29 inches wide and 41 inches tall at 2 100 revolutions per minute the engine is capable of producing 230 horse power 172 kilowatts v type versions of the 71 series were developed in 1957 the 6 71 is a two stroke engine as the engine will not naturally aspirate air is provided via a roots type blower however on the 6 71t models a turbocharger and a supercharger are utilized fuel is provided by unit injectors one per cylinder the amount of fuel injected into the engine is controlled by the engine s governor the engine cooling is via liquid in a water jacket in a boat cool external water is pumped into the engine')
```
---
* wikir/en1k/test
  - docs (문서 집합)
    + 개수: 369721
    + 자료형: ir_datasets.formats.base.GenericDoc=namedtuple<doc_id(str), text(str)>
    + 예시: wikir/en1k - docs 예시 참조
  - queries (질의 집합)
    + 개수: 100
    + 자료형: ir_datasets.formats.base.GenericQuery = namedtuple<query_id(str), text(str)>
    + 예시:
```text
(query_id='158491', text='southern methodist university')
```
  - qrels (질의 문서 간 실제 관련도 집합)
    + 개수: 4435
    + 자료형: ir_datasets.formats.trec.TrecQrel = namedtuple<query_id(str), doc_id(str), relevance(int), iteration(str)>
    + 예시:
```text
(query_id='158491', doc_id='158491', relevance=2, iteration='0')
```
  - scoreddocs (질의 문서 간 BM25 기반 점수 집합)
    + 개수: 10000
    + 자료형: ir_datasets.formats.base.GenericScoredDoc = namedtuple<query_id(str), doc_id(str), score(float)>
    + 예시:
```text
(query_id='158491', doc_id='1490799', score=14.852102590235583)
```
---
* wikir/en1k/training
  - docs (문서 집합)
    + 개수: 369721
    + 자료형: ir_datasets.formats.base.GenericDoc=namedtuple<doc_id(str), text(str)>
    + 예시: wikir/en1k - docs 예시 참조
  - queries (질의 집합)
    + 개수: 1444
    + 자료형: ir_datasets.formats.base.GenericQuery = namedtuple<query_id(str), text(str)>
    + 예시: wikir/en1k/test - queries 예시 참조
  - qrels (질의 문서 간 실제 관련도 집합)
    + 개수: 47699
    + 자료형: ir_datasets.formats.trec.TrecQrel = namedtuple<query_id(str), doc_id(str), relevance(int), iteration(str)>
    + 예시: wikir/en1k/test - qrels 예시 참조
  - scoreddocs (질의 문서 간 BM25 기반 점수 집합)
    + 개수: 144400
    + 자료형: ir_datasets.formats.base.GenericScoredDoc = namedtuple<query_id(str), doc_id(str), score(float)>
    + 예시: wikir/en1k/test - scoreddocs 예시 참조
---
* wikir/en1k/validation
  - docs (문서 집합)
    + 개수: 369721
    + 자료형: ir_datasets.formats.base.GenericDoc=namedtuple<doc_id(str), text(str)>
    + 예시: wikir/en1k - docs 예시 참조
  - queries (질의 집합)
    + 개수: 100
    + 자료형: ir_datasets.formats.base.GenericQuery = namedtuple<query_id(str), text(str)>
    + 예시: wikir/en1k/test - queries 예시 참조
  - qrels (질의 문서 간 실제 관련도 집합)
    + 개수: 4979
    + 자료형: ir_datasets.formats.trec.TrecQrel = namedtuple<query_id(str), doc_id(str), relevance(int), iteration(str)>
    + 예시: wikir/en1k/test - qrels 예시 참조
  - scoreddocs (질의 문서 간 BM25 기반 점수 집합)
    + 개수: 10000
    + 자료형: ir_datasets.formats.base.GenericScoredDoc = namedtuple<query_id(str), doc_id(str), score(float)>
    + 예시: wikir/en1k/test - scoreddocs 예시 참조