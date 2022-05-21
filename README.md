# CSB-exam 

due 25.05 

Week 01 software security 1 [컴퓨터 안에서 운용되는 프로그램,문서] <-> hardware [ 컴퓨터의 직접적인 성능에 관련된 부분 ( 마우스, 키보드, 모니터) ]


*security properties. (CIA)

1. confidentiality.(기밀성)
-> avoiding unauthorised disclousre of information. 

기밀성이란 특정 정보에 대해서 허가된 사용자 또는 대상에 대해서만 확인이 가능해야 한다. 
즉, 허가받지 않은 사용자 혹은 대상에 대해서는 접근이 되지 않아야 하며, 만약 접근이 된다면 해당 정보에 대해서는 기밀성이 깨졌다고 한다. 

2. intergrity.(무결성)
-> avoiding unauthorised modification of data.

무결성이란 특정 정보에 대해서 허가된 사용자 또는 대상에 대해서만 수정 및 삭제등 가능해야 한다. 
즉, 허가받지 않은 사용자 혹은 대상이 특정 정보에 대해서 수정 및 삭제가 되어야 하지 않아야 하며,만약 수정 및 삭제가 이뤄진다면 해당 정보에 대해서는 무결성이 깨졌다고 한다. 

3. availability.(가용성)
-> avoiding periods where authorised users can't use a system.

가용성이란 사용자 또는 대상에 대해서 특정 정보에 대한 접근 및 사용 필요시 항상 가능해야 한다. 즉, 원하는 시간,환경,서비스에 특정 정보를 사용할 수 있어야 하며, 만약 사용이 불가능 하면 해당 정보에 대해서는 가용성이 깨졌다고 한다. 


* Threat Modeling 

-> 사실 threat modeling 이라는 단어는 비단 IT에서만 쓰는 용어는 아니고, 위험 요소에 대해 평가해보는 전반에 걸쳐 사용되는 언어이다. 하지만 IT용어로써 Threat Modeling 이란 MS 사에서 대중화한 개념으로 잠재적인 위협을 모델링하고 이를 완화할 수 있도록 한 프로세스를 말한다. 

가령, 구조적 취약점이나 방화벽 등 보안장치의 부재와 같은 위협들이 모델링의 대상이 될 수 있다. 
위협 모델링의 목적은 시스템의 특성과 방어 시스템을 고려했을 때 어떤 부분에 있어서 방어가 필요하고 보안상 취약할 수 잇는지 가능성을 찾는 것으로 특히 특정한 위협포인트에 대해 미지수일 경우 가능한 취약점을 찾는 것이 되겠다. 또한, 공격자의 입장을 시뮬레이션 해보고 공격 측면을 찾아내는 일이 포함된다. 

그렇기 때문에 Threat Modeling 이 가능하려면 먼저 다음을 알아야 한다.
-시스템의 구조
-시스템의 보안 상태
-보호해야하는 가치있는 자산이 무엇인지
-가능한 공격자 후보군

*STRIDE

S : spoofing(공격자가 권한이 있는 사용자인척 위장하는 공격 방식)
T : Tampering(목적을 위해 시스템 내부 데이터를 악의적 수정해서 공격) 
R : Repudiation(악의적 활동 이후에 해당 활동에 대해 부인하는 것) 
I : Information Disclousre(보호된 정보에 대한 노출) 
D : Denail of Service(서비스에 대한 믿을 수 있는 접근을 바탕으로 한 공격. 분산해서 공격하는 것을 DDOS라 한다)
E : Elevation of Privilege


* Software Security Bugs

1. Integer overflow and underflow 
 
2. Buffer Overflow
 
3. Control flow corruption



**********************************************************************************************************************************************************

Week02 SoftWare Security 2

1. Memory Corruption (메모리부패)
-> 사용자가 부주의하여 명확한 할당 없이 주소에 접근하여 데이터를 변경하려 하거나 잘못된 주소 위치로 접근하려 할때. 
can lead to - arbitrary read/ write/ control flow hijack / corruption. 


* segmentation fault 
-> 잘못된 메모리 참조때문에 발생. 즉 건드리지 말아야 할곳을 건드렸기 때문에 발생. 

