# poom-policy

poom 앱의 버전 정책 JSON과 공개 문서를 GitHub Pages로 호스팅하는 저장소입니다.

- 정책 URL: https://greming1-cyber.github.io/poom-policy/version_policy.json
- 개인정보처리방침: https://greming1-cyber.github.io/poom-policy/privacy.html (스토어 등록·AdMob 심사 제출용)
- 앱 쪽 참조 위치: IVF_app `lib/infrastructure/update/update_checker.dart`의 `policyUrl`

## privacy.html 관리

앱 내 화면(IVF_app `lib/presentation/more/privacy_policy_screen.dart`)과 문구를 동일하게 유지합니다.
방침 내용을 바꿀 때는 **두 곳을 함께 수정**하고 시행일도 같이 갱신하세요.
특히 광고(7항)는 현재 "광고 미포함" 문구인데, AdMob 게재가 시작되는 릴리스 때 두 곳 모두 갱신이 필요합니다.

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
