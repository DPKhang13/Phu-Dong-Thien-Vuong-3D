# ⚔️ Thánh Gióng: Mộng Lạc (Thanh Giong: Mong Lac) — Beta Version

<div align="center">

## 3D Action-Adventure Folk Mythological Game

A 20–30 minute narrative and combat beta experience built with Unity, C#, Universal Render Pipeline (URP), and State Machine Architecture.

![Unity](https://img.shields.io/badge/Engine-Unity%206%20%2F%202022.3%20LTS-black?logo=unity)
![C#](https://img.shields.io/badge/Language-C%23-blue?logo=csharp)
![Render Pipeline](https://img.shields.io/badge/Graphics-URP-lightblue)
![Version](https://img.shields.io/badge/Build-Beta%20v0.9.0-orange)
![Target Time](https://img.shields.io/badge/Playtime-20--30%20Mins-green)

</div>

---

# Project Overview

**Thánh Gióng: Mộng Lạc** là dự án game hành động - phiêu lưu góc nhìn thứ ba (Third-Person Action-Adventure) lấy cảm hứng từ truyền thuyết dân gian Việt Nam về người anh hùng Phù Đổng Thiên Vương. 

Phiên bản Beta được cô đọng trong thời lượng trải nghiệm **20–30 phút** xuyên suốt **2 map chính**, tập trung thể hiện trọn vẹn vòng lặp cốt truyện kinh điển: *Nguồn gốc thiêng liêng → Gióng lớn nhanh như thổi → Nhận vũ khí & Lên ngựa sắt → Chiến đấu tại Mộng Lạc → Gãy vũ khí, nhổ tre hạ Boss → Khải hoàn bay về trời*.

---

# Why This Project Matters & Beta Strategy

Phát triển một tựa game cốt truyện kết hợp combat trong quỹ thời gian ngắn (4 tuần) thường gặp các thách thức:
* Phạm vi (Scope) bị dàn trải qua quá nhiều địa danh (Làng quê, Mỏ sắt, Chiến trường, Sóc Sơn).
* Tốn kém chi phí sản xuất 3D asset và cinematic cutscene phức tạp.
* Rủi ro không hoàn thiện cơ chế điều khiển và boss fight.

**Chiến lược tối ưu hóa bản Beta:**
* **Nén không gian thông minh:** Toàn bộ chiến trường, thử thách và trận đánh Boss được gói gọn trong **Mộng Lạc** — biến thể u tối, méo mó của chính Làng Phù Đổng (tận dụng lại 100% layout và modular asset của Map 1).
* **Tái sử dụng tài nguyên (Asset Reuse):** Cơ chế chia địch thành các tier (Lính thường / Lính mạnh) bằng cách tùy biến chỉ số (HP, Speed, Damage) từ cùng một enemy prefab; tái sử dụng animation đánh gậy cho vũ khí tre.
* **Kể chuyện tối giản (Minimalist Storytelling):** Thay thế cutscene cinematic đắt đỏ bằng camera focus, text narrative gợi mở, model swap và hiệu ứng fade in/out mượt mà.

---

# System Actors & Characters

Dự án xoay quanh các nhân vật và thực thể chính:

| Actor / Entity | Vai trò / Cơ chế điều khiển | Mô tả chi tiết |
| :--- | :--- | :--- |
| **Mẹ Gióng** | Nhân vật điều khiển (Act 1 - Act 4) | Góc nhìn TPS, tương tác cơ bản (WASD, trigger sự kiện, thu thập gạo từ dân làng). |
| **Gióng (Thơ ấu)** | Story NPC | Biểu tượng cho sự im lặng thiêng liêng, chỉ cất tiếng nói khi vận mệnh đất nước lâm nguy. |
| **Gióng (Tráng sĩ)**| Nhân vật điều khiển (Act 5 - End) | Chiến binh trưởng thành, sở hữu hệ thống combo cận chiến, thanh máu, đổi vũ khí (Gậy sắt / Tre ngà). |
| **Dân Làng & Sứ Giả**| Interactive NPCs | Cung cấp bối cảnh, giao nhiệm vụ thu thập lương thảo và trao lệnh vua. |
| **Quân Giặc Ân** | AI Enemies | Lính địch tuần tra, phát hiện, truy đuổi và bao vây người chơi theo từng khu vực/wave. |
| **Huyền Kỵ** | Final Boss | Thủ lĩnh giặc mang phong thái hắc ám, có 2 phase giao tranh, cơ chế ra đòn uy lực. |

---

# Core Features & Gameplay Mechanics

## Player & Character Controller
* **Dual-Character Progression:** Chuyển đổi mượt mà giữa Mẹ Gióng (thăm dò, đối thoại) sang Gióng Tráng Sĩ (chiến đấu, hành động) thông qua Model Swap logic.
* **Third-Person Movement:** Hệ thống di chuyển WASD mượt mà, camera xoay theo chuột, hỗ trợ sprint và interaction trigger.

## Combat & Weapon System
* **Light / Heavy Melee Combos:** Tấn công liên hoàn bằng chuột trái, hiệu ứng âm thanh va đập và hit stop chân thực.
* **Dynamic Weapon Swap (Phase Transition):** Khi Boss xuống 50% HP, vũ khí sắt gãy vụn buộc người chơi tương tác với bụi tre để chuyển sang vũ khí **Tre Phù Đổng** (tăng sải đánh/range và sát thương/damage).

## AI & Encounter Design
* **Detection & Chase System:** AI tự động quét tầm nhìn, áp sát và tấn công Gióng khi bước vào khu vực kích hoạt.
* **Wave / Gauntlet Logic:** Cổng dẫn vào khu vực tiếp theo chỉ mở khi toàn bộ kẻ địch trong khu vực hiện tại bị tiêu diệt.

## Progression & Quest Loop
* **Interactive Narrative Quests:** Chuỗi sự kiện dấu chân kỳ lạ, đối thoại sứ giả, gom góp 3/3 phần gạo từ dân làng.
* **Boss Phase Management:** Boss tự động biến đổi chỉ số và nhịp độ tấn công (tăng tốc độ đánh, giảm cooldown) ở Phase 2.

---

# Technology Stack

## Game Engine & Frameworks
* **Engine:** Unity (URP - Universal Render Pipeline)
* **Programming Language:** C# (.NET Framework)
* **Physics & Navigation:** Unity Built-in 3D Physics & NavMesh AI
* **Input Management:** Unity New Input System / Legacy Input System

## Core Architectural Modules
* **Player State Machine:** Quản lý các trạng thái Idle, Walk, Run, Attack, Hit, Death.
* **Event-Driven Architecture:** Hệ thống C# Events / UnityEvents lắng nghe kích hoạt cốt truyện, cập nhật UI và trigger chuyển cảnh.
* **Cinemachine:** Quản lý Virtual Camera, focus dấu chân và boss reveal.

## Tools & Pipeline
* **Source Control:** Git, Git LFS (Large File Storage)
* **Audio:** Unity AudioSource & FMOD/Audacity
* **Optimization:** Occlusion Culling, LOD Groups, Texture Compression

---

# System Architecture & Game Flow

## End-to-End Game Flow

```text
MAIN MENU
    ↓
NEW GAME
    ↓
ACT 1–7: MAP 1 — LÀNG PHÙ ĐỔNG (Nguồn gốc & Thức tỉnh)
[Dấu chân] → [Gióng sinh ra] → [Sứ giả] → [Góp gạo 3/3] → [Gióng trưởng thành] → [Nhận vũ khí] → [Lên Thiết Mã]
    ↓ (Transition / Dismount Animation)
ACT 8–12: MAP 2 — MỘNG LẠC (Chiến trường tâm thức & Khải hoàn)
[Khu 1: Tutorial 2 lính] → [Khu 2: 3 lính áp lực] → [Khu 3: Gauntlet 2 Waves]
    ↓
[Arena: Boss HUYỀN KỴ (Phase 1)]
    ↓ (HP <= 50%)
[Roi sắt gãy] → [Nhổ Tre Phù Đổng] → [Boss Phase 2 (Tăng tốc)]
    ↓
[Hạ gục Boss] → [Thiết Mã xuất hiện] → [Ending & Credits]
