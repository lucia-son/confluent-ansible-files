
### Confluent Kafka Ansible (cp-ansible) TEST Files  
  <br/><br/>
 
[TEST 01. ANSIBLE COMPONENTS NODE 확인](#test-01-ansible-components-node-확인)  
[TEST 02. 기본 클러스터 구성](#test-02-기본-클러스터-구성)  
[TEST 03. 2개 클러스터 구성](#test-03-2개-클러스터-구성)  
[TEST 04. 서비스 자동 시작 비활성화](#test-04-서비스-자동-시작-비활성화)  
[TEST 05. SSL 구성](#test-05-ssl-구성)  
[TEST 06: Kerberos 구성](#test-06-kerberos-구성)  
[TEST 07: Broker 단일 Listener 구성](#test-07-broker-단일-listener-구성)  
[TEST 08: Component별 실행 계정/그룹 구분 설정](#test-08-Component별-실행-계정/그룹-구분-설정)  <br/><br/>
---------------------------------------------

#### TEST 01. ANSIBLE COMPONENTS NODE 확인
- ansible control node와 component node 간 ssh 통신 가능한지 확인한다. 
- File: test-ping.yml  
- Execute: `ansible -i test-ping.yml all -m ping`   
  
  
#### TEST 02: 기본 클러스터 구성
- zookeeper 3대, broker 3대, schema-registry/connect workerk/ksql/controlcenter 각 1대씩 ansible 기본 설정으로 구성한다.
- File: hosts.yml   
- Execute: `ansible-playbook -i hosts.yml confluent.platform.all`  
```bash
# 옵션1. tags옵션을 통해 component별 구성
$ ansible-playbook -i hosts.yml confluent.platform.all --tags=zookeeper  

# 옵션2. ansible 실행시 사용하는 python 경로 지정하여 구성 
$ ansible-playbook -i hosts.yml confluent.platform.all -e ansible_python_interpreter=/usr/bin/python3
```
  
  
#### TEST 03: 2개 클러스터 구성 
- Replicator등의 테스트를 위한 두 개의 클러스터, 각 클러스터별 zk/br/schema/connect 1대씩 구성한다.
- File: hosts-dc1.yml & hosts-dc2.yml  
- Execute: `ansible-playbook -i hosts-dc1.yml confluent.platform.all; ansible-playbook -i hosts-dc2.yml confluent.platform.all`  
  
  
#### TEST 04: 서비스 자동 시작 비활성화  
- Ansible 실행 시 서비스 자동 시작 없이 설정파일만 배포
- health_checks_enabled 를 비활성화하고, 각 component별 tasks/main.yml 에서 서비스를 시작하는 task 의 tags를
systemd에서 systemd_start 로 수정하여 ansible 실행시 tags를 통해 해당 task를 제외한다.
- File: hosts-nostart.yml    
- Execute: `ansible-playbook -i hosts-nostart.yml confluent.platform.all --skip-tags systemd_start` 
  
  
#### TEST 05: SSL   
- 미리 Confluent Component가 구성될 노드에 Keystore/Truststore 파일을 위치시켜두고, ansible inventory 파일에 해당 파일 관련 정보를 host별로 명시한다.
- File: hosts-ssl.yml  
- Execute:   
  
  
#### TEST 06: Kerberos 구성  
- 
- File: hosts-kerberos.yml   
- Execute:   
  
  
#### TEST 07: Broker 단일 Listener 구성  
- File: hosts-sole-listener.yml   
- Execute:   
  
  
#### TEST 08: Component별 실행 계정/그룹 구분 설정   
- File: hosts-each-run.yml   
- Execute:   
    
  
