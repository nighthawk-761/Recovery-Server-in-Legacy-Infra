# Day 3 — Service Validation

[← Project Overview](../README.md)

## 서비스 재검증

Remote Desktop Service의 상세 Version을 다시 확인했지만 추가 정보는 얻지 못했습니다. 일부 Legacy Service에도 연결을 시도해 다음 상태를 확인했습니다.

- Remote Desktop Service는 계속 응답했습니다.
- RPC Query는 정상적인 정보를 반환하지 않았습니다.
- SSH Banner를 통해 이전 조사와 같은 OpenSSH 8.0 계열임을 다시 확인했습니다.
- 그 외 Service는 복구에 필요한 최소 범위를 넘기지 않고 조사를 중단했습니다.

실제 Endpoint, 사용자명, 명령 출력과 전체 Port 목록은 공개본에 포함하지 않았습니다.

## 복구 방향

이 시점에서 서버는 살아 있지만, 오래된 Service와 불명확한 Credential 상태 때문에 그대로 운영망에 복귀시키는 것은 위험하다고 판단했습니다.

권장 순서는 다음과 같습니다.

1. 서버를 운영망에서 격리합니다.
2. Disk Image 또는 Offline Backup을 먼저 생성합니다.
3. 저장된 Data와 필요한 Service를 식별합니다.
4. Hardware 상태와 재사용 가능성을 점검합니다.
5. 필요한 Data만 이전한 뒤 지원되는 OS로 재설치합니다.
6. 신규 Credential을 발급하고 불필요한 Service와 Port를 제거합니다.
7. 최신 Topology와 Asset 정보를 다시 문서화합니다.

## Day 3 결론

복구의 핵심은 취약한 Legacy System에 진입하는 것이 아니라, Data를 보존하면서 신뢰할 수 있는 상태로 다시 구축하는 것입니다. 현재 서버는 즉시 재사용하기보다 Backup과 Inventory를 거친 뒤 재설치하는 편이 안전합니다.
