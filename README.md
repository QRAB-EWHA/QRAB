<!-- Template for PROJECT REPORT of CapstoneDesign 2024-2H, initially written by khyoo -->
<!-- 본 파일은 2024년도 컴공 졸업프로젝트의 <1차보고서> 작성을 위한 기본 양식입니다. -->
<!-- 아래에 "*"..."*" 표시는 italic체로 출력하기 위해서 사용한 것입니다. -->
<!-- "내용"에 해당하는 부분을 지우고, 여러분 과제의 내용을 작성해 주세요. -->

# Team-Info

| (1) 과제명            | QRAB(큐랩): 대학생을 위한 AI 기반 퀴즈 생성을 통한 학습 보조 서비스                                                                                                                                                                                                                                                                                                                                                                                                                                                                                            |
| :-------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| (2) 팀 번호 / 팀 이름 | 16-불사신                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| (3) 팀 구성원         | 김민영 (2076040): 리더, 백엔드, AI <br> 이윤진 (2176000): 팀원, 백엔드, AI <br> 최영서 (2176000) : 팀원, 프론트엔드, AI                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |
| (4) 팀 지도교수       | 심재형 교수님                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| (5) 팀 멘토           | 임도형 / 로완 / CTO/CAIO                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
| (6) 과제 분류         | 산학 과제                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| (6) 과제 키워드       | 텍스트 생성형 AI, RAG, OCR, WEB                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| (7) 과제 내용 요약    | QRAB(큐랩)은 온라인으로 노트, 학습 블로그 등을 작성하는 대학생을 대상으로 하는 AI 기반 퀴즈 생성 및 학습 보조 웹 서비스입니다. 현재 시중에 온라인 노트 작성 서비스나 퀴즈 서비스는 존재하지만, 사용자가 자신의 학습 자료를 활용해 복습할 수 있는 플랫폼은 존재하지 않습니다. 이에 저희는 사용자가 자신이 기존에 작성한 학습 자료를 활용할 수 있도록 하고, 학습 효율을 높일 수 있게 하는 새로운 플랫폼을 개발하고자 했습니다.<br><br>QRAB에서 사용자는 자신이 기존에 작성한 자료를 URL, PDF, 이미지 파일 등 다양한 형태로 불러와 노트로 저장합니다. 그 다음 저장한 노트를 통해 자동 퀴즈를 생성하고, 다양한 난이도로 생성된 퀴즈를 풀며 자연스럽게 복습을 수행합니다. 이후 필요에 따라 틀린 퀴즈를 바탕으로 하는 응용 퀴즈를 생성해 학습 효과를 높일 수 있습니다. 이렇게 푼 퀴즈들을 바탕으로 사용자는 학습 분석 단계에서 월 별 학습 분석, 취약 카테고리 분석 등을 살펴보며 자신의 학습 패턴과 보완점을 인지할 수 있습니다. 또, 상세 분석을 통해 사용자 맞춤형 학습 전략 및 추천 자료를 제공받습니다.<br><br>사용된 기술은 다음과 같습니다. 우선 Frontend는 React, Backend는 Spring Boot를 활용해 개발했습니다. 저희는 크롤링 기능을 위해 JSoup 라이브러리를 활용하며, 이미지 파일의 텍스트를 추출하기 위해 Naver Clova OCR API를 사용합니다. 웹 페이지의 전체 화면을 캡처하기 위해 Selenium WebDriver를 사용하며, PDF parsing을 위해 Apache PDFBox 라이브러리를 사용합니다. 노트 요약, 퀴즈 생성, 학습 분석에는 ChatGPT-4o mini API가 사용되며, 학습 분석에는 RAG와 Langchain을 사용해 학습 분석의 정확도를 높입니다.|

<br>

# Project-Summary

