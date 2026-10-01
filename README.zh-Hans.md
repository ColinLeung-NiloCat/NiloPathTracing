[English](README.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [繁體中文](README.zh-Hant.md) | [简体中文](README.zh-Hans.md)

# NiloPathTracing (NiloPT)
- RTX Real-Time Path Tracing + DLSS Ray Reconstruction。Unity URP 的次世代 renderer。
- 一键设置，立即获得次世代光照：导入 unitypackage、点击一下，数秒内 path tracing 就开始运行。真正即插即用。
- 零学习成本，也无需修改场景资产。
- 原生支持 [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 角色的 path tracing 渲染。
- 专为音乐视频（MV）、3D Live、演唱会与虚拟制作打造。为 VTuber 行业开启 Unity 光照的新时代。
- NiloPT 视频：[MV1](https://youtu.be/9nlSDtqcS-Q) / [MV2](https://youtu.be/t_yeGLrhi6Q) / [MV3](https://youtu.be/FVIbkuZhtq0) / [MV4](https://youtu.be/iq7ACdJfv8U) / [MV5](https://youtu.be/U4a0Vj2BxVY) / [MV6](https://youtu.be/wgxyj_5rET8) / [MV7](https://www.youtube.com/watch?v=paCZO7G3YKE) / [PView1](https://youtu.be/vfMJ43fT3os) / [PView2](https://youtu.be/tb0aHot0VwQ) / [PView3](https://youtu.be/I0l9cNORIpM)

## 一键开启 / 关闭 NiloPT
[![Banner7](images/preview/NiloPT_Banner7.avif)](images/full/NiloPT_Banner7.avif?raw=true)
[![Banner6](images/preview/NiloPT_Banner6.avif)](images/full/NiloPT_Banner6.avif?raw=true)
[![Banner1](images/preview/NiloPT_Banner1.avif)](images/full/NiloPT_Banner1.avif?raw=true)
[![Banner2](images/preview/NiloPT_Banner2.avif)](images/full/NiloPT_Banner2.avif?raw=true)
[![Banner3](images/preview/NiloPT_Banner3.avif)](images/full/NiloPT_Banner3.avif?raw=true)
[![Banner4](images/preview/NiloPT_Banner4.avif)](images/full/NiloPT_Banner4.avif?raw=true)
[![Banner5](images/preview/NiloPT_Banner5.avif)](images/full/NiloPT_Banner5.avif?raw=true)

## 一键完成所有设置
只需点击一下，即可将 URP renderer 的 rasterization 渲染替换为 NiloPathTracing。
- 无需学习：导入 NiloPT unitypackage > 一键自动安装 > path tracing 立即开始运行。
- 无需修改 material、灯光、场景、Prefab、Volume、mesh 等资产。
- 无需修改 URP / UnityEngine 源代码。现有的 URP 项目即可立即使用，无需任何 hack 或 workaround。
- 无需 baking。所有 path-traced rendering 都是完全实时、动态的，不再需要繁琐的 lightmap baking，也不必费心配置 light probes 或 reflection probes。
- 无需其他光照资产。NiloPT 可取代 URP / Asset Store / GitHub 中大部分现有的 rasterization 光照工具（详见下文）。

## 一个 path tracer 取代整套 URP rasterization 光照系统
- skybox 与所有 emissive material（Mesh、Skinned Mesh、Particle、VFX Graph、Decal 等）都是真正照亮场景的光源，也包含使用 RenderTexture 播放视频的 material。例如演唱会舞台上的大型发光屏幕，可通过播放视频动态照亮整个场景。
- 表面光照全面改用 path-traced shadows 与 occlusion，取代传统的 rasterization shadow maps 及 AO。
- 反射与折射全程使用实时 path tracing，并受 smoothness、metallic 等 material 属性影响。

NiloPT 可取代 URP / Asset Store / GitHub 中大部分现有的 rasterization 光照工具。以下大部分项目都不再需要：
- (X) Lightmaps / Light Probes / Adaptive Probe Volumes (APV)
- (X) URP Surface Cache / Screen Space Global Illumination / World Space Global Illumination
- (X) Reflection Probes（baked 与 real-time）
- (X) Planar Reflections / Screen Space Reflections / Ray-Traced Reflection tools
- (X) Shadow Maps / Contact Shadows / PCSS / Ray-Traced Shadow tools
- (X) SSAO / HBAO / GTAO / RTAO / 任何 AO
- (X) Volumetric Light Beams（NiloPT 内置 Ray-Traced Volumetric Light Beams，已支持 cookies / shadows / occlusion）
- (X) 任何仅用于改善 URP rasterization 光照的工具

## NiloToon 原生集成
[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 角色可在 path tracing 的世界中正确渲染。
- NiloToon 角色会投射 path-traced shadows，包含布料产生的半透明多层阴影。
- NiloToon 角色也会正确出现在 path-traced 反射与折射中。
- NiloToon 角色的 emissive material 也是真正的光源。
- NiloPT 依然完整支持 NiloToon 的所有功能。照常使用 NiloToon 的 material、scripts、Volume 等即可，在 path tracing 中同样正常运行。

## 支持的 Unity 版本 / GPU / shaders
**支持的 Unity 版本：** 6.0 / 6.3 / 6.7 (Beta)\
**平台：** Windows（DirectX 12）\
**支持的 GPU：** 显存 16 GB 以上的所有 NVIDIA RTX GPU（例如 RTX 4070 Ti SUPER、RTX 5090）\
**支持的 shaders：**
- [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample)
- 所有官方 URP shaders（Lit / Complex Lit / Unlit / Particle / VFX Graph / Decal 等）
- 自定义 Shader Graph shaders
- Amplify Shader Editor (ASE) shaders

*不支持的 shaders，例如 Asset Store 中手写的 vertex/fragment object shaders，会在 path tracing 中以近似方式渲染。*

*Post-processing shaders / non-object shaders 不受 NiloPT 影响，仍会照常运行。*

## 获取 NiloPT
- **[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 用户：** 请发送邮件至 [nilotoon@gmail.com](mailto:nilotoon@gmail.com) 获取 NiloPT 最新信息。提供您或所属公司参与制作的 NiloToon 视频链接（MV、演唱会、3D Live 等），可大幅增加获取 NiloPT 内测资格的机会。
- **公开销售：** 详情将于 2026 年内公布。

## 用户作品 / 图库

### [청백가요대전2] ATEEZ - WONDERLAND l 구슬요 X 양도끼 X 여르미 X 힌콕 COVERㅣ♬ Symphony No.9 “From The Wonderland”ㅣ8K
- [8K 完整 MV](https://youtu.be/9nlSDtqcS-Q)
- [幕后制作](https://youtu.be/vfMJ43fT3os)

[![UserCreation1](images/preview/NiloPT_UserCreation1.avif)](images/full/NiloPT_UserCreation1.png?raw=true)
[![UserCreation2](images/preview/NiloPT_UserCreation2.avif)](images/full/NiloPT_UserCreation2.png?raw=true)
[![UserCreation3](images/preview/NiloPT_UserCreation3.avif)](images/full/NiloPT_UserCreation3.png?raw=true)
[![UserCreation4](images/preview/NiloPT_UserCreation4.avif)](images/full/NiloPT_UserCreation4.png?raw=true)
[![UserCreation5](images/preview/NiloPT_UserCreation5.avif)](images/full/NiloPT_UserCreation5.png?raw=true)
[![UserCreation6](images/preview/NiloPT_UserCreation6.avif)](images/full/NiloPT_UserCreation6.png?raw=true)
[![UserCreation7](images/preview/NiloPT_UserCreation7.avif)](images/full/NiloPT_UserCreation7.png?raw=true)
[![UserCreation8](images/preview/NiloPT_UserCreation8.avif)](images/full/NiloPT_UserCreation8.png?raw=true)
[![UserCreation9](images/preview/NiloPT_UserCreation9.avif)](images/full/NiloPT_UserCreation9.png?raw=true)
[![UserCreation10](images/preview/NiloPT_UserCreation10.avif)](images/full/NiloPT_UserCreation10.png?raw=true)
[![UserCreation11](images/preview/NiloPT_UserCreation11.avif)](images/full/NiloPT_UserCreation11.png?raw=true)
[![UserCreation12](images/preview/NiloPT_UserCreation12.avif)](images/full/NiloPT_UserCreation12.png?raw=true)
[![UserCreation13](images/preview/NiloPT_UserCreation13.avif)](images/full/NiloPT_UserCreation13.png?raw=true)
[![UserCreation14](images/preview/NiloPT_UserCreation14.avif)](images/full/NiloPT_UserCreation14.png?raw=true)
[![UserCreation57](images/preview/NiloPT_UserCreation57.avif)](images/full/NiloPT_UserCreation57.png?raw=true)
[![UserCreation15](images/preview/NiloPT_UserCreation15.avif)](images/full/NiloPT_UserCreation15.png?raw=true)

### [8k] BTS - FAKE LOVE (Cover) 크앙희, im미오 | 청백가요대전2
- [8K 完整 MV](https://youtu.be/t_yeGLrhi6Q)
- [幕后制作](https://youtu.be/I0l9cNORIpM)

[![UserCreation16](images/preview/NiloPT_UserCreation16.avif)](images/full/NiloPT_UserCreation16.png?raw=true)
[![UserCreation17](images/preview/NiloPT_UserCreation17.avif)](images/full/NiloPT_UserCreation17.png?raw=true)
[![UserCreation18](images/preview/NiloPT_UserCreation18.avif)](images/full/NiloPT_UserCreation18.png?raw=true)
[![UserCreation19](images/preview/NiloPT_UserCreation19.avif)](images/full/NiloPT_UserCreation19.png?raw=true)
[![UserCreation20](images/preview/NiloPT_UserCreation20.avif)](images/full/NiloPT_UserCreation20.png?raw=true)
[![UserCreation21](images/preview/NiloPT_UserCreation21.avif)](images/full/NiloPT_UserCreation21.png?raw=true)
[![UserCreation22](images/preview/NiloPT_UserCreation22.avif)](images/full/NiloPT_UserCreation22.png?raw=true)
[![UserCreation23](images/preview/NiloPT_UserCreation23.avif)](images/full/NiloPT_UserCreation23.png?raw=true)
[![UserCreation24](images/preview/NiloPT_UserCreation24.avif)](images/full/NiloPT_UserCreation24.png?raw=true)
[![UserCreation25](images/preview/NiloPT_UserCreation25.avif)](images/full/NiloPT_UserCreation25.png?raw=true)
[![UserCreation26](images/preview/NiloPT_UserCreation26.avif)](images/full/NiloPT_UserCreation26.png?raw=true)
[![UserCreation27](images/preview/NiloPT_UserCreation27.avif)](images/full/NiloPT_UserCreation27.png?raw=true)
[![UserCreation28](images/preview/NiloPT_UserCreation28.avif)](images/full/NiloPT_UserCreation28.png?raw=true)
[![UserCreation29](images/preview/NiloPT_UserCreation29.avif)](images/full/NiloPT_UserCreation29.png?raw=true)
[![UserCreation30](images/preview/NiloPT_UserCreation30.avif)](images/full/NiloPT_UserCreation30.png?raw=true)

### [8K] KISS OF LIFE(키스 오브 라이프) - Nobody Knows │COVER BY 따린 & 마냥 [청백가요대전2]
- [8K 完整 MV](https://youtu.be/FVIbkuZhtq0)
- [幕后制作](https://youtu.be/tb0aHot0VwQ)

[![UserCreation31](images/preview/NiloPT_UserCreation31.avif)](images/full/NiloPT_UserCreation31.png?raw=true)
[![UserCreation32](images/preview/NiloPT_UserCreation32.avif)](images/full/NiloPT_UserCreation32.png?raw=true)
[![UserCreation33](images/preview/NiloPT_UserCreation33.avif)](images/full/NiloPT_UserCreation33.png?raw=true)
[![UserCreation34](images/preview/NiloPT_UserCreation34.avif)](images/full/NiloPT_UserCreation34.png?raw=true)
[![UserCreation35](images/preview/NiloPT_UserCreation35.avif)](images/full/NiloPT_UserCreation35.png?raw=true)
[![UserCreation36](images/preview/NiloPT_UserCreation36.avif)](images/full/NiloPT_UserCreation36.png?raw=true)
[![UserCreation37](images/preview/NiloPT_UserCreation37.avif)](images/full/NiloPT_UserCreation37.png?raw=true)
[![UserCreation38](images/preview/NiloPT_UserCreation38.avif)](images/full/NiloPT_UserCreation38.png?raw=true)
[![UserCreation39](images/preview/NiloPT_UserCreation39.avif)](images/full/NiloPT_UserCreation39.png?raw=true)
[![UserCreation40](images/preview/NiloPT_UserCreation40.avif)](images/full/NiloPT_UserCreation40.png?raw=true)
[![UserCreation41](images/preview/NiloPT_UserCreation41.avif)](images/full/NiloPT_UserCreation41.png?raw=true)
[![UserCreation42](images/preview/NiloPT_UserCreation42.avif)](images/full/NiloPT_UserCreation42.png?raw=true)
[![UserCreation43](images/preview/NiloPT_UserCreation43.avif)](images/full/NiloPT_UserCreation43.png?raw=true)

### [8K] 빅스(VIXX) - 도원경(桃源境) Cover by 민결희 랑코 재리포터 성기사샬롯 | 청백가요대전2
- [8K 完整 MV](https://youtu.be/iq7ACdJfv8U)
- [幕后制作](https://youtu.be/IbrFmMFtYuQ)

[![UserCreation44](images/preview/NiloPT_UserCreation44.avif)](images/full/NiloPT_UserCreation44.png?raw=true)
[![UserCreation45](images/preview/NiloPT_UserCreation45.avif)](images/full/NiloPT_UserCreation45.png?raw=true)
[![UserCreation46](images/preview/NiloPT_UserCreation46.avif)](images/full/NiloPT_UserCreation46.png?raw=true)
[![UserCreation47](images/preview/NiloPT_UserCreation47.avif)](images/full/NiloPT_UserCreation47.png?raw=true)
[![UserCreation48](images/preview/NiloPT_UserCreation48.avif)](images/full/NiloPT_UserCreation48.png?raw=true)
[![UserCreation49](images/preview/NiloPT_UserCreation49.avif)](images/full/NiloPT_UserCreation49.png?raw=true)
[![UserCreation50](images/preview/NiloPT_UserCreation50.avif)](images/full/NiloPT_UserCreation50.png?raw=true)
[![UserCreation51](images/preview/NiloPT_UserCreation51.avif)](images/full/NiloPT_UserCreation51.png?raw=true)
[![UserCreation52](images/preview/NiloPT_UserCreation52.avif)](images/full/NiloPT_UserCreation52.png?raw=true)
[![UserCreation53](images/preview/NiloPT_UserCreation53.avif)](images/full/NiloPT_UserCreation53.png?raw=true)
[![UserCreation54](images/preview/NiloPT_UserCreation54.avif)](images/full/NiloPT_UserCreation54.png?raw=true)
[![UserCreation55](images/preview/NiloPT_UserCreation55.avif)](images/full/NiloPT_UserCreation55.png?raw=true)
[![UserCreation56](images/preview/NiloPT_UserCreation56.avif)](images/full/NiloPT_UserCreation56.png?raw=true)

### [8k] 야생화 - 미현영 (Cover) | 청백가요대전2
- [8K 完整 MV](https://youtu.be/U4a0Vj2BxVY)
- [幕后制作](https://youtu.be/oPj9WcI-GQM)

[![UserCreation58](images/preview/NiloPT_UserCreation58.avif)](images/full/NiloPT_UserCreation58.png?raw=true)
[![UserCreation59](images/preview/NiloPT_UserCreation59.avif)](images/full/NiloPT_UserCreation59.png?raw=true)
[![UserCreation60](images/preview/NiloPT_UserCreation60.avif)](images/full/NiloPT_UserCreation60.png?raw=true)
[![UserCreation61](images/preview/NiloPT_UserCreation61.avif)](images/full/NiloPT_UserCreation61.png?raw=true)
[![UserCreation62](images/preview/NiloPT_UserCreation62.avif)](images/full/NiloPT_UserCreation62.png?raw=true)
[![UserCreation63](images/preview/NiloPT_UserCreation63.avif)](images/full/NiloPT_UserCreation63.png?raw=true)
[![UserCreation64](images/preview/NiloPT_UserCreation64.avif)](images/full/NiloPT_UserCreation64.png?raw=true)
[![UserCreation65](images/preview/NiloPT_UserCreation65.avif)](images/full/NiloPT_UserCreation65.png?raw=true)
[![UserCreation66](images/preview/NiloPT_UserCreation66.avif)](images/full/NiloPT_UserCreation66.png?raw=true)
[![UserCreation67](images/preview/NiloPT_UserCreation67.avif)](images/full/NiloPT_UserCreation67.png?raw=true)
[![UserCreation68](images/preview/NiloPT_UserCreation68.avif)](images/full/NiloPT_UserCreation68.png?raw=true)
[![UserCreation69](images/preview/NiloPT_UserCreation69.avif)](images/full/NiloPT_UserCreation69.png?raw=true)

### [청백가요대전2] 윤이제 (Eze) - 어떻게 사랑이 그래요 fr.이승환 │COVER
- [8K 完整 MV](https://youtu.be/wgxyj_5rET8)
- [幕后制作](https://youtu.be/jjd66ms8jbA)

[![UserCreation70](images/preview/NiloPT_UserCreation70.avif)](images/full/NiloPT_UserCreation70.png?raw=true)
[![UserCreation71](images/preview/NiloPT_UserCreation71.avif)](images/full/NiloPT_UserCreation71.png?raw=true)
[![UserCreation72](images/preview/NiloPT_UserCreation72.avif)](images/full/NiloPT_UserCreation72.png?raw=true)
[![UserCreation73](images/preview/NiloPT_UserCreation73.avif)](images/full/NiloPT_UserCreation73.png?raw=true)
[![UserCreation74](images/preview/NiloPT_UserCreation74.avif)](images/full/NiloPT_UserCreation74.png?raw=true)
[![UserCreation75](images/preview/NiloPT_UserCreation75.avif)](images/full/NiloPT_UserCreation75.png?raw=true)
[![UserCreation76](images/preview/NiloPT_UserCreation76.avif)](images/full/NiloPT_UserCreation76.png?raw=true)
[![UserCreation77](images/preview/NiloPT_UserCreation77.avif)](images/full/NiloPT_UserCreation77.png?raw=true)
[![UserCreation78](images/preview/NiloPT_UserCreation78.avif)](images/full/NiloPT_UserCreation78.png?raw=true)
[![UserCreation79](images/preview/NiloPT_UserCreation79.avif)](images/full/NiloPT_UserCreation79.png?raw=true)
[![UserCreation80](images/preview/NiloPT_UserCreation80.avif)](images/full/NiloPT_UserCreation80.png?raw=true)
[![UserCreation81](images/preview/NiloPT_UserCreation81.avif)](images/full/NiloPT_UserCreation81.png?raw=true)
[![UserCreation82](images/preview/NiloPT_UserCreation82.avif)](images/full/NiloPT_UserCreation82.png?raw=true)
[![UserCreation83](images/preview/NiloPT_UserCreation83.avif)](images/full/NiloPT_UserCreation83.png?raw=true)
[![UserCreation85](images/preview/NiloPT_UserCreation85.avif)](images/full/NiloPT_UserCreation85.png?raw=true)
[![UserCreation86](images/preview/NiloPT_UserCreation86.avif)](images/full/NiloPT_UserCreation86.png?raw=true)
[![UserCreation87](images/preview/NiloPT_UserCreation87.avif)](images/full/NiloPT_UserCreation87.png?raw=true)
[![UserCreation88](images/preview/NiloPT_UserCreation88.avif)](images/full/NiloPT_UserCreation88.png?raw=true)
[![UserCreation89](images/preview/NiloPT_UserCreation89.avif)](images/full/NiloPT_UserCreation89.png?raw=true)

### 하데스 HADES (https://www.youtube.com/@HADES_offi)
- [키마 (KYMA) - '어린 나 (Little Me)' Official MV](https://www.youtube.com/watch?v=paCZO7G3YKE)

[![UserCreation90](images/preview/NiloPT_UserCreation90.avif)](images/full/NiloPT_UserCreation90.png?raw=true)
[![UserCreation91](images/preview/NiloPT_UserCreation91.avif)](images/full/NiloPT_UserCreation91.png?raw=true)
[![UserCreation92](images/preview/NiloPT_UserCreation92.avif)](images/full/NiloPT_UserCreation92.png?raw=true)
[![UserCreation93](images/preview/NiloPT_UserCreation93.avif)](images/full/NiloPT_UserCreation93.png?raw=true)
[![UserCreation94](images/preview/NiloPT_UserCreation94.avif)](images/full/NiloPT_UserCreation94.png?raw=true)
[![UserCreation95](images/preview/NiloPT_UserCreation95.avif)](images/full/NiloPT_UserCreation95.png?raw=true)
[![UserCreation96](images/preview/NiloPT_UserCreation96.avif)](images/full/NiloPT_UserCreation96.png?raw=true)
[![UserCreation97](images/preview/NiloPT_UserCreation97.avif)](images/full/NiloPT_UserCreation97.png?raw=true)
[![UserCreation98](images/preview/NiloPT_UserCreation98.avif)](images/full/NiloPT_UserCreation98.png?raw=true)
[![UserCreation99](images/preview/NiloPT_UserCreation99.avif)](images/full/NiloPT_UserCreation99.png?raw=true)
[![UserCreation100](images/preview/NiloPT_UserCreation100.avif)](images/full/NiloPT_UserCreation100.png?raw=true)

*NiloPathTracing 为独立产品，与 Unity Technologies 或 NVIDIA 无关联，亦未获其背书。Unity、URP、RTX、DLSS 与 DirectX 为其各自所有者的商标。*
