
### Confluent Kafka Ansible (cp-ansible) TEST Files  

[TEST 01. ANSIBLE COMPONENTS NODE 확인](#test-01-ansible-components-node-확인)  
[TEST 02. 기본 클러스터 구성](#test-02-기본-클러스터-구성)  
[TEST 03. 2개 클러스터 구성](#test-03-2개-클러스터-구성)  
[TEST 04. 서비스 자동 시작 비활성화](#test-04-서비스-자동-시작-비활성화)  
[TEST 05. SSL 구성](#test-05-ssl-구성)  
[TEST 06: Kerberos 구성](#test-06-kerberos-구성)  
[TEST 07: Broker 단일 Listener 구성](#test-07-broker-단일-listener-구성)  
[TEST 08: Component별 실행 계정/그룹 구분 설정](#test-08-Component별-실행-계정/그룹-구분-설정)  

---------------------------------------------

##### TEST 01. ANSIBLE COMPONENTS NODE 확인
File: test-ping.yml  
Note:  
Execute:  
`ansible -i test-ping.yml all -m ping`    


##### TEST 02: 기본 클러스터 구성
File: hosts.yml   
Note:  
Execute:   

##### TEST 03: 2개 클러스터 구성 
File: hosts-dc1.yml & hosts-dc2.yml  
Note:  
Execute:   

##### TEST 04: 서비스 자동 시작 비활성화  
File: hosts-nostart.yml   
Note:  
Execute:   

##### TEST 05: SSL   
File: hosts-ssl.yml  
Note:  
Execute:   

##### TEST 06: Kerberos 구성  
File: hosts-kerberos.yml  
Note:   
Execute:   

##### TEST 07: Broker 단일 Listener 구성  
File: hosts-sole-listener.yml  
Note:  
Execute:   

##### TEST 08: Component별 실행 계정/그룹 구분 설정   
File: hosts-each-run.yml   
Note:  
Execute:   
  
