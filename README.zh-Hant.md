[English](README.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [繁體中文](README.zh-Hant.md) | [简体中文](README.zh-Hans.md)

# NiloPathTracing (NiloPT)
- RTX Real-Time Path Tracing + DLSS Ray Reconstruction。Unity URP 的次世代 renderer。
- 一鍵設定，立即獲得次世代光照：匯入 unitypackage、按一下，數秒內 path tracing 就開始運作。真正即插即用。
- 沒有學習門檻，也無需修改場景資產。
- 原生支援 [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 角色的 path tracing 渲染。
- 專為音樂影片（MV）、3D Live、演唱會與虛擬製作打造。為 VTuber 產業開啟 Unity 光照的新時代。
- NiloPT 影片：[MV1](https://youtu.be/9nlSDtqcS-Q) / [MV2](https://youtu.be/t_yeGLrhi6Q) / [MV3](https://youtu.be/FVIbkuZhtq0) / [MV4](https://youtu.be/iq7ACdJfv8U) / [MV5](https://youtu.be/U4a0Vj2BxVY) / [MV6](https://youtu.be/wgxyj_5rET8) / [MV7](https://www.youtube.com/watch?v=paCZO7G3YKE) / [PView1](https://youtu.be/vfMJ43fT3os) / [PView2](https://youtu.be/tb0aHot0VwQ) / [PView3](https://youtu.be/I0l9cNORIpM)

## 一鍵開啟 / 關閉 NiloPT
[![Banner6](images/preview/NiloPT_Banner6.webp)](images/full/NiloPT_Banner6.webp?raw=true)
[![Banner1](images/preview/NiloPT_Banner1.webp)](images/full/NiloPT_Banner1.webp?raw=true)
[![Banner2](images/preview/NiloPT_Banner2.webp)](images/full/NiloPT_Banner2.webp?raw=true)
[![Banner3](images/preview/NiloPT_Banner3.webp)](images/full/NiloPT_Banner3.webp?raw=true)
[![Banner4](images/preview/NiloPT_Banner4.webp)](images/full/NiloPT_Banner4.webp?raw=true)
[![Banner5](images/preview/NiloPT_Banner5.webp)](images/full/NiloPT_Banner5.webp?raw=true)

## 一鍵完成所有設定
只需按一下，即可將 URP renderer 的 rasterization 渲染替換為 NiloPathTracing。
- 無需學習：匯入 NiloPT unitypackage > 一鍵自動安裝 > path tracing 立即開始運作。
- 無需修改 material、燈光、場景、Prefab、Volume、mesh 等資產。
- 無需修改 URP / UnityEngine 原始碼。現有的 URP 專案即可立即使用，無需任何 hack 或 workaround。
- 無需 baking。所有 path-traced rendering 都是完全即時、動態的，不再需要繁瑣的 lightmap baking，也不必費心配置 light probes 或 reflection probes。
- 無需其他光照資產。NiloPT 可取代 URP / Asset Store / GitHub 中大部分現有的 rasterization 光照工具（詳見下文）。

## 一個 path tracer 取代整套 URP rasterization 光照系統
- skybox 與所有 emissive material（Mesh、Skinned Mesh、Particle、VFX Graph、Decal 等）都是真正照亮場景的光源，也包含使用 RenderTexture 播放影片的 material。例如演唱會舞台上的大型發光螢幕，可藉由播放影片動態照亮整個場景。
- 表面光照全面改用 path-traced shadows 與 occlusion，取代傳統的 rasterization shadow maps 及 AO。
- 反射與折射全程使用即時 path tracing，並受 smoothness、metallic 等 material 屬性影響。

NiloPT 可取代 URP / Asset Store / GitHub 中大部分現有的 rasterization 光照工具。以下大部分項目都不再需要：
- (X) Lightmaps / Light Probes / Adaptive Probe Volumes (APV)
- (X) URP Surface Cache / Screen Space Global Illumination / World Space Global Illumination
- (X) Reflection Probes（baked 與 real-time）
- (X) Planar Reflections / Screen Space Reflections / Ray-Traced Reflection tools
- (X) Shadow Maps / Contact Shadows / PCSS / Ray-Traced Shadow tools
- (X) SSAO / HBAO / GTAO / RTAO / 任何 AO
- (X) Volumetric Light Beams（NiloPT 內建 Ray-Traced Volumetric Light Beams，已支援 cookies / shadows / occlusion）
- (X) 任何僅用於改善 URP rasterization 光照的工具

## NiloToon 原生整合
[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 角色可在 path tracing 的世界中正確渲染。
- NiloToon 角色會投射 path-traced shadows，包含布料產生的半透明多層陰影。
- NiloToon 角色也會正確出現在 path-traced 反射與折射中。
- NiloToon 角色的 emissive material 也是真正的光源。
- NiloPT 依然完整支援 NiloToon 的所有功能。照常使用 NiloToon 的 material、scripts、Volume 等即可，在 path tracing 中同樣正常運作。

## 支援的 Unity 版本 / GPU / shaders
**支援的 Unity 版本：** 6.0 / 6.3 / 6.7 (Beta)\
**平台：** Windows（DirectX 12）\
**支援的 GPU：** VRAM 16 GB 以上的所有 NVIDIA RTX GPU（例如 RTX 4070 Ti SUPER、RTX 5090）\
**支援的 shaders：**
- [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample)
- 所有官方 URP shaders（Lit / Complex Lit / Unlit / Particle / VFX Graph / Decal 等）
- 自訂 Shader Graph shaders
- Amplify Shader Editor (ASE) shaders

*不支援的 shaders，例如 Asset Store 中手寫的 vertex/fragment object shaders，會在 path tracing 中以近似方式渲染。*

*Post-processing shaders / non-object shaders 不受 NiloPT 影響，仍會照常運作。*

## 取得 NiloPT
- **[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 使用者：** 請寄信至 [nilotoon@gmail.com](mailto:nilotoon@gmail.com) 取得 NiloPT 最新資訊。提供您或所屬公司參與製作的 NiloToon 影片連結（MV、演唱會、3D Live 等），可大幅增加取得 NiloPT Closed Beta 資格的機會。
- **公開販售：** 詳情將於 2026 年內公布。

## 使用者作品 / 圖庫

### [청백가요대전2] ATEEZ - WONDERLAND l 구슬요 X 양도끼 X 여르미 X 힌콕 COVERㅣ♬ Symphony No.9 “From The Wonderland”ㅣ8K
- [8K 完整 MV](https://youtu.be/9nlSDtqcS-Q)
- [幕後製作](https://youtu.be/vfMJ43fT3os)

[![UserCreation1](images/preview/NiloPT_UserCreation1.webp)](images/full/NiloPT_UserCreation1.png?raw=true)
[![UserCreation2](images/preview/NiloPT_UserCreation2.webp)](images/full/NiloPT_UserCreation2.png?raw=true)
[![UserCreation3](images/preview/NiloPT_UserCreation3.webp)](images/full/NiloPT_UserCreation3.png?raw=true)
[![UserCreation4](images/preview/NiloPT_UserCreation4.webp)](images/full/NiloPT_UserCreation4.png?raw=true)
[![UserCreation5](images/preview/NiloPT_UserCreation5.webp)](images/full/NiloPT_UserCreation5.png?raw=true)
[![UserCreation6](images/preview/NiloPT_UserCreation6.webp)](images/full/NiloPT_UserCreation6.png?raw=true)
[![UserCreation7](images/preview/NiloPT_UserCreation7.webp)](images/full/NiloPT_UserCreation7.png?raw=true)
[![UserCreation8](images/preview/NiloPT_UserCreation8.webp)](images/full/NiloPT_UserCreation8.png?raw=true)
[![UserCreation9](images/preview/NiloPT_UserCreation9.webp)](images/full/NiloPT_UserCreation9.png?raw=true)
[![UserCreation10](images/preview/NiloPT_UserCreation10.webp)](images/full/NiloPT_UserCreation10.png?raw=true)
[![UserCreation11](images/preview/NiloPT_UserCreation11.webp)](images/full/NiloPT_UserCreation11.png?raw=true)
[![UserCreation12](images/preview/NiloPT_UserCreation12.webp)](images/full/NiloPT_UserCreation12.png?raw=true)
[![UserCreation13](images/preview/NiloPT_UserCreation13.webp)](images/full/NiloPT_UserCreation13.png?raw=true)
[![UserCreation14](images/preview/NiloPT_UserCreation14.webp)](images/full/NiloPT_UserCreation14.png?raw=true)
[![UserCreation57](images/preview/NiloPT_UserCreation57.webp)](images/full/NiloPT_UserCreation57.png?raw=true)
[![UserCreation15](images/preview/NiloPT_UserCreation15.webp)](images/full/NiloPT_UserCreation15.png?raw=true)

### [8k] BTS - FAKE LOVE (Cover) 크앙희, im미오 | 청백가요대전2
- [8K 完整 MV](https://youtu.be/t_yeGLrhi6Q)
- [幕後製作](https://youtu.be/I0l9cNORIpM)

[![UserCreation16](images/preview/NiloPT_UserCreation16.webp)](images/full/NiloPT_UserCreation16.png?raw=true)
[![UserCreation17](images/preview/NiloPT_UserCreation17.webp)](images/full/NiloPT_UserCreation17.png?raw=true)
[![UserCreation18](images/preview/NiloPT_UserCreation18.webp)](images/full/NiloPT_UserCreation18.png?raw=true)
[![UserCreation19](images/preview/NiloPT_UserCreation19.webp)](images/full/NiloPT_UserCreation19.png?raw=true)
[![UserCreation20](images/preview/NiloPT_UserCreation20.webp)](images/full/NiloPT_UserCreation20.png?raw=true)
[![UserCreation21](images/preview/NiloPT_UserCreation21.webp)](images/full/NiloPT_UserCreation21.png?raw=true)
[![UserCreation22](images/preview/NiloPT_UserCreation22.webp)](images/full/NiloPT_UserCreation22.png?raw=true)
[![UserCreation23](images/preview/NiloPT_UserCreation23.webp)](images/full/NiloPT_UserCreation23.png?raw=true)
[![UserCreation24](images/preview/NiloPT_UserCreation24.webp)](images/full/NiloPT_UserCreation24.png?raw=true)
[![UserCreation25](images/preview/NiloPT_UserCreation25.webp)](images/full/NiloPT_UserCreation25.png?raw=true)
[![UserCreation26](images/preview/NiloPT_UserCreation26.webp)](images/full/NiloPT_UserCreation26.png?raw=true)
[![UserCreation27](images/preview/NiloPT_UserCreation27.webp)](images/full/NiloPT_UserCreation27.png?raw=true)
[![UserCreation28](images/preview/NiloPT_UserCreation28.webp)](images/full/NiloPT_UserCreation28.png?raw=true)
[![UserCreation29](images/preview/NiloPT_UserCreation29.webp)](images/full/NiloPT_UserCreation29.png?raw=true)
[![UserCreation30](images/preview/NiloPT_UserCreation30.webp)](images/full/NiloPT_UserCreation30.png?raw=true)

### [8K] KISS OF LIFE(키스 오브 라이프) - Nobody Knows │COVER BY 따린 & 마냥 [청백가요대전2]
- [8K 完整 MV](https://youtu.be/FVIbkuZhtq0)
- [幕後製作](https://youtu.be/tb0aHot0VwQ)

[![UserCreation31](images/preview/NiloPT_UserCreation31.webp)](images/full/NiloPT_UserCreation31.png?raw=true)
[![UserCreation32](images/preview/NiloPT_UserCreation32.webp)](images/full/NiloPT_UserCreation32.png?raw=true)
[![UserCreation33](images/preview/NiloPT_UserCreation33.webp)](images/full/NiloPT_UserCreation33.png?raw=true)
[![UserCreation34](images/preview/NiloPT_UserCreation34.webp)](images/full/NiloPT_UserCreation34.png?raw=true)
[![UserCreation35](images/preview/NiloPT_UserCreation35.webp)](images/full/NiloPT_UserCreation35.png?raw=true)
[![UserCreation36](images/preview/NiloPT_UserCreation36.webp)](images/full/NiloPT_UserCreation36.png?raw=true)
[![UserCreation37](images/preview/NiloPT_UserCreation37.webp)](images/full/NiloPT_UserCreation37.png?raw=true)
[![UserCreation38](images/preview/NiloPT_UserCreation38.webp)](images/full/NiloPT_UserCreation38.png?raw=true)
[![UserCreation39](images/preview/NiloPT_UserCreation39.webp)](images/full/NiloPT_UserCreation39.png?raw=true)
[![UserCreation40](images/preview/NiloPT_UserCreation40.webp)](images/full/NiloPT_UserCreation40.png?raw=true)
[![UserCreation41](images/preview/NiloPT_UserCreation41.webp)](images/full/NiloPT_UserCreation41.png?raw=true)
[![UserCreation42](images/preview/NiloPT_UserCreation42.webp)](images/full/NiloPT_UserCreation42.png?raw=true)
[![UserCreation43](images/preview/NiloPT_UserCreation43.webp)](images/full/NiloPT_UserCreation43.png?raw=true)

### [8K] 빅스(VIXX) - 도원경(桃源境) Cover by 민결희 랑코 재리포터 성기사샬롯 | 청백가요대전2
- [8K 完整 MV](https://youtu.be/iq7ACdJfv8U)
- [幕後製作](https://youtu.be/IbrFmMFtYuQ)

[![UserCreation44](images/preview/NiloPT_UserCreation44.webp)](images/full/NiloPT_UserCreation44.png?raw=true)
[![UserCreation45](images/preview/NiloPT_UserCreation45.webp)](images/full/NiloPT_UserCreation45.png?raw=true)
[![UserCreation46](images/preview/NiloPT_UserCreation46.webp)](images/full/NiloPT_UserCreation46.png?raw=true)
[![UserCreation47](images/preview/NiloPT_UserCreation47.webp)](images/full/NiloPT_UserCreation47.png?raw=true)
[![UserCreation48](images/preview/NiloPT_UserCreation48.webp)](images/full/NiloPT_UserCreation48.png?raw=true)
[![UserCreation49](images/preview/NiloPT_UserCreation49.webp)](images/full/NiloPT_UserCreation49.png?raw=true)
[![UserCreation50](images/preview/NiloPT_UserCreation50.webp)](images/full/NiloPT_UserCreation50.png?raw=true)
[![UserCreation51](images/preview/NiloPT_UserCreation51.webp)](images/full/NiloPT_UserCreation51.png?raw=true)
[![UserCreation52](images/preview/NiloPT_UserCreation52.webp)](images/full/NiloPT_UserCreation52.png?raw=true)
[![UserCreation53](images/preview/NiloPT_UserCreation53.webp)](images/full/NiloPT_UserCreation53.png?raw=true)
[![UserCreation54](images/preview/NiloPT_UserCreation54.webp)](images/full/NiloPT_UserCreation54.png?raw=true)
[![UserCreation55](images/preview/NiloPT_UserCreation55.webp)](images/full/NiloPT_UserCreation55.png?raw=true)
[![UserCreation56](images/preview/NiloPT_UserCreation56.webp)](images/full/NiloPT_UserCreation56.png?raw=true)

### [8k] 야생화 - 미현영 (Cover) | 청백가요대전2
- [8K 完整 MV](https://youtu.be/U4a0Vj2BxVY)
- [幕後製作](https://youtu.be/oPj9WcI-GQM)

[![UserCreation58](images/preview/NiloPT_UserCreation58.webp)](images/full/NiloPT_UserCreation58.png?raw=true)
[![UserCreation59](images/preview/NiloPT_UserCreation59.webp)](images/full/NiloPT_UserCreation59.png?raw=true)
[![UserCreation60](images/preview/NiloPT_UserCreation60.webp)](images/full/NiloPT_UserCreation60.png?raw=true)
[![UserCreation61](images/preview/NiloPT_UserCreation61.webp)](images/full/NiloPT_UserCreation61.png?raw=true)
[![UserCreation62](images/preview/NiloPT_UserCreation62.webp)](images/full/NiloPT_UserCreation62.png?raw=true)
[![UserCreation63](images/preview/NiloPT_UserCreation63.webp)](images/full/NiloPT_UserCreation63.png?raw=true)
[![UserCreation64](images/preview/NiloPT_UserCreation64.webp)](images/full/NiloPT_UserCreation64.png?raw=true)
[![UserCreation65](images/preview/NiloPT_UserCreation65.webp)](images/full/NiloPT_UserCreation65.png?raw=true)
[![UserCreation66](images/preview/NiloPT_UserCreation66.webp)](images/full/NiloPT_UserCreation66.png?raw=true)
[![UserCreation67](images/preview/NiloPT_UserCreation67.webp)](images/full/NiloPT_UserCreation67.png?raw=true)
[![UserCreation68](images/preview/NiloPT_UserCreation68.webp)](images/full/NiloPT_UserCreation68.png?raw=true)
[![UserCreation69](images/preview/NiloPT_UserCreation69.webp)](images/full/NiloPT_UserCreation69.png?raw=true)

### [청백가요대전2] 윤이제 (Eze) - 어떻게 사랑이 그래요 fr.이승환 │COVER
- [8K 完整 MV](https://youtu.be/wgxyj_5rET8)
- [幕後製作](https://youtu.be/jjd66ms8jbA)

[![UserCreation70](images/preview/NiloPT_UserCreation70.webp)](images/full/NiloPT_UserCreation70.png?raw=true)
[![UserCreation71](images/preview/NiloPT_UserCreation71.webp)](images/full/NiloPT_UserCreation71.png?raw=true)
[![UserCreation72](images/preview/NiloPT_UserCreation72.webp)](images/full/NiloPT_UserCreation72.png?raw=true)
[![UserCreation73](images/preview/NiloPT_UserCreation73.webp)](images/full/NiloPT_UserCreation73.png?raw=true)
[![UserCreation74](images/preview/NiloPT_UserCreation74.webp)](images/full/NiloPT_UserCreation74.png?raw=true)
[![UserCreation75](images/preview/NiloPT_UserCreation75.webp)](images/full/NiloPT_UserCreation75.png?raw=true)
[![UserCreation76](images/preview/NiloPT_UserCreation76.webp)](images/full/NiloPT_UserCreation76.png?raw=true)
[![UserCreation77](images/preview/NiloPT_UserCreation77.webp)](images/full/NiloPT_UserCreation77.png?raw=true)
[![UserCreation78](images/preview/NiloPT_UserCreation78.webp)](images/full/NiloPT_UserCreation78.png?raw=true)
[![UserCreation79](images/preview/NiloPT_UserCreation79.webp)](images/full/NiloPT_UserCreation79.png?raw=true)
[![UserCreation80](images/preview/NiloPT_UserCreation80.webp)](images/full/NiloPT_UserCreation80.png?raw=true)
[![UserCreation81](images/preview/NiloPT_UserCreation81.webp)](images/full/NiloPT_UserCreation81.png?raw=true)
[![UserCreation82](images/preview/NiloPT_UserCreation82.webp)](images/full/NiloPT_UserCreation82.png?raw=true)
[![UserCreation83](images/preview/NiloPT_UserCreation83.webp)](images/full/NiloPT_UserCreation83.png?raw=true)
[![UserCreation85](images/preview/NiloPT_UserCreation85.webp)](images/full/NiloPT_UserCreation85.png?raw=true)
[![UserCreation86](images/preview/NiloPT_UserCreation86.webp)](images/full/NiloPT_UserCreation86.png?raw=true)
[![UserCreation87](images/preview/NiloPT_UserCreation87.webp)](images/full/NiloPT_UserCreation87.png?raw=true)
[![UserCreation88](images/preview/NiloPT_UserCreation88.webp)](images/full/NiloPT_UserCreation88.png?raw=true)
[![UserCreation89](images/preview/NiloPT_UserCreation89.webp)](images/full/NiloPT_UserCreation89.png?raw=true)

### 하데스 HADES (https://www.youtube.com/@HADES_offi)
- [키마 (KYMA) - '어린 나 (Little Me)' Official MV](https://www.youtube.com/watch?v=paCZO7G3YKE)

[![UserCreation90](images/preview/NiloPT_UserCreation90.webp)](images/full/NiloPT_UserCreation90.png?raw=true)
[![UserCreation91](images/preview/NiloPT_UserCreation91.webp)](images/full/NiloPT_UserCreation91.png?raw=true)
[![UserCreation92](images/preview/NiloPT_UserCreation92.webp)](images/full/NiloPT_UserCreation92.png?raw=true)
[![UserCreation93](images/preview/NiloPT_UserCreation93.webp)](images/full/NiloPT_UserCreation93.png?raw=true)
[![UserCreation94](images/preview/NiloPT_UserCreation94.webp)](images/full/NiloPT_UserCreation94.png?raw=true)
[![UserCreation95](images/preview/NiloPT_UserCreation95.webp)](images/full/NiloPT_UserCreation95.png?raw=true)
[![UserCreation96](images/preview/NiloPT_UserCreation96.webp)](images/full/NiloPT_UserCreation96.png?raw=true)
[![UserCreation97](images/preview/NiloPT_UserCreation97.webp)](images/full/NiloPT_UserCreation97.png?raw=true)
[![UserCreation98](images/preview/NiloPT_UserCreation98.webp)](images/full/NiloPT_UserCreation98.png?raw=true)
[![UserCreation99](images/preview/NiloPT_UserCreation99.webp)](images/full/NiloPT_UserCreation99.png?raw=true)
[![UserCreation100](images/preview/NiloPT_UserCreation100.webp)](images/full/NiloPT_UserCreation100.png?raw=true)

*NiloPathTracing 為獨立產品，與 Unity Technologies 或 NVIDIA 無關聯，亦未獲其背書。Unity、URP、RTX、DLSS 與 DirectX 為其各自所有者的商標。*
