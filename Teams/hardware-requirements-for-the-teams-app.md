---
title: Requisiti hardware per Microsoft Teams
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: In questo articolo vengono illustrati i requisiti hardware necessari per installare ed eseguire Microsoft teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5aeeee4bf16a05b24056a6602f008b5ecaee12bb
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766759"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisiti hardware per Microsoft Teams

Tutti i requisiti nelle sezioni seguenti sono validi sia per l'applicazione desktop che per l'app Web di Microsoft Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisiti hardware per Teams su PC Windows

| Componente | Requisito |
|---------|---------|
|Computer e processore    | Minimo 1,6 GHz (o superiore), 2 Core        |
|Memoria     |    4,0 GB DI RAM     |
|Disco rigido    | 3,0 GB di spazio disponibile su disco        |
|Schermo    |   Risoluzione dello schermo 1024 x 768 |
|Hardware grafico |  Sistema operativo Windows: l'accelerazione hardware grafica richiede DirectX 9 o versione successiva, con WDDM 2,0 o versione successiva per Windows 10 (o WDDM 1,3 o versioni successive per Windows 10 Fall Creators Update)
|Sistema operativo  |    Windows 10, Windows 10 su ARM, Windows 8,1, Windows Server 2019, Windows Server 2016|
|Versione .NET    |  Richiede .NET 4.5 CLR o versione successiva       |
|Video    |  Videocamera USB 2.0       |
|Dispositivi    |   Videocamera, microfono e altoparlanti standard del portatile    |
|Videochiamate e riunioni|<ul><li>Richiede il processore 2-Core. Per una maggiore risoluzione del video e della condivisione dello schermo e la frequenza dei fotogrammi, è consigliabile un processore a 4 core o superiore.</li> <li>Gli effetti video in background richiedono Windows 10 o un processore con set di istruzioni AVX2.</li> <li>Per un elenco dei decodificatori e codificatori non supportati, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md).</li><li>Partecipare a una riunione con il rilevamento di prossimità in una sala Microsoft teams richiede Bluetooth LE, che richiede l'abilitazione di Bluetooth sul dispositivo client e per i client Windows richiede anche il client teams di 64 bit. Questa caratteristica non è disponibile nei client Team di 32 bit.</li></ul> |
|Eventi live in Teams | Se si sta producendo un evento teams Live, è consigliabile usare un computer in cui è installato un processore del lago Core i5 KABY, una RAM da 4,0 GB (o superiore) e un codificatore hardware. Vedere [Suggerimenti per decoder hardware e driver Encoder](hardware-decoders-and-encoders.md) per un elenco di decodificatori e codificatori non **supportati** . |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisiti hardware per Teams su Mac

| Componente | Requisito |
|---------|---------|
|Computer e processore    | Processore Intel Core Duo |
|Memoria     |   4,0 GB DI RAM      |
|Disco rigido    |   1,5 GB di spazio disponibile su disco      |
|Schermo    | Risoluzione 1280 × 800 o superiore    |
|Sistema operativo  |    Una delle tre versioni più recenti di macOS. Puoi trovare informazioni sulle versioni più recenti di macOS e su come eseguire l'aggiornamento della versione di macOS [.](https://support.apple.com/en-us/HT201260) Ad esempio, quando viene rilasciata una nuova versione di macOS, la nuova versione e le due immediatamente precedenti diventano le versioni supportate.      |
|Video  |    Compatibilità con webcam     |
|Opzioni vocali    |  Compatibilità con microfoni e altoparlanti, auricolari con microfono o dispositivi equivalenti       |
|Videochiamate e riunioni | <ul><li>Richiede il processore 2-Core. Per una maggiore risoluzione del video e della condivisione dello schermo e la frequenza dei fotogrammi, è consigliabile un processore a 4 core o superiore. </li><li>La partecipazione a una riunione con il rilevamento di prossimità in una sala Microsoft teams non è disponibile in macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisiti hardware per Teams su Linux

| Componente | Requisito |
|---------|---------|
|Computer e processore    | 1,6 GHz (o superiore) (32 bit o 64 bit), 2 Core        |
|Memoria     |    4,0 GB DI RAM     |
|Disco rigido    | 3,0 GB di spazio disponibile su disco        |
|Schermo    |   Risoluzione dello schermo 1024 x 768 |
|Hardware grafico |  memoria grafica di 128 MB
|Sistema operativo  | Distribuzione Linux in grado di installare DEB o RPM. |
|Video    |  Videocamera USB 2.0       |
|Dispositivi    |   Videocamera, microfono e altoparlanti standard del portatile    |
|Opzioni vocali    |  Compatibilità con microfoni e altoparlanti, auricolari con microfono o dispositivi equivalenti       |
|Videochiamate e riunioni | <ul><li>Richiede il processore 2-Core. Per una maggiore risoluzione del video e della condivisione dello schermo e la frequenza dei fotogrammi, è consigliabile un processore a 4 core o superiore.</li><li>La funzionalità di partecipazione a una riunione tramite il rilevamento di prossimità in una sala riunioni di Microsoft Teams non è disponibile su Linux.</li></ul>
|Distribuzioni Linux supportate | Ubuntu 18,04 LTS, 20,04 LTS, Fedora 30 workstation, RHEL 8 workstation, CentOS 8       |
|Ambiente desktop supportato | GNOME, KDE       |
|Server di visualizzazione supportato | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisiti hardware per Teams su dispositivi mobili

È possibile usare Teams sulle piattaforme mobili seguenti:

- Android: compatibilità con telefoni e tablet Android.

  Il supporto è limitato alle **ultime quattro** versioni principali di Android. Ad esempio, quando viene rilasciata una nuova versione principale di Android, il requisito Android è la nuova versione e le tre versioni più recenti che lo precedono.

- iOS: compatibilità con iPhone, iPad e iPod touch.

  Il supporto è limitato alle **due** versioni principali più recenti di iOS. Ad esempio, quando viene rilasciata una nuova versione principale di iOS, il requisito iOS è la nuova versione e le versioni più recenti che lo hanno preceduto. L'effetto di **sfocatura** del video di sfondo facoltativo su iOS richiede un sistema operativo di iOS 12 o versioni successive, compatibile con i dispositivi seguenti: iPhone 7 o versione successiva, iPad 2018 (sesta generazione) o versione successiva e l'iPod touch 2019 (7a generazione).

> [!Note]
> Per un'esperienza ottimale di Teams, usare le versioni di Android e iOS più recenti.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisiti hardware per Teams in un ambiente VDI (Virtual Desktop Infrastructure)

Per i requisiti per l'esecuzione di Teams in un ambiente virtualizzato, vedere [Teams per Virtual Desktop Infrastructure](teams-for-vdi.md).

### <a name="related-topics"></a>Argomenti correlati

- [Ottenere le app di Teams](get-clients.md)
- [Microsoft Teams su dispositivi mobili](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Installare l'app Microsoft Teams usando un MSI](msi-deployment.md)
- [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md)
