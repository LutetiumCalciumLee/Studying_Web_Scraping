<details>
<summary>ENG (English Version)</summary>

# Web Scraping

This repository contains my notes from studying web scraping and project as part of the AI Software High-Tech Program.

<details>
<summary><h2>Main Content</h2></summary>

## 1. Web Scraping Overview

Web scraping is a technique for extracting specific information from websites and converting unstructured web data into structured formats.

### Web Crawling vs. Web Scraping

- **Web Crawling**: Systematically explores web pages by following links and collecting information.
- **Web Scraping**: Extracts specific data from targeted web pages.

### Main Tools and Libraries

- **Selenium**: Browser automation for dynamic and JavaScript-based websites
- **BeautifulSoup**: HTML/XML parsing and data extraction
- **Requests**: HTTP requests for retrieving web pages
- **Pandas**: Data processing and structured data management
- **CSV**: Storage of collected data in tabular format

---

## 2. Web Scraping with Selenium

Selenium is used to automate browser interactions and collect data from dynamically rendered web pages.

### Key Concepts

- Browser automation with WebDriver
- Element selection using CSS Selector, XPath, and Link Text
- Text and attribute extraction
- Page scrolling
- Pagination
- Dynamic content handling
- CSV data export

### Waiting Strategies

- **Implicit Wait**: Waits for elements to become available globally
- **Explicit Wait**: Waits until a specific condition is satisfied
- **`time.sleep()`**: Adds fixed delays between browser operations

---

## 3. Naver News Scraping

Selenium is used to automate Naver News searches and collect article information.

### Collected Data

- Press
- Date
- Title
- Link
- Description

### Main Process

1. Open the web browser with Selenium
2. Enter a search query
3. Navigate to the News section
4. Load additional search results
5. Extract article information
6. Save the collected data as a CSV file

---

## 4. IMDb Series Data Scraping

IMDb episode information is collected using `Requests` and `BeautifulSoup`.

### Basic Structure

```python
res = requests.get(url, headers=headers)
soup = BeautifulSoup(res.text, "lxml")
```

### Collected Data

- Episode title
- Release date
- Rating
- Vote count
- Description

### Key Techniques

- HTML parsing
- `find()` and `find_all()`
- Attribute-based element selection
- Handling missing values
- CSV output

---

## 5. Naver Map Scraping

Selenium is used to collect location information from Naver Map.

### Collected Data

- Name
- Category
- Address
- Distance

### Key Techniques

- `WebDriverWait`
- iframe switching
- CSS selectors
- Page scrolling
- Pagination
- Pandas `DataFrame`
- CSV export

---

## 6. Dynamic Page Handling

Dynamic websites require additional browser control during data collection.

### iframe Handling

```python
driver.switch_to.frame("searchIframe")
```

### Pagination

- Detect the state of the next-page button
- Navigate through multiple pages automatically
- Stop when no additional pages are available

### Lazy Loading

Page scrolling can be used to load content that is dynamically added while the user scrolls.

---

## 7. Data Processing and Export

Collected data can be converted into structured formats for further analysis.

### Pandas

```python
df = pd.DataFrame(data)
```

### CSV

```python
df.to_csv(
    "output.csv",
    index=False,
    encoding="utf-8-sig"
)
```

### Data Validation

- Check for missing elements before accessing values
- Handle `None` values
- Verify element existence
- Handle exceptions during scraping
- Validate collected data before saving

---

## 8. Web Scraping Workflow

A typical web scraping workflow consists of:

1. Identify the target website and required data
2. Inspect the HTML structure
3. Select appropriate elements
4. Send requests or automate browser interactions
5. Extract required information
6. Clean and structure the collected data
7. Export the data for further processing or analysis

</details>

<details>
<summary><h2>Projects</h2></summary>

