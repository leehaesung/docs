---

copyright:
  years: 2015, 2016

---
# {{site.data.keyword.mobileanalytics_short}}를 사용하여 앱 모니터링
{: #monitoringapps}
*마지막 업데이트 날짜: 2016년 5월 6일*
{: .last-updated}

{{site.data.keyword.mobileanalytics_full}}는 모바일 애플리케이션에 대한 모니터링 및 분석을 제공합니다. 클라이언트 로그를 기록하고 {{site.data.keyword.mobileanalytics_short}} 클라이언트 SDK를 사용하여 데이터를 모니터링할 수 있습니다. 개발자는 이 데이터를 {{site.data.keyword.mobileanalytics_short}} 서비스에 전송할 시기를 제어할 수 있습니다. 데이터가 {{site.data.keyword.mobileanalytics_short}}에 전달될 때 {{site.data.keyword.mobileanalytics_short}} 대시보드를 사용하여 모바일 애플리케이션, 디바이스 및 클라이언트 로그에 대한 분석 통찰을 가져올 수 있습니다.
{: shortdesc}

## 사용자 정의 차트를 사용하여 데이터 시각화
{: #custom-charts}

분석 저장소에서 수집된 분석 데이터를 시각화할 수 있습니다. 이 시각화는 특정 유스 케이스에 대한 데이터를 조사할 수 있는 강력한 방법입니다. 보고하는 사용자 정의 데이터 외에 Operational Analytics에 의해 이미 수집된 데이터를 사용하여 차트를 작성할 수 있습니다.

### 클라이언트 로그에 대한 사용자 정의 차트 작성
{: #custom-charts-client-logs}

플랫폼에 대한 로거 API를 사용하여 전송된 로그 정보를 포함하는 클라이언트 로그에 대한 사용자 정의 차트를 작성할 수 있습니다. 또한 로그 정보는 환경, 앱 이름 및 앱 버전을 포함하여 디바이스에 대한 컨텍스트 정보를 포함합니다.

이 예에서는 클라이언트 로그 데이터를 사용하여 순서도를 작성할 수 있습니다. 최종 그래프는 특정 앱의 로그 레벨의 배포를 표시합니다. 또한 차트에서 다음 데이터를 볼 수 있습니다.

* 특정 데이터
  * 로그 레벨
* 메시지 데이터
  * 시간소인
* 디바이스 OS 컨텍스트 데이터
  * 애플리케이션 이름
  * 애플리케이션 버전
  * 디바이스 OS
* 디바이스 컨텍스트 데이터
  * 디바이스 ID
  * 디바이스 모델
  * 디바이스 OS 버전


1. 디바이스 로그를 수집하거나 분석을 수집하는 애플리케이션이 있는지 확인하십시오.
2. {{site.data.keyword.mobileanalytics_short}} 콘솔에서 **대시보드** 페이지의 **사용자 정의 차트** 탭을 클릭하십시오. 서버에 전송된 분석 메시지를 기반으로 하여 차트를 작성할 수 있습니다.
3. **차트 작성**을 클릭하여 새 사용자 정의 차트를 작성하고 다음 값을 제공하십시오.
  * 차트 제목: 애플리케이션 및 로그 레벨
  * 이벤트 유형: 클라이언트 로그
  * 차트 유형: 순서도
5. **차트 정의** 탭을 클릭하여 다음 값을 제공하십시오.
  * 소스: 애플리케이션 이름
  * 대상: 로그 레벨
  * 특성: 사용자의 앱 이름
7. **저장**을 클릭하십시오.

### 사용자 정의 데이터 내보내기
{: #export-custom-data}

각 사용자 정의 차트에서 JSON, XML 또는 CSV 형식으로 데이터를 내보낼 수 있습니다.

내보낸 데이터의 구조는 내보내는 차트에 따라 다릅니다. 데이터를 내보내려면 사용자 정의 차트의 오른쪽 상단에서 내보내기 아이콘을 클릭하십시오.



### 사용자 정의 차트 정의 내보내기 및 가져오기
{: #export-import-custom}

{{site.data.keyword.mobileanalytics_short}} 대시보드에서 프로그래밍 방식 또는 수동으로 사용자 정의 차트 정의를 가져오거나 내보낼 수 있습니다.

{{site.data.keyword.mobileanalytics_short}} 대시보드에 하나 이상의 사용자 정의 차트가 있는지 확인하십시오.
이 예에서는 수동으로 사용자 정의 차트 정의를 내보내고 가져옵니다.

1. {{site.data.keyword.mobileanalytics_short}} 콘솔에서 **대시보드** 페이지의 **사용자 정의 차트** 탭을 클릭하십시오. 
2. 사용자 정의 차트 정의를 내보내려면 **차트 내보내기**를 클릭하십시오. 이 조치는 `customChartsDefinition.json` 파일을 저장하기 위한 대화 상자를 표시합니다.
3. 파일을 저장할 위치를 선택하십시오.
4. 각 사용자 정의 차트 옆의 **차트 삭제** 아이콘을 클릭하여 모든 사용자 정의 차트를 삭제하십시오.
5. 사용자 정의 차트 정의를 가져오려면 **차트 가져오기**를 클릭하십시오. 이 조치는 파일을 선택하기 위한 대화 상자를 표시합니다.
6. 이전에 내보낸 `customChartsDefinition.json` 파일을 선택하여 여십시오.

또한 선택한 HTTP 클라이언트(예: CURL 또는 postman)를 사용하여 프로그래밍 방식으로 사용자 정의 차트를 내보내고 가져올 수 있습니다.
* 내보내기에 대한 GET 엔드포인트는 `http://mobile-analytics-dashboard.ng.bluemix.net/analytics-service/rest/data/customCharts/`입니다.
* 가져오기에 대한 POST 엔드포인트는 `http://mobile-analytics-dashboard.ng.bluemix.net/analytics-service/rest/data/customCharts/import`입니다.

**참고**: 존재하는 사용자 정의 차트 정의를 가져오는 경우, 결과적으로 중복 정의가 발생하며 {{site.data.keyword.mobileanalytics_short}} 대시보드가 중복 사용자 정의 차트를 표시함을 의미합니다.

## 경보 설정
{: #alerts}

활동을 더 잘 모니터링하기 위해 {{site.data.keyword.mobileanalytics_short}} 콘솔에서 경보 정의의 임계값을 설정할 수 있습니다.

초과되는 경우, {{site.data.keyword.mobileanalytics_short}} 콘솔 모니터를 알리기 위한 경보를 트리거하는 임계값을 구성할 수 있습니다. 트리거되는 경보가 콘솔에서 시각화되거나 경보가 사용자 정의 Webhook에 의해 처리될 수 있습니다. 이 기능은 클라이언트 로그 오류, 서버 로그 오류, 네트워크 대기 시간의 확장 기간 및 인증 실패를 발견하는 능동적인 방법을 제공합니다. 반응성 임계값 및 경보를 사용하면 사용자가 데이터를 이동하고 넓은 범위의 세분성 임계값을 설정할 필요가 없습니다.

### 클라이언트 로그에 대한 경보 정의 작성
{: #alert-def-client-logs}

클라이언트 로그를 기반으로 하는 경보 정의를 작성할 수 있습니다.

이 예에서는 클라이언트 로그 데이터를 사용하여 경보 정의를 작성할 수 있습니다. 경보는 마지막 5분 내에 수신된 모든 클라이언트 로그를 모니터링하며 경보 정의가 사용할 수 없게 되거나 삭제될 때까지 매5분마다 계속 확인합니다. 경보는 동일한 앱 이름 및 버전을 가진 세 개 이상의 클라이언트 오류 로그를 전송하는 각 디바이스에 대해 트리거됩니다.

1. {{site.data.keyword.mobileanalytics_short}} 콘솔에서 종 아이콘을 클릭하여 **경보 로그** 페이지로 이동하십시오.
2. **경보 관리** 페이지로 이동하여 **경보 작성**을 클릭하십시오.
3. 다음 값을 제공하십시오.
	* 경보 이름: 클라이언트 로그에 대한 경보
	* 메시지: 오류 메시지 경보
	* 조회 빈도: 5분
	* 이벤트 유형: 클라이언트 로그
		* 특성: 로그 레벨
			* 값: 오류
			* 임계값
				* 임계값 유형: 애플리케이션 인스턴스에 대한 총계

					**참고**: 애플리케이션 옵션에 대한 평균을 선택하면 클라이언트 로그가 디바이스 수 기준으로 평균이 됩니다. 예를 들어, 두 개의 디바이스가 있으며 한 디바이스가 여섯 개의 클라이언트 로그를 전송하고 다른 디바이스가 세 개의 클라이언트 로그를 전송하는 경우, 평균은 4.5 클라이언트 로그입니다.
				* 연산자: 3 이상
<!-- insert alert definition tab image? -->

4. **다음** 또는 **분산 방법** 탭을 클릭하고 다음 값을 제공하십시오.
	* 방법: 분석 콘솔 전용

		참고: 사용자 정의된 URL에 JSON 페이로드가 있는 POST 메시지를 추가적으로 전송하려면 분석 콘솔 및 네트워크 게시 옵션을 선택하십시오. 이 옵션을 선택하는 경우 다음 필드가 사용 가능합니다.
		* 네트워크 게시 URL
        * 헤더
        * 인증 유형
5. **저장**을 클릭하십시오. 

클라이언트 로그의 수가 세 개 이상의 오류 로그인 임계값에 도달한 경우, 각 5분 간격의 끝에 경보를 트리거하도록 경보 정의를 작성했습니다.

### 앱 충돌에 대한 경보 정의 작성
{: #alert-def-app-crash}

앱 충돌을 기반으로 하는 경보 정의를 작성할 수 있습니다.

이 예에서는 앱 충돌 데이터를 사용하여 경보 정의를 작성할 수 있습니다. 경보는 마지막 2분 내의 모든 앱 충돌을 모니터링하며 경보 정의가 사용할 수 없게 되거나 삭제될 때까지 매2분마다 계속 확인합니다. 경보는 다섯 번 이상 충돌한 각 앱에 대해 트리거됩니다. 앱 충돌에 대한 자세한 정보는 [앱 충돌](app_crash/c_op_analytics_crashes.html)을 참조하십시오.

1. {{site.data.keyword.mobileanalytics_short}} 콘솔에서 **경보** 아이콘을 클릭하십시오. 이 조치는 경보 로그 페이지를 가져옵니다.
2. **경보 관리** 탭을 클릭하여 **경보 작성**을 클릭하십시오.
3. 다음 값을 제공하십시오.
	* 경보 이름: 앱 충돌에 대한 경보
	* 메시지: 앱 충돌 경보
	* 조회 빈도: 애플리케이션 충돌
		* 애플리케이션 이름: 임의의 애플리케이션
		* 애플리케이션 버전: 임의의 버전
    * 임계값
      * 임계값 유형: 충돌 개수
      * 연산자: 3 이상
4. **분산 방법** 탭을 클릭하고 다음 값을 제공하십시오.
  * 방법: 분석 콘솔 전용

    **참고**: 사용자 정의된 URL에 JSON 페이로드가 있는 POST 메시지를 추가적으로 전송하려면 **분석 콘솔 및 네트워크 게시** 옵션을 선택하십시오. 이 옵션을 선택하는 경우 다음 필드가 사용 가능합니다.
      * 네트워크 게시 URL(필수)
      * 헤더(선택사항)
      * 인증 유형(필수)
5. **저장**을 클릭하십시오. 

### 경보 정의 관리
{: #managing-alert-definitions}

이 예에서는 경보 관리 페이지에서 경보 정의를 관리합니다.

1. {{site.data.keyword.mobileanalytics_short}} 콘솔에서 **경보** 아이콘을 클릭하십시오. 이 조치는 경보 로그 페이지를 엽니다.
2. **경보 관리** 탭을 클릭하십시오.
3. 선택사항: **사용** 열 아래의 선택란을 토글하여 특정 경보 정의를 사용하거나 사용하지 마십시오.
4. 선택사항: 경보 정의의 사본을 작성하고 일부 값을 변경하려면 **중복** 아이콘을 클릭하십시오.
5. 선택사항: 경보 정의를 편집하려면 **연필** 아이콘을 클릭하십시오.
6. 선택사항: 경보 정의를 삭제하려면 **휴지통** 아이콘을 클릭하십시오.

### 경보 세부사항 보기
{: #viewing-alert-details}

이 예에서는 경보 로그 페이지에서 트리거된 경보의 세부사항을 볼 수 있습니다.

1. {{site.data.keyword.mobileanalytics_short}} 콘솔에서 **경보** 아이콘을 클릭하십시오. 이 조치는 경보 로그 페이지를 가져옵니다.
2. 임의의 경보에 대해 **+** 아이콘을 클릭하십시오. 이 조치는 **경보 정의** 및 **경보 인스턴스** 섹션을 표시합니다.

    **참고**: 해당 경보 정의가 삭제되거나 수정되지 않은 경우, **경보 편집**을 클릭하여 경보 정의를 편집할 수 있습니다. 그렇지 않으면 **경보 편집** 단추가 사용 불가능하거나 다음 메시지가 표시됩니다.

    `이 경보 정의가 수정되었거나 삭제되었습니다.`

3. 선택사항: 경보를 선택하고 **휴지통** 아이콘을 클릭하여 경보를 삭제하십시오.

## 앱 충돌
{: #monitor-app-crash}

앱을 더 잘 모니터링하고 문제를 해결하기 위해 {{site.data.keyword.mobileanalytics_short}} 콘솔에서 앱 충돌에 대한 정보를 볼 수 있습니다.

### 앱 충돌 모니터링
{: #app-crash}

{{site.data.keyword.mobileanalytics_short}} 콘솔의 **대시보드** 섹션에서 앱 충돌에 대한 정보를 더 빠르게 볼 수 있습니다.

**대시보드** 섹션의 **개요** 페이지에서 **충돌** 막대 그래프는 시간 경과에 따른 충돌 히스토그램을 표시합니다.

두 가지 방법으로 데이터를 표시할 수 있습니다.

1. 충돌 비율 표시: 시간 경과에 따른 충돌 비율 표시
2. 총 충돌 표시: 시간 경과에 따른 충돌 총계


### 앱 충돌 문제점 해결
{: #app-crash-troubleshooting}

앱을 더 잘 관리하기 위해 {{site.data.keyword.mobileanalytics_short}} 콘솔의 **애플리케이션** 섹션에서 **충돌** 페이지를 볼 수 있습니다.

**충돌 개요** 표에는 다음 데이터 열이 표시됩니다.

* 앱: 앱 이름
* 충돌: 해당 앱에 대한 충돌 총계
* 총 사용: 사용자가 해당 앱을 열고 닫은 총 횟수
* 충돌 비율: 사용당 충돌 백분율

**충돌 요약** 표는 정렬 가능하며 다음 데이터 열을 포함합니다.

* 충돌
* 디바이스
* 최근 충돌
* 앱
* OS
* 메시지

임의의 항목 옆의 + 아이콘을 클릭하여 다음 열을 포함하는 **충돌 세부사항** 표를 표시할 수 있습니다.

* 충돌한 시간
* 앱 버전
* OS 버전
* 디바이스 모델
* 디바이스 ID
* 다운로드: 충돌을 발생시킨 로그를 다운로드하기 위한 링크

**충돌 세부사항** 표의 임의의 항목을 펼쳐서 스택 추적을 포함한 더 많은 세부사항을 가져올 수 있습니다.

**참고**: **충돌 요약** 표에 대한 데이터는 심각한 레벨 클라이언트 로그를 조회하여 채워집니다. 앱이 심각한 클라이언트 로그를 수집하지 않은 경우, 사용 가능한 데이터가 없습니다.


