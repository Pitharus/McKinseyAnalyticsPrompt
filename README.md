# McKinseyAnalyticsPrompt

## 🏗️ Architecture & Design (1–10)

1. Thiết kế OpenHuman-Protocol binary frame format (delta motion + anti-crawl spec)
2. Thiết kế schema 135 curves chuẩn hóa cho OpenHuman-Dataset
3. Thiết kế consistent hashing strategy cho in-process KV routing giữa các Erlang node
4. Thiết kế tree context structure cho OpenHuman-Brain (multi-domain routing)
5. Thiết kế API contract giữa OpenHuman-Backend và GPU worker pool (gRPC spec)
6. Thiết kế audio-motion sync protocol (timestamp tagging strategy)
7. Thiết kế cache key schema cho `(tree_id, prompt_hash, user_context_hash)`
8. Thiết kế OTP supervisor tree cho OpenHuman-Backend
9. Thiết kế embed SDK interface (web component API + native SDK API) theo phong cách Mapbox
10. Thiết kế sharding + replication strategy cho OpenHuman-Cache

---

## 💻 Code Generation (11–22)

11. Viết Cowboy WebSocket handler skeleton trong Elixir/OTP
12. Viết Tokio Rust KV NIF cơ bản dùng Rustler (lock-free HashMap)
13. Viết yt-dlp crawler pipeline bằng Python (filter single-speaker, language, quality)
14. Viết mel-spectrogram extraction module (client-side WebAssembly)
15. Viết motion delta codec (encoder phía server, decoder phía client JS)
16. Viết CTC decoder wrapper cho ASR server endpoint
17. Viết LLM adapter interface cho OpenHuman-Brain (pluggable per tree)
18. Viết Postgres sync background process cho OpenHuman-Cache (dirty flush + warm load)
19. Viết OpenHuman-Protocol client decoder bằng TypeScript (cho Render Engine web)
20. Viết consistent hashing module bằng Elixir
21. Viết session state machine bằng Elixir GenServer
22. Viết benchmark harness đo cache hit rate và latency end-to-end

---

## 🤖 ML & Training (23–31)

23. Thiết kế architecture OpenHuman-Motion (Transformer vs Diffusion cho 135-dim continuous output)
24. Viết training loop PyTorch cho OpenHuman-Motion với DeepSpeed
25. Thiết kế loss function cho lip-sync accuracy (motion ↔ audio alignment)
26. Viết data loader cho dataset format `(audio, transcript, phoneme, 135_curves, emotion)`
27. Thiết kế distillation strategy (teacher → student) cho OpenHuman-Motion production inference
28. Viết evaluation script: FID-style metric cho 135 curves diversity
29. Thiết kế prosody/rhythm control architecture cho OpenHuman-Voice Phase 2
30. Thiết kế fine-tuning strategy cho OmniVoice (Phase 1) với single-voice MVP character
31. Viết INT8 quantization pipeline cho OpenHuman-Motion inference

---

## 📊 Data & Infrastructure (32–38)

32. Viết QA pipeline để validate chất lượng 135 curves output từ MetaHuman Animator
33. Thiết kế Postgres schema cho OpenHuman-Dataset (metadata + index)
34. Viết pre-compute pipeline: batch render greetings + FAQ → cache audio + motion
35. Thiết kế Cloudflare CDN caching strategy (cache key, TTL, edge rules)
36. Viết Hetzner provisioning script (AMD EPYC setup, GPU node config)
37. Thiết kế object storage layout trên Cloudflare R2 cho raw video + processed data
38. Viết monitoring & alerting setup cho Elixir cluster (telemetry, metrics)

---

## 🔐 Security & Protocol (39–43)

39. Thiết kế anti-crawl encoding scheme (session-key-based obfuscation cho motion stream)
40. Thiết kế key rotation strategy cho anti-crawl (per-build rotation)
41. Viết privacy layer cho OpenHuman-Memory (encryption at rest, GDPR delete flow)
42. Thiết kế auth flow cho cross-device memory (OAuth + device pairing)
43. Threat model: liệt kê attack vectors và mitigation cho OpenHuman-Protocol

---

## 📝 Documentation & Spec (44–48)

44. Viết OpenHuman-Protocol spec v1 (public spec cho third-party embedding)
45. Viết ADR (Architecture Decision Records) cho các quyết định lớn (no Redis, no k8s, no three.js...)
46. Viết onboarding guide cho Digital Human Designer (cách config LLM per context tree)
47. Viết cost model spreadsheet: tính cost/user/month tại 1k, 100k, 10M, 100M users
48. Viết integration guide cho third-party app nhúng OpenHuman SDK (Mapbox-style)

---

## 🧪 Testing & Ops (49–50)

49. Viết load test scenario: 1M concurrent WebSocket connections trên 1 Hetzner box
50. Viết runbook cho hot code reload với OTP Release (zero-downtime deploy)
