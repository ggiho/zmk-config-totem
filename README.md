# zmk-config-totem

독립적으로 빌드 가능한 TOTEM용 ZMK 설정 저장소입니다.

원본 기반:
- https://github.com/Keycoon/zmk-config-totem

현재 구성:
- 보드: `xiao_ble`
- 실드: `totem_left`, `totem_right`
- ZMK Studio 활성화: `config/totem.conf`
- GitHub Actions 빌드: `.github/workflows/build.yml`
- 빌드 매트릭스: `build.yaml`

## 빌드 방식

이 저장소는 GitHub Actions의 ZMK 공용 워크플로를 사용해 펌웨어를 빌드합니다.
`push`, `pull_request`, `workflow_dispatch` 시 자동으로 빌드됩니다.

안정적으로 독립 빌드되도록 ZMK 업스트림은 `v0.3`으로 고정했습니다.

## 생성되는 펌웨어

`build.yaml` 기준으로 아래 2개가 빌드됩니다.

- `xiao_ble + totem_left`
- `xiao_ble + totem_right`

## 다음 단계

1. 이 폴더를 새 Git 저장소로 사용
2. 본인 GitHub 새 레포에 push
3. GitHub Actions에서 생성된 `.uf2` 아티팩트 다운로드
4. 좌/우 각각 맞는 파일을 플래시

## 로컬 메모

로컬에서 ZMK 워크스페이스를 잡아 빌드하더라도 `.west/`, `zmk/`, `zephyr/`, `modules/`, `build/`는 커밋되지 않도록 `.gitignore`에 추가해 두었습니다.
