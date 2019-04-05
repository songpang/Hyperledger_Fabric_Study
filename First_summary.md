# 첫 번째 강의 요약

## Hyperledger?

+ 공통된 블록체인 표준을 만들기 위해 리눅스 재단에서 후원하여 만들어진 프로젝트
  + IBM에서 기존에 개발하던 블록체인 프로젝트를 하이퍼렛저에 투고 (Fabric)
  + 하이퍼렛저에는 종류가 여러개 있다 ( Burrow, Sawtooth, Fabic, Indy, Iroha )

<br/>

+ Not Public, < Private! > 폐쇄적인 Blockchain
  + (Q) 탈 중앙화의 장점을 가지지 못하는 것 아닌가요 ?
  + (A) inner circle 안에서 더욱 결합력 높은 조직력. 허가된 사용자만 들어올 수 있기 때문에 안정적으로 동작
  
<br/>

+ Private Network는 네트워크 유지를 필요로 하는 사람들의 집합체 <br/>
-> 이때문에 Public Network의 특성인 리워드를 제공할 필요성이 없음.


## Hyperledger Fabric's key design feature ( 간단 정리 )

+ **Assets** : Chain에 저장될 정보
+ **Chaincode** : ( =Smartcontract ) 간단한 비즈니스 로직. 코드의 변경도 consensus를 거쳐야 한다.
+ **Ledger Features** : 원장
  + 일각에서는 Blockchain을 단순히 DB로 보기도한다. ( CRUD가 되지만 history가 전부 남는 DB )
  + CRUD ( Create, Read, Update, Delete )
+ **Privacy through Channels** : Network에 참여한 organization들은 정보의 공유 여부를 Channel을 통해 구분할 수 있다.
  + A Channel : X, Y, Z사
  + B Channel : Y, Z, W사 ...
+ Security & Membership services
+ Consensus
  
## 1. System Architecture
  > [Link](https://hyperledger-fabric.readthedocs.io/en/release-1.1/arch-deep-dive.html#system-architecture)
### 1.1 Transactions
> blockchain을 변화시키는 모든 것은 transaction에 포함

+ Deploy : Chaincode를 blockchain에 넣는 것. ( smartcontract deploy 라고 생각하면 될듯 )
+ Invoke : 내가 이미 있는 chaincode에 맞춰서 chain들을 쌓는 것

### 1.2 Ledger

+ 지금까지 어떤 상태로 배포가 되어있는가, history가 어떻게 되어있는가
```
OrdererLedger
PeerLedger
```

### 1.3 Nodes

+ 어떤 Component들이 있는가.
  + Client OR submitting-client : end user 입장에서 chaincode를 호출하기 위해 요청
  + Peer : Node 중에서 ledger들을 수정하고 관리
  + Ordering-service-node OR orderer : ledger를 업데이트 하는 Peer들을 관리. 분산이지만 순서를 결정
    > 1.0에 새로 업데이트


## 2. Basic workflow of transaction endorsement
  > [Link](https://hyperledger-fabric.readthedocs.io/en/release-1.1/arch-deep-dive.html#basic-workflow-of-transaction-endorsement)

*blockchain의 근간 : 이전 block의 hash값을 다음 block으로 가져감*


## 3. Endorsement policies
  > [Link](https://hyperledger-fabric.readthedocs.io/en/release-1.1/arch-deep-dive.html#endorsement-policies)

+ 노드의 가용성 확보를 위한 policy
+ 전체 노드의 정상적인 운용이 가능하지 않은 상황의 경우가 항상 발생할 수 있기 때문에 설정한다.
```
E = {Alice, Bob, Charlie, Dave, Eve, Frank, George}

(Alice OR Bob) AND (any two of: Charlie, Dave, Eve, Frank, George)
// Alice, Charlie, Eve -> OK
```





