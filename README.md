# 달맞이 들판

펫이 싸우고, 나는 농사·채집·제작·요리로 돕는 생활형 RPG. 브라우저에서 돌아가는 HTML 파일 하나(`index.html`)로 되어 있습니다.

## 실행

가장 간단한 방법: `index.html`을 더블클릭해서 브라우저로 엽니다.

IDE(VS Code 등)에서:

```bash
npm start
```

(또는 `python3 -m http.server 5173`) 그다음 브라우저에서 http://localhost:5173 을 엽니다. 추가 설치는 필요 없습니다.
VS Code를 쓴다면 `Live Server` 확장을 설치하고 `index.html`에서 우클릭 → "Open with Live Server"도 됩니다.

코드를 고친 뒤에는 브라우저를 새로고침하면 바로 반영됩니다.

## 조작

- 이동: 방향키 / WASD (쿼터뷰라서 ↑는 화면 오른쪽 위)
- 상호작용: Space / E / Enter
- 가방 I · 펫 P · 석상의 시험 Q · 닫기 Esc

## 코드 구조 (`index.html` 안의 `<script>`)

| 구역 | 내용 |
| --- | --- |
| 맵 | `MAPS`(타일 문자열), `TRANS`(맵 이동), `GATES`(승리 수로 열리는 길), `LVR`(맵별 몬스터 레벨) |
| 아이템 | `ITEMS`, `EQUIPS`(장신구), `COOKS`(요리), `SHOP`, `TAVERN`, `CROPS`, `NODES`(채집물) |
| 펫 | `ROLES`(유형별 능력치), `PETS`(종류·털색·생김새 부위) |
| 몬스터·시험 | `MONS`, `SPAWNS`, `QUESTS` |
| 캐릭터 꾸미기 | `LOOK_OPTS` |
| 그리기 | `drawPlayer`, `drawPet`(부위 조합), `drawMon`, 쿼터뷰 렌더러(`drawObjIso`, `draw`) |

새 펫은 `PETS`에 한 줄, 새 장신구는 `EQUIPS`에 한 줄 추가하면 됩니다.
