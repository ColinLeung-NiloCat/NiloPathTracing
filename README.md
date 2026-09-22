[English](README.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [繁體中文](README.zh-Hant.md) | [简体中文](README.zh-Hans.md)

# NiloPathTracing (NiloPT)
- RTX Real-Time Path Tracing + DLSS Ray Reconstruction. Next-gen renderer for Unity URP.
- One-click setup, next-gen lighting instantly: import the unitypackage, click once, and path tracing is running within seconds. True plug and play.
- No learning curve. No edits to scene assets are required.
- Native [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) character support inside the path tracer.
- Built for music videos (MVs), 3D Live, concerts and virtual production. A new era for Unity lighting, made for the VTuber industry.
- NiloPT videos: [MV1](https://youtu.be/9nlSDtqcS-Q) / [MV2](https://youtu.be/t_yeGLrhi6Q) / [MV3](https://youtu.be/FVIbkuZhtq0) / [MV4](https://youtu.be/iq7ACdJfv8U) / [MV5](https://youtu.be/U4a0Vj2BxVY) / [MV6](https://youtu.be/wgxyj_5rET8) / [MV7](https://www.youtube.com/watch?v=paCZO7G3YKE) / [PView1](https://youtu.be/vfMJ43fT3os) / [PView2](https://youtu.be/tb0aHot0VwQ) / [PView3](https://youtu.be/I0l9cNORIpM)

## NiloPT ON/OFF (One-click)
[![Banner6](images/preview/NiloPT_Banner6.webp)](images/full/NiloPT_Banner6.webp?raw=true)
[![Banner1](images/preview/NiloPT_Banner1.webp)](images/full/NiloPT_Banner1.webp?raw=true)
[![Banner2](images/preview/NiloPT_Banner2.webp)](images/full/NiloPT_Banner2.webp?raw=true)
[![Banner3](images/preview/NiloPT_Banner3.webp)](images/full/NiloPT_Banner3.webp?raw=true)
[![Banner4](images/preview/NiloPT_Banner4.webp)](images/full/NiloPT_Banner4.webp?raw=true)
[![Banner5](images/preview/NiloPT_Banner5.webp)](images/full/NiloPT_Banner5.webp?raw=true)

## One click = all setup done
One click replaces the URP renderer's rasterization with NiloPathTracing.
- No learning required: import the NiloPT unitypackage > one-click auto-install > path tracing is running immediately.
- No edits to materials/lights/scenes/prefabs/volumes/meshes... are required.
- No URP / UnityEngine source code edits required. It works immediately in existing URP projects. No hacks or workarounds needed.
- No baking required. All path-traced rendering is fully dynamic in real time: no more painful lightmap baking, no more annoying placement of light probes / reflection probes.
- No other lighting assets required. NiloPT replaces most of the existing rasterization lighting tools from URP / Asset Store / GitHub (see below).

## One path tracer replaces the whole URP rasterization lighting stack
- The skybox and all emissive materials (Mesh/Skinned Mesh/Particle/VFX Graph/Decal...) are real light sources that will light the scene, including those using a RenderTexture that plays video (e.g. a big emissive monitor on a concert stage can light the whole scene dynamically by playing a video).
- Surface lighting uses fully path-traced shadows and occlusion instead of traditional rasterization shadow maps and AO.
- Reflections and refractions are fully path-traced in real time and affected by material properties (e.g. smoothness/metallic).

NiloPT replaces most of the existing rasterization lighting tools from URP / Asset Store / GitHub. You can forget most of the following:
- (X) Lightmaps / Light Probes / Adaptive Probe Volumes (APV)
- (X) URP Surface Cache / Screen Space Global Illumination / World Space Global Illumination
- (X) Reflection Probes (baked and real-time)
- (X) Planar Reflections / Screen Space Reflections / Ray-Traced Reflection tools
- (X) Shadow Maps / Contact Shadows / PCSS / Ray-Traced Shadow tools
- (X) SSAO / HBAO / GTAO / RTAO / any AO
- (X) Volumetric Light Beams (NiloPT has built-in Ray-Traced Volumetric Light Beams that already handle cookies / shadows / occlusion)
- (X) Any tools whose sole purpose is to improve URP rasterization lighting

## NiloToon native integration
[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) characters will render correctly in a path-traced world.
- NiloToon characters will cast path-traced shadows (including semi-transparent multi-layer shadows from cloth).
- Render NiloToon characters in path-traced reflections / refractions.
- Emissive NiloToon character materials are also real light sources.
- Everything NiloToon offers is still supported in NiloPT. Use NiloToon as usual (materials/scripts/volumes...) and expect it to work in path tracing.

## Supported Unity versions / GPUs / shaders
**Supported Unity versions:** 6.0 / 6.3 / 6.7 (Beta)  
**Platform:** Windows (DirectX 12)  
**Supported GPUs:** All NVIDIA RTX GPUs with 16 GB VRAM or more (e.g. RTX 4070 Ti SUPER, RTX 5090)  
**Supported Shaders:**  
- [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample)
- All official URP shaders (Lit / Complex Lit / Unlit / Particle / VFX Graph / Decal...)
- Custom Shader Graph shaders
- Amplify Shader Editor (ASE) shaders

*Unsupported shaders, such as hand-written vertex/fragment object shaders from the Asset Store, are approximated in path tracing.*

*Post-processing shaders / non-object shaders are not affected by NiloPT; they will work correctly as usual.*

## Get NiloPT
- **For [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) users:** Email [nilotoon@gmail.com](mailto:nilotoon@gmail.com) for the latest NiloPT info. Submitting links to NiloToon videos (MVs, concerts, 3D live performances...) that you or your company worked on will greatly increase your chances of getting access to NiloPT's Closed Beta.
- **Public purchase:** Details will be announced later in 2026.

## User creations / gallery

### [청백가요대전2] ATEEZ - WONDERLAND l 구슬요 X 양도끼 X 여르미 X 힌콕 COVERㅣ♬ Symphony No.9 “From The Wonderland”ㅣ8K
- [8K Full MV](https://youtu.be/9nlSDtqcS-Q)
- [Production View](https://youtu.be/vfMJ43fT3os)

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
- [8K Full MV](https://youtu.be/t_yeGLrhi6Q)
- [Production View](https://youtu.be/I0l9cNORIpM)

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
- [8K Full MV](https://youtu.be/FVIbkuZhtq0)
- [Production View](https://youtu.be/tb0aHot0VwQ)

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
- [8K Full MV](https://youtu.be/iq7ACdJfv8U)
- [Production View](https://youtu.be/IbrFmMFtYuQ)

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
- [8K Full MV](https://youtu.be/U4a0Vj2BxVY)
- [Production View](https://youtu.be/oPj9WcI-GQM)

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
- [8K Full MV](https://youtu.be/wgxyj_5rET8)
- [Production View](https://youtu.be/jjd66ms8jbA)

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

*NiloPathTracing is an independent product and is not affiliated with or endorsed by Unity Technologies or NVIDIA. Unity, URP, RTX, DLSS and DirectX are trademarks of their respective owners.*
