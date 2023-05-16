


### Confluent Kafka Ansible (cp-ansible) TEST Files 
[1. ANSIBLE COMPONENTS NODE 확인](#TEST00:-ANSIBLE-COMPONENTS-NODE-확인)
1. [기본 클러스터용 YML] 
2. [2개 클러스터 구성]
3. [자동 재시작 비활성화]
4. [SSL 구성된 클러스터]
5. [Kerberos 구성된 클러스터]
6. [브로커 단일 Listener 구성된 클러스터]
7. [Component 별 설정파일 디렉토리 및 실행 계정/그룹 다르게 설정]
---------------------------------------------

##### TEST00: ANSIBLE COMPONENTS NODE 확인
File: test-ping.yml


##### TEST 01: 기본 클러스터용 YML 
File: hosts.yml 


##### TEST 02: 2개 클러스터 구성 
File: hosts-dc1.yml & hosts-dc2.yml


##### TEST 03: 자동 재시작 비활성화
File: hosts-nostart.yml 

##### TEST 04: SSL 구성된 클러스터
File: hosts-ssl.yml


##### TEST 05: Kerberos 구성된 클러스터
File: hosts-kerberos.yml


##### TEST 06: 브로커 단일 Listener 구성된 클러스터
File: hosts-sole-listener.yml

##### TEST 07: Component 별 설정파일 디렉토리 및 실행 계정/그룹 다르게 설정 
File: hosts-each-run.yml 
