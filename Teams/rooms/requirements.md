---
title: Requisiti per Microsoft Teams Rooms
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: Informazioni sui requisiti per il supporto di Microsoft Teams Rooms, inclusa la scelta del dispositivo, dei microfoni, degli altoparlanti, delle fotocamere e degli schermi appropriati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 361a81e4945e191bbb0443d0a73555b14a8770fb
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584377"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisiti per Microsoft Teams Rooms

Microsoft Teams Rooms scala in base a diverse dimensioni della stanza. Teams Rooms utilizzare un'ampia gamma di periferiche audio e video certificate in base alle dimensioni e all'uso della stanza. Selezionando il dispositivo e la console di base appropriati, in combinazione con microfoni, altoparlanti, fotocamere e schermi appropriati per lo spazio, è possibile distribuire Microsoft Teams Rooms in spazi di qualsiasi dimensione, da piccoli spazi rannicchiati attraverso grandi spazi per conferenze e sale riunioni.  Il set completo delle periferiche audio e video certificate che possono essere utilizzate per configurare la sala, è disponibile in [Presentazione dei dispositivi](https://products.office.com/microsoft-teams/across-devices).

In questo articolo vengono riepilogati i requisiti di configurazione e distribuzione dei dispositivi per il supporto di Microsoft Teams Rooms.

La distribuzione implica la creazione di account delle risorse e la configurazione di Teams Rooms come descritto in [Distribuire Microsoft Teams Rooms](rooms-deploy.md).

Fare riferimento a:

- [Opzioni di licenza basate sul tuo piano: Microsoft Teams Rooms](rooms-licensing.md)

> [!NOTE]
> Microsoft Teams Rooms accedere a Microsoft Teams, Skype for Business Server 2019 o Skype for Business Server 2015 e può partecipare a riunioni ospitate da uno di questi servizi.
>
> Le piattaforme precedenti, come Lync Server 2013, non sono supportate da Microsoft Teams Rooms. Microsoft Teams Rooms non è supportato in Microsoft 365 o Office 365 gestito da ambienti 21Vianet o DoD.
>
> Se si dispone di un server Exchange locale, è necessario usare Exchange Server 2013 SP1 o versione successiva per Microsoft Teams Rooms.

## <a name="hardware-requirements"></a>Requisiti hardware
Una distribuzione hardware include una selezione di un sistema Microsoft Teams Rooms, combinato con periferiche audio e video certificate, e una soluzione di disabilitazione per integrare questi dispositivi.  Tali opzioni sono descritte di seguito.

**Sistemi Microsoft Teams Rooms supportati**

Tutti i dispositivi e i bundle Microsoft Teams Rooms correnti sono disponibili nella vetrina del [prodotto Teams Rooms](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processore|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Crestron Flex UC-C140-T con Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-M150-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T) +  [CCS-UCA-MIC](https://www.crestron.com/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T con Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Crestron Flex UC-MMX30-T con UC Presentation Transmitter (UC-PR) e ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MMX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-BX30-T con UC Presentation Transmitter (UC-PR) e ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-BX30-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-CX100-T con UC Presentation Transmitter (UC-PR) e ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T)|Core i5/i7|8 GB |128 GB |
  |[Crestron Flex UC-B30-T con ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-C100-T con ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M50-T con ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-M70-T con ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX50-T con ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5/i7|8 GB |128 GB |
   |[Crestron Flex UC-MX70-T con ASUS PC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5/i7|8 GB |128 GB |
   |Crestron FLEX UC-B30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-Bx30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MM30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MMX30-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M50-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX50-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-M70-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-MX70-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-C100-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
   |Crestron FLEX UC-CX100-T con Dell OPTIPLEX|Core i5|8 GB|128 GB|
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 con Logitech TAP](https://www.dell.com/en-us/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i7 |16 GB |128 GB|
  |[HP Elite Slice G2 per le sale riunioni ](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio predisposto per Microsoft Teams Rooms](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP Slice Partner Ready con Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB| 
  |[Soluzione HP Presence Small Space Con Microsoft Teams Rooms](https://www.hp.com/us-en/solutions/presence.html)|Core i5/i7|8 GB/16 GB|256 GB|
  |[Hp Presence Small Space Solution Plus AI Camera with Microsoft Teams Rooms](https://www.hp.com/us-en/solutions/presence.html)|Core i5/i7|8 GB/16 GB|256 GB|
  | Lenovo ThinkSmart Hub 500 |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |Lenovo ThinkSmart Core Kit |Core i5|8 GB|128 GB|
  |[Logitech Tap con Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |Pc Logitech Tap e Intel Tiger Canyon NUC |Core i5|8 GB|128 GB|
  |Logitech TAP Console con Lenovo Core Compute |Core i5|8 GB|128 GB|
  |[Logitech Tap e Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T con Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
  |[Kit Poly G40-T con Poly Studio USB, con Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g40) |Core i5| 8 GB | 128 GB|
  |[Poly G85-T Kit con Poly Eagle Eye Director II, con Lenovo](https://www.poly.com/us/en/support/products/video-conferencing/poly-room-solutions/g85) |Core i5| 8 GB | 128 GB|
  |Poly GC8 Console con Lenovo Thinksmart Core|Core i5|8 GB|128 GB|
  |Console Poly GC8 con Dell Optiplex 7080|Core i5|8 GB|128 GB|
  |[Yealink MVC300 con Intel NUC](https://www.yealink.com/products_154.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC500 con Intel NUC](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
  |[Yealink MVC800 con Intel NUC](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
  |[Yealink MVC900 con Intel NUC](https://www.yealink.com/product/microsoft-teams-room-system-mvc900)|Core i5|8 GB|128 GB|
  |[Yealink MVC 300 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc300II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC400](https://www.yealink.com/product/microsoft-teams-room-system-mvc400)        |Core i5|8 GB | 128 GB|
  |[Yealink MVC 500 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc500II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 800 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc800II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC 900 II](https://www.yealink.com/product/microsoft-teams-room-system-mvc900II) |Core i5|8 GB | 128 GB|
  |[Yealink MVC840](https://www.yealink.com/product/microsoft-teams-room-system-mvc840) |Core i5|8 GB | 128 GB|
  |[Yealink MVC940](https://www.yealink.com/product/microsoft-teams-room-system-mvc940) |Core i5|8 GB | 128 GB|
  |Yealink MVC660|Core i5|8 GB | 128 GB|
  |Yealink MVC640|Core i5|8 GB | 128 GB|
  |Yealink MVC320|Core i5|8 GB | 128 GB|
  |Yealink MVC340|Core i5|8 GB | 128 GB|
  
  
> [!NOTE]
> - I processori Core M3 non sono supportati. 
> - È necessaria un'unità USB da 32 GB o dimensioni superiori, configurata come supporto di installazione di Windows avviabile per Windows 10 Enterprise.

**Tablet Surface Pro compatibili con i sistemi di alloggiamento di estensione**

  |Tablet|Processore|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB o 8 GB |128 GB o dimensioni superiori |
  |Surface Pro </br>(Quinta gen) |Core i5 |8 GB o 4 GB |128 GB o dimensioni superiori |
  |Surface Pro 4 |Core i5 |8 GB o 4 GB |128 GB o dimensioni superiori |

- Surface Pro dispositivi richiedono una delle seguenti opzioni dell'alloggiamento di espansione:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versioni del firmware certificate per le periferiche audio e video USB

Questi dispositivi sono disponibili in [Presentazione degli accessori per sistemi di videoconferenza](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) e [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Periferiche Microsoft Teams Rooms|Versione del firmware certificata | Supporta la fotocamera dei contenuti|Fotocamera intelligente|
|:--- |:--- | :--- |:--- |
|[Fotocamera Aver VC520 Pro + Vivavoce](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Sistema di conferenza Aver VC520 PRO2](https://www.averusa.com/products/conference-camera/vc520pro2) | 00.0.7200.79 |
|[Barra audio Della fotocamera Aver VB342+](https://www.averusa.com/products/conference-camera/vb342plus) | Soundbar: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 550](https://www.averusa.com/products/conference-camera/cam550) |0.0.8000.51 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Aver CAM 520 Pro 2](https://www.averusa.com/products/conference-camera/cam520pro2) |0.0.7200.3 |
|[Aver CAM 130](https://www.averusa.com/products/conference-camera/cam130) |0.0.7450.02 | &#x2714; |
|[Aver Fone540](https://www.averusa.com/products/vc-accessories/fone540) |0.0.7002.17|
|[Barra audio della fotocamera Aver VB130](https://www.averusa.com/products/conference-camera/vb130) |0.0.7300.71 |
|[Audiocodice RXVCAM50L](https://www.audiocodes.com/solutions-products/products/room-experience-rx-suite/rxvcam50lm-video-camera) |1.0.5 |
|[Bose Video Bar VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Biamp Devio SCR-20CX Web-Based Hub di conferenza con microfono a soffitto](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9|
|[Biamp Devio SCR-20TX Web-Based Hub di Conferenza con microfono da tavolo](https://www.biamp.com/products/product-families/devio/huddle-room-solutions) |2.2.0.9 |
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|Hp Presence Vedi Fotocamera| 1.0.23.0 |
|[Tela di Huddly](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Fotocamera Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Huddly L1](https://www.huddly.com/conference-cameras/l1/) | 1.2.9 |
|Fotocamera Huddly L1 con kit [Crestron UC-C100-T MTR](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T) | Fotocamera Huddly L1: 1.2.1 </br> Crestron UC-C100-T con ASUS Tek Computer INC 9934 calcolato 1.0.20.246 o superiore |
|Fotocamera Huddly L1 con [Crestron UC-CX100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-CX100-T) MTR-W Kit | Fotocamera Huddly L1: 1.2.9 </br> Crestron UC-CX100-T con ASUS Tek Computer INC 9934 1.00.20.246 o versione successiva |
|Fotocamera Huddly L1 con kit MTR Crestron UC-M70-T | Fotocamera Huddly L1: 1.2.1 </br> Crestron UC-M70-T con ASUS Tek Computer INC 9934 calcolato 1.0.20.246 o superiore |
|Fotocamera Huddly L1 con kit Crestron UC-MX70-T MTR | Fotocamera Huddly L1: 1.2.1 </br> Crestron UC-MX70-T con ASUS Tek Computer INC 9934 calcolato 1.0.20.246 o superiore |
|[Fotocamera Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Barra video Jabra Panacast 50](https://www.jabra.com/business/video-conferencing/jabra-panacast-50)|4.0.15| &#x2714; | &#x2714;|
|[Lenovo ThinkSmart Cam Camera](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|[Lenovo ThinkSmart Bar](https://www.lenovo.com/us/en/virtual-reality-and-smart-devices/smart-collaboration/thinksmart/ThinkSmart-Bar/p/11SP1TSSDBR)|0.9.3|
|Lenovo ThinkSmart Bar Expand XL|5.9.5|
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech Rally Bar Mini](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybarmini.960-001336.html) |10.5.880|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio - 1.0.172 <br/> Video - 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Logitech Scribe](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/scribe.960-001332.html) | 1.1.1 | &#x2714; |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube Camera](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.md)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://support.polycom.com/content/dam/polycom-support/products/peripherals/eagle-eye-director-ii/user/en/eagleeye-director-ii-admin-guide-2-0.pdf#:~:text=The%20Polycom%C2%AE%20EagleEye%E2%84%A2%20Director%20II%20camera%20is%20a,while%20the%20other%20camera%20tracks%20the%20second%20speaker.)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Poly Sync 60](https://www.poly.com/us/en/products/phones/sync/sync-60)|0.0.150.1671|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[Barra video Poly Studio P15](https://www.poly.com/us/en/products/video-conferencing/studio-p/studio-p15)|1.2.0.000287 |
|[Fotocamera Poly Studio E70](https://www.poly.com/us/en/products/video-conferencing/studio/studio-e70)|1.1|
|[Poly Studio R30](https://www.poly.com/us/en/products/video-conferencing/studio/studio-r30)|2.0.0.001096|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Espandi 80T + 2 Microfoni di estensione](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Vivavoce - 4.6.55 <br/> Microfono estensione - 0.2.314|
|[EPOS Expand Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Extron DMP128 PLUS C V AT DSP System (DMP 128 Plus C V AT, DMP 128 Plus C AT, DMP 128 Plus C V, DMP 128 Plus C, DMP 128 Plus AT, DMP 128 Plus, DMP 128 FlexPlus C AT, DMP 128 FlexPlus C V AT)](https://www.extron.com/product/dmp128plus) | 1.08 |
|[Extron DMP 64 PLUS C V AT DSP System (DMP 64 Plus C V AT, DMP 64 Plus C AT, DMP 64 Plus C V, DMP 64 Plus C)](https://www.extron.com/product/dmp64plus) | 1.08|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yamaha YVC-1000MS](https://uc.yamaha.com/products/conference-phones/usb-bluetooth/) |1.0.0 |
|[Soluzione per soffitto Yamaha ADECIA](https://uc.yamaha.com/products/microphone-systems/adecia/)|1.2.0|
|[Yamaha ADECIA Soluzione da tavolo](https://uc.yamaha.com/products/adecia/adecia-tabletop/)|E1.2.0 per il microfono da tabella, D1.2.0 per processore (entrambi gli stessi contenuti di V1.5.1)|
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Barra video Yealink UVC34 Tutto in uno](https://www.yealink.com/product/usb-videobar-uvc34) | 265.410.0.9 |
|[Yealink UVC40 Barra video tutto in uno](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Yealink UVC84](https://www.yealink.com/product/camera-uvc84) |262.410.0.10|
|[Yealink UVC86]( https://www.yealink.com/product/camera-uvc86) |151.410.0.5|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Shure MXA 910 con Intellimix Ceiling Array Mic](https://www.shure.com/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300)+</br>[Shure MXA 310 Table Array Mic ](https://www.shure.com/products/microphones/mxa310) +</br>[Altoparlante MXN5W-C Ceiling](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA310 Table Array mic: 4.1.41 </br> Altoparlante MXN5W-C: 1.0.4 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) + </br>[Shure MXA 920 con Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[Altoparlante MXN5W-C Ceiling](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.7.7 </br> Microfono MXA920 Ceiling Array: 1.1.56 </br> Altoparlante MXN5W-C: 1.5.6 |
|ANIUSB + </br> [Shure MXA 920 con Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa920?utm_source=linkedin&utm_medium=social&sfid=&prod=) +</br>[Altoparlante MXN5 Ceiling](https://www.shure.com/en-US/products/loudspeakers/mxn5)| ANIUSB: 4.4.7 </br> MXA920: 1.1.56 </br> MXN5: 1.5.6|
|[Shure MXA 710 2ft Table Linear Array Microphone](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Altoparlante per soffitto MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Altoparlante MXN5-C: 1.1.1 |
|[Shure MXA 710 4ft Muro Lineare Array Microfono](https://www.shure.com/products/microphones/mxa710) + </br>[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/products/mixers/p300) +</br>[Altoparlante per soffitto MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Altoparlante MXN5-C: 1.1.1 |
|[Shure MXA 910 con microfono Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br> [Crestron UC-C100-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)| Shure Intellimix Room Software: 3.0.4.14 </br> Shure MXA 910 con Intellimix Ceiling Array Microfono: 4.4.11 </br> Altoparlanti Shure MXN5-C: 1.2.1 </br> Crestron UC-C100-T con ASUS Tek Computer INC 9934 compute | 
|[Shure MXA 910 con microfono Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Lenovo ThinkSmart Core | Shure Intellimix Room Software: 3.2.0.52 </br> Shure MXA 910 con Intellimix Ceiling Array Microfono: 4.4.11 </br> Altoparlanti Shure MXN5-C: 1.2.1 |
|[Shure MXA920XX-R Round Ceiling Array Microphone](https://www.shure.com/en-US/products/microphones/mxa920?variant=MXA920AL-R) + </br> [Processore P300](https://www.shure.com/en-US/products/mixers/p300?variant=P300-IMX) + </br> [Altoparlanti MXN5](https://www.shure.com/en-US/products/loudspeakers/mxn5) | MXA920XX-R: 1.1.56 </br> Processore P300: 4.7.7 </br> Altoparlanti MXN5: 1.5.6 |
|[Shure MXA 910 con microfono Intellimix Ceiling Array](https://www.shure.com/products/microphones/mxa910) + </br> [Shure Intellimix Room Software](https://www.shure.com/products/software/intellimix_room) +</br>Dell Optiplex 7080 | Shure Intellimix Room Software: 3.2.0.52 </br> Shure MXA 910 con Intellimix Ceiling Array Microfono: 4.4.11 </br> Altoparlanti Shure MXN5-C: 1.2.1 |
|[Sennheiser TeamConnect Intelligent Speaker/TC ISP (T-Rock)](https://en-us.sennheiser.com/tcisp)|1.0.2|
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br>[Sennheiser TeamConnect Ceiling 2 Microphone](https://sennheiser.com/tcc2)+ &Dagger;</br>[Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15 </br> TCC2:1.3.3 </br>EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+</br>[Microfono da soffitto Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Altoparlante da soffitto Biamp Desono C-IC6](https://www.biamp.com/products/tesira-speakers)| Versione FW audio: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br>[Ex-UBT]() |Versione FW audio: 3.15|
|[Biamp Devio SCX Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Microfono da soffitto Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Altoparlante da soffitto Biamp Desono C-IC6](https://www.biamp.com/products/tesira-speakers) | Devio SERIE SCX: 4.2.5 |
|[Biamp Tesira Forte X Series  Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br>[Microfono da soffitto Biamp Parlé TCM-XA](https://www.biamp.com/products/product-families/parle/parle-microphones) + </br> [Altoparlante da soffitto Biamp Desono C-IC6](https://www.biamp.com/products/tesira-speakers) | Tesira FORTE X Serie: 4.2.5 |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink amplificatore +</br> Sennheiser TCC2 microfono da soffitto + </br> Bose EdgeMax EM180 altoparlante da soffitto](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink Amplificatore + Sennheiser TCC2 Microfono da soffitto + </br> Bose DesignMax Altoparlante per soffitto DM2C-P](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplificatore +</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Altoparlante per soffitto DesignMax DM2C -LP](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplificatore+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Altoparlante per soffitto EdgeMax EM180](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A: 1.160  </br> TCC2: 1.4.2  |
|QSC Q-SYS Core ([110f](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-110f/), [8 Flex](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-8-flex/), [Nano](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/core-nano/) o [NV-32-H](https://www.qsc.com/solutions-products/q-sys-ecosystem/processing/nv-32-h-core-capable/)) + </br> [Sennheiser TCC2 Ceiling Microphone](https://en-us.sennheiser.com/tcc2) + </br> Amplificatore QSC ([serie SPA](https://www.qsc.com/solutions-products/power-amplifiers/installed/non-network/low-power-applications/spa-series/) o [serie CX-Q](https://www.qsc.com/solutions-products/power-amplifiers/installed/network/cx-q-series/)) + </br> [Altoparlanti della serie QSC AcousticDesign](https://www.qsc.com/solutions-products/loudspeakers/installed/passive/solutions/acousticdesigntm-series-solutions/) + </br> Fotocamera IP QSC ([PTZ-IP 20x60](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/), [PTZ-IP 12x72](https://www.qsc.com/solutions-products/q-sys-ecosystem/video/ptz-ip-conference-cameras/)) facoltativa + </br> [Bridge USB QSC Q-SYS I/O](https://www.qsc.com/solutions-products/q-sys-ecosystem/audio-io-peripherals/io-usb-bridge/) facoltativo | QSC Q-SYS Core, fotocamera PTZ-IP e bridge USB I/O: QSC Q-SYS Designer 9.0.1-2104.022 </br> Microfono da soffitto Sennheiser TCC2: TCC2 - 1.5.1, Dante 1.2.0 </br> Amplificatori QSC: N/D </br> Altoparlanti QSC AcousticDesign Series: N/D | 
|[Vaddio IntelliSHOT-M](https://www.legrandav.com/products/cameras/hd_fixed_camera/intellishot-eptz-camera) | 1.0.0 |


&Dagger; I clienti possono scegliere l'interfaccia Dante o la commutazione di rete consigliata da Biamp/Sennheiser per il pacchetto.

#### <a name="usb-extenders"></a>Extender USB

- Le porte USB negli alloggiamenti di estensione sono compatibili con USB 3.0. È possibile usare un extender USB 2.x, ma alla fine sarà limitata a velocità USB 2.x. Gli extender non sono consigliati per le periferiche USB 3.0.
- Un extender deve soddisfare le specifiche USB 2.0 o più recenti.
  - Gli alloggiamenti di estensione dei tablet supportano almeno due stadi di estensione dell'hub USB esterno. Se si connettono più di due hub USB in serie, rivolgersi al produttore degli alloggiamenti di estensione per verificare se supportano la connessione in serie.
  - Connessioni GbE cablate nella sala. Cavo Ethernet della lunghezza appropriata.
  - Fino a due schermi da 1080p con connessioni HDMI. Cavi HDMI della lunghezza appropriata.

> [!NOTE]
> Un televisore per uso privato usato come schermo per la visualizzazione nella sala deve supportare o abilitare la funzionalità Consumer Electronics Control (CEC) di HDMI in modo che possa passare automaticamente dalla modalità di standby a un'origine video attiva. Questa funzionalità non è supportata da tutti i televisori.
>
> Microsoft Teams Rooms non supporta la tastiera. Se necessario, l'amministratore deve usare la tastiera su schermo. Per l'elaborazione delle immagini nei dispositivi Microsoft Teams Rooms sarà necessario un mouse o una tastiera USB.

Nelle tabelle seguenti sono disponibili suggerimenti per le periferiche in base alle dimensioni della sala:

**Periferiche audio certificate per Microsoft Teams Rooms**

|Tipo di sala|Numero di utenti|Distanza massima consigliata del microfono dall'altoparlante|
|:-----|:-----|:-----|
|**Raccolta** <br/> 10' x 9'   |2-4  |1,5 m  |
|**Piccola** <br/> 16' x 16'  |4-6  |2,0 m  |
|**Media**. <br/> 18' x 20'  |6-12  |2,4 m  |
|**Grande** <br/> 15' x 32'  |12-16  |3 m <br/> Questa distanza si applica anche all'area coperta da ogni microfono satellite connesso.  |

**Periferiche video certificate per Microsoft Teams Rooms**

|Tipo di sala|Numero di utenti|
|:-----|:-----|
|**Raccolta** <br/> 10' x 9'  |2-4  |
|**Piccola** <br/> 16' x 16'  |4-6  |
|**Media**. <br/> 18' x 20'  |6-12  |
|**Grande** <br/> 15' x 32'  |12-16  |

 > [!NOTE]
 > La risoluzione dello schermo in posizione anteriore nella sala deve essere impostata su un valore non superiore a 1920x1080p.


## <a name="see-also"></a>Vedere anche

[Esplorare tutti i pacchetti](https://products.office.com/microsoft-teams/across-devices/devices)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).
