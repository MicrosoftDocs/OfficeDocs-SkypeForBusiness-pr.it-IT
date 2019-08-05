---
title: Requisiti di Microsoft teams rooms
ms.author: v-lanac
author: lanachin
ms.reviewer: davgroom
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b2b2684-8e9e-49ea-8c46-1c690964f982
ms.collection: M365-voice
description: Questo articolo riepiloga i requisiti per il supporto delle sale di Microsoft teams.
ms.openlocfilehash: 7e78c2f33a52d5848b8b996c65fefbeabdab4c3e
ms.sourcegitcommit: dcc5c09e6b891fe44c9d2cf384fe7ef678e7768c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/26/2019
ms.locfileid: "36185143"
---
# <a name="microsoft-teams-rooms-requirements"></a>Requisiti di Microsoft teams rooms

Questo articolo riepiloga i requisiti per il supporto delle sale di Microsoft teams. 

La distribuzione comporterà la creazione di account come descritto in [distribuire le sale di Microsoft teams](room-systems-v2.md) e la configurazione di una console riunione come descritto in [configurare una console Microsoft teams Rooms](console.md). 

Potrebbe essere necessario fare riferimento a:

- [Licenze per i componenti aggiuntivi di Skype for Business](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing)
- [Opzioni di licenza basate sul piano: Microsoft teams rooms](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)

> [!NOTE]
> Microsoft teams Rooms è progettato per l'uso con Microsoft teams, Skype for Business Server 2019, Skype for Business Server 2015 o Skype for business online. <br><br>Non è previsto che le piattaforme precedenti come Lync Server 2013 funzionino con le sale di Microsoft teams.

> [!NOTE]
> Se si usa un server Exchange on-Prem, le sale di Microsoft teams richiedono l'uso di Exchange Server 2013 SP1 o versioni successive.

## <a name="hardware-requirements"></a>Requisiti hardware

Le sale di Microsoft teams possono variare in base a diverse dimensioni della sala tramite accessori a seconda delle periferiche audio e video. L'hardware elencato in questo articolo supporta le modalità di riunione Skype e teams.  Le periferiche audio e video si connettono a Microsoft teams Rooms tramite una connessione USB o HDMI sul dispositivo di ancoraggio. Sarà inoltre necessario:

- Un disco USB da 32GB o più grande che verrà configurato come supporto di installazione di Windows per Windows 10 Enterprise. 

- Uno dei tablet o delle console seguenti:

**Compresse supportate**

|Tablet|Processore|RAM|Disco|
|:-----|:-----|:-----|:-----|
|Surface Pro 6          |Core i5  |16GB o 8GB |128GB o più  |
|Surface Pro (5a generazione)  |Core i5  |8GB o 4GB  |128GB o più  |
|Surface Pro 4          |Core i5  |8GB o 4GB  |128GB o più  |

- Una delle opzioni della stazione di ancoraggio seguenti per proteggere un tablet nella tabella della sala riunioni. 

  - [Logitech SmartDock](https://www.logitech.com/product/smartdock)

  - [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system )

  - [Serie MSR Polycom](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.html)


**Altre console della sala di Microsoft teams supportate**

|Console|Processore|RAM|Disco|
|:-----|:-----|:-----|:-----|
|[Crestron Flex UC-M150-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Tabletop-Conferencing-Systems/UC-M150-T)|Core i7|8GB |128GB |
[Crestron Flex UC-B160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Wall-Mount-Conferencing-Systems/UC-B160-T)|Core i7|8GB |128GB|
|[Crestron Flex UC-C160-T](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-Flex-Integrator-Kits/UC-C160-T)|Core i7|8GB|128GB|
|[HP Elite Slice per sale riunioni G2](https://www8.hp.com/us/en/elite-family/elite-slice-for-meetings.html) |Core i5  |8GB  |128GB  | 
|[HP Elite Slice G2 audio pronto con le sale di Microsoft Teams](https://store.hp.com/us/en/pdp/hp-elite-slice-for-meeting-rooms-g2-skype-room-systems-audio-ready?jumpid=cp_r12131_us/en/psg/elite_slice_for_meetings/product/shop-now-eliteslicemeeting-g2-audio) |Core i5 |8GB |128GB | 
|[Lenovo ThinkSmart Hub 500](https://www3.lenovo.com/us/en/hub500) |Core i5  |8GB  |128GB  |  
|[Logitech Tap](https://www.logitech.com/en-us/product/microsoft-rooms)|Core i5|8GB |128GB |
|[Yealink MVC800](https://www.yealink.com/products_125.html)|Core i5|8GB|128GB|
|[Yealink MVC500](https://www.yealink.com/products_126.html)|Core i5|8GB |128GB |
|||||

> [!NOTE]
> I processori M3 principali non sono supportati.

**Versioni del firmware certificate per periferiche audio e video USB**

|Periferiche Microsoft teams rooms|Versione del firmware certificata per Microsoft teams rooms|
|:-----|:-----|
|[Logitech Rally](https://www.logitech.com/en-us/product/rally-ultra-hd-conferencecam) <br/> |1.2.4 |
|[Logitech BRIO](https://www.logitech.com/en-us/product/brio) <br/> |v240|
|[Logitech MeetUp](http://www.logitech.com/en-us/product/meetup-conferencecam) <br/> |Audio-1.0.172  <br/> Video-1.0.156  <br/> |
|[Logitech ConferenceCam Connect](http://www.logitech.com/en-us/product/conferencecam-connect) <br/> |1.1.248.0  <br/> 1.1.684  <br/> |
|[Gruppo Logitech](http://www.logitech.com/en-us/product/conferencecam-group) <br/> |8.5.778  <br/> |
|[Logitech 930E](http://www.logitech.com/en-us/product/c930e-webcam) <br/> | 8.0.914 <br/> |
|[Logitech PTZ Pro](http://www.logitech.com/en-us/product/conferencecam-ptz-pro) <br/> | 1.1.219 <br/> |
|[Logitech PTZ Pro 2](http://www.logitech.com/en-us/product/conferencecam-ptz-pro2) <br/> |
|[Polycom EagleEye IV](http://www.polycom.com/products-services/hd-telepresence-video-conferencing/realpresence-accessories/eagleeye-cameras.mdl) <br/> |1.0.0  <br/> |
|[Polycom CX5100](http://www.polycom.com/products-services/products-for-microsoft/lync-optimized/cx5100-unified-conference-station.mdl) <br/> | 1.2.0.70232 <br/> |
|[Polycom Eagle Eye Director II](https://www.polycom.com/hd-video-conferencing/peripherals/eagleeye-director-ii.html)|2.1.0.10|
|[Polycom Trio 8500/8800](https://www.polycom.com/voice-conferencing-solutions/conference-phones/trio.html) <br/> |5.7.2.3205|
|[Sennheiser SP 220 MS](http://no-no.sennheiser.com/dual-speakerphones-sp-220-ms-uc) <br/> |2.0.12.0  <br/> |
|[Sennheiser SP20](http://en-us.sennheiser.com/sp-20-og-sp-20-ml) <br/> |1.2.15  <br/> |
|[Sennheiser SP30](https://en-us.sennheiser.com/sp-30) <br/> |2.1.52 <br/>|
|[Jabra 510](http://www.jabra.com/support/Jabra-SPEAK™-510_7510-209) <br/> |2.10.0  <br/> |
|[Jabra 710](http://www.jabra.com/business/speakerphones/jabra-speak-series/jabra-speak-710) <br/> |1.8.0  <br/> |
|[Jabra 810](http://www.jabra.com/supportpages/jabra-speak-810) <br/> |1.2.23  <br/> |
|[Yamaha YVC-1000](http://www.yamaha.com/products/en/communication/usb_conference_speakerphones/yvc-1000/) <br/> |100C  <br/> |

- **Estensioni USB**:

  - Le porte USB nei Dock tablet sono compatibili con USB 3,0. Puoi usare un'estensione USB 2. x, ma in questo modo puoi limitare le velocità di USB 2. x sul lato estremo e non è consigliato per le periferiche USB 3,0.

  - Un estensore deve soddisfare le specifiche USB 2,0 o più recenti.

  - I dock per Tablet supportano almeno due fasi dell'estensione dell'hub USB esterna. Se è necessario connettere più di due hub USB in serie, sarà necessario verificare che sia supportato il produttore del dock per confermare l'operazione.

- Connessione GbE cablata nella sala. Cavo Ethernet di lunghezza appropriata.

- Fino a due schermi 1080p con connessioni HDMI. Cavi HDMI di lunghezza appropriata.

> [!NOTE]
> Un televisore consumer usato come parte anteriore dello schermo della sala deve supportare/abilitare la funzionalità CEC (Consumer Electronics Control) di HDMI in modo che possa passare automaticamente a un'origine video attiva dalla modalità standby. Questa caratteristica non è supportata in tutti i televisori. 

> [!NOTE]
> Microsoft teams Rooms non usa una tastiera. Se necessario, l'amministratore deve usare la tastiera su schermo. Quando si Imaging il dispositivo Microsoft teams Rooms sarà necessario un mouse o una tastiera USB. 

Le tabelle seguenti includono suggerimenti per le periferiche in base alle dimensioni della sala:

**Periferiche audio certificate di Microsoft teams rooms**

|Tipo di sala|Numero di persone|Distanza massima consigliata da microfono a persona che parla|Dispositivo per dimensione massima della sala|Commenti|
|:-----|:-----|:-----|:-----|:-----|
|**Lo attivo** <br/> 10' x 9'  <br/> |2-4  <br/> |1.5 m  <br/> |Logitech Connect  <br/> |I dispositivi Logitech Connect includono una fotocamera, quindi deve essere posizionata nella parte anteriore della sala (non al centro della tabella) per acquisire partecipanti alla riunione locale.  <br/> |
|**Small** <br/> 16' x 16'  <br/> |4-6  <br/> |2,0 m  <br/> |Jabra 510  <br/> Sennheiser SP20  <br/> |Il volume di riproduzione può essere limitato per le camere più grandi.  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |2.4 m  <br/> |Jabra 710  <br/> Jabra 810  <br/> Logitech MeetUp  <br/> Gruppo Logitech  <br/> Polycom Trio  <br/> Polycom CX5100  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS  <br/> |Il Logitech MeetUp include una fotocamera, quindi deve essere posizionata nella parte anteriore della chat room (non al centro della tabella per acquisire partecipanti alla riunione locale).  <br/> In generale, le camere con lunghe tabelle rettangolari o a forma di u possono beneficiare di altri microfoni satellitari.  <br/> SP 220 MS deve essere usato nella configurazione a catena a Margherita.  <br/> |
|**Grande** <br/> 15' x 32'  <br/> |12-16  <br/> |3M  <br/> Questa distanza si applica anche all'area coperta da ogni microfono satellitare aggiuntivo collegato al dispositivo audio in questione.  <br/> |Logitech Group + microfoni satellitari  <br/> Polycom Trio + microfoni satellitari  <br/> Polycom CX5100 + microfoni satellitari  <br/> Sennheiser SP 220 MS  <br/> Yamaha YVC-1000MS + microfoni satellitari  <br/> |Tutti i dispositivi audio elencati in questa riga supportano le opzioni del microfono satellitare.  <br/> CX5100 include una fotocamera di grado 360 incorporata in modo che il dispositivo possa essere posizionato al centro della tabella.  <br/> SP 220 MS deve essere usato nella configurazione a catena a Margherita.  <br/> |

**Periferiche video certificate di Microsoft teams rooms**

|Tipo di sala|Numero di persone|Dispositivo per dimensioni ottimali della sala|Commenti|
|:-----|:-----|:-----|:-----|
|**Lo attivo** <br/> 10' x 9'  <br/> |2-4  <br/> |Logitech Connect  <br/> Logitech MeetUp  <br/> Polycom CX5100  <br/> ||
|**Small** <br/> 16' x 16'  <br/> |4-6  <br/> |Logitech C930e  <br/> Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> |Logitech PTZ Pro spesso in bundle con il gruppo Logitech  <br/> |
|**Media** <br/> 18' x 20'  <br/> |6-12  <br/> |Logitech MeetUp  <br/> Logitech BRIO  <br/> Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||
|**Grande** <br/> 15' x 32'  <br/> |12-16  <br/> |Logitech PTZ Pro  <br/> Polycom MSR  <br/> Polycom CX5100  <br/> ||

 > [!NOTE]
 > Il lato anteriore della risoluzione dello schermo della sala deve essere impostato su non maggiore di 1920x1080p.

## <a name="required-software-downloads"></a>Download di software necessari

Per creare una propria immagine di Microsoft teams rooms, seguire le istruzioni in [configurare una console Microsoft teams Rooms](console.md). Queste istruzioni ti guideranno a scaricare tutto il software necessario per il processo di installazione. 

> [!NOTE]
> I professionisti IT dovranno accedere ai file ISO di Windows 10 Enterprise tramite il contratto multilicenza.

Inoltre, è probabile che tu voglia una copia di [SkypeRoomProvisioningScript. ps1](https://go.microsoft.com/fwlink/?linkid=870105), che puoi usare per eseguire il provisioning degli account di Microsoft teams rooms.

## <a name="see-also"></a>Vedere anche
[Esplorare tutti i bundle](https://products.office.com/en-us/microsoft-teams/across-devices/devices)

[Pianificare le sale di Microsoft Teams](skype-room-systems-v2-0.md)

[Distribuire le sale di Microsoft Teams](room-systems-v2.md)

[Configurare una console Microsoft teams rooms](console.md)

[Gestire le sale di Microsoft Teams](skype-room-systems-v2.md)

[Licenze per i componenti aggiuntivi Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)
