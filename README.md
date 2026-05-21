# ⛓ OpenHash Global Root Node

![Layer](https://img.shields.io/badge/Layer-5-red)
![Status](https://img.shields.io/badge/Status-Active-brightgreen)
![OpenHash](https://img.shields.io/badge/OpenHash-v2.2-blue)

## Node Information

| 항목 | 값 |
|---|---|
| Node ID | `KR-JEJU-JEJU-IDO1-L5` |
| Layer | L5 — Global Root |
| Endpoint | `https://nounweb.github.io/openhash-L5-global` |
| Protocol | OpenHash v2.2 (GDUDA v1.0) |

## 📡 API

| Endpoint | 설명 |
|---|---|
| `/node.json` | 노드 정보 |
| `/routing_table.json` | 사용자 라우팅 테이블 |
| `/chain_status.json` | 해시체인 상태 |
| `/blocks/block_NNNN.json` | 개별 블록 |
| `/api/` | 웹 UI (사용자 검색) |

## 🔗 계층 구조

```
L5 Global  ← nounweb/openhash-L5-global
 └ L4 KR   ← nounweb/openhash-L4-kr
    └ L3 Jeju ← nounweb/openhash-L3-jeju
       └ L2 Jeju City ← nounweb/openhash-L2-jeju-city
          └ L1 Ido1-dong ← nounweb/openhash-L1-ido1  ★ 현재 노드
```

## ⚡ GDUDA 사용자 등록 (Repository Dispatch)

```bash
curl -X POST \
  -H "Authorization: Bearer $OPENHASH_TOKEN" \
  -H "Content-Type: application/json" \
  https://api.github.com/repos/nounweb/openhash-L5-global/dispatches \
  -d '{
    "event_type": "USER_REGISTER",
    "client_payload": {
      "guid"           : "YOUR_GUID",
      "gopang_id"      : "YOUR_ID",
      "display"        : "YOUR_NAME",
      "l1_node"        : "KR-JEJU-JEJU-IDO1",
      "public_key_hash": "SHA256_OF_PUBKEY",
      "endpoint"       : "YOUR_PDV_ENDPOINT"
    }
  }'
```

## 📊 ILMV (양방향 무결성 검증)

- **하향 감사**: 매 시간 자동 실행 (GitHub Actions Scheduled)
- **상향 모니터링**: 이상 감지 시 Issue 자동 생성
- **체인 상태**: `/chain_status.json` 참조

---

*OpenHash Network v2.2 · AI City Inc. · 제주특별자치도*  
*GDUDA (Gopang Distributed User Discovery Algorithm) v1.0*
