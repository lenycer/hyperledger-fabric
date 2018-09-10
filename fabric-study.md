## fabric 설정 파일
	- configtx.yaml (제네시스 블록을 만들기 위한 디폴트 설정)
	- crypto-config.yaml (msp 설정, orderer 갯수, org 갯수, org당 포함 peer 수)
	- core.yaml
	- orderer.yaml

## fabric-samples
0. git 다운 경로
	- git clone https://github.com/hyperledger/fabric-samples.git
	- git clone https://github.com/IBM-Blockchain/marbles.git
1. basic-network > start.sh (generate.sh 했다면 docker-compose.yaml > ca 값 변경)
	- fabric network 구동
2. marbles > npm install
	- marbles : client 역할
3. fabcar > npm install
4. fabcar > node enrollAdmin.js
5. fabcar > node registerUser.js
6. marbles > config 디렉토리 내 connection_profile_local.json 경로 수정
	- client -> credentialStore -> path (단 hfc-key-store directory 를 $HOME 경로에 카피하고 /Users/a1100440/.hfc-key-store 형태로 설정 해 줘야 함..현재 버그)
	- organizations -> x-adminCert -> path
	- organizations -> x-adminKeyStore -> path
7. marbles > scripts 내 체인코드 설치
	- node install_chaincode.js
	- node instantiate_chaincode.js
8. marbles > 실행
	- npm install gulp -g
	- gulp marbles_local

## orderer solo -> kafka 설정
1. configtx.yaml 
	solo -> kafaka
	kafka address -> kafka0

2. generate.sh
3. docker-compose.yaml -> ca key 수정
4. start.sh
5. zookafka.sh (kafka, zookeeper 실행 쉘)

