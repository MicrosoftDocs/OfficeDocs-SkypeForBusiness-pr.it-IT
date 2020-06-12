---
title: Requisiti hardware per Microsoft Teams
ms.reviewer: microthk, sthurlow
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: In questo articolo verranno illustrati i requisiti hardware necessari per installare ed eseguire Microsoft teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3096673df464b02ae828423c5aebf8690a7ab853
ms.sourcegitcommit: 862ba1d2b3bd4622b1b0baa15096c29c591cc6c4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2020
ms.locfileid: "44702621"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisiti hardware per Microsoft Teams

Tutti i requisiti nelle sezioni seguenti sono validi sia per l'applicazione desktop che per l'app Web di Microsoft Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisiti hardware per Teams su PC Windows

|**Componente**|**Requisito**  |
|---------|---------|
|Computer e processore    | Minimo 1,6 GHz o superiore (32 bit o 64 bit).        |
|Memoria     |    2,0 GB di RAM     |
|Disco rigido    | 3,0 GB di spazio disponibile su disco        |
|Schermo    |   Risoluzione dello schermo 1024 x 768 |
|Hardware grafico |  Almeno 128 MB di memoria grafica
|Sistema operativo  |    Windows Server 2012 R2+, Windows 10 o Windows 8.1 versione a 32 bit e 64 bit. Per un'esperienza ottimale, usare la versione più recente del sistema operativo.|
|Versione .NET    |  Richiede .NET 4.5 CLR o versione successiva       |
|Video    |  Videocamera USB 2.0       |
|Dispositivi    |   Videocamera, microfono e altoparlanti standard del portatile    | 
|Videochiamate e riunioni | <ul><li>Per una migliore esperienza con le videochiamate di 1:1, è consigliabile usare un computer con processore single-core e 4,0 GB di RAM (o versioni successive). </li><li>Per una migliore esperienza con le riunioni online, è consigliabile usare un computer con processore dual-core e 8,0 GB di RAM (o versioni successive). </li><li>Gli **effetti video di sfondo** facoltativi non sono supportati nei processori senza un set di istruzioni AVX2 in uso in Windows 8,1 o successiva.</li><li>Per un elenco dei decodificatori e codificatori non supportati, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md).</li><li>Per partecipare a una riunione con il rilevamento di prossimità in una sala riunioni di Microsoft Teams è necessario il Bluetooth LE, il quale richiede l'abilitazione del Bluetooth nel dispositivo client, mentre per i client Windows è necessario il client Teams a 64 bit. Non è disponibile nei client Teams a 32 bit.</li></ul> |
|Eventi live in Teams | Se si sta producendo un evento teams Live, è consigliabile usare un computer in cui è installato un processore per Lake KABY di Core i5, 4,0 GB di RAM (o superiore) e hardware Encoder. Per un elenco dei decodificatori e codificatori non supportati, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md). |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisiti hardware per Teams su Mac

|**Componente**|**Requisito**  |
|---------|---------|
|Processore    | Processore Intel minimo, Core 2 Duo o superiore |
|Memoria     |   2,0 GB di RAM      |
|Disco rigido    |   1,5 GB di spazio disponibile su disco      |
|Schermo    | Risoluzione 1280 × 800 o superiore    |
|Sistema operativo  |    Mac OS X 10.11 El Capitan o versione successiva     |
|Video  |    Compatibilità con webcam     |
|Opzioni vocali    |  Compatibilità con microfoni e altoparlanti, auricolari con microfono o dispositivi equivalenti       |
|Videochiamate e riunioni | <ul><li>Per una migliore esperienza con le videochiamate di 1:1, è consigliabile usare un computer con processore single-core e 4,0 GB di RAM (o versioni successive). </li><li>Per una migliore esperienza con le riunioni online, è consigliabile usare un computer con processore dual-core e 8,0 GB di RAM (o versioni successive).</li><li>Per un elenco dei decodificatori e codificatori non supportati, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md).</li><li>La funzionalità di partecipazione a una riunione tramite il rilevamento di prossimità in una sala riunioni di Microsoft Teams non è disponibile su Mac OS.</li></ul> |

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisiti hardware per Teams su Linux

|**Componente**|**Requisito**  |
|---------|---------|
|Computer e processore    | Minimo 1,6 GHz o superiore (32 bit o 64 bit).        |
|Memoria     |    2,0 GB di RAM     |
|Disco rigido    | 3,0 GB di spazio disponibile su disco        |
|Schermo    |   Risoluzione dello schermo 1024 x 768 |
|Hardware grafico |  Almeno 128 MB di memoria grafica
|Sistema operativo  | Distribuzione Linux in grado di installare DEB o RPM. |
|Video    |  Videocamera USB 2.0       |
|Dispositivi    |   Videocamera, microfono e altoparlanti standard del portatile    | 
|Opzioni vocali    |  Compatibilità con microfoni e altoparlanti, auricolari con microfono o dispositivi equivalenti       |
|Videochiamate e riunioni | <ul><li>Per una migliore esperienza con le videochiamate di 1:1, è consigliabile usare un computer con processore single-core e 4,0 GB di RAM (o versioni successive). </li><li>Per una migliore esperienza con le riunioni online, è consigliabile usare un computer con processore dual-core e 8,0 GB di RAM (o versioni successive).</li><li>Per un elenco dei decodificatori e codificatori non supportati, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md).</li><li>La funzionalità di partecipazione a una riunione tramite il rilevamento di prossimità in una sala riunioni di Microsoft Teams non è disponibile su Linux.</li></ul>
|Distribuzioni Linux supportate | Ubuntu 16.04 LTS, 18.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisiti hardware per Teams su dispositivi mobili

È possibile usare Teams sulle piattaforme mobili seguenti:

- Android: compatibilità con telefoni e tablet Android.

  Il supporto è limitato alle ultime quattro versioni principali di Android. Quando viene rilasciata una nuova versione principale di Android, sono ufficialmente supportate la nuova versione e le tre versioni precedenti.

- iOS: compatibilità con iPhone, iPad e iPod touch.

  Il supporto è limitato alle ultime due versioni principali di iOS. Quando viene rilasciata una nuova versione principale di iOS, sono ufficialmente supportate la nuova versione e la versione precedente.
  L'effetto di **sfocatura** del video di sfondo facoltativo su iOS richiede un sistema operativo di iOS 12 o versioni successive ed è compatibile con i dispositivi seguenti: iPhone 7 o versione successiva, iPad 2018 (sesta generazione) o versione successiva e l'iPod touch 2019 (7a generazione).

Per un'esperienza ottimale di Teams, usare le versioni di Android e iOS più recenti.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisiti hardware per Teams in un ambiente VDI (Virtual Desktop Infrastructure)

Per i requisiti per l'esecuzione di Teams in un ambiente virtualizzato, vedere [Teams per Virtual Desktop Infrastructure](teams-for-vdi.md).

### <a name="related-topics"></a>Argomenti correlati
- [Ottenere le app di Teams](get-clients.md)
- [Microsoft Teams su dispositivi mobili](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installare l'app Microsoft Teams usando un MSI](msi-deployment.md)
- [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md)
