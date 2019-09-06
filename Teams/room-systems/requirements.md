---
title: Requisiti di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: Questo articolo riepiloga i requisiti per il supporto delle sale di Microsoft teams.
ms.openlocfilehash: 4a92ba051564800dace5eafec8e573d807c11d04
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775173"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisiti di Microsoft teams rooms

Questo articolo riepiloga i requisiti per il supporto delle sale di Microsoft teams.

La distribuzione prevede la creazione di account come descritto in [distribuire le sale di Microsoft teams](room-systems-v2.md) e la configurazione delle console riunioni come descritto in [configurare una console Microsoft teams Rooms](console.md).

Vedi anche:

- [Licenze per i componenti aggiuntivi di Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opzioni di licenza basate sul piano: Microsoft teams rooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft teams Rooms è progettato per l'uso con Microsoft teams, Skype for Business Server 2019, Skype for Business Server 2015 o Skype for business online.
>
> Non è previsto che le piattaforme precedenti come Lync Server 2013 funzionino con le sale di Microsoft teams.
>
> Se si dispone di un server Exchange su Prem, le sale di Microsoft teams richiedono l'uso di Exchange Server 2013 SP1 o versioni successive.

## <a name="hardware-requirements"></a>Requisiti hardware

Le sale di Microsoft teams variano a seconda delle dimensioni della sala attraverso gli accessori in base alle periferiche audio e video. L'hardware elencato in questo articolo supporta le modalità di riunione Skype e teams. Le periferiche audio e video si connettono a Microsoft teams Rooms tramite una connessione USB o HDMI sul dispositivo di ancoraggio. Sarà inoltre necessario:

- Un 32 GB o un disco USB più grande configurato come supporto di installazione di Windows di avvio per Windows 10 Enterprise.

- Uno dei tablet o delle console seguenti:

**Compresse supportate**

|Tablet|Processore|RAM|Disco|
|:-----|:-----|:-----|:-----|
|Surface Pro 6| Core i5 |16 GB o 8 GB |128 GB o più |
|Surface Pro (Quinta generazione) |Core i5 |8 GB o 4 GB |128 GB o più |
|Surface Pro 4 |Core i5 |8 GB o 4 GB |128 GB o più |

- Una delle opzioni della stazione di ancoraggio seguenti per proteggere un tablet nella tabella della sala riunioni.

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Serie MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)

**Altre console di Microsoft teams rooms supportate**

