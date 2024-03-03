# 컬렉션 조회에 대한 최적화의 결과 by Apach Jmeter
<br><br>
![image](https://github.com/domino0628/CS/assets/59598751/0719b8aa-ab32-4b2d-8670-5e445b22ebf4)
<br><br>
average는 1회 요청을 처리하는 데 걸리는 평균 시간이다.
<br><br>
엔티티 조회
<br><br>
엔티티 조회(페치 조인으로 다대일 관계의 N+1 문제 개선)
<br><br>
JPA에서 DTO 직접 조회
<br><br>
일대다 관계는 memory에서 미리 조회하여 최적화
<br><br>
flatDTO는 설정결과 4번의 처리속도보다 약 5% 정도 성능이 개선되었는데, 성능 개선적인 측면과 코드의 번잡성으로 인한 개발자 사이의 피드백에 걸리는 시간을 고려했을 때, 적절한 방식이라고 생각하지 않는다.
<br><br>
<br><br>
