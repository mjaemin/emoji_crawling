# EDITH_emoji_crawling

## 사용법
### 1. unicode 이모지 오픈소스 xml 크롤링
- emoji unicode 컨소시움 (https://github.com/unicode-org)에서 cldr 페이지로 접근한다.
- 참고 프로젝트: 유니코드 콘소시움 (https://github.com/unicode-org)
- 언어별로 xml로 정리되어있는 원본페이지를 찾고, xml import를 한다.
- ".//annotation"위치에 있는 모든 데이터를 변환한다.
    - 도큐먼트 설명
        - //annotation[@cp] : emoji (key)
        - //annotation : name (value)
        - //annotation[@type] : TTS타입인지 아닌지 (condition)
- type이 tts인 도큐먼트의 emoji(key) : name(value) 쌍을 구한다.
### 2. 1번의 방법 * 한/영/프/스
1. 한: https://raw.githubusercontent.com/unicode-org/cldr/latest/common/annotations/ko.xml
2. 영: https://raw.githubusercontent.com/unicode-org/cldr/latest/common/annotations/en.xml
3. 프: https://raw.githubusercontent.com/unicode-org/cldr/latest/common/annotations/fr.xml
4. 스: https://raw.githubusercontent.com/unicode-org/cldr/latest/common/annotations/es.xml

### 3. csv export
- 한/영/프/스 도큐먼트를 한 파일로 통합하여 csv export
- csv 설명
    - emoji: emoji
    - tts_ko: 한국어 name
    - tts_en: 영어 name
    - tts_fr: 불어 name
    - tts_es: 스페인 name