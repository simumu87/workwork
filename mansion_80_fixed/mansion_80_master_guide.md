# 「우리집 대저택」 79장 완전판 공간 LoRA 마스터 가이드

## 1. 프로젝트 개요 및 건축 정합성 핵심 원칙
- **부지 및 건축 규모**: 약 620평(2,050㎡) 숲속 프라이빗 대저택 (남측 정문 및 27.8m 인피니티 풀 & 티크 데크 + 1층 본채 + 2층 옥상 테라스 & 다락방 + 독립 별동 3개동[프라이빗 홈짐, 작업실, 수영장 탈의실&샤워실] + 북측 후면 젠 중정 + 지하 1층 짐)
- **통합 베이스 트리거 워드**: `mn5vx` (존 트리거 체계는 아래 「트리거 체계」 참고)
- **전체 데이터셋 구성**: 총 **79장** (24-bit RGB 무손실 `.png` 이미지 79장 + 1:1 매칭 `.txt` 상세 캡션 79개 + 본 마스터 가이드 `.md` 문서 1개 = 총 159개 파일 수록, 07번은 이미지 품질 불량으로 제외한 결번)
- **핵심 공간 체이닝 및 도면/원본 정합성 원칙**:
  1. **1층 본채(`우리집 도면.png`) & 2층 옥상(`우리집 옥상.jpg`) 완벽 분리·결합**:
     - 1층 본채 서측 라인: `방 3` → `방 2` → `방 1` → `방 6`이 조경 끊김 없이 하나의 일체형 본채 서벽으로 연결되며, 각 침실(방 1~5)은 원본 인테리어 사진과 1:1 일반 방문(문틀 폭·높이 = 문짝 폭·높이 100% 일치)으로 체이닝됨.
     - 1층 본채 중앙 및 북측 라인: `거실`(서측 크림 L자 소파 존 + 동측 4인용 라운드 스톤 파이어핏 라운지 존, 단차 없는 평탄한 오크 원목 바닥) ↔ `주방 & 다이닝`(외부 창문 없는 솔리드 우드 상부장/수납장) ↔ `중앙 욕실`(외부 창문 없는 100% 실내 트라버틴 석재 욕실) ↔ `책장존` ↔ `서재`(창문 없는 전면 월넛 서가) ↔ `그레이존`(비밀 회전 책장문 너머 무창 다크 시어터 & 위스키·기네스 바).
     - 2층 옥상 테라스 & 다락방: 서측 외관 경사 계단 및 동측 본채 스투코 일체형 외부 계단을 통해 올라가는 2층 평지붕 옥상 위에 **박공지붕 다락방(`44~46번`, `65~69번`, `79번`)**과 스트링 조명이 달린 다크 메탈 퍼골라·바비큐·파이어핏·북서측 썬베드 데크가 일관되게 유지됨.
  2. **독립 별동 3개동 및 야외 산책로 정합성**:
     - **작업실(남동측 별동, `48~50번`, `65번`, `68번`, `76번`)**: 수영장을 바라보는 서측 외벽은 문과 창문이 전혀 없는 **100% 솔리드 베이지 스투코 벽면**이며, 출입문은 오직 **남측으로만** 나 있어 문을 열면 대문이나 수영장이 보이지 않고 울창한 나무 그늘 아래 **야외 패브릭 소파 휴게 공간**이 보임.
     - **수영장 탈의실 & 샤워실(동측 별동, `61~64번`, `70번`)**: `61번` 마스터 내부(원목 락커·벤치, 불투명 유리 WC 도어, 트라버틴 트윈 세면대·타원형 백라이트 거울, 유리 레인샤워 부스)를 기준으로 `62번`(락커·세면대 측면), `63번`(내부에서 서측 출입문 너머 동측 정원 산책로·본채 동벽 조망), `64번`(동측 정원 산책로에서 내부 진입 뷰)이 100% 동일 레퍼런스로 체이닝됨.
     - **서측·동측 정원 산책로(`69번`, `70번`, `79번`)**: `69번` 서측 산책로는 좌측 프라이빗 홈짐, 우측 일체형 본채 서벽(방 3·2·1·6 + 상부 2층 다락방 & 썬베드)이 곧게 이어지고, `70번` 동측 산책로는 우측 철제 계단 없이 좌측 본채 동벽 일체형 스투코 계단과 우측 수영장 탈의실 별동 사이를 지나 정면 북측 젠 중정 퍼골라 입구(`79번`)로 직결됨.
  3. **지하 1층 짐(`58~60번`, `80번`)**:
     - 외부 채광창이 전혀 없는 100% 지하 콘크리트·거울 벽면 구조로, 간접 LED 콘크리트 계단(`80번`)을 내려오면 중앙 `'오빠짐 BROTHER GYM'` 원형 매트, 좌측 `'MAX FC'` 샌드백 및 `'Brother Gym'` 네온 옥타곤 케이지, 우측 턱걸이 스텐실 벽화 및 복싱 글러브 랙이 원본(`지하실 오빠짐.jpg`) 그대로 펼쳐짐.

---

## 트리거 체계 (캡션 공통 규칙)

- **전역 트리거**: `mn5vx` — 79장 전부의 캡션 맨 앞에 1회만 쓴다.
- **존 트리거**: 전역 트리거 바로 뒤에 쉼표로 이어 쓴다. 촬영 위치(카메라가 서 있는 존)를 먼저, 그다음 화면에 보이는 존을 쓴다. 79장 전부 최소 1개 존 트리거를 가진다.
- **캡션 형식**: `mn5vx, 존1[, 존2[, 존3]], 샷 설명…, empty scene|room|gym, no people|no humans`
- **명명 규칙**: 소문자 영문(+숫자)만, 한 단어, 밑줄 없음. 캐릭터 이름·약칭(한국어/로마자)은 트리거와 캡션 본문에 쓰지 않는다(캡션 txt 파일명은 사진 파일명을 따르므로 예외). 방은 번호(`bedroom1~6`)와 위치/용도 단어로만 부른다. (캐릭터 로라 트리거와 섞이지 않게 하기 위함)
- **이미지 속 간판 글자**(`BROTHER GYM`, `MAX FC`, `오빠짐`, `PUZZLE FILES` 등)는 이미지에 실제로 보이는 글자라서 캡션에서 그대로 유지한다.
- 표의 번호: 일반 숫자 = 촬영 위치 존, 괄호 = 화면에 보이는 존.

| 존 트리거 | 공간 | 파일 번호 |
|---|---|---|
| `exterior` | 대저택 전경(항공·외관 마스터) | 01, 02, 03, 04, 05 |
| `gate` | 남측 정문 진입로 | 68 |
| `pool` | 27.8m 인피니티 풀 & 티크 데크 | 13, (16), 47, 51, 52, (55), 65, 66, 67, (68) |
| `living` | 1층 거실(L자 소파 + 라운드 스톤 파이어핏) | (10), 11, 12, (13), 14, (16), (30), (32), (37), (40), (66), 74, 75, (76), (77) |
| `kitchen` | 주방 & 다이닝 | 15, 16, (20) |
| `bath` | 중앙 욕실(무창 트라버틴) | 17, 77 |
| `shelf` | 책장존 | (17), 76 |
| `study` | 서재(월넛 서가·듀얼모니터) | 31, 32, 33, (78) |
| `greyzone` | 그레이존(비밀 시어터·바) | (33), 34, 78 |
| `corridor` | 서측 복도 | 21, 22, (26), 71, 72, 73 |
| `bedroom1` | 1층 침실 1 | 18, 19, 20, (71) |
| `bedroom2` | 1층 침실 2 | 23, 24, 25, 26, (72) |
| `bedroom3` | 1층 침실 3 | 27, 28, 29, 30, (73) |
| `bedroom4` | 1층 침실 4 | 35, 36, 37, (74) |
| `bedroom5` | 1층 침실 5 | 38, 39, 40, (75) |
| `bedroom6` | 1층 침실 6(북서측 스튜디오 스위트) | (06), 08, 09, 10, (79) |
| `attic` | 2층 박공지붕 다락방 | 44, 45, 46 |
| `rooftop` | 2층 옥상 테라스 | 41, 42, 43, (46), (47) |
| `workshop` | 남동측 작업실 별동 | 48, 49, 50 |
| `homegym` | 남서측 프라이빗 홈짐 별동 | 53, 54, 55, (67) |
| `changing` | 동측 수영장 탈의실 & 샤워실 별동 | 61, 62, 63, (64) |
| `sauna` | 동측 샤워·사우나 파빌리온 | (56), 57 |
| `parking` | 동측 오토바이 주차 레인 | 56, (57) |
| `basement` | 지하 1층 짐 | 58, 59, 60, 80 |
| `zen` | 북측 젠 중정 | 06, (09), (43), 79 |
| `westpath` | 서측 정원 산책로 | 69 |
| `eastpath` | 동측 정원 산책로 | (63), 64, 70 |

---

## 2. 전 구간 (01번 ~ 80번, 07번 결번) 파일 목록 및 1:1 매칭 캡션 일람

- 항목 번호(`[NN]`)가 사진·캡션 파일명 앞 두 자리 번호와 같다. 아래 제목의 파일명은 캐릭터 이름을 뺀 표기이고, 실제 txt 파일명은 사진 파일명과 동일하다.


### [01] `01_mansion_exterior_master_topview.png`
- **Caption (`.txt`)**: `mn5vx, exterior, exterior master top-down 90-degree vertical drone photograph of the 620-pyeong luxury modern forest mansion estate, 27.8m swimming pool and teak deck in the south, detached private home gym on southwest lawn, detached workshop and motorcycle parking on southeast, 2nd-floor wooden rooftop terrace with dark gabled attic cottage on west and string-lit black steel pergola on center-east, extended northwest rooftop deck above 1st-floor bedroom 6, walled zen forest courtyard on north with white raked karesansui gravel, green moss islands, bamboo groves, red japanese maple and stone water basin on northeast, golden hour twilight lighting, empty scene, no humans`

### [02] `02_mansion_exterior_master_south.png`
- **Caption (`.txt`)**: `mn5vx, exterior, exterior master south view aerial photograph looking north across the estate, front road and stone gate, glowing blue 27.8m swimming pool with brown teak deck, 1-story glass-walled private home gym on left, 1-story workshop and motorcycle parking on right, 1st-floor living room panoramic glass wall with L-shaped sofa, 2nd-floor wooden rooftop terrace with angled front stairs, dark gabled attic cottage on west, extended northwest lounge deck above 1st-floor bedroom 6, black steel pergola with warm string lights, 1st-floor zen forest courtyard visible behind pergola railing with bamboo groves, white gravel and red maple on northeast, sunset twilight sky, empty scene, no humans`

### [03] `03_mansion_exterior_master_north.png`
- **Caption (`.txt`)**: `mn5vx, exterior, exterior master north view aerial photograph looking south across the back of the estate, foreground left and center showing 1st-floor walled zen forest courtyard with red japanese maple, round stone tsukubai water basin, stepping stones, two green bamboo groves, white raked karesansui gravel, green moss islands, wooden engawa deck and solid 1st-floor north wall of main house, foreground right showing 1st-floor bedroom 6 integrated flush under the northwest wooden rooftop deck with lounge chairs, midground showing 2nd-floor rooftop pergola and dark gabled attic cottage, background showing 27.8m swimming pool, private home gym on right and workshop on left, golden hour sunset, empty scene, no humans`

### [04] `04_mansion_exterior_master_east.png`
- **Caption (`.txt`)**: `mn5vx, exterior, exterior master east view aerial photograph looking west across the estate, foreground showing motorcycle parking lane with parked bikes, east annex, workshop on left, trellis pergola path and straight exterior staircase ascending east wall of main house, left side showing 27.8m swimming pool and teak deck leading to private home gym in far west, center showing 2nd-floor rooftop terrace with bbq grill, string-lit pergola, sofa, dining table and gabled attic cottage at far west, right side showing 1st-floor walled zen forest courtyard with red maple tree, stone water basin, stepping stones, white raked gravel and bamboo groves leading to 1st-floor bedroom 6, twilight sky, empty scene, no humans`

### [05] `05_mansion_exterior_master_west.png`
- **Caption (`.txt`)**: `mn5vx, exterior, exterior master west view aerial photograph looking east across the estate, foreground right showing 1-story private home gym with glass walls and workout equipment, foreground left and center showing continuous straight 1st-floor west wall of main house from bedroom 6 on north-left to bedroom 3 on south-right, 2nd-floor wooden rooftop terrace above with lounge chairs over bedroom 6, west dining table and dark gabled attic cottage, background left showing 1st-floor zen forest courtyard stretching east to red maple tree, background center showing string-lit rooftop pergola, background right showing 27.8m swimming pool and workshop, golden hour twilight, empty scene, no humans`

### [06] `06_mansion_zen_courtyard_to_bedroom6.png`
- **Caption (`.txt`)**: `mn5vx, zen, bedroom6, eye-level exterior-to-interior transition photograph from inside the 1st-floor zen forest courtyard looking west toward bedroom 6, foreground right with round stone tsukubai water basin, bamboo spout, red maple branches and green bamboo groves along north wall, center with wavy white karesansui raked gravel, green moss mounds and grey stepping stones, left with brown wooden engawa deck walkway along solid north wall of main house, background center showing wide sliding glass doors of 1st-floor bedroom 6 revealing light oak desk, monitor, pour-over coffee station, bookcase and olive-green bed inside, 2nd-floor rooftop railing and attic cottage roof visible above, twilight, empty scene, no humans`

### [08] `08_mansion_bedroom6_master_wide.png`
- **Caption (`.txt`)**: `mn5vx, bedroom6, interior master wide photograph of 1st-floor bedroom 6 studio suite looking west, warm light oak flooring and white walls, center background with light oak king bed, olive-green sheets, cream textured throw blanket, grey knit sweater, nightstand and horizontal clerestory window above bed, left studio zone with light oak work desk, dark grey ergonomic chair, laptop, monitor, stainless steel kettle, coffee beans jar, mug, beige cushioned wooden stool, cream rug, corkboard and bookcase with trailing green plant, left sliding glass door opening onto wooden engawa deck and zen forest courtyard with red maple, bamboo, stone water basin and white raked gravel outside, right side with built-in oak wardrobe, standing mirror, grey armless loveseat sofa and open en-suite bathroom door, empty room, no people`

### [09] `09_mansion_bedroom6_studio_desk_to_courtyard.png`
- **Caption (`.txt`)**: `mn5vx, bedroom6, zen, interior-to-exterior 180-degree reverse angle photograph from inside bedroom 6 looking east past the studio work desk directly out into the zen forest courtyard, foreground right with light oak desk, dark grey ergonomic chair, laptop, external monitor, stainless kettle, coffee beans jar, beige cushioned wooden stool on cream rug, corkboard, bookcase with trailing green plant and olive-green bed edge, outside left and center showing brown wooden engawa deck, wavy white karesansui raked gravel, sculpted green moss islands, green bamboo groves along north wall, solid windowless grey-beige main house north wall on right, and orange-red japanese maple tree with round stone tsukubai water basin at east end, twilight, empty scene, no humans`

### [10] `10_mansion_bedroom6_doorway_to_west_corridor.png`
- **Caption (`.txt`)**: `mn5vx, bedroom6, living, interior true 180-degree rotated camera photograph standing in front of the bed inside 1st-floor bedroom 6 looking south through the open wooden bedroom door down the west corridor into the central living room, foreground bottom showing foot of olive-green and cream knit bed with folded grey sweater, left side showing leaning oak full-length mirror, grey fabric armless loveseat sofa, open pocket door to grey-tiled en-suite bathroom and built-in light oak wardrobe, right side showing light oak bookcase with trailing plant, light oak work desk with laptop, monitor, stainless kettle, dark grey chair, beige wooden stool on cream rug and sliding glass door opening to zen forest courtyard with red maple and stone water basin, center straight ahead showing open wooden door with grey robe on hook leading down west corridor directly into main living room with cream L-shaped sofa, empty room, no people`

### [11] `11_mansion_living_room_master_east.png`
- **Caption (`.txt`)**: `mn5vx, living, 1st floor central living room master looking east, solid windowless oak kitchen cabinets and walnut dining table on far left, bookshelf zone and study openings along north oak wall, cream-beige L-shaped sofa and live-edge wooden coffee table in center, round stone firepit table with 4 curved cream-beige barrel lounge chairs in front of bedroom 4 and 5 flush oak doors ahead, floor-to-ceiling south glass curtain wall on right showing 27.8m turquoise swimming pool, white umbrella sunbeds, and 1-story beige-stucco workshop annex with solid doorless west wall, empty scene, no people`

### [12] `12_mansion_living_room_reverse_west.png`
- **Caption (`.txt`)**: `mn5vx, living, 1st floor central living room 180-degree reverse looking west, round stone firepit table with 4 curved cream-beige barrel lounge chairs on round jute rug in center foreground, wide opening into the study on right foreground showing dark oak bookshelves and charcoal sofa and dual-monitor desk, followed along right north wall by bookshelf zone, central bathroom, and kitchen, cream-beige L-shaped sofa and vertical-slat oak TV partition wall ahead on west side, floor-to-ceiling south glass wall on left showing 27.8m swimming pool and 1-story private home gym, empty scene, no people`

### [13] `13_mansion_living_room_south_to_pool_deck.png`
- **Caption (`.txt`)**: `mn5vx, pool, living, elevated aerial exterior view from the south across 27.8m turquoise swimming pool to the 1st floor central living room glass wall, front road and stone gate in foreground, main house floor-to-ceiling south glass wall and 2nd-floor attic and string-lit rooftop pergola, 1-story glass-walled private home gym on west left, 1-story beige-stucco workshop annex on south-east right with solid doorless west wall facing pool and entrance on south facade, sunset twilight sky, empty scene, no people`

### [14] `14_mansion_living_room_firepit_to_east_rooms.png`
- **Caption (`.txt`)**: `mn5vx, living, 1st floor central living room east lounge looking east toward bedroom 4 and 5 flush oak doors, round stone firepit table surrounded by 4 curved cream-beige barrel lounge chairs on round jute rug in center, open portal to the study on left showing solid windowless dark oak bookshelves and charcoal sofa and dual-monitor desk, floor-to-ceiling south glass wall on right showing swimming pool, sunbeds with umbrella, and solid doorless west wall of workshop annex, empty scene, no people`

### [15] `15_mansion_kitchen_dining_master.png`
- **Caption (`.txt`)**: `mn5vx, kitchen, interior master wide photograph of the 1st-floor kitchen and dining room looking northwest, warm light oak wood flooring, perimeter cove ceiling lighting and two woven rattan dome pendant lights hanging over a 6-seater walnut wooden dining table with ceramic bowl, back north and left west walls with L-shaped built-in flat-panel walnut-toned oak kitchen cabinetry with no island and no window, matte cream stone countertops, under-cabinet LED lighting, sink, induction cooktop, range hood and built-in black oven, right east interior wall shared with bathroom featuring stainless steel double-door refrigerator and solid floor-to-ceiling warm oak pantry cabinetry with no windows, left open doorway leading to west corridor and bedroom 1 door, empty room, no people`

### [16] `16_mansion_kitchen_reverse_to_living_and_pool.png`
- **Caption (`.txt`)**: `mn5vx, kitchen, living, pool, 1st floor kitchen at dusk looking south across walnut dining table and central living room L-sofa to 27.8m swimming pool, waterfall-edge veined beige stone kitchen island countertop in foreground, shaker-panel light oak cabinets, stainless double-door fridge and stacked built-in black double ovens with a small window beside the sink on right, rattan pendant lights above walnut dining table, solid doorless west wall of workshop annex visible outside glass wall on left, empty scene, no people`

### [17] `17_mansion_central_bathroom_and_bookshelf_corridor.png`
- **Caption (`.txt`)**: `mn5vx, bath, shelf, 1st floor central bathroom and U-shaped bookshelf zone looking east into enclosed living room, open oak door on left revealing windowless warm beige travertine stone bathroom with freestanding oval bathtub and backlit mirror vanity, warm-lit oak bookshelf alcove in center, enclosed living room with cream-beige L-sofa and south pool glass wall on right, empty scene, no people`

### [18] `18_mansion_bedroom1_master_wide.png`
- **Caption (`.txt`)**: `mn5vx, bedroom1, 1st floor bedroom 1 master looking north, dark walnut desk with burgundy tufted velvet armchair and 3-tier dark bookshelf with antique grimoire book on left, waist-high 1st-floor west window with dark curtains on far left, vertical-channel-tufted deep burgundy velvet north wall with glowing golden crescent moon sconce and burgundy velvet bed in center, red-string timestamped note card wall and glowing miniature lighthouse lamp on right, empty scene, no people`

### [19] `19_mansion_bedroom1_reverse_desk_and_window.png`
- **Caption (`.txt`)**: `mn5vx, bedroom1, 1st floor bedroom 1 rotated view looking west toward waist-high dark-framed casement window and dark walnut desk, burgundy tufted velvet armchair with glowing miniature lighthouse lamp on a round dark side table and red-string note wall on left, burgundy velvet bed with dark bookshelf and antique book and golden crescent moon sconce on right, empty scene, no people`

### [20] `20_mansion_bedroom1_doorway_to_west_corridor.png`
- **Caption (`.txt`)**: `mn5vx, bedroom1, kitchen, interior true 180-degree reverse doorway transition photograph standing near the west window inside 1st-floor bedroom 1 looking east through the open wooden bedroom door across the west corridor directly into the kitchen and dining room, foreground left north wall showing deep burgundy velvet vertical channel-tufted wall with glowing golden crescent moon sconce above king bed with cream sheets, burgundy knitted throw blanket and glowing miniature lighthouse lamp on round dark side table, foreground right wall showing dark textured wall covered in pinned notes and red investigation strings, center straight ahead through open wooden door showing light-oak west corridor and open kitchen dining room with walnut dining table, two woven rattan dome pendant lights, built-in black oven and oak kitchen counters, empty room, no people`

### [21] `21_mansion_west_corridor_north_to_south.png`
- **Caption (`.txt`)**: `mn5vx, corridor, 1st floor west corridor looking south, solid west wall with 3 flush oak bedroom doors on right, open portal to kitchen walnut dining table with solid oak cabinets on left, vertical slat oak TV partition wall, south pool glass door ahead, empty scene, no people`

### [22] `22_mansion_west_corridor_south_to_north.png`
- **Caption (`.txt`)**: `mn5vx, corridor, 1st floor west corridor 180-degree reverse looking north, solid west wall with 3 oak bedroom doors on left, living room L-sofa and oak TV partition wall and kitchen dining portal with solid oak cabinets on right, open doorway into bedroom 6 ahead, empty scene, no people`

### [23] `23_mansion_bedroom2_master_north.png`
- **Caption (`.txt`)**: `mn5vx, bedroom2, 1st floor bedroom 2 master looking north in warm golden-hour sunlight, waist-high white-framed casement window with blue curtains above 3-drawer natural oak study desk with black lamp and laptop and yellow rubber duck on left, blue plaid shirt on chair, low wooden bed with navy-to-sunset-orange gradient duvet and yellow plush duck and sunset poster ahead, hourglass nightstand and 3-door white built-in wardrobe and black standing mirror on right, blue-and-cream patchwork block rug on floor, empty scene, no people`

### [24] `24_mansion_bedroom2_west_desk_window.png`
- **Caption (`.txt`)**: `mn5vx, bedroom2, 1st floor bedroom 2 rotated view looking west in warm golden-hour sunlight, waist-high white-framed multi-pane casement window with blue curtains above 3-drawer natural oak study desk with black lamp, laptop, yellow rubber duck, coloured pencils, and blue-plaid-shirt chair, cork pinboard on the wall left of the window, navy-to-sunset-orange gradient bed with yellow plush duck on right, blue-and-cream patchwork block rug on floor, empty scene, no people`

### [25] `25_mansion_bedroom2_east_mirror_wardrobe.png`
- **Caption (`.txt`)**: `mn5vx, bedroom2, 1st floor bedroom 2 rotated view looking north-east in warm golden-hour sunlight, navy-to-sunset-orange gradient bed with yellow plush duck, sunset poster wall, wooden nightstand with two hourglasses and warm lamp, 3-door white built-in wardrobe and black standing mirror on right, blue geometric woven rug in foreground, empty scene, no people`

### [26] `26_mansion_bedroom2_doorway_to_west_corridor.png`
- **Caption (`.txt`)**: `mn5vx, bedroom2, corridor, 1st floor bedroom 2 180-degree reverse looking east through open oak bedroom door in warm golden-hour sunlight, navy-to-sunset-orange gradient bed and hourglass nightstand and 3-door white wardrobe on left, black standing mirror reflecting waist-high west window in center, oak desk and plaid-shirt chair on right, blue geometric woven rug on floor, open doorway looking across west corridor into central living room L-sofa, empty scene, no people`

### [27] `27_mansion_bedroom3_master_wide.png`
- **Caption (`.txt`)**: `mn5vx, bedroom3, 1st floor bedroom 3 master wide angle under pale overcast daylight through the curtained windows, warm-grey linen low platform bed under curtained window on left, wooden stool with stacked manuscripts, vintage dark-wood writer desk with black lamp and leather journal and dried flowers under colourful pastel post-it sticky note mosaic corner wall, tall dark-wood bookshelf on right, empty scene, no people`

### [28] `28_mansion_bedroom3_desk_postit_wall.png`
- **Caption (`.txt`)**: `mn5vx, bedroom3, 1st floor bedroom 3 rotated close-up on vintage dark-wood writer desk, leather journal, dried lavender vase, black task lamp, dense pastel post-it sticky note mosaic on solid corner walls, tall dark-wood bookshelf on right, empty scene, no people`

### [29] `29_mansion_bedroom3_south_window_to_pool_and_gym.png`
- **Caption (`.txt`)**: `mn5vx, bedroom3, 1st floor bedroom 3 at south-west corner looking through two waist-high dark-wooden-framed windows with sheer beige linen curtains, warm-grey linen low platform bed on left, wooden stool with stacked manuscripts, vintage dark-wood writer desk with black lamp and pastel post-it sticky-note mosaic wall on right, outdoor dusk view of 27.8m turquoise swimming pool on left and 1-story glass-walled private home gym on right, empty scene, no people`

### [30] `30_mansion_bedroom3_doorway_to_living_and_pool.png`
- **Caption (`.txt`)**: `mn5vx, bedroom3, living, 1st floor bedroom 3 180-degree reverse looking east through open wooden bedroom door, pastel post-it sticky-note mosaic wall and vintage dark-wood writer desk and tall dark-wood bookshelf on solid left north wall, warm-grey linen bed and 100% solid plaster east interior wall on right, open doorway looking directly into central living room vertical-slat oak TV wall and cream-beige L-sofa, empty scene, no people`

### [31] `31_mansion_study_master.png`
- **Caption (`.txt`)**: `mn5vx, study, 1st floor study master looking north-east, vintage mechanical typewriter on left wooden desk corner, deep charcoal fabric sofa with knit blanket in center, wooden desk with dual glowing monitors and stacked manuscripts on right, Persian rug with scattered pages, floor-to-ceiling dark oak bookshelves with flush secret door on right east wall, empty scene, no people`

### [32] `32_mansion_study_reverse_to_living_firepit.png`
- **Caption (`.txt`)**: `mn5vx, study, living, 1st floor study 180-degree reverse looking south through open doorway into central living room, dual-monitor wooden desk and dark oak bookshelves on left east wall, charcoal fabric sofa with knit blanket and vintage typewriter desk corner and dark oak bookshelves on solid right west wall, flat continuous oak floor leading to living room round stone firepit table with 4 curved cream-beige barrel chairs and south swimming pool glass wall, empty scene, no people`

### [33] `33_mansion_study_to_greyzone_secret_door.png`
- **Caption (`.txt`)**: `mn5vx, study, greyzone, 1st floor study transition looking east through open secret bookcase door into grey zone private theater, dual monitor desk and Persian rug on left, swung-open dark oak bookcase door in center revealing plush charcoal floor daybed, LED-lit whiskey shelf, cork memo board, and ceiling projector beam inside grey zone, empty scene, no people`

### [34] `34_mansion_greyzone_theater_master.png`
- **Caption (`.txt`)**: `mn5vx, greyzone, 1st floor north-east secret private theater grey zone master, plush charcoal-grey floor daybed mattress in center, built-in walnut bar shelf with warm LED strip lighting displaying whiskey bottles and Guinness cans on left wall, cork memo board and ceiling projector beam on back wall, Edison glass lantern and Marshall speaker on side table, projection screen on right wall, empty scene, no people`

### [35] `35_mansion_bedroom4_master_wide.png`
- **Caption (`.txt`)**: `mn5vx, bedroom4, 1st floor bedroom 4 master looking east, matte dark charcoal north wall with black-and-white photography gallery and dark walnut editing desk with task lamp and camera and laptop on left, waist-high double-casement window with baseboard heater and dark curtains looking out at dusk to 1st-floor east garden path ahead, built-in dark 2-door closet on back-right, rumpled navy-bedding platform king bed on right, empty scene, no people`

### [36] `36_mansion_bedroom4_desk_and_gallery_wall.png`
- **Caption (`.txt`)**: `mn5vx, bedroom4, 1st floor bedroom 4 rotated view looking north-east, black-and-white photography gallery wall and dark walnut editing desk with task lamp and vintage camera and contact sheets on left, waist-high double-casement window with solid lower wall and baseboard heater and dark curtains in center looking out at dusk to 1st-floor east garden path, built-in dark 2-door closet and navy king bed on right, empty scene, no people`

### [37] `37_mansion_bedroom4_doorway_to_living_firepit.png`
- **Caption (`.txt`)**: `mn5vx, bedroom4, living, 1st floor bedroom 4 180-degree reverse looking west through open oak door into central living room, navy king bed on left south wall, dark walnut editing desk and black-and-white photo gallery on solid windowless right north wall, open doorway revealing round stone firepit table with 4 curved cream-beige barrel lounge chairs, south pool glass wall on left, study and bookshelf zone on right, and west oak slat TV wall ahead, empty scene, no people`

### [38] `38_mansion_bedroom5_master_wide.png`
- **Caption (`.txt`)**: `mn5vx, bedroom5, 1st floor bedroom 5 master looking east, continuous solid windowless warm-grey plaster north wall on left with dual-monitor wooden desk, black lamp, yellow sticky notes, calendar, and beige-grey linen bed, floor-to-ceiling natural oak bookshelf wall filled with archive binders on right, 1st-floor ground-level east lawn and pine forest window ahead, empty scene, no people`

### [39] `39_mansion_bedroom5_dual_monitor_desk_and_bookshelf.png`
- **Caption (`.txt`)**: `mn5vx, bedroom5, 1st floor bedroom 5 180-degree interior view looking west toward closed oak bedroom door, floor-to-ceiling natural oak bookshelf wall with white and black archive binders on left south wall, beige-grey linen bed and dual-monitor wooden desk with yellow sticky notes on solid windowless right north wall, empty scene, no people`

### [40] `40_mansion_bedroom5_doorway_to_living_firepit.png`
- **Caption (`.txt`)**: `mn5vx, bedroom5, living, 1st floor bedroom 5 180-degree reverse looking west through open oak door into central living room, floor-to-ceiling natural oak bookshelf wall with archive binders on left south wall, beige-grey linen bed and dual-monitor wooden desk with yellow sticky notes on solid windowless right north wall, open doorway revealing round stone firepit table with 4 curved cream-beige barrel lounge chairs and south pool glass wall on left, empty scene, no people`

### [41] `41_mansion_rooftop_terrace_master_west.png`
- **Caption (`.txt`)**: `mn5vx, rooftop, 2nd floor rooftop pergola terrace master looking west toward gabled dark-roof attic cottage, 8-seater wooden dining table on right, modular fabric sofa lounge in center under black steel pergola with warm Edison string lights, 1st-floor 27.8m turquoise swimming pool and 1-story glass-walled home gym below on left at twilight, empty scene, no people`

### [42] `42_mansion_rooftop_terrace_reverse_east.png`
- **Caption (`.txt`)**: `mn5vx, rooftop, 2nd floor rooftop pergola terrace 180-degree reverse looking east from in front of attic cottage, 100% brown wooden timber deck, 8-seater wooden dining table on left north side, modular fabric sofa lounge in center-left with 1st-floor swimming pool below on right south side, built-in black BBQ grill station at far east end under Edison string-lit pergola, empty scene, no people`

### [43] `43_mansion_rooftop_northwest_sunbed_deck_to_courtyard.png`
- **Caption (`.txt`)**: `mn5vx, rooftop, zen, 2nd floor north-west extended rooftop sunbed deck above 1st-floor bedroom 6 looking south-east, two beige sunbeds on brown timber deck in foreground, gabled attic cottage on right, string-lit rooftop pergola in center-back, 1st-floor zen forest courtyard with white raked gravel and red maple tree and solid windowless main house north wall below on left, empty scene, no people`

### [44] `44_mansion_attic_bedroom_master.png`
- **Caption (`.txt`)**: `mn5vx, attic, 2nd floor gabled attic bedroom master looking west, pitched A-frame ceiling with dark wooden rafters and two warm central pendant lights, rustic wooden drafting desk with brass lamp and spread-out blueprints on left, low platform bed with mustard-ochre bedding and unfolded blueprint map in center-left, low coffee table and tan leather pouf on jute rug, centered grid gable window with full-width low wooden bookshelf and ship wheel ornament ahead, 6-drawer wooden chest with glowing lantern and scroll barrel on right, empty scene, no people`

### [45] `45_mansion_attic_bedroom_reverse_interior.png`
- **Caption (`.txt`)**: `mn5vx, attic, 2nd floor gabled attic bedroom rotated angle focusing on left rustic wooden drafting desk with glowing task lamp and architectural blueprints, mustard-ochre linen bed with draped blueprint map, low wooden coffee table and tan leather pouf ottoman, back gable grid window and low wooden bookshelf with ship wheel ornament under dark timber A-frame rafters, empty scene, no people`

### [46] `46_mansion_attic_doorway_to_rooftop_terrace.png`
- **Caption (`.txt`)**: `mn5vx, attic, rooftop, 2nd floor gabled attic bedroom 180-degree reverse looking east through open cottage doors onto rooftop pergola terrace at dusk, 6-drawer wooden chest with hurricane lantern and blueprint scroll barrel on left north wall, rustic drafting desk with blueprints and foot of mustard-ochre bed on right south side and tan leather pouf and low coffee table in center foreground, string-lit rooftop pergola dining and sofa lounge ahead, empty scene, no people`

### [47] `47_mansion_pool_deck_to_rooftop_stairs_transition.png`
- **Caption (`.txt`)**: `mn5vx, pool, rooftop, exterior transition from 1st-floor poolside wooden deck up the angled black-steel and wood staircase to 2nd-floor rooftop terrace, gabled dark-roof attic cottage at top left, string-lit black steel pergola at top right, 1st-floor bedroom 3 window on lower left, central living room floor-to-ceiling glass curtain wall and 27.8m turquoise swimming pool on lower right at twilight, empty scene, no people`

### [48] `48_mansion_workshop_annex_master.png`
- **Caption (`.txt`)**: `mn5vx, workshop, 1st floor south-east annex workshop master, large wooden drafting workbench in foreground covered with mechanical blueprints, rolled scrolls, brass weights, magnifying glass, and glowing brass banker lamp, rustic wooden shelving with PUZZLE FILES crates and pegboard tool rack on right wall, red-string cork pinboard and side workbench on left wall, single wooden door with wire-mesh glass pane on back wall, exposed ceiling conduit pipes and caged Edison bulbs, empty scene, no people`

### [49] `49_mansion_workshop_toolwall_and_pinboard.png`
- **Caption (`.txt`)**: `mn5vx, workshop, 1st floor south-east annex workshop wide cross-room view, central wooden drafting workbench with mechanical blueprints and brass lamp, floor-to-ceiling PUZZLE FILES wooden crates and pegboard wrench/hammer tool wall on right, red-string cork pinboard with sconces and side workbench on left, single wire-mesh glass wooden door ahead, empty scene, no people`

### [50] `50_mansion_workshop_doorway_to_pool_and_mansion.png`
- **Caption (`.txt`)**: `mn5vx, workshop, 1st floor south-east annex workshop 180-degree reverse looking straight south through open single wire-mesh glass wooden door, PUZZLE FILES wooden crates and pegboard tool rack on left east wall, red-string cork pinboard and side workbench on right west wall, wooden drafting workbench with mechanical blueprints and glowing brass banker lamp in foreground, looking south out the entrance door onto a secluded stone patio surrounded by lush green landscaping and a large leafy shade tree with a cozy outdoor fabric sofa resting lounge area and warm lantern coffee table underneath, empty scene, no people`

### [51] `51_mansion_swimming_pool_deck_master_west.png`
- **Caption (`.txt`)**: `mn5vx, pool, 1st floor 27.8m turquoise swimming pool and wooden pool deck master looking west from east end, shimmering pool on left, brown timber deck with sunbeds and outdoor dining table and main house south glass wall and angled rooftop stairs on right, 1-story glass-walled private home gym straight ahead at west end at twilight, empty scene, no people`

### [52] `52_mansion_swimming_pool_deck_reverse_east.png`
- **Caption (`.txt`)**: `mn5vx, pool, 1st floor 27.8m turquoise swimming pool and wooden pool deck 180-degree reverse looking east from west end, main house south glass curtain wall and angled rooftop staircase and string-lit 2nd-floor pergola on left north side, turquoise swimming pool and stone garden path on right south side, sunbeds with white umbrella and 1-story beige-stucco workshop annex with solid doorless west wall straight ahead at east end, empty scene, no people`

### [53] `53_mansion_private_home_gym_master.png`
- **Caption (`.txt`)**: `mn5vx, homegym, 1st floor south-west annex private home gym master looking north-east, black steel power rack with barbell in front of full-height mirror wall and dumbbell rack and weight bench on rubber mat on left, cable pulley machine and kettlebell rack on right, two treadmills and two spin bikes facing floor-to-ceiling glass wall looking out to main house and 2nd-floor attic and rooftop pergola at twilight, empty scene, no people`

### [54] `54_mansion_private_home_gym_power_rack_and_mirror.png`
- **Caption (`.txt`)**: `mn5vx, homegym, 1st floor private home gym rotated angle focusing on black steel power rack with Olympic barbell, full-height mirror wall with warm linear cove lighting, 2-tier dumbbell rack and adjustable bench on black rubber mat on left, two treadmills and two spin bikes along east glass curtain wall on right, empty scene, no people`

### [55] `55_mansion_private_home_gym_to_pool_deck_transition.png`
- **Caption (`.txt`)**: `mn5vx, homegym, pool, 1st floor private home gym interior-to-exterior transition looking east through open glass wall, power rack and two spin bikes on left, two treadmills in center foreground, cable pulley machine on right, looking out across stone path to 27.8m turquoise swimming pool on right, main house 1st-floor south glass wall and 2nd-floor attic and pergola on left, and solid doorless west wall of workshop annex at far east end, empty scene, no people`

### [56] `56_mansion_east_motorcycle_parking_and_shower_annex.png`
- **Caption (`.txt`)**: `mn5vx, parking, sauna, 1st floor east wing exterior master looking north-west, row of parked motorcycles along east stone driveway in front of 1-story beige-stucco workshop on lower left, 1-story shared shower and sauna pavilion with wooden doors on lower right, straight exterior staircase ascending to 2nd-floor rooftop BBQ and pergola in center, wood-slat pergola entrance and 1st-floor zen forest courtyard with white gravel and red maple tree at upper right, empty scene, no people`

### [57] `57_mansion_east_shower_sauna_pavilion_to_parking.png`
- **Caption (`.txt`)**: `mn5vx, sauna, parking, 1st floor east shared shower and sauna pavilion interior looking out to east motorcycle parking, warm cedar-wood dry sauna cabin with glass door on left, dark stone vanity with twin vessel sinks and backlit mirror and glass rain shower stall on right, open wooden door and glass wall revealing parked motorcycles and straight exterior staircase to 2nd-floor rooftop pergola ahead, empty scene, no people`

### [58] `58_mansion_basement_gym_master_arena.png`
- **Caption (`.txt`)**: `mn5vx, basement, underground basement gym master arena wide shot, dark speckled rubber floor with white circular sparring ring and white lettering 오빠짐 BROTHER GYM in center, hanging black leather MAX FC heavy punching bags on left, octagonal chain-link MMA cage with glowing Brother Gym neon sign ahead, raw concrete wall with pull-up fighter stencil mural and 오빠짐 BROTHER GYM lettering and boxing glove rack and digital timer on right, empty scene, no people`

### [59] `59_mansion_basement_gym_boxing_ring_and_weights.png`
- **Caption (`.txt`)**: `mn5vx, basement, underground basement gym rotated view showing full-size boxing ring with red corner pads and ropes on left in front of concrete 오빠짐 BROTHER GYM mural and glove rack, white circular sparring mat and hanging MAX FC heavy bags in center, black steel free-weight squat racks and bench press and dumbbell racks on right, empty scene, no people`

### [60] `60_mansion_basement_gym_locker_room_to_arena.png`
- **Caption (`.txt`)**: `mn5vx, basement, underground basement gym locker room and entrance staircase transition, matte black metal lockers with warm interior lighting and black bench and glowing white stencil motto DISCIPLINE RESPECT HONOR on right brick-and-concrete wall, twin white basins and shower booth on left, open doorway looking into main sparring mat with MAX FC heavy bags and concrete staircase leading up to 1st floor ahead, empty scene, no people`

### [61] `61_mansion_pool_changing_shower_pavilion_master.png`
- **Caption (`.txt`)**: `mn5vx, changing, 1st floor east annex pool changing room restroom and shower pavilion master view looking east from west sliding glass entrance, warm beige non-slip travertine stone floor with recessed linear stainless drains, natural teak-wood slatted ceiling with recessed warm linear LED strip lighting, built-in warm-oak wooden locker cabinets with matte-black handles and oak changing bench with folded white pool towels on left north wall, closed frosted-glass restroom WC door at back-left corner, floating beige travertine double-basin vanity countertop with two stone vessel sinks, matte-black wall-mounted faucets, and two pill-shaped backlit LED mirrors reflecting the warm-oak locker wall inside the room in center, two walk-in clear glass rain-shower stalls with matte-black ceiling rain showerheads and backlit stone niches on right east wall, empty room, no people`

### [62] `62_mansion_pool_changing_room_lockers_and_vanity.png`
- **Caption (`.txt`)**: `mn5vx, changing, 1st floor east annex pool changing room 45-degree rotated interior view looking northeast at locker wall and twin vanity, floor-to-ceiling warm-oak wooden locker cabinets with matte-black handles and integrated oak bench with neatly folded white pool towels on left, closed frosted-glass restroom WC door in center, floating beige travertine double-basin vanity countertop with two stone vessel sinks, matte-black faucets, and two tall pill-shaped backlit LED mirrors reflecting the warm-oak locker cabinets on right, non-slip beige travertine floor with linear drain and teak slatted ceiling with linear LED lighting, empty room, no people`

### [63] `63_mansion_pool_changing_room_reverse_to_pool_deck.png`
- **Caption (`.txt`)**: `mn5vx, changing, eastpath, 1st floor east annex pool changing room 180-degree reverse inside-out view looking straight west through open black-framed sliding glass entrance doors, floating beige travertine double-basin vanity with two stone vessel sinks and backlit pill-shaped mirrors on left south wall, closed frosted-glass WC door on left, built-in warm-oak locker cabinets and changing bench with white pool towels on right north wall, looking west out across the manicured green east garden lawn and grey stone stepping-stone pathway directly toward the 1-story beige-stucco east exterior wall of the main house with waist-high windows of bedroom 5 and bedroom 4, straight black-metal exterior staircase ascending to 2nd-floor rooftop terrace with string-lit black steel pergola, black BBQ grill, and pitched-roof attic cottage on roof, and east end of turquoise swimming pool with white umbrella sunbeds on far left, empty scene, no people`

