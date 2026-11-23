# Recovering a Server in Legacy Infrastructure

동아리의 레거시 인프라에서 장기간 방치된 서버를 식별하고, 실제 네트워크 연결 상태와 서비스 노출을 확인한 뒤 안전한 복구 방향을 정리한 기록입니다.

## Project Goal

- 오래된 인수인계 토폴로지와 실제 케이블 연결 상태 비교
- 외부 관리 경로가 동작하지 않는 원인 추적
- 격리된 직접 연결을 통한 서버 식별과 서비스 확인
- 데이터 보존과 재설치를 고려한 복구 절차 수립

## Timeline

| Day | 기록 | 주요 내용 |
| --- | --- | --- |
| 1 | [Asset and Topology](docs/day-01-asset-and-topology.md) | 기존 토폴로지 검증, 물리 연결 확인, 다음 실험 계획 |
| 2 | [Establishing a Direct Link](docs/day-02-establishing-a-direct-link.md) | 서버 NIC 식별, 직접 연결, 제한된 서비스 조사 |
| 3 | [Service Validation](docs/day-03-service-validation.md) | 노출 서비스 재검증과 안전한 복구 방향 결정 |

## Key Findings

- 인수인계된 토폴로지와 실제 배선 상태가 일치하지 않았습니다.
- 서버 NIC와 노트북을 직접 연결해 대상 서버와의 통신 경로를 확인했습니다.
- 서버에는 오래된 Linux 기반 서비스가 남아 있었지만 유효한 관리자 계정은 확인되지 않았습니다.
- 취약점 이용보다 격리, 디스크 백업, 데이터 확인, 재설치 순서가 적절하다고 판단했습니다.

## Publication Notes

- 토폴로지의 IP와 Port는 Notion에서 내보내기 전에 작성자가 공개용 값으로 조정했습니다.
- 조사 과정의 근거가 되는 원본 캡처와 현장 사진을 각 Day 기록에 그대로 보존했습니다.
- JPEG의 화면 내용은 수정하지 않았으며, GPS·기기 모델·촬영 시각 등 EXIF만 제거했습니다.
- 캡처에 표시되는 Endpoint와 사용자명은 조사 당시의 기록이며 현재 구성을 의미하지 않습니다.
