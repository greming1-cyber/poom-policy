# poom-policy

poom 앱의 버전 정책 JSON을 GitHub Pages로 호스팅하는 저장소입니다.

- 정책 URL: https://greming1-cyber.github.io/poom-policy/version_policy.json
- 앱 쪽 참조 위치: IVF_app `lib/infrastructure/update/update_checker.dart`의 `policyUrl`

## version_policy.json 필드

| 필드 | 의미 |
|---|---|
| `minSupportedVersion` | 이 미만 버전은 강제 업데이트 안내 |
| `latestVersion` | 최신 버전 (미만이면 권장 업데이트 안내) |
| `message` | 안내 문구 커스텀 (null이면 기본 문구) |
| `storeUrl` | 스토어 이동 링크 (null이면 버튼 미표시) |

## 릴리스 때 할 일

1. `version_policy.json`의 `latestVersion`을 새 버전으로 수정 (강제 업데이트가 필요하면 `minSupportedVersion`도 함께)
2. 커밋·푸시 — Pages 반영까지 수 분 소요
3. 스토어 등록 후에는 `storeUrl`에 실제 스토어 링크 입력

앱은 fail-open이므로 이 파일에 문제가 생겨도 앱 동작에는 영향이 없습니다.