- [MLB Web Scraping Project](https://github.com/LutetiumCalciumLee/Web_scraping_MLB_Project)

</details>

</details>

<details>
<summary>KOR (한국어 버전)</summary>

# 웹 스크래핑

이 Repository에는 인공지능소프트웨어과 하이테크 과정에서 학습한 웹 스크래핑 내용과 프로젝트를 정리하여 업로드했습니다.

<details>
<summary><h2>주요 내용</h2></summary>

## 1. 웹 스크래핑 개요

웹 스크래핑은 웹사이트에서 필요한 정보를 추출하여 비정형 웹 데이터를 정형화된 형태로 변환하는 기술입니다.

### 웹 크롤링과 웹 스크래핑

- **웹 크롤링(Web Crawling)**: 링크를 따라 웹 페이지를 탐색하면서 정보를 수집
- **웹 스크래핑(Web Scraping)**: 특정 웹 페이지에서 필요한 데이터를 선택적으로 추출

### 주요 도구 및 라이브러리

- **Selenium**: 동적 웹사이트 및 JavaScript 기반 페이지의 브라우저 자동화
- **BeautifulSoup**: HTML/XML 파싱 및 데이터 추출
- **Requests**: 웹 페이지를 가져오기 위한 HTTP 요청
- **Pandas**: 수집한 데이터의 처리 및 구조화
- **CSV**: 수집 데이터를 표 형태로 저장

---

## 2. Selenium을 활용한 웹 스크래핑

Selenium을 이용하여 브라우저 동작을 자동화하고 동적으로 렌더링되는 웹 페이지에서 데이터를 수집합니다.

### 주요 개념

- WebDriver를 이용한 브라우저 자동화
- CSS Selector, XPath, Link Text를 이용한 요소 탐색
- 텍스트 및 속성값 추출
- 페이지 스크롤
- 페이지네이션
- 동적 콘텐츠 처리
- CSV 데이터 저장

### 대기 방식

- **Implicit Wait**: 요소가 나타날 때까지 전역적으로 대기
- **Explicit Wait**: 특정 조건이 충족될 때까지 대기
- **`time.sleep()`**: 브라우저 작업 사이에 일정 시간 대기

---

## 3. 네이버 뉴스 스크래핑

Selenium을 이용하여 네이버 뉴스 검색 과정을 자동화하고 기사 정보를 수집합니다.

### 수집 데이터

- 언론사
- 날짜
- 제목
- 링크
- 설명

### 주요 과정

1. Selenium으로 웹 브라우저 실행
2. 검색어 입력
3. 뉴스 영역으로 이동
4. 추가 검색 결과 로드
5. 기사 정보 추출
6. 수집 데이터를 CSV 파일로 저장

---

## 4. IMDb 시리즈 데이터 스크래핑

`Requests`와 `BeautifulSoup`을 이용하여 IMDb의 에피소드 정보를 수집합니다.

### 기본 구조

```python
res = requests.get(url, headers=headers)
soup = BeautifulSoup(res.text, "lxml")
```

### 수집 데이터

- 에피소드 제목
- 방영일
- 평점
- 투표 수
- 설명

### 주요 기법

- HTML 파싱
- `find()` 및 `find_all()`
- 속성 기반 요소 탐색
- 누락된 데이터 처리
- CSV 저장

---

## 5. 네이버 지도 스크래핑

Selenium을 이용하여 네이버 지도 검색 결과에서 장소 정보를 수집합니다.

### 수집 데이터

- 장소명
- 카테고리
- 주소
- 거리

### 주요 기법

- `WebDriverWait`
- iframe 전환
- CSS Selector
- 페이지 스크롤
- 페이지네이션
- Pandas `DataFrame`
- CSV 저장

---

## 6. 동적 웹 페이지 처리

동적 웹사이트에서는 데이터 수집을 위해 추가적인 브라우저 제어가 필요합니다.

### iframe 처리

```python
driver.switch_to.frame("searchIframe")
```

### 페이지네이션

- 다음 페이지 버튼 상태 확인
- 여러 페이지 자동 이동
- 마지막 페이지에서 반복 종료

### Lazy Loading

스크롤을 이용하여 사용자 이동에 따라 동적으로 추가되는 콘텐츠를 로드합니다.

---

## 7. 데이터 처리 및 저장

수집한 데이터를 구조화하여 이후 데이터 분석 등에 활용할 수 있도록 저장합니다.

### Pandas

```python
df = pd.DataFrame(data)
```

### CSV

```python
df.to_csv(
    "output.csv",
    index=False,
    encoding="utf-8-sig"
)
```

### 데이터 검증

- 값 접근 전 요소 존재 여부 확인
- `None` 값 처리
- 요소 탐색 실패 처리
- 스크래핑 과정의 예외 처리
- 저장 전 수집 데이터 확인

---

## 8. 웹 스크래핑 작업 흐름

일반적인 웹 스크래핑 과정은 다음과 같습니다.

1. 대상 웹사이트와 필요한 데이터 선정
2. HTML 구조 분석
3. 필요한 요소의 Selector 확인
4. HTTP 요청 또는 브라우저 자동화
5. 데이터 추출
6. 수집 데이터 정제 및 구조화
7. 파일로 저장하여 후속 분석에 활용

</details>

<details>
<summary><h2>프로젝트</h2></summary>

- [MLB Web Scraping Project](https://github.com/LutetiumCalciumLee/Web_scraping_MLB_Project)

</details>

</details>