### [64] `64_mansion_east_garden_to_pool_changing_room_entry.png`
- **Caption (`.txt`)**: `mn5vx, eastpath, changing, 1st floor outside-in entry view standing on the east garden stone stepping-stone pathway looking east into the open black-framed sliding glass entrance of the 1-story flat-roofed beige-stucco pool changing room and shower pavilion surrounded by green lawn and bamboo trees, interior clearly showing teak-wood slatted ceiling with linear LED strips, beige travertine stone floor with linear drains, warm-oak locker cabinets and bench with folded white towels on left, closed frosted-glass WC door, floating travertine double-basin vanity with two backlit pill-shaped mirrors reflecting the oak lockers in center, and walk-in glass rain-shower stalls on right, empty scene, no people`

### [65] `65_mansion_pool_east_steps_and_umbrella_lounge.png`
- **Caption (`.txt`)**: `mn5vx, pool, exterior elevated high-angle view from the east end of the 27.8m turquoise swimming pool deck looking straight west at twilight, wide underwater stone steps descending into the glowing turquoise pool water in foreground, teak pool deck on left south side with white cushioned sunbeds, white patio umbrella, and 1-story beige-stucco workshop annex featuring a 100% solid doorless and windowless west wall facing the pool, 1-story main house on right north side with floor-to-ceiling south glass curtain wall revealing the 4-chair round stone firepit lounge in the right east glass bay and cream-beige L-shaped sofa in the center bay, 6-seater outdoor wooden dining table on deck, angled west rooftop staircase, 2nd-floor rooftop terrace with string-lit dark metal pergola and pitched-roof attic cottage on west roof, and 1-story private home gym pavilion at far west end, empty scene, no people`

### [66] `66_mansion_pool_deck_dining_to_living_room.png`
- **Caption (`.txt`)**: `mn5vx, pool, living, exterior elevated view from the central wooden swimming pool deck beside the 6-seater outdoor teak dining table looking northwest toward the main house at twilight, sparkling turquoise swimming pool on left, wide floor-to-ceiling black-framed glass curtain wall of the 1st-floor living room in center-right showing continuous flat light-oak floor with cream-beige L-shaped sofa in left bay and round stone firepit table surrounded by 4 curved cream barrel chairs on a round jute rug in right bay backed by solid windowless bookshelves of the study, angled west exterior rooftop staircase and bedroom 3 window on left, and 2nd-floor rooftop terrace above featuring the pitched-roof attic cottage on left and dark metal pergola with warm string lights on right, empty scene, no people`

### [67] `67_mansion_pool_west_end_gym_and_stairs_junction.png`
- **Caption (`.txt`)**: `mn5vx, pool, homegym, exterior eye-level twilight view standing at the west end of the wooden swimming pool deck looking northwest at the architectural junction between the 1-story private home gym pavilion and the main house, open black-framed sliding glass doors of private home gym on left revealing black power rack, barbell, dumbbell rack, and warm wood floor with a grey mat inside, grey stone stepping-stone pathway leading north into the west garden in center, 1st-floor main house west wing with bedroom 3 window and angled black exterior staircase ascending to the 2nd-floor rooftop terrace with the pitched-roof attic cottage and string-lit pergola above, west glass corner of living room with vertical oak slat TV wall and cream L-sofa on right, and turquoise swimming pool water in lower-right foreground, empty scene, no people`

### [68] `68_mansion_south_main_gate_arrival_pov.png`
- **Caption (`.txt`)**: `mn5vx, gate, pool, exterior elevated aerial arrival view from just inside the open south main gate looking straight north across the estate at twilight, grey stone-paved entry walkway flanked by manicured bamboo hedges and open dark metal gates in foreground, 27.8m turquoise swimming pool with wooden decks, white sunbeds, and white umbrellas in midground center, 1-story private home gym pavilion on midground left west side, 1-story workshop annex on midground right east side with solid doorless west wall facing the pool and south entrance facing a shaded garden patio with an outdoor fabric sofa under a large leafy tree, 1-story main house in background center with south glass living room facade, angled west rooftop staircase, and 2nd-floor rooftop terrace featuring the pitched-roof attic cottage on left and string-lit dark metal pergola lounge in center-right, empty scene, no people`

### [69] `69_mansion_west_garden_pathway_north_view.png`
- **Caption (`.txt`)**: `mn5vx, westpath, exterior slightly elevated view over the west garden stone stepping-stone pathway looking straight north in daylight, open manicured green west lawn on left with a small round outdoor coffee table and two lounge chairs under shade trees along the low west perimeter wall and lush green forest (no building on the left opposite bedrooms 1 to 3), straight grey stone stepping-stone pathway in center leading north, 1-story main house continuous straight flush beige-stucco west exterior wall on right featuring the 3 waist-high dark-framed casement windows of bedroom 3, bedroom 2, and bedroom 1 followed seamlessly on the same attached building mass by bedroom 6 at the north-west corner, topped by the 2nd-floor rooftop terrace with black metal railing, white sunbeds, and the dark pitched-roof attic cottage, empty scene, no people`

### [70] `70_mansion_east_garden_pathway_north_view.png`
- **Caption (`.txt`)**: `mn5vx, eastpath, exterior elevated view over the east garden stone stepping-stone pathway looking straight north at twilight, 1-story main house continuous straight beige-stucco east exterior wall on left featuring waist-high windows of bedroom 5 and bedroom 4 followed by the solid windowless grey zone east wall and the straight black-metal exterior staircase ascending to the 2nd-floor wooden rooftop terrace with black metal railing, black BBQ grill, string-lit black steel pergola, and dark pitched-roof attic cottage on the roof, straight grey stone stepping-stone pathway on manicured green lawn in center leading north into the dark wood-slat pergola entrance of the north zen courtyard with vibrant red japanese maple tree, stone water basin tsukubai, white raked gravel, and bamboo groves, and 1-story flat-roofed beige-stucco pool changing room and shower pavilion on right with black-framed sliding glass doors facing the path, empty scene, no people`

### [71] `71_mansion_west_corridor_into_bedroom1.png`
- **Caption (`.txt`)**: `mn5vx, corridor, bedroom1, interior 180-degree outside-in doorway transition standing in the bright warm-cream 1st-floor west corridor looking west through a standard single-width warm-oak wooden door frame into bedroom 1, solid warm-cream corridor wall framing both left and right sides of the doorway, single warm-oak wooden door leaf hinged on the left jamb matching the door frame width and height 1-to-1, interior of the room preserving exact reference layout with vertical-channel-tufted deep burgundy velvet wall and glowing golden crescent moon wall sconce in center, burgundy velvet headboard bed with cream bedding and dark burgundy throw blanket on right, round black side table with glowing miniature lighthouse lamp in foreground right, and dark walnut desk, burgundy velvet chair, low wooden bookcase with antique book on top, and red persian rug on dark wood floor on left, empty room, no people`