|Console|Processore|RAM|Disco|
|:-----|:-----|:-----|:-----|
|[Crestron Flex UC-M130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M130-T)|Core i5|8 GB |128 GB |
|[Crestron Flex UC-B130-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B130-T)|Core i5|8 GB |128 GB |
|[Crestron Flex UC-B140-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B140-T)|Core i5|8 GB |128 GB |
|[Crestron Flex UC-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Core i7|8 GB |128 GB |
[Crestron Flex UC-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8 GB |128 GB|
|[Crestron Flex UC-C160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8 GB|128 GB|
|[HP Elite Slice per sale riunioni G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5 |8 GB |128 GB |
|[HP Elite Slice G2 audio pronto con le sale di Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8 GB |128 GB |
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5 |8 GB |128 GB |
|[Logitech Tap](https://www.logitech.com/en-us/product/microsoft-rooms)|Core i5|8 GB |128 GB |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8 GB|128 GB|
|[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8 GB |128 GB |
|||||

> [!NOTE]
> I processori M3 principali non sono supportati.

### <a name="certified-firmware-versions-for-usb-audio-and-video-peripherals"></a>**Versioni del firmware certificate per periferiche audio e video USB**

Questi dispositivi sono disponibili su [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

|Periferiche Microsoft teams rooms|Versione del firmware certificata per Microsoft teams rooms| Fotocamera supporta l'uso della fotocamera del contenuto|
|:--- |:--- | :--- |
|[Qi Crestron](https://www.crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Accessories/CCS-CAM-USB-F-400)   | 1.02.09.33901  | &#x2714; |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio)   |v240| &#x2714; |
|[Logitech 930E](http://www.logitech.com/en-us/product/c930e-webcam)   | 8.0.914   | &#x2714; |
|[Logitech Rally](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam)   |1.2.4 |
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam)   |Audio-1.0.172 <br/> Video — 1.0.156  |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect)   |1.1.248.0 <br/> 1.1.684   |
|[Gruppo Logitech](http://www.logitech.com/en-us/product/conferencecam-group)   |8.5.778   |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro)   | 1.1.219   |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2)   |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl)   |1.0.0   |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl)   | 1.2.0.70232   |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html)   |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc)   |2.0.12.0   |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml)   |1.2.15   |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30)   |2.1.52  |
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209)   |2.10.0   |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710)   |1.8.0   |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810)   |1.2.23   |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/)   |100C   |
| |  | |

- **Estensioni USB**:

  - Le porte USB nei Dock tablet sono compatibili con USB 3,0. È possibile usare un'estensione USB 2. x, ma questo limita l'uso di velocità USB 2. x all'estrema fine e non è consigliabile per le periferiche USB 3,0.

  - Un estensore deve soddisfare le specifiche USB 2,0 o più recenti.

  - I dock per Tablet supportano almeno due fasi dell'estensione dell'hub USB esterna. Se è necessario connettere più di due hub USB in serie, consultare il produttore del dock per verificare se è supportato.

- Connessione GbE cablata nella sala. Cavo Ethernet di lunghezza appropriata.

- Fino a 2 1080-p Visualizza con connessioni HDMI. Cavi HDMI di lunghezza appropriata.

> [!NOTE]
> Un televisore consumer usato come parte anteriore dello schermo della sala deve supportare/abilitare la funzionalità CEC (Consumer Electronics Control) di HDMI in modo che possa passare automaticamente a un'origine video attiva dalla modalità standby. Questa caratteristica non è supportata in tutti i televisori.

> [!NOTE]
> Microsoft teams Rooms non usa una tastiera. Se necessario, l'amministratore deve usare la tastiera su schermo. Quando si Imaging il dispositivo Microsoft teams Rooms sarà necessario un mouse o una tastiera USB.

Le tabelle seguenti includono suggerimenti per le periferiche in base alle dimensioni della sala:

**Periferiche audio certificate di Microsoft teams rooms**

|Tipo di sala|Numero di persone|Distanza massima consigliata da microfono a altoparlante|Dispositivo per dimensione massima della sala|Commenti|
|:-----|:-----|:-----|:-----|:-----|
|**Lo attivo** <br/> 10' x 9'   |2 – 4  |1,5 m  |Logitech Connect  |I dispositivi Logitech Connect includono una fotocamera, quindi deve essere posizionata nella parte anteriore della sala (non al centro della tabella) per acquisire partecipanti alla riunione locale.  |
|**Small** <br/> 16' x 16'  |4 – 6  |2,0 m  |Jabra 510 <br/> Sennheiser SP20  |Il volume di riproduzione può essere limitato per le camere più grandi.  |
|**Media** <br/> 18' x 20'  |6-12  |2,4 m  |Jabra 710 <br/> Jabra 810 <br/> Logitech MeetUp <br/> Gruppo Logitech <br/> Polycom Trio <br/> Polycom CX5100 <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS  |Il Logitech MeetUp include una fotocamera, quindi deve essere posizionata nella parte anteriore della chat room (non al centro della tabella per acquisire partecipanti alla riunione locale). <br/> In generale, le camere con tabelle lunghe rettangolari o a forma di u possono trarre vantaggio da microfoni satellitari. <br/> SP 220 MS deve essere usato nella configurazione a catena a Margherita.  |
|**Grande** <br/> 15' x 32'  |12-16  |3 m <br/> Questa distanza si applica anche all'area coperta da ogni microfono satellitare collegato al dispositivo audio.  |Logitech Group + microfoni satellitari <br/> Polycom Trio + microfoni satellitari <br/> Polycom CX5100 + microfoni satellitari <br/> Sennheiser SP 220 MS <br/> Yamaha YVC-1000MS + microfoni satellitari  |Tutti i dispositivi audio elencati in questa riga supportano le opzioni del microfono satellitare. <br/> CX5100 include una fotocamera incorporata di 360 gradi in modo che il dispositivo possa essere posizionato al centro della tabella. <br/> SP 220 MS deve essere usato nella configurazione a catena a Margherita.  |

**Periferiche video certificate di Microsoft teams rooms**

|Tipo di sala|Numero di persone|Dispositivo per dimensioni ottimali della sala|Commenti|
|:-----|:-----|:-----|:-----|
|**Lo attivo** <br/> 10' x 9'  |2 – 4  |Logitech Connect <br/> Logitech MeetUp <br/> Polycom CX5100  ||
|**Small** <br/> 16' x 16'  |4 – 6  |Logitech C930e <br/> Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  |Logitech PTZ Pro spesso in bundle con il gruppo Logitech  |
|**Media** <br/> 18' x 20'  |6-12  |Logitech MeetUp <br/> Logitech BRIO <br/> Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||
|**Grande** <br/> 15' x 32'  |12-16  |Logitech PTZ Pro <br/> Polycom MSR <br/> Polycom CX5100  ||

 > [!NOTE]
 > Il lato anteriore della risoluzione dello schermo della sala deve essere impostato su non maggiore di 1920x1080p.

## <a name="required-software-downloads"></a>Download di software necessari

Per creare una propria immagine di Microsoft teams rooms, seguire le istruzioni in [configurare una console Microsoft teams Rooms](console.md). Queste istruzioni guidano il download di tutto il software necessario per il processo di installazione.

> [!NOTE]
> I professionisti IT dovranno accedere ai file ISO di Windows 10 Enterprise tramite il contratto multilicenza.

[SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105) è un download facoltativo che puoi usare per eseguire il provisioning degli account di Microsoft teams rooms.

## <a name="see-also"></a>Vedere anche

[Esplorare tutti i bundle](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)

[Distribuire le sale di Microsoft Teams](room-systems-v2.md)

[Configurare una console Microsoft teams rooms](console.md)

[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)

[Licenze per i componenti aggiuntivi Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