원인) 1. Null 값을 가르키는 포인터에 접근할 경우.
     2. 할당 받은 메모리 공간을 넘은 곳을 건드린 경우.
     3. 더 이상 존재하지 않는 메모리 영역을 가르킬 경우(Free)
     4. ready-only 표시 메모리 영역에 쓰려고 할 경우. 
     
     
********************************************************************************************************************************************************** 
 
 Week03 Cryptography. (암호화)
 
 This process converts the original representation of the information, known as plaintext into an alternative form known as ciphertext. 
 
 *symmentric key crytography (대칭키 암호화)
 
 공개키 / 개인키
 
 * 공개키 : 누구든지 키를 확인할 수 있고 사용할 수 있도록 대중에게 공개된 키를 의미한다.
 * 개인키 : 자기자신만이 관리하고 가지고 있는 키를 의미합니다. 

*대칭키 암호화 (secret key) 

-> 대칭키는 이름에서 알 수 있듯이, 어떤 정보를 암호화 복화화 할떄 사용하는 키가 동일한 경우. 
어떠한 정보가 대칭키를 통해 암호화 되었다면, 똑같은 키를 갖고 있는 사용자가 아니면 해당 정보를 확인 할 수 없다. 

따라서, 암호화된 정보를 전달하고 확인하기 위해서는 송,수신자 둘다 똑같은 키를 가지고 있어야 한다.

이러한 키를 안전하게 교환하는것이 대칭키 암호화 방식의 가장 중요한 부분이다 ! 이처럼 대칭키 암호화 방식은 키가 없다면 누구도 열어볼 수 없어 안전하지만, 이 키를 안전하게 전달하는것이 핵심

ex) 부산에 살고 있는 철수는 1번이라는 열쇠로만 열 수 있는 보물상자를 서울에 살고 있는 영희에게 보내려고한다. 그렇다면 철수는 영희에게 보물상자는 물론이고 1번이라는 열쇠를 같이 보내야지만
보물상자를 열 수 있다. 만약 보물상자와 함께 열쇠를 담아 보낸다면, 중간에 누군가가 가로채서 상자를 열어볼 수 있다. 따라서 이 열쇠는 보물상자와 다른 경로로 안전하게 전달 되어야한다. 


대칭키 암호화의 단점 -> 대칭키 암호화의 단점은 통신 네트워크 상의 맴버들의 수가 증가할 수록 필요한 키의 수는 제곱에 비례해 보안성을 위한 키 관리를 매우 어렵게 만든다. 
공개키 암호화에선 공개키는 다른 사람에게 알려져도 되지만, 공개키와 동시에 비밀스럽게 생선된 개인키는 반드시 비밀로 남아있어야 한다. 





*비대칭키 암호화 

-> 비대칭키 또한 이름에서 알 수 있듯이, 어떠한 정보를 암호화 복호화 할때 사용하는 키가 서로 다른경우를 의미한다. 
대칭키와 다르게 비대칭키를 활용한 암호화에는 개인키와 공개키 두가지가 사용된다.

또한, 비대칭키를 활용한 암호화는 개인키로 암호화를 하는 방식과 공개키로 암호를 하는 방식 두가지로 나눈다. 

1) 공개키로 정보를 암호화하는 경우
-> 공개키는 누가나 알 수 있도록 공개된 키이므로, 어떠한 정보를 특정 사용자에게 보낼 때 해당 사용자의 공개키를 통해 정보를 암호화하여 전송한다. 

ex) 부산에 살고 있는 철수는 서울에 살고있는 영희에게 보물상자를 보내려고 한다. 이때 A는 B의 공개키를 이용해 암호화를 하고 B는 이 보물상자를 열기위해서 B의 개인키가 필요하다. 
(공개키로 해제불가)

[ 철수는 영희의 공개키를 이용해서 암호화 하고 보물상자를 받은 영희는 본인의 공개키롤 암호화가 되어 있기 때문에 본인의 개인키로 열람가능]



2) 개인키로 정보를 암호화하는 경우
-> 개인키는 자신만이 가지고 있는 키이므로, 어떠한 정보를 특정 사용자에게 보낼때 자기자신의 개인키를 통해 정보를 암호화하여 전송한다. 