### [72] `72_mansion_west_corridor_into_bedroom2.png`
- **Caption (`.txt`)**: `mn5vx, corridor, bedroom2, interior 180-degree outside-in doorway transition standing in the bright warm-cream 1st-floor west corridor looking west through a standard single-width warm-oak wooden door frame into bedroom 2, solid warm-cream corridor wall framing both left and right sides of the doorway with white baseboard, single warm-oak wooden door leaf hinged on the left jamb matching the door frame width and height 1-to-1, interior of the room showing wooden bed with blue-to-orange sunset gradient duvet and yellow duck plushie on pillow against back wall with sunset postcard prints, small wooden nightstand with warm lamp and hourglass on right, and geometric blue-beige rug on wooden floor, empty room, no people`

### [73] `73_mansion_west_corridor_into_bedroom3.png`
- **Caption (`.txt`)**: `mn5vx, corridor, bedroom3, interior 180-degree outside-in doorway transition standing at the south end of the bright warm-cream 1st-floor west corridor looking west through a standard single-width warm-oak wooden door frame into bedroom 3, solid warm-cream corridor wall framing both left and right sides of the doorway, single warm-oak wooden door leaf hinged on the left jamb matching the door frame width and height 1-to-1, interior of the room showing waist-high dark-wood casement window with sheer white curtains on left above single bed with rumpled grey-brown linen bedding, wooden stool nightstand topped with manuscript stack in center, and vintage wooden writer desk on right under a wall covered in colorful pastel post-it notes with dried flowers in a vase, empty room, no people`

### [74] `74_mansion_living_room_into_bedroom4.png`
- **Caption (`.txt`)**: `mn5vx, living, bedroom4, interior 180-degree outside-in doorway transition standing in the 1st-floor living room east side looking east through a standard single-width warm-oak wooden door frame into bedroom 4, solid warm-cream living room wall framing both left and right sides of the doorway, single warm-oak wooden door leaf hinged on the left jamb matching the door frame width and height 1-to-1, moody dark interior of the room showing dark wooden desk with laptop, scattered photo prints, chair with dark jacket, and framed wall photos on left north wall, waist-high window with dark navy curtains looking out to night trees and dark built-in 2-door closet on back east wall, and wooden platform bed with crumpled dark navy-blue bedding and round wooden side table on right south wall, empty room, no people`

### [75] `75_mansion_living_room_into_bedroom5.png`
- **Caption (`.txt`)**: `mn5vx, living, bedroom5, interior 180-degree outside-in doorway transition standing in the 1st-floor living room south-east side looking east through a standard single-width warm-oak wooden door frame into bedroom 5, solid warm-cream living room wall framing both left and right sides of the doorway, single warm-oak wooden door leaf hinged on the left jamb matching the door frame width and height 1-to-1, bright organized interior of the room showing wooden desk with monitor, black swivel office chair, and yellow sticky notes on the solid left north wall in front of the single bed with grey-beige linen bedding, sheer-curtained floor-to-ceiling glass balcony door at back opening to a small balcony with a railing and a folding chair, and floor-to-ceiling wooden bookcase packed with books, binders, and small wooden drawers along the right south wall with a beige runner rug on oak plank floor, empty room, no people`

### [76] `76_mansion_bookshelf_zone_reverse_to_living_and_pool.png`
- **Caption (`.txt`)**: `mn5vx, shelf, living, interior 180-degree reverse view standing inside the 1st-floor north bookshelf zone between floor-to-ceiling backlit warm-oak bookcases on left and right edges looking straight south across the open-plan living room and out through the floor-to-ceiling south glass curtain wall toward the swimming pool and south main gate, continuous flat light-oak floor in living room featuring the round stone firepit table surrounded by 4 curved cream-beige barrel chairs on a round jute rug on the left east side in front of the closed flush warm-oak bedroom 4 door, and the cream-beige L-shaped modular sofa with oak coffee table on the right west side, outdoor pool deck ahead with 6-seater teak dining table, 27.8m turquoise swimming pool, south main gate in center distance, 1-story workshop annex on far left with a 100% solid doorless and windowless west beige-stucco wall facing the pool, and private home gym pavilion on far right, empty room, no people`

### [77] `77_mansion_central_bathroom_reverse_to_living_room.png`
- **Caption (`.txt`)**: `mn5vx, bath, living, interior 180-degree reverse view standing at the north end inside the 100% windowless 1st-floor central bathroom looking straight south through the open single warm-oak door toward the living room and swimming pool, solid beige travertine stone walls and floor with warm indirect ceiling cove lighting and no exterior windows inside bathroom, floating warm-oak double-basin vanity countertop with two white vessel sinks, matte-black faucets, and two backlit rectangular mirrors reflecting dark bookshelves on left west wall, freestanding white oval bathtub with floor-mounted matte-black faucet on right east wall, looking south through open oak door across bookshelf corridor and living room cream L-sofa out to the turquoise swimming pool, south main gate, and green bamboo perimeter hedge, empty room, no people`

### [78] `78_mansion_greyzone_reverse_into_study.png`
- **Caption (`.txt`)**: `mn5vx, greyzone, study, interior 180-degree reverse view standing at the east end inside the windowless dark-charcoal grey zone secret hideout room looking west through the open secret revolving wooden bookcase door into the study, matte dark-charcoal acoustic wall panels and dark plush carpet inside grey zone, low dark-charcoal floor daybed sofa with cushions and warm glowing vintage edison lantern on wooden crate on left south side, built-in dark walnut home bar shelves with warm amber LED strip lighting displaying whiskey bottles, guinness cans, and glassware on right north side, black ceiling-mounted projector overhead, looking west through open secret bookcase door into the study showing floor-to-ceiling walnut bookshelves, dark charcoal leather sofa, vintage red persian rug with scattered white manuscript pages on herringbone wood floor, and walnut desk with dual monitors, empty room, no people`

### [79] `79_mansion_zen_courtyard_east_pergola_entrance.png`
- **Caption (`.txt`)**: `mn5vx, zen, bedroom6, exterior eye-level view standing inside the dark natural wood-slat pergola entrance at the east end of the 1st-floor north zen forest courtyard looking straight west at sunset, overhead wood-slat pergola beams framing the shot, 1-story main house north exterior wall on left south side featuring a completely smooth, flat, windowless solid beige-stucco wall with a low warm-wood engawa deck along its base and the 2nd-floor rooftop metal railing and pitched-roof attic cottage visible above, white raked karesansui gravel garden in center with wavy patterns, sculpted green moss islands, and flat grey stepping stones, vibrant red japanese maple tree, traditional stone water basin tsukubai with bamboo spout, and lush bamboo groves along the north perimeter wall on right, and floor-to-ceiling black-framed sliding glass doors of bedroom 6 glowing warmly straight ahead on the west end, empty scene, no people`

### [80] `80_mansion_basement_gym_staircase_descent.png`
- **Caption (`.txt`)**: `mn5vx, basement, interior single unified 16:9 wide-angle eye-level view descending the industrial raw concrete entrance staircase with matte-black metal handrails and warm recessed linear LED step lighting into the windowless underground basement gym, black heavy-duty rubber gym floor in center featuring the large white circle printed on the rubber floor with Korean and English text 오빠짐 BROTHER GYM, row of hanging black heavy punching bags printed with MAX FC on left in front of windowless dark concrete wall and interior gym mirrors, black chain-link MMA octagon cage at back center under glowing warm neon sign Brother Gym, exposed raw concrete wall on right featuring black stencil mural of a fighter doing pull-ups next to text 오빠짐 BROTHER GYM, wall-mounted pull-up bars, and multi-tier storage rack filled with red, blue, and white boxing gloves and headgear under rectangular linear LED ceiling lights, empty gym, no people`
