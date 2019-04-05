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
  