| 항목                  | 내용                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| :-------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| (1) 문제 정의         | [고객 페르소나]<br><br>- 20대 대학생<br>- 평소 Notion, Velog, Tistory 등의 공간에 자신의 학습 내용을 정리하는 것을 즐긴다. 많은 양의 노트를 작성하면서도 그 노트를 제대로 활용하지 못해 답답함을 느낀다.<br>- 노트를 다시 읽을 시간이 부족하거나, 노트를 바탕으로 어떻게 복습해야 할지 몰라 어려움을 겪고 있다.<br>- 매 학기 필기는 열심히 하지만 막상 시험 기간이 되면 복습이 부족해 처음부터 다시 공부를 해야 하고, 필기를 읽는 것만으로는 자신의 수준이 파악되지 않아 시험이 다가올수록 불안감이 커진다.<br><br>[Pain Point]<br><br>1. 읽고 외우는 학습 방식에 효능감을 느끼지 못한다.<br>- 학습 자료를 읽고 외우는 방식은 가장 고전적인 방식이지만, 학습 효율에 대해서는 의문을 제기하는 학생들이 많았습니다. 학습 시간이 오래 걸리는 것은 물론, 적절한 동기 부여를 받지 못하고 자신의 학습 수준을 파악하지 못한다는 단점이 있었습니다.<br><br>2. 문제 풀이를 통해 지식을 익히려 하지만, 풀 문제가 없다.<br>- 읽고 외우는 방식이 자신에게 적합하지 않다고 느낀 학생들은 자주 문제 풀이를 통해 학습 효과를 증진하려 합니다. 그런데 운 좋게도 공부하려는 분야의 기출 문제가 제공되어 있는 경우도 있지만, 그렇지 않은 경우가 더 많습니다. 또, 같은 분야라 하더라도 인터넷 검색을 통해 습득한 기출 문제는 문제의 기반이 되는 자료가 다르기 때문에 문제에 학생들이 학습하지 않은 내용이 등장하기도 합니다.<br><br>3. 어느 부분을 더 공부해야 하는지 스스로 파악하기 어렵다.<br>- 보완할 부분을 찾아 그 부분을 중점적으로 공부하는 것은 어느 분야에서든 중요합니다. 그러나 이를 스스로 해내기란 몹시 어렵습니다. 스스로 일정 수준 이상 공부를 했다고 여기는 학생들은 자료를 봐도 모두 자신이 아는 내용이라 여기는 오류를 범하게 됩니다.<br><br>4. 꾸준한 복습을 원하지만, 습관 개선이 어렵다.<br>- 매번 시험이 다가오면 급하게 벼락치기를 하는 습관이 있는 학생들이 많았습니다. 배운 직후부터 꾸준히 복습하지 않으니 막상 자료를 펼쳐 봤을 때에는 이미 기억에서 휘발된 내용이 많습니다. 학생들은 배운 내용을 다시 익혀야 하는 과정을 불필요하게 겪게 되며, 이는 자연스럽게 학습 효율 저하로 이어집니다.<br><br>5. 자신의 학습 기록을 기록할 수 있는 공간은 많지만, 이를 바탕으로 복습을 유도하는 플랫폼은 없다.<br>- 기업 입사 시에도 개인 공부 블로그의 중요성이 강조되면서 Notion, Velog, Tistory 등 자신의 학습 내용을 기록할 수 있는 플랫폼이 인기를 끌게 되었습니다. 그러나 아무리 개인 블로그에 정리해 둔 내용이라 하더라도 수차례 복습하지 않으면 쓸모가 없어집니다. 공부 블로그 작성은 당장 학습 내용을 정리하며 일시적으로 기억을 향상하는 데에는 긍정적인 영향을 미치지만, 이를 통해 다시 학습하지 않는다면 읽고 외우는 학습 방식과 마찬가지로 장기적으로는 큰 도움이 되지 않을 수 있습니다. |
| (2) 기존연구와의 비교 | [시장 내 경쟁 제품 비교]<br><br>현재 시장에 마땅한 경쟁 제품이 존재하지 않기 때문에, 기능 면에서 유사한 부분이 있는 세 가지 서비스와 비교해 보겠습니다. 저희 서비스와 유사한 기능인 AI 기반 학습 기능을 가지고 있는 기존 서비스에는 **Santa**와 **Speak**이 존재하며, 자체 퀴즈 제작 기능을 가지고 있는 서비스에는 **Quizlet**이 존재합니다.<br><br>![타 서비스 기존 평가 이미지](https://drive.google.com/uc?export=view&id=1mpQsIDdSsuu3KgL1jCkWj1GnpnBc332L) <br>안 보일 시 클릭해 주세요!<br>유사 기능을 지닌 서비스인 Santa, Speak, 그리고 Quizlet의 기존 평가입니다. 대체로 유료 모드의 가격이 높다는 것과 난이도 조절이 불가능하다는 것, 출제 분야가 제한되어 있다는 비판이 많습니다. 즉, 세 가지 모두 사용자 맞춤형 퀴즈 서비스는 아니라는 것입니다.<br><br>![타 서비스와의 비교 표 이미지](https://drive.google.com/uc?export=view&id=1FZF2Rn2OxIvcaNcwTSdOQybFTh8ME-gc) <br>안 보일 시 클릭해 주세요!<br>구체적인 타 서비스와의 비교입니다. **Santa**, **Speak**은 TOEIC 시험 대비 서비스로, 자동으로 퀴즈가 생성되기는 하지만 자기 자료 기반 학습이 아닌 영어 학습에만 특화되어 있습니다. **Quizlet**은 자기 자료에 기반하기는 하지만 퀴즈를 업로드할 수 있는 플랫폼일 뿐, 퀴즈는 사용자가 직접 출제해야 합니다. 이외에도 자동 퀴즈 생성, 복습 유도, 학습 결과 분석 등 다른 모든 부분에서 미흡합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| (3) 제안 내용         | 1. 읽고 외우는 방식이 아닌, 문제 풀이 환경을 제공<br>- 시험을 대비하는 가장 빠른 방법은 기출 문제를 푸는 것입니다. 공부도 마찬가지입니다. 단순히 회독을 거듭하며 암기하는 방식에서 벗어나 직접 문제를 풀어 봄으로써 사용자는 자신의 수준을 정량적으로 평가할 수 있습니다.<br><br>2. 자기 자료 기반의 문제 제공<br>- 기출 문제가 모든 분야에 다 존재하는 것은 아닙니다. 기출 문제를 소지하고 있지 않은 사용자를 위해, 사용자 자신이 작성한 자료를 기반으로 한 문제를 제공합니다. 이를 통해 사용자는 보다 정확하고 높은 품질의 문제를 풀어 볼 수 있습니다.<br><br>3. 취약점 분석과 학습 방향 제시<br>- 자신의 미흡한 부분을 객관적으로 짚어내기란 어렵습니다. 카테고리 별 정답률 분석을 통해 사용자의 취약점을 객관적으로 분석하여 제공합니다. 또, 이를 보완하기 위해 앞으로의 학습 가이드라인과 참고 자료 또한 제공합니다.<br><br>4. 복습 유도와 동기 부여<br>- 알림 메시지를 지속적으로 보내 복습을 유도하고, 친구들과 경쟁하는 스코어보드와 학습량에 따른 별자리 채우기 등 사용자가 시각적으로 자극받을 수 있는 요소를 제공합니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| (4) 기대효과 및 의의  | [기대 효과]<br><br>ㅇ 효율적인 지식 습득<br>- 단순히 필기한 노트를 읽기만 하는 복습 방식을 통해서는 학습 동기 부여가 미미할뿐더러 자신의 학습 수준을 파악하기도 어렵습니다. QRAB에서 사용자는 자료를 읽고 외우기만 하는 학습 방식에서 벗어나 자신의 학습 자료로 생성된 퀴즈를 풀며 효율적으로 학습할 수 있습니다.<br><br>ㅇ 약점 보완을 통한 자신감 향상 도모<br>- 부족한 부분을 모르면 자신의 학습 수준을 파악할 수 없습니다. 응용 퀴즈 생성을 통해 사용자는 자신이 틀린 퀴즈를 기반으로 생성된 유사한 내용의 퀴즈를 풀어 보며 취약한 분야를 보완하고, 자신감 향상을 도모할 수 있습니다.<br><br>ㅇ 꾸준한 복습 습관 형성<br>- 학습 분석 페이지의 월별 학습 기록과 카테고리별 학습 분석, 취약 카테고리 분석, 상세 분석, 그리고 알림 메시지와 스코어보드 기능을 통해 사용자는 학습 욕구와 경쟁심을 자극받아 꾸준히 복습할 수 있습니다.<br><br>ㅇ 쉽고 빠른 목표 달성<br>- QRAB에서 할 수 있는 일은 중간고사, 기말고사 등의 시험 대비만이 아닙니다. 사용자들은 QRAB을 취업 준비 시에는 기업/직무별 맞춤형 준비용, 고시 공부 시에는 문제 은행 및 취약점 체크용으로 사용하는 등 각자의 목적에 맞게 활용하며 목표를 이룰 수 있습니다.<br><br>[QRAB 서비스의 파급 효과]<br><br>1. 학습 접근성과 효율성 향상<br>- 온라인 학습 시장이 확대되며 교육의 기회는 많은 사람들에게 보다 평등하게 주어지고 있습니다. QRAB을 통해 대학생들이 시간과 장소에 구애받지 않고 자신만의 학습 패턴에 맞춰 공부할 수 있게 된다면, 결과적으로는 학습 격차가 줄어들고 보다 평등한 교육 환경을 조성할 수 있을 것입니다.<br><br>2. 바쁜 사용자에게 시간 확보<br>- 사용자는 QRAB의 퀴즈 생성과 응용 퀴즈 생성 기능을 이용하며 불필요한 부분에서 헤매느라 낭비되는 공부 시간을 줄이고 핵심 내용에 집중할 수 있습니다. 이를 통해 단기적으로는 전반적인 학습 성과를 향상할 수 있고, 장기적으로는 원활한 학점 관리와 전공 지식의 꾸준한 복습을 꾀할 수 있습니다. QRAB은 학생들이 다른 활동에 더 많은 시간을 할애할 수 있도록 도와줄 것입니다.<br><br>3. 다양한 니즈에 맞춘 서비스 제공<br>- 취업 준비와 고시 공부 등 다양한 니즈에 맞춘 서비스 제공으로 여러 목적을 가진 사용자들의 훌륭한 러닝메이트가 되어 줍니다. QRAB은 대학생뿐만 아니라 직무 전환을 고려하는 직장인 사용자에게도 큰 도움이 될 수 있으며, 다양한 직업군에서의 인재 양성과 직무 역량 강화에도 기여할 것입니다.<br><br>4. 학습 데이터를 활용한 교육 기술 발전 기여<br>- AI를 활용한 학습 분석 데이터 분석은 교육 기관과 기업이 더 나은 교육 콘텐츠를 개발하고, 학습자들에게 보다 효과적인 학습 방법을 제공할 수 있는 기반이 될 것입니다. QRAB은 교육 기술 분야의 혁신을 주도하고, 전 세계적으로 더 나은 학습 환경을 구축하는 데에 긍정적인 파급 효과를 일으킬 수 있습니다.                |
| (5) 주요 기능 리스트  | [기능 설명]<br><br> ㅇ 노트 저장<br>- 사용자가 Notion, Velog, Tistory 등 타 플랫폼에서 작성한 학습 자료는 물론, PDF나 이미지 파일 또한 불러와 텍스트를 추출한 뒤 노트에 저장할 수 있습니다.<br><br> ㅇ 학습 자료 요약<br>- 사용자에게 자신의 학습 자료를 요약한 요약본을 제공합니다. 사용자는 퀴즈 풀이 전에 언제나 요약본을 열람할 수 있습니다.<br><br> ㅇ 퀴즈 생성<br>- 사용자의 학습 자료를 바탕으로 퀴즈를 생성합니다. 사용자는 직접 생성할 퀴즈의 개수를 설정할 수 있으며, 다양한 난이도의 퀴즈를 풀 수 있습니다. 사용자는 생성한 퀴즈를 자신이 원하는 때에 풀 수 있습니다.<br><br> ㅇ 응용 퀴즈 생성<br>- 사용자가 틀린 퀴즈를 기반으로 한 응용 퀴즈를 생성합니다. 이전에 퀴즈를 생성했던 노트라면, 해당 노트로 퀴즈 재생성 시에 이전 퀴즈 결과를 기반으로 퀴즈를 생성할지, 새로 퀴즈를 생성할지 선택할 수 있습니다.<br><br> ㅇ 학습 분석<br>- 사용자의 월별 학습 기록과 이에 대한 분석 결과, 카테고리별 학습 분석, 취약점 분석, 상세 분석을 지원합니다. 사용자는 이를 통해 자신의 학습 패턴과 약점과 강점 등을 파악하고 앞으로의 학습 방향을 제시받을 수 있습니다.<br><br> ㅇ 알림 메시지<br>- 복습 유도를 위해 사용자에게 SMS를 통해 알림 메시지를 발송합니다. 알림은 사용자 설정에 따라 ON/OFF 할 수 있습니다.<br><br> ㅇ 스코어보드<br>- 사용자가 메인 화면에서 스코어보드를 확인할 수 있도록 하여 사용자에게 학습 동기를 부여합니다. 스코어보드는 친구 목록 내의 사용자를 기준으로 하며, 자신과 친구들의 학습량 순위를 통해 순위가 정해집니다.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |

<br>
 
# Project-Design
| 항목 | 내용 |
|:---  |---  |
| (1) 요구사항 정의 | ![ER 다이어그램 이미지](https://drive.google.com/uc?id=1ey8cE0OzjvX_C4eHsDdJUubtrPsBgp8R) <br><br>1. USER 중심 구조: USER 테이블은 주요 기능(퀴즈, 노트, 친구 관계, 로그인 기록, 프로필 등)과 연결된 중심 테이블로, 사용자 권한(USERAUTHORITY)과 사용자 학과(USERMAJOR)를 관리합니다.<br><br>2. QUIZ와 ANALYSIS 관계: QUIZSET과 QUIZRESULT는 사용자의 퀴즈 활동을 기록하고, 이를 통해 DETAILEDANALYSIS와 CATEGORYANALYSIS에서 학습 통계를 생성합니다.<br><br>3. NOTE와 CATEGORY 관계: 사용자가 작성한 NOTE는 특정 CATEGORY에 속하며(상위 혹은 하위 카테고리), AI 생성 콘텐츠(chatgpt_content)도 포함해 사용자별 개인 노트 정보를 체계적으로 관리합니다.<br><br>4. FRIENDSHIP: FRIENDSHIP 테이블은 사용자의 친구 관계를 정의하며, 사용자별 친구 정보를 저장합니다.<br><br>5. AI 대화 기록: CHATGPT 테이블은 노트 요약본 생성 및 퀴즈 생성 데이터를 생성합니다. |
| (2) 전체 시스템 구성 | ![전체 시스템 구조도 이미지](https://drive.google.com/uc?id=1oPjgvcG7UyIR0HCJGsGQJ3f1_7nwxyAU) <br> [주요 SW 모듈] <br><br>ㅇ 노트 저장 <br><br>노트 저장 기능의 구현을 위하여 텍스트를 추출할 수 있는  JSOUP 라이브러리, Naver OCR API, Apache PDF BOX, Selenium Web Driver 라이브러리를 사용하였고, 추출된 텍스트 데이터요약을 위해 Chat GPT-4o mini API를 사용했습니다. <br>클라이언트가 노트 링크 또는 파일을 보내면 서버에서 해당 데이터를 저장하고 사용하기 위해 백엔드와 프론트엔드에서는 노트 생성, 조회, 수정, 삭제 관련 기능을 구현하는 Note App 모듈을 만들고 데이터베이스를 설계했습니다. Amazon 클라우드 서비스를 이용하여 텍스트를 저장하는 데이터베이스는 RDS를, 이미지 파일을 저장하는 데이터베이스는 S3를 사용했습니다. <br><br> ㅇ 퀴즈 생성 <br><br>퀴즈 생성 기능의 구현을 위하여 Chat GPT-4o mini API를 도입하였고 프롬프트 엔지니어링을 통한 few shot prompting을 거쳐 퀴즈 생성과 응용 퀴즈 생성을 구현했습니다. <br>백엔드와 프론트엔드에서는 퀴즈 풀이 결과 저장 및 과거 퀴즈 기록 조회 등의 퀴즈 관련 기능을 위해 Quiz App 모듈을 만들고 이에 해당하는 데이터베이스를 설계했습니다. <br><br> ㅇ 학습 분석 <br><br>학습 분석 기능의 구현을 위하여 Chat GPT-4o mini API를 도입했으며, 자료 추천 성능 향상과 Hallucination 해소를 위해 FastAPI와 Docker, LangChain을 이용해 RAG 시스템을 구현했습니다. FastAPI는 사용자의 학습 기록을 바탕으로 RAG 프로세스를 처리하고, LangChain을 이용해 Chroma DB에서 데이터를 검색한 뒤 ChatGPT 4o-mini API를 호출해 적합한 학습 자료를 제공합니다. Docker는 FastAPI와 Chroma DB를 동일한 환경에서 실행하고 관리하며 관리를 용이하게 해줍니다.<br>백엔드와 프론트엔드에서는 Analysis App 모듈을 구현하여 사용자의 퀴즈 정답률, 학습량을 기반으로 한 월별 / 카테고리별 그래프 및 차트를 제공하였고 상세 학습 분석을 통해 학습 로드맵 제시 및 학습 자료 추천 기능을 구현했습니다.  |
| (3) 주요엔진 및 기능 설계 | <br> [클라이언트]<br><br>ㅇ 회원가입 : 이메일, 닉네임, 학과를 비롯한 사용자 정보를 입력하여 사용자 데이터를 서버에 전송합니다.<br><br>ㅇ 노트 저장 : 기술 블로그 등 퀴즈 생성의 source가 되는 웹사이트의 URL 링크를 입력하거나, 이미지, PDF 파일을 사용자 컴퓨터에서 업로드 하여 서버에게 전송할 수 있습니다. 이를 통해 서버가 해당 웹사이트 또는 파일의 텍스트를 추출하여 텍스트 데이터를 기반으로 한 노트를 생성할 수 있습니다.<br><br>ㅇ 퀴즈 생성 : 퀴즈 풀기 버튼 클릭 시 퀴즈 문제들을 담고 있는 퀴즈 set를 불러오라는 요청이 서버로 전송됩니다.<br><br>ㅇ 퀴즈 풀이 : 사용자가 퀴즈를 다 풀고 채점하기 버튼을 클릭하면 정/오답 결과가 서버로 전송됩니다.<br><br>ㅇ 학습 분석 : 학습 분석 탭 클릭 시 사용자가 풀이한 퀴즈 결과를 기반으로 한 학습 분석 데이터를 불러오라는 요청이 서버에 전송됩니다.<br><br>ㅇ 친구 추가 : 친구 추가 버튼 클릭 시 팔로잉 요청이 서버로 전송되고, 친구의 노트 보기 버튼을 클릭 시 친구의 노트 데이터를 불러오라는 요청이 서버에 전송됩니다.<br><br> [서버] <br><br>ㅇ 로그인/회원가입 및 소셜 기능 <br><br>1. 서버는 사용자로부터 입력받은 정보를 기반으로 사용자 개인정보를 생성하고, 사용자 요청에 따라 데이터 조회, 수정, 삭제 기능을 수행합니다.<br>2. 팔로잉 한 친구 목록을 조회하고 수정하는 기능을 수행합니다.<br><br>ㅇ 노트 관련 기능<br><br>1. 사용자로부터 입력받은 웹사이트 링크 또는 이미지/PDF 파일들로부터 텍스트 추출 후 요약본을 저장합니다. 텍스트 추출 시에는 Tistory, Velog 블로그 웹사이트의 경우 JSOUP 라이브러리를 사용하여 HTML 파일을 크롤링하고, PDF 파일의 경우에는 APACHE PDF BOX 라이브러리를 이용하여 텍스트를 추출합니다. 이미지 파일의 경우에는 NAVER CLOVA OCR API를 이용해 이미지 내의 텍스트를 추출하고, Tistory, Velog 외의 웹사이트는 Selenium Web Driver를 이용해 웹사이트 전체 화면을 스크린샷 하여 이미지 파일로 변환한 후, 마찬가지로 NAVER CLOVA OCR API를 이용합니다.<br>2. 위와 같은 방식으로 추출된 텍스트 데이터는 Chat GPT-4o mini에 의해 요약본이 만들어지고 서버에 저장합니다.<br>3. 사용자가 저장한 노트 목록들을 조회할 수 있는 기능을 수행합니다.<br><br>ㅇ 퀴즈 관련 기능<br><br>1. 사용자가 특정 노트에 대해 퀴즈 생성 버튼을 클릭하면 서버는  Chat GPT-4o mini를 이용하여 해당 노트 데이터를 기반으로 한 퀴즈를 생성합니다.<br>2. 응용 퀴즈 풀기 버튼 클릭 시 이전의 퀴즈 채점 결과 기록을 바탕으로 사용자에게 적합한 응용 퀴즈를 제공합니다.<br>3. 사용자가 전송한 퀴즈 채점 결과를 데이터베이스에 저장합니다.<br>4. 틀린 퀴즈들을 분류하고, 사용자가 오답 다시 풀기 버튼을 클릭 시 틀린 퀴즈 조회 기능을 수행합니다.<br>5. 클라이언트가 퀴즈 채점 후 저장하고자 하는 퀴즈를 북마크로 표시하면, 서버는 전송된 북마크 퀴즈를 저장하고, 사용자가 이후에 북마크 퀴즈 버튼 클릭 시 조회할 수 있는 기능을 수행합니다.<br><br>ㅇ 학습 분석 기능<br><br>1. 사용자의 퀴즈 채점 결과 데이터를 기반으로, 정답률에 따른 카테고리별 학습 그래프와, 퀴즈 생성 횟수를 기반으로 한 학습량에 따른 월별 학습 그래프를 조회하는 기능을 수행합니다. 이를 통해 사용자는 취약한 카테고리를 확인할 수 있고, 학습량이 부족한 달이 언제인지 확인할 수 있습니다.<br>2. 특정 월의 각 날짜마다 몇 문제를 풀었는지, 정답률은 몇 퍼센트인지를 표시하는 학습량/정답률 표시 캘린더 조회 기능을 수행합니다.<br>3. Chat GPT-4o mini를 이용하여 취약한 카테고리가 무엇인지 분석하고 사용자에게 도움이 될 만한 학습 방법이나 참고 자료를 제공합니다. 학습 분석 기능의 정확성을 위해 RAG 시스템을 구현하여 Chat GPT-4o mini가 허구의 데이터를 제공하지 않도록 합니다.  |
| (4) 주요 기능의 구현 | ㅇ 노트 저장<br>1. Prompt 내용 요약<br>- 사용자가 선택한 노트 내용을 요약하기 위해 다양한 주제(예: 스프링 부트, 심리학 개념 등)에 대한 간결하고 체계적인 요약 예시를 제공하고, 요약 방식에 대한 구체적인 안내를 포함했습니다.<br><br>2. 상세 구현 방법<br>- Few-shot prompting* 기법을 활용해 모델이 주어진 노트 내용을 A4 한 페이지 분량으로 요약하도록 했습니다. 프롬프트는 요약 예시와 함께 주요 개념을 논리적으로 정리하도록 안내하며, 불필요한 기호(#, * )는 포함하지 않도록 설정했습니다.<br>- 요약된 결과는 논리적 흐름을 유지하면서도 상세하고 포괄적인 내용을 담도록 설계했습니다. 테스트 결과, 사용자가 이해하기 쉽고 체계적인 요약본이 생성됨을 확인할 수 있었습니다.<br><br>* Few-shot prompting: prompt에 소량의 예시를 제공하여 모델이 더 나은 성능을 발휘하도록 하는 방법.<br><br>ㅇ 퀴즈 생성<br>1. Prompt 내용 요약<br>- 사용자의 전공 정보(예: 컴퓨터공학, 심리학)와 해당 노트의 노트 요약본을 입력 정보로 제공하고 난이도, 질문, 4개의 선택지, 정답, 풀이, 퀴즈 요약을 포함한, 사용자가 원하는 개수의 퀴즈를 생성하도록 했습니다.<br><br>2. 상세 구현 방법<br>- 프롬프트에 사용자가 선택한 노트 요약본을 더해 해당 노트를 통해 퀴즈를 출제하게 했습니다. 고품질 퀴즈 생성을 위해 Few-shot prompting을 진행했으며, JSON 형식으로 결과물을 반환하게 해 로직을 간단히 했습니다.<br><br>- 난이도 책정 기준<br>  - Easy: 기본 개념을 묻는 문제로, 약 80% 이상의 정답자 예상<br>  - Medium: 심화 개념이나 깊은 이해가 필요한 문제로, 약 50% 이상의 정답자 예상<br>  - Hard: 고급 개념을 요구하는 문제로, 약 30% 미만의 정답자 예상<br>위와 같은 기준을 세워 각 난이도에 따라 퀴즈를 출제하도록 했으며, 여러 차례 테스트 결과 기준대로 난이도가 올바르게 매겨진 것을 확인할 수 있었습니다.<br><br>ㅇ 학습 분석<br>1. Prompt 내용 요약<br>- 사용자의 취약 카테고리와 강한 카테고리, 사용자가 틀린 퀴즈들의 퀴즈 요약을 입력 정보로 제공하고 사용자의 강점과 약점을 분석, 약점 보완 방법과 추천 자료를 제공하도록 했습니다.<br><br>2. 상세 구현 방법<br>사용자 분석 결과를 사용자가 퀴즈를 풀 때마다 DB에 업데이트 합니다. DB에 저장해 둔 사용자 분석 결과를 토대로 프롬프트에 사용자의 틀린 퀴즈 요약을 더해 사용자가 주로 틀리는 퀴즈의 유형이 어떤 것인지 알아낼 수 있도록 틀린 퀴즈 요약의 공통점을 찾도록 했습니다. 여러 차례 테스트 결과 공통점을 올바르게 찾아낸 것을 확인할 수 있었습니다. 원활한 결과 출력과 자료 추천 시의 Hallucination* 방지를 위해 few-shot prompting과 RAG** 를 적용했습니다.<br><br>* Hallucination: 환각, LLM이 답을 모르는 질문에 그럴싸한 답변을 제공하는 현상.<br>** RAG(Retrieval Augmented Generation): 검색 증강 생성, LLM(Large Language Model)의 한계 중 하나인 Hallucination을  보완하는 방법. 외부 데이터에서 검색하여 사용자의 질문을 보강하고, 더 좋은 답변을 생성함. |
| (5) 기타 | 이미지 파일이 안 보이시면 이미지 글씨 클릭해 주시면 됩니다. |
<br>

# Evaluation
| 항목 | 내용 |
|:---  |---  |
| (1) 평가(Evaluation) | 1. 평가항목 선정 <br> - 평가항목 설명 : 사용자 요구사항과 기술적 목표를 기반으로 3가지 주요 평가항목을 선정했습니다. <br> - 평가항목 선정 사유 : 서비스 타겟층이 대학생이고, 특히 교육 관련 서비스이므로 사용자 인터페이스의 직관성과 기능의 완성도가 중요합니다. 또한 학습 데이터 처리 성능이 서비스 품질에 직접적인 영향을 미치기 때문에 이를 평가항목으로 선정했습니다. <br> 2. UI/UX 사용성 <br>2.1. UI/UX 사용성 <br> - 직관적인 사용자 인터페이스 설계와 사용자 경험을 평가합니다. 특히 노트 저장, 학습 자료 요약, 퀴즈 생성 등 핵심 기능들의 사용 편의성을 중점적으로 평가합니다. <br>2.2 평가 기준 <br> - 기준 1 (50-65점): 기본적인 UI 구성요소가 구현되어 있으나 사용성이 부족함 <br>- 기준 2 (66-85점): 직관적인 UI와 원활한 기능 사용이 가능함<br>- 기준 3 (86-100점): 사용자 친화적 UI와 함께 효율적인 기능 사용이 가능함<br>2.3 평가 방식 <br> - 실제 사용자 테스트를 통한 피드백 수집<br>- 주요 기능별 사용성 테스트 진행 (노트 저장, 퀴즈 생성, 학습 분석 등)<br>- 5명의 테스트 사용자를 선정하여 각 기능당 수행 시간과 오류 횟수를 측정<br> 3. 기능 완성도 <br>3.1. 다양한 학습 지원 기능들의 구현 완성도와 안정성을 평가합니다. 특히 노트 저장, 텍스트 요약, 퀴즈 생성, 맞춤형 학습 보조, 통합 학습 환경 제공 등 핵심 기능의 완성도를 중점적으로 평가합니다. <br>3.2. 평가 기준 <br> - 기준 1 (50-65점): 기본적인 기능이 구현되어 있으나 안정성이 부족함<br> - 기준 2 (66-85점): 대부분의 기능이 안정적으로 구현되어 있음<br> - 기준 3 (86-100점): 모든 기능이 완벽하게 구현되어 있고 높은 안정성을 보임 <br>3.3 평가 방식 <br> - 각 기능별 요구사항 체크리스트 작성 및 검증 <br> - 기능 테스트 시나리오 실행 및 결과 측정<br> - 스트레스 테스트를 통한 안정성 검증 <br>4.성능 <br> 4.1. 시스템의 전반적인 성능과 효율성을 평가합니다. 특히 데이터 처리 속도와 시스템 응답 시간을 중점적으로 평가하여 사용자에게 원활한 서비스를 제공할 수 있는지 확인합니다. <br>4.2. 평가 기준 <br> - 기준 1 (50-65점): 기본적인 성능 요구사항을 충족하나 처리 속도가 느림 <br> - 기준 2 (66-85점): 대부분의 기능이 적정 속도로 처리되며 안정적으로 동작함 <br> - 기준 3 (86-100점): 모든 기능이 빠른 속도로 처리되며 자원을 효율적으로 사용함 <br>4.3. 평가 방식 <br> - 데이터 처리 속도 측정: 노트 저장, 텍스트 변환, 퀴즈 생성 등 주요 기능의 처리 시간 측정 <br> - 시스템 응답 시간 테스트: 각 기능 실행 시 서버 응답 시간 측정





|

<br>

# Conclusion
| 항목 | 내용 |
|:---  |---  |
| (1) 결론(Conclusion) |UI/UX 평가에는 '직관적인 인터페이스 구현 여부'와 '사용자 피드백 반영도'의 기준이 존재하였고, 95점의 결과를 얻었습니다. <br> 기능 완성도 평가에는 '요구사항 대비 구현된 기능의 완성도'의 기준이 존재하였고, 90점의 결과를 얻었습니다. <br> 성능 평가에는 '데이터 처리 속도'와 '시스템 응답 시간 UI/UX 평가'의 기준이 존재하였고, 90점의 결과를 얻었습니다. |