Ex) 부산에 살고 있는 철수는 자기만의 개인키를 통해 보물상자를 암호화하여 영희에게 보낸다. 이 보물상자는 철수의 개인키로 암호화 되어 있기 때문에 철수의 공개키가 있어야만 열수있다.
하지만 철수의 공개키는 누구에게나 공개되어 있다. 따라서 영희는 보물상자를 받은 후 철수의 공개키를 이용해서 보물상자를 열 수 있다.

그럼? 철수의 공개키는 누구에게나 열려있으니깐 중간에 아무개가 가로채서 상자를 열어볼 수 있지 않을까? 

개인키로 정보를 암호화 하는 방법은 보물상자 안에 무엇이 들어있다기 보다는 누가 그 보물상자를 보냈는지가 중요하다. 

그러므로 이 보물상자는 철수의 공개키로만 열람할 수 있으므로 철수가 보낸 것이 확실하다는 증거 


* MAC (message authentication code) 메세지 인증 코드[블록 암호]
-> 메세지를 보냈을 때 보낸 사람으로부터 메세지가 변조되지 않았는지 여부 판단 가능 (무결성: 메세지 변조 여부 / 신뢰성 보장: 보낸 사람이 올바른지 여부 판단)

밥 / 앨리스 통신 

밥과 앨리스는 서로 사전에 대칭키 암호화 방식과 동일하게 키를 공유했다고 가정하자. 
밥은 메세지를 보낼 때 사전에 공유된 키를 이용해 MAC 알고리즘을 계산한다 ( 메세지를 전송할 때 뒤에 붙혀 전송)

앨리스는 해당 메세지와 공유된 키를 이용해서 MAC 알고리즘을 계산후 밥이 보낸 알고리즘과 일치하면 Valid. 

MAC / Hash 차이점 
-> Mac 의 기능은 암호학적 해쉬 가능과 매우 유사하지만, 해쉬의 경우 무결성이나 인증 자체를 제공하지 않는다. 중간자 공격의 영향에 취약하기 때문에 단순히 해쉬값을 Mac값 처럼 사용하면 중간에 
해커가 가로채서 자신의 메세지와 메세지에 대한 해쉬값을 보내면 알아차릴 수 없다. 

MAC / 전자서명 차이점
-> Mac의 경우 서명과 검증이 가능하지만 전자서명은 다르다. 동일 키를 사용하기 때문에 둘만의 통신에서 한명이 메세지를 보내지 않았다고 부인(Repudiation)을 하면 그것에 대한 증명이 불가하다.
(네트워크 전체 공유 비밀키의 경우도 마찬가지) 

반면, 전자서명의 경우 개인 키를 사용해서 서명이 되기 때문에 부인방지 가능 그러나, Mac 키에 사용자 정보를 바인딩하는 시스템에 의해서 부인방지 기능이 제공될 수 있다. 

동일한 키는 두사람이 소유하지만, 하나는 Mac생성에 사용할 수 있는 키, 다른 하나는 Mac 서명용으로만 허용하는 하드웨어 모듈에 두면 다른 키를 사용하므로 부인방지 기능을 제공할 수 있다.(금융권)

* 디피 헬만 키 교환 

-> 비대칭 알고리즘 사용 방식이고 상대방의 공개키와 나의 비밀키를 이용해서 비밀키를 생성.

ex) 철수의 공개키 & 영희의 비밀키를 DH연산을 통해서 영희의 비밀키를 만든다. 
    영희의 공개키 & 철수의 비밀키를 DH연산을 통해서 철수의 비밀키를 만든다. 
    
    즉 철수와 영희의 비밀키는 같아짐. 
    
********************************************************************************************************************************************************

*Week03 Web security 


* CSRF(Cross Site Request Forgery) 
인터넷 사용자가 자신의 의지와는 무관하게 공격자가 의도한 행위를 특정 웹사이트에 요청하게 만드는 공격 => 서버를 공격 

* XSS (Cross Site Scripting) [Reflective / Stored(Persistant] 
해커가 웹사이트에 악성 스크립트를 등록 -> 웹서비스는 이를 DB에 저장 -> User는 이 악성스크립트를 읽음 -> 악성 스크립트가 User Pc에서 실행 => 유저를 공격 

1) Reflective : 






