# ALICE-Inference-Cloud

Unified LLM inference & training platform — GPU-free 70B on Apple Silicon

## License

AGPL-3.0

## Architecture

```
Frontend :3000  -->  API Gateway :8080  -->  Core Engine :8081
```

| Layer | Port | Technology |
|-------|------|-----------|
| Frontend | 3000 | Next.js 14, Tailwind CSS |
| API Gateway | 8080 | Rust, Axum |
| Core Engine | 8081 | Rust, Axum |

## ALICE Crate Integration

alice-ml, alice-simd, alice-cache, alice-token, alice-train

## Endpoints

| Method | Path | Description |
|--------|------|-------------|
| `POST` | `/api/v1/infer` | テキスト生成（1.58bit Ternary推論） |
| `POST` | `/api/v1/tokenize` | テキストトークナイズ |
| `POST` | `/api/v1/train` | 訓練ジョブ開始 |
| `GET ` | `/api/v1/models` | モデル一覧・ステータス |
| `GET ` | `/health` | ヘルスチェック |

## Quick Start

```bash
cd services/core-engine
cargo run --release
curl http://localhost:8081/health
```

## Author

Moroya Sakamoto
