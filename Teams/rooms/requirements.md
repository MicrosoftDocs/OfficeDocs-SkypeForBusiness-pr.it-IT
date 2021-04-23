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
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection:
- M365-collaboration
description: Informazioni sui requisiti per il supporto di Microsoft Teams Rooms, tra cui la scelta del dispositivo, dei microfoni, degli altoparlanti, delle fotocamere e degli schermi appropriati.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9083a66add26ff7149fddd16052bac87625d2b27
ms.sourcegitcommit: 234c928b9ac127716e3d5a92ee2bcdda1a415a38
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2021
ms.locfileid: "51959473"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisiti per Microsoft Teams Rooms

Le sale di Microsoft Teams si adattano a diverse dimensioni delle sale. Teams Rooms usa un'ampia varietà di periferiche audio e video certificate in base alle dimensioni e all'uso della sala. Selezionando il dispositivo e la console di base appropriati, combinati con microfoni, altoparlanti, fotocamere e schermi appropriati per lo spazio, è possibile distribuire Le sale di Microsoft Teams in spazi di qualsiasi dimensione, da piccoli spazi di riunione fino a grandi sale riunioni e sale riunioni.  Il set completo delle periferiche audio e video certificate che possono essere utilizzate per configurare la sala, è disponibile in [Presentazione dei dispositivi](https://products.office.com/microsoft-teams/across-devices).

In questo articolo vengono riepilogati i requisiti di configurazione e distribuzione dei dispositivi per il supporto di Microsoft Teams Rooms.

La distribuzione implica la creazione di account come descritto in [Distribuire Microsoft Teams Room](rooms-deploy.md) e la configurazione di console per riunioni come descritto in [Configurare una console per Microsoft Teams Rooms](console.md).

Fare riferimento a:

- [Licenze per i componenti aggiuntivi di Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opzioni di licenza basate sul tuo piano: Microsoft Teams Rooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft Teams Rooms consente di accede a Microsoft Teams, Skype for Business Server 2019, Skype for Business Server 2015 o Skype for Business Online e può partecipare alle riunioni ospitate da tali prodotti.
>
> Le piattaforme precedenti, come Lync Server 2013, non sono supportate da Microsoft Teams Rooms. Microsoft Teams Rooms non è supportato in Microsoft 365 o Office 365 gestito da 21Vianet o in ambienti GCC-High o DoD.
>
> Se si dispone di un server Exchange locale, è necessario usare Exchange Server 2013 SP1 o versione successiva per Microsoft Teams Rooms.

## <a name="hardware-requirements"></a>Requisiti hardware
La distribuzione hardware include la selezione di un sistema per Sala riunioni di Microsoft Teams, oltre alle periferiche audio e video certificate e una soluzione di cablaggio per integrare tali dispositivi.  Tali opzioni sono descritte di seguito.

**Sistemi per Sala riunioni di Microsoft Teams supportati**

Tutti gli attuali dispositivi e pacchetti per Sala riunioni di Microsoft Teams sono disponibili in [Presentazione dei prodotti per sistemi per videoconferenza](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=20&page=1&filterIds=).

  |Console|Processore|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |[Crestron Flex UC-M130-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC- B130-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
  |[Crestron Flex UC-B140-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
  [Crestron Flex UC-C140-T con Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C140-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-M150-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)  +  [CCS-UCA-MIC](https://www.crestron.com/en-US/Products/Audio/Microphones/Wired-Microphones/CCS-UCA-MIC-KIT)|Core i7|8 GB |128 GB |
  |[Crestron Flex UC-MX150-T con Intel NUC](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX150-T)|Core i5|8 GB |128 GB |
   [Crestron Flex UC-B160-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
  |[Crestron Flex UC-C160-T con Intel NUC](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
  |[Crestron Flex UC-B30-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B30-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-C100-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C100-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-M50-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M50-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-M70-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M70-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-MX50-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX50-T)|Core i5|8 GB |128 GB |
   |[Crestron Flex UC-MX70-T con PC ASUS](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MX70-T)|Core i5|8 GB |128 GB |
  |[Crestron Mercury Mini UC-MM30-T](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-MM30-T)|Core i5|8 GB |128 GB |
  |[Dell OptiPlex 7080 con tap Logitech](https://www.dell.com/work/shop/cty/pdp/spd/optiplex-7080-xe-teams) | Core i5 & i7 |8 GB |128 GB|
  |[HP Elite Slice G2 per le sale riunioni ](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
  |[HP Elite Slice G2 Audio predisposto per Microsoft Teams Rooms](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
  |[HP Slice Partner Ready with Logitech TAP]( https://www.logitech.com/video-collaboration/partners/hp.html)|Core i5|8 GB|128 GB|
  |[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
  |[Lenovo ThinkSmart Hub](https://news.lenovo.com/pressroom/press-releases/new-thinksmart-hub-collaboration-solution-from-lenovo-helps-organizations-embrace-hybrid-working-model/) |Core i5 |8 GB |128 GB|
  |[Logitech Tap con Intel NUC](https://www.logitech.com/product/microsoft-rooms)|Core i5|8 GB |128 GB |
  |[Logitech Tap e Lenovo ThinkSmart Tiny](https://www.logitech.com/video-collaboration/partners/lenovo.html)|Core i5|8 GB |128 GB|
  |[Poly G10-T con Lenovo ThinkSmart Tiny](https://www.poly.com/us/en/products/video-conferencing/g/g10) |Core i5| 8 GB | 128 GB|
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
  
> [!NOTE]
> - I processori Core M3 non sono supportati. 
> - È necessaria un'unità USB da 32 GB o dimensioni superiori, configurata come supporto di installazione di Windows avviabile per Windows 10 Enterprise.

**Tablet Surface Pro compatibili con i sistemi di alloggiamento di estensione**

  |Tablet|Processore|RAM|Disco|
  |:-----|:-----|:-----|:-----|
  |Surface Pro 6| Core i5 |16 GB o 8 GB |128 GB o dimensioni superiori |
  |Surface Pro </br>(Quinta gen) |Core i5 |8 GB o 4 GB |128 GB o dimensioni superiori |
  |Surface Pro 4 |Core i5 |8 GB o 4 GB |128 GB o dimensioni superiori |

- I dispositivi Surface Pro richiedono una delle opzioni seguenti dell'alloggiamento di espansione:

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)
  - [Crestron SR](https://www.crestron.com/products/line/sr-for-skype-for-business-room-system )
  - [Polycom MSR Series](https://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>Versioni del firmware certificate per le periferiche audio e video USB

Questi dispositivi sono disponibili in [Presentazione degli accessori per sistemi di videoconferenza](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=73&page=1&filterIds=) e [https://office.com/teamsdevices](https://office.com/teamsdevices).

|Periferiche Microsoft Teams Rooms|Versione del firmware certificata | Videocamera supporta l'uso del contenuto della fotocamera|
|:--- |:--- | :--- |
|[Aver VC520 Pro Fotocamera + Vivavoce](https://www.averusa.com/products/conference-camera/vc520pro) |1004.35|
|[Aver VB342+ Camera Soundbar](https://www.averusa.com/products/conference-camera/vb342plus) | Barra audio: 0.0.0000.97|
|[Aver CAM 540](https://www.averusa.com/products/conference-camera/cam540) |0.0.6002.83 |
|[Aver CAM 520 Pro](https://www.averusa.com/products/conference-camera/cam520pro) |0.0.1000.73 |
|[Barra video Di Bose VB1](https://pro.bose.com/en_us/products/conferencing/videobars/bose-videobar-vb1.html?mc=25_PS_VB_BO_00_BI_&&msclkid=fc99b79880f714727a63e86ea0e5642a&utm_source=bing&utm_medium=cpc&utm_campaign=US%20-%20Brand_Videobar%20VB1_Exact&utm_term=bose%20videobar%20vb1&utm_content=Bose%20Videobar%20VB1&gclid=fc99b79880f714727a63e86ea0e5642a&gclsrc=3p.ds) |19.2|
|[Crestron Huddly IQ](https://www.crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | 
|[Huddly Canvas](https://www.huddly.com/blog/say-hello-to-huddly-canvas-our-latest-ai-technology-for-content-capture-and-enhancement/) | 1.3.25 |  &#x2714; |
|[QI di Huddly](https://www.huddly.com/conference-cameras/iq/) |1.3.22|
|[Huddly IQ Lite](https://www.huddly.com/conference-cameras/iq/) |1.3.29|
|[Fotocamera Huddly IQ](https://www.huddly.com/conference-cameras/iq/) |1.3.27|
|[Fotocamera Jabra Panacast3](https://www.jabra.com/business/video-conferencing/jabra-panacast)|1.3.9.12|
|[Fotocamera Lenovo ThinkSmart Cam](https://www.lenovo.com/us/en/accessories-and-monitors/webcams-and-video/webcams/SMARTOF-BO-ThinkSmart-Cam/p/4Y71C41660)|1.0.111.4|
|Lenovo ThinkSmart Bar |0.9.3| 
|[Logitech Brio](https://www.logitech.com/product/brio)   |V2.2.50| &#x2714; |
|[Logitech 930e](https://www.logitech.com/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech Rally Bar](https://www.logitech.com/en-us/products/video-conferencing/room-solutions/rallybar.960-001308.html)   |10.3.82|
|[Logitech MeetUp](https://www.logitech.com/product/meetup-conferencecam)   |Audio - 1.0.172 <br/> Video - 1.0.156  |
|[Logitech ConferenceCam Connect](https://www.logitech.com/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Logitech Group](https://www.logitech.com/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](https://www.logitech.com/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](https://www.logitech.com/product/conferencecam-ptz-pro2)   |
|[Nureva HDL300](https://www.nureva.com/audio-conferencing/hdl300) |2.3.6|
|[Poly Eagle Eye Cube Camera](https://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.html)  |1.2.0 |
|[Polycom EagleEye IV](https://www.poly.com/us/en/products/video-conferencing/eagleeye/eagleeye-iv)   |1.0.0   |
|[Polycom CX5100](https://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Studio Soundbar](https://www.polycom.com/hd-video-conferencing/room-video-systems/polycom-studio.html)|1.1.2.000570|
|[Poly Sync 40](https://www.poly.com/us/en/products/phones/sync/sync-40)|0.0.94.1461|
|[Polycom Trio 8500 / 8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Poly Trio C60](https://www.poly.com/us/en/products/phones/trio/trio-c60)  |5.9.5.3066|
|[EPOS SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[EPOS SP20](https://www.eposaudio.com/en/us/enterprise/products/sp-20-ml-142ee5ca-speakerphone-1000226)   |1.2.15   |
|[EPOS SP30](https://www.eposaudio.com/en/us/enterprise/products/sp-30-78c0cecc-bluetooth-speakerphone-1000223)   |2.1.52  |
|[EPOS SP30T](https://www.eposaudio.com/en/us/enterprise/products/sp-30t-b949fe9a-bluetooth-speakerphone-1000225)  |3.2.63  |
|[EPOS Espandi 80T + 2 microfoni di estensione](https://www.eposaudio.com/en/us/enterprise/products/expand-80t-bluetooth-speakerphone-1000203) |Vivavoce - 4.6.55 <br/> Microfono di estensione - 0.2.314|
|[Espansione di EPOS Capture 5](https://www.eposaudio.com/en/us/enterprise/products/expand-capture-5-speakerphone-1000895)  |1.0.1|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK&trade;-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100c   |
|[Yealink CP900](https://www.yealink.com/products_150.html) |100.20.0.29 |
|[Yealink UVC30](https://www.yealink.com/product/microsoft-teams-room-system-uvc30)| 105.420.0.11 |  &#x2714; |
|[Barra video Yealink UVC40 All-in-one](https://www.yealink.com/product/usb-videobar-uvc40) |128.410.0.10|  
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/en-US/products/microphones/mxa310) | 4.1 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 con Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) | 4.1|
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/en-US/products/mixers/p300)+</br></br> [Shure MXA 310 Table Array Mic ](https://www.shure.com/en-US/products/microphones/mxa310) +</br></br> [Altoparlante MXN5W-C Ceiling](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MxA310 Table Array mic: 4.1.41 </br> Altoparlante MXN5W-C: 1.0.4 |
|[Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/en-US/products/mixers/p300) + </br></br> [Shure MXA 910 con Intellimix Ceiling Array Mic](https://www.shure.com/en-US/products/microphones/mxa910) +</br></br> [Altoparlante MXN5W-C Ceiling](https://www.shure.com/en-US/products/loudspeakers/mxn5)| P300 DSP: 4.1.11 </br> MXA910 Ceiling Array mic: 4.1.41 </br> Altoparlante MXN5W-C: 1.0.4 |
|[Shure MXA 710 2ft Table Linear Array Microphone](https://www.shure.com/en-US/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/en-US/products/mixers/p300) +</br></br> [Altoparlante a soffitto MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 2ft Table Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Altoparlante MXN5-C: 1.1.1 |
|[Shure MXA 710 4ft Wall Linear Array Microphone](https://www.shure.com/en-US/products/microphones/mxa710) + </br></br> [Shure Intellimix P300 Audio Conferencing Processor](https://www.shure.com/en-US/products/mixers/p300) +</br></br> [Altoparlante a soffitto MXN5-C](https://www.shure.com/en-US/products/loudspeakers/mxn5)| MXA710 4ft Wall Linear Array Mic: 1.2.0 </br> P300 DSP: 4.4.8 </br> Altoparlante MXN5-C: 1.1.1 |
|[Biamp Tesira Fore AVB VT4 Fixed audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ &Dagger;</br></br> [Sennheiser TeamConnect Ceiling 2 Microphone](https://en-us.sennheiser.com/tcc2)+ &Dagger;</br></br> [Tesira EX-UBT](https://www.biamp.com/products/tesira/tesira-expanders) &Dagger; |  Biamp DSP: 3.12.0.15  </br></br> TCC2:1.3.3 </br></br> EX-UBT: 3.12.0.15 |
|[Biamp Tesira FORTÉ AVB VT4 Audio DSP](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Biamp Parlé TCM-XA Ceiling Microphone](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br> [Altoparlante biamp Desono C-IC6 a soffitto montato](https://www.biamp.com/products/tesira-speakers)| Versione audio FW: 3.15|
|[Biamp TesiraFORTE AVB VT4](https://www.biamp.com/products/tesira-fixed-audio-dsp)+ </br></br>[Parle TTM-X(Table Mic)](https://www.biamp.com/products/product-families/parle/parle-microphones)+</br></br>[Ex-UBT]() |Versione audio FW: 3.15|
|[Bose ControlSpace EX-440C DSP + </br>Bose P2600A AmpLink amplificatore +</br> Sennheiser TCC2 microfono da soffitto + </br> Bose EdgeMax EM180 altoparlante da soffitto](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-440C DSP + </br> Bose P2600A AmpLink Amplifier + Sennheiser TCC2 Ceiling Microphone + </br> Bose DesignMax DM2C-P Ceiling Speaker](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html)|  Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |  |
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Amplificatore AmpLink Bose P2600A +</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [DesignMax DM2C -LP Ceiling Speaker](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/designmax/designmax_dm2c_lp.html#v=designmax_dm2c_lp_black) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  | 
|[Bose ControlSpace EX-1280C DSP](https://pro.bose.com/en_us/products/signal_processing_and_networking/controlspace_ex/cs_ex_1280c.html#v=cs_ex_1280c_black) +</br>Bose P2600A AmpLink Amplifier+</br> [Sennheiser TCC2 Ceiling Microphone](https://pro.bose.com/en_us/solutions/bose-work/es1-ceiling-audio-solution.html) +</br> [Altoparlante EdgeMax EM180 Ceiling](https://pro.bose.com/en_us/products/loudspeakers/background_foreground/edgemax/edgemax_em180.html#v=edgemax_em180_white) | Bose DSP: 2.290  </br> P2600A : 1.160  </br> TCC2: 1.4.2  |
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Sennheiser TCC2 Ceiling Microphone]() +</br> [Amplificatore di potenza QSC EnergyStar SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS Series Network Switch NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [Altoparlanti di montaggio surface QSC Column Surface AD-S402T](https://www.qsc.com/systems/products/loudspeakers/column-surface-mount-loudspeakers/acousticdesigntm-series-column-surface-mount/ad-s402t/) +</br> [Fotocamera QSC PTZ 20x60](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |Progettazione domande e risposte: 8.4.0.1 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> N/D </br>  <br>N1100v6.4.2.8 </br> N/D </br> <br> 6.3.2.2|
|[QSC Q-SYS Core 110f](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/q-sys-cores/core-110f/) +</br> [Sennheiser TCC2 Ceiling Microphone]() +</br> [Amplificatore di potenza QSC EnergyStar SPA2-60](https://www.qsc.com/systems/products/power-amplifiers/energystar-amplifiers/spa-series/spa2-60/) +</br> [Q-SYS NS Series Network Switch NS-1108P](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/network-switches/q-sys-ns-series-network-switches/) + </br> [Altoparlanti per montaggio Surface A colonne QSC AD-C6T-LP](https://www.qsc.com/systems/products/loudspeakers/ceiling-mount-loudspeakers/acousticdesigntm-series-ceiling-mount/ad-c6t-lp/?L=) +</br> [Fotocamera QSC PTZ 20x60](https://www.qsc.com/systems/products/q-sys-ecosystem/products-peripherals-accessories/conference-room-integration/ptz-ip-conference-cameras/) |Progettazione domande e risposte: 8.4.0.1 </br> <br> TCC2 : 1.5.1 Dante 1.2.0 </br>  <br> N/D </br>  <br>N1100v6.4.2.8 </br> N/D </br> <br> 6.3.2.2|


&Dagger; I clienti possono scegliere l'interfaccia Dante o la commutazione di rete consigliata da Biamp/Sennheiser per il pacchetto.

#### <a name="usb-extenders"></a>Extender USB

- Le porte USB negli alloggiamenti di estensione sono compatibili con USB 3.0. È possibile usare un extender USB 2.x, ma in questo modo si limitano le velocità di USB 2. x all'estremità opposta. Gli extender non sono consigliati per le periferiche USB 3.0.
- Un extender deve soddisfare le specifiche USB 2.0 o più recenti.
  - Gli alloggiamenti di estensione dei tablet supportano almeno due stadi di estensione dell'hub USB esterno. Se si connettono più di due hub USB in serie, rivolgersi al produttore degli alloggiamenti di estensione per verificare se supportano la connessione in serie.
  - Connessioni GbE cablate nella sala. Cavo Ethernet della lunghezza appropriata.
  - Fino a 2 schermi 1080-p con connessioni HDMI. Cavi HDMI della lunghezza appropriata.

> [!NOTE]
> Un televisore per uso privato usato come schermo per la visualizzazione nella sala deve supportare o abilitare la funzionalità Consumer Electronics Control (CEC) di HDMI in modo che possa passare automaticamente dalla modalità di standby a un'origine video attiva. Questa funzionalità non è supportata da tutti i televisori.
>
> Microsoft Teams Rooms non supporta la tastiera. Se necessario, l'amministratore deve usare la tastiera su schermo. Per l'elaborazione delle immagini nei dispositivi Microsoft Teams Rooms sarà necessario un mouse o una tastiera USB.

Nelle tabelle seguenti sono disponibili suggerimenti per le periferiche in base alle dimensioni della sala:

**Periferiche audio certificate per Microsoft Teams Rooms**

|Tipo di sala|Numero di utenti|Distanza massima consigliata del microfono dall'altoparlante|Dispositivo per dimensione massima della stanza|Commenti|
|:-----|:-----|:-----|:-----|:-----|
|**Raccolta** <br/> 10' x 9'   |2-4  |1,5 m  |Logitech Connect  |I dispositivi Logitech Connect includono una videocamera che deve essere posizionata nella parte anteriore della sala, non al centro del tavolo, per riprendere i partecipanti alla riunione. |
|**Piccola** <br/> 16' x 16'  |4-6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |Il volume di riproduzione può essere limitato per le sale più grandi.  |
|**Media**. <br/> 18' x 20'  |6-12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Logitech Group <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |I dispositivi Logitech MeetUp includono una videocamera che deve essere posizionata nella parte anteriore della stanza, non al centro del tavolo per riprendere i partecipanti alla riunione. <br/> In generale, le sale con lunghi tavoli rettangolari o a forma di U potrebbero trarre vantaggio dai microfoni satellite. <br/> SP 220 MS deve essere usato con un collegamento a margherita.  |
|**Grande** <br/> 15' x 32'  |12-16  |3 m <br/> Questa distanza si applica anche all'area coperta da ogni microfono satellite connesso.  |Logitech Group + microfoni satellite <br/> Polycom Trio + microfoni satellite <br/> Polycom CX5100 + microfoni satellite <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + microfoni satellite  |Tutti i dispositivi audio elencati in questa riga supportano le opzioni per il microfono satellite. <br/> CX5100 include una videocamera integrata a 360 gradi, in modo che il dispositivo possa essere posizionato al centro del tavolo. <br/> SP 220 MS deve essere usato con un collegamento a margherita.  |

**Periferiche video certificate per Microsoft Teams Rooms**

|Tipo di sala|Numero di utenti|Dispositivo per dimensioni della sala ottimali|Commenti|
|:-----|:-----|:-----|:-----|
|**Raccolta** <br/> 10' x 9'  |2-4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Piccola** <br/> 16' x 16'  |4-6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro spesso integrato con Logitech Group  |
|**Media**. <br/> 18' x 20'  |6-12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Grande** <br/> 15' x 32'  |12-16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > La risoluzione dello schermo in posizione anteriore nella sala deve essere impostata su un valore non superiore a 1920x1080p.

## <a name="required-software-downloads"></a>Download del software necessario

Per creare un'immagine di Microsoft Teams Rooms, seguire le istruzioni in Configurare una console per [Microsoft Teams Rooms](console.md). Queste istruzioni illustrano come effettuare il download di tutto il software necessario per l'installazione.

> [!NOTE]
> I professionisti IT dovranno avere accesso ai file ISO di Windows 10 Enterprise tramite il contratto multilicenza.

[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105) è un download facoltativo che è possibile usare per eseguire il provisioning degli account di Microsoft Teams Rooms.

## <a name="see-also"></a>Vedere anche

[Esplorare tutti i pacchetti](https://products.office.com/microsoft-teams/across-devices/devices)

[Piano per Microsoft Teams Rooms](rooms-plan.md)

[Distribuire Microsoft Teams Rooms](rooms-deploy.md)

[Configurare una console per Microsoft Teams Rooms](console.md)

[Gestire Microsoft Teams Rooms](rooms-manage.md).

[Licenze per i componenti aggiuntivi di Skype for Business](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
