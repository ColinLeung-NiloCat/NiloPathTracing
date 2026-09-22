[English](README.md) | [日本語](README.ja.md) | [한국어](README.ko.md) | [繁體中文](README.zh-Hant.md) | [简体中文](README.zh-Hans.md)

# NiloPathTracing (NiloPT)
- RTX Real-Time Path Tracing + DLSS Ray Reconstruction. Unity URP를 위한 차세대 renderer입니다.
- 클릭 한 번으로 차세대 라이팅을 바로 구현: unitypackage를 임포트하고 한 번 클릭하면 몇 초 안에 path tracing이 작동합니다. 진정한 플러그 앤 플레이입니다.
- 러닝 커브가 없습니다. 씬 에셋을 수정할 필요도 없습니다.
- [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 캐릭터를 path tracing에서 네이티브 지원.
- 뮤직비디오(MV), 3D 라이브, 콘서트, 버추얼 프로덕션을 위해 설계. VTuber 업계를 위한 Unity 라이팅의 새로운 시대를 엽니다.
- NiloPT 영상: [MV1](https://youtu.be/9nlSDtqcS-Q) / [MV2](https://youtu.be/t_yeGLrhi6Q) / [MV3](https://youtu.be/FVIbkuZhtq0) / [MV4](https://youtu.be/iq7ACdJfv8U) / [MV5](https://youtu.be/U4a0Vj2BxVY) / [MV6](https://youtu.be/wgxyj_5rET8) / [MV7](https://www.youtube.com/watch?v=paCZO7G3YKE) / [PView1](https://youtu.be/vfMJ43fT3os) / [PView2](https://youtu.be/tb0aHot0VwQ) / [PView3](https://youtu.be/I0l9cNORIpM)

## NiloPT ON/OFF (클릭 한 번)
[![Banner6](images/preview/NiloPT_Banner6.webp)](images/full/NiloPT_Banner6.webp?raw=true)
[![Banner1](images/preview/NiloPT_Banner1.webp)](images/full/NiloPT_Banner1.webp?raw=true)
[![Banner2](images/preview/NiloPT_Banner2.webp)](images/full/NiloPT_Banner2.webp?raw=true)
[![Banner3](images/preview/NiloPT_Banner3.webp)](images/full/NiloPT_Banner3.webp?raw=true)
[![Banner4](images/preview/NiloPT_Banner4.webp)](images/full/NiloPT_Banner4.webp?raw=true)
[![Banner5](images/preview/NiloPT_Banner5.webp)](images/full/NiloPT_Banner5.webp?raw=true)

## 클릭 한 번으로 모든 설정 완료
클릭 한 번으로 URP renderer의 rasterization을 NiloPathTracing으로 대체합니다.
- 학습이 필요 없습니다: NiloPT unitypackage 임포트 > 클릭 한 번으로 자동 설치 > path tracing이 즉시 작동합니다.
- material / 조명 / 씬 / Prefab / Volume / mesh 등을 수정할 필요가 없습니다.
- URP / UnityEngine 소스 코드를 수정할 필요가 없습니다. 기존 URP 프로젝트에서 즉시 작동하며, 별도의 편법이나 우회 방법도 필요하지 않습니다.
- baking이 필요 없습니다. 모든 path tracing 렌더링이 실시간으로 완전히 동적이므로, 번거로운 lightmap baking이나 light probes / reflection probes 배치가 필요 없습니다.
- 다른 라이팅 에셋이 필요 없습니다. URP / Asset Store / GitHub에 있는 기존 rasterization 라이팅 도구 대부분을 NiloPT가 대체합니다 (아래 참고).

## 하나의 path tracer로 URP rasterization 라이팅 스택 전체를 대체
- skybox와 모든 emissive material (Mesh / Skinned Mesh / Particle / VFX Graph / Decal 등)이 씬을 비추는 실제 광원이 됩니다. 동영상을 재생하는 RenderTexture를 사용하는 경우도 포함됩니다. 예를 들어 콘서트 무대의 대형 발광 모니터에서 동영상을 재생하면 씬 전체를 동적으로 비출 수 있습니다.
- 표면 라이팅에는 기존 rasterization shadow maps와 AO 대신 완전히 path tracing된 shadows와 occlusion을 사용합니다.
- 반사와 굴절은 실시간으로 완전히 path tracing되며, smoothness / metallic 같은 material properties의 영향을 받습니다.

NiloPT는 URP / Asset Store / GitHub에 있는 기존 rasterization 라이팅 도구 대부분을 대체합니다. 다음 항목 대부분을 더 이상 사용하지 않아도 됩니다.
- (X) Lightmaps / Light Probes / Adaptive Probe Volumes (APV)
- (X) URP Surface Cache / Screen Space Global Illumination / World Space Global Illumination
- (X) Reflection Probes (baked 및 실시간)
- (X) Planar Reflections / Screen Space Reflections / Ray-Traced Reflection 도구
- (X) Shadow Maps / Contact Shadows / PCSS / Ray-Traced Shadow 도구
- (X) SSAO / HBAO / GTAO / RTAO / 기타 모든 AO
- (X) Volumetric Light Beams (NiloPT에는 cookies / shadows / occlusion을 이미 지원하는 Ray-Traced Volumetric Light Beams가 내장되어 있습니다)
- (X) URP rasterization 라이팅 개선만을 목적으로 하는 모든 도구

## NiloToon 네이티브 통합
[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 캐릭터가 path tracing된 환경에서 올바르게 렌더링됩니다.
- NiloToon 캐릭터가 path tracing된 shadows를 드리웁니다. 천으로 인한 반투명 다층 shadows도 포함됩니다.
- path tracing된 반사와 굴절에도 NiloToon 캐릭터를 렌더링합니다.
- NiloToon 캐릭터의 emissive material도 실제 광원이 됩니다.
- NiloToon의 모든 기능이 NiloPT에서도 그대로 지원됩니다. materials / scripts / volumes 등을 평소처럼 사용하면 path tracing에서도 작동합니다.

## 지원 Unity 버전 / GPU / shaders
**지원 Unity 버전:** 6.0 / 6.3 / 6.7 (Beta)\
**플랫폼:** Windows (DirectX 12)\
**지원 GPU:** VRAM 16 GB 이상의 모든 NVIDIA RTX GPU (예: RTX 4070 Ti SUPER, RTX 5090)\
**지원 shaders:**
- [NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample)
- 모든 공식 URP shaders (Lit / Complex Lit / Unlit / Particle / VFX Graph / Decal 등)
- 커스텀 Shader Graph shaders
- Amplify Shader Editor (ASE) shaders

*Asset Store의 직접 작성한 vertex/fragment 오브젝트 shaders 등 지원되지 않는 shaders는 path tracing에서 근사하여 렌더링됩니다.*

*Post-processing shaders / non-object shaders는 NiloPT의 영향을 받지 않으며 기존과 동일하게 정상 작동합니다.*

## NiloPT 받는 방법
- **[NiloToon](https://github.com/ColinLeung-NiloCat/UnityURPToonLitShaderExample) 사용자:** NiloPT의 최신 정보는 [nilotoon@gmail.com](mailto:nilotoon@gmail.com)으로 문의해 주세요. 본인 또는 소속 회사가 제작에 참여한 NiloToon 영상(MV, 콘서트, 3D 라이브 등) 링크를 보내 주시면 NiloPT Closed Beta에 참여할 가능성이 크게 높아집니다.
- **일반 판매:** 자세한 내용은 2026년 중에 발표할 예정입니다.

## 사용자 작품 / 갤러리

### [청백가요대전2] ATEEZ - WONDERLAND l 구슬요 X 양도끼 X 여르미 X 힌콕 COVERㅣ♬ Symphony No.9 “From The Wonderland”ㅣ8K
- [8K 풀 MV](https://youtu.be/9nlSDtqcS-Q)
- [메이킹 영상](https://youtu.be/vfMJ43fT3os)

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
- [8K 풀 MV](https://youtu.be/t_yeGLrhi6Q)
- [메이킹 영상](https://youtu.be/I0l9cNORIpM)

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
- [8K 풀 MV](https://youtu.be/FVIbkuZhtq0)
- [메이킹 영상](https://youtu.be/tb0aHot0VwQ)

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
- [8K 풀 MV](https://youtu.be/iq7ACdJfv8U)
- [메이킹 영상](https://youtu.be/IbrFmMFtYuQ)

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
- [8K 풀 MV](https://youtu.be/U4a0Vj2BxVY)
- [메이킹 영상](https://youtu.be/oPj9WcI-GQM)

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
- [8K 풀 MV](https://youtu.be/wgxyj_5rET8)
- [메이킹 영상](https://youtu.be/jjd66ms8jbA)

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

*NiloPathTracing은 독립 제품이며 Unity Technologies 또는 NVIDIA와 제휴하거나 승인을 받지 않았습니다. Unity, URP, RTX, DLSS, DirectX는 각 소유자의 상표입니다.*
