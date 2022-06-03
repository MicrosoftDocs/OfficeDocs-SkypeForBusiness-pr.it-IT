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
- m365initiative-deployteams
ms.localizationpriority: high
search.appverid: MET150
description: In questo articolo verranno descritti i requisiti hardware necessari per installare ed eseguire Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39025c0ccd9cb3b7bc02de85719f98f4ec7f3090
ms.sourcegitcommit: 1788f852508208a01f230f6f68a5a81ec8594c47
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860069"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisiti hardware per Microsoft Teams

Tutti i requisiti nelle sezioni seguenti sono validi sia per l'applicazione desktop che per l'app Web di Microsoft Teams.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisiti hardware per Teams su PC Windows

| Componente | Requisiti |
|---------|---------|
|Computer e processore    | Almeno 1,1 GHz o superiore, dual core<br><br>Nota: per i processori Intel, bisogna considerare la velocità massima raggiunta utilizzando la tecnologia Intel Turbo Boost (Max Turbo Frequency)         |
|Memoria     |  4,0 GB di RAM |
|Disco rigido    | 3,0 GB di spazio disponibile su disco        |
|Schermo    |   Risoluzione dello schermo 1024 x 768 |
|Hardware grafico |  Sistema operativo Windows: l'accelerazione grafica hardware richiede DirectX 9 o versione successiva, con WDDM 2.0 o versione successiva per Windows 10 (o WDDM 1.3 o versione successiva per Windows 10 Fall Creators Update)
|Sistema operativo  |    Windows 11, Windows 10 (escluso Windows 10 LTSC), Windows 10 in ARM, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2. Nota: è consigliabile usare la versione di Windows più recente e le patch di sicurezza disponibili.|
|Versione .NET    |  Richiede .NET 4.5 CLR o versione successiva       |
|Video    |  Videocamera USB 2.0       |
|Dispositivi    |   Videocamera, microfono e altoparlanti standard del portatile    |
|Videochiamate e riunioni|<ul><li>Richiede un processore a due core. Per una risoluzione e una frequenza fotogrammi di condivisione video/schermo più elevate, si consiglia un processore a quattro core o superiore.</li> <li>Gli effetti video in background richiedono Windows 10 o un processore con set di istruzioni AVX2.</li> <li>Per un elenco dei decodificatori e codificatori non supportati, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md).</li><li>Per partecipare a una riunione con il rilevamento di prossimità in una sala riunioni di Microsoft Teams è necessario il Bluetooth LE. Questo richiede l'abilitazione del Bluetooth nel dispositivo client, mentre per i client Windows è anche necessario il client Teams a 64 bit. Tale funzionalità non è disponibile nei client Teams a 32 bit.</li></ul> |
|Eventi live in Teams | Se si desidera creare un evento live di Teams, è consigliabile usare un computer con processore Core i5 Kaby Lake con 4,0 GB di RAM (o superiore) e codificatore hardware. Per un elenco dei decodificatori e codificatori **non supportati**, vedere [Suggerimenti sui driver codificatori e decodificatori hardware](hardware-decoders-and-encoders.md). |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisiti hardware per Teams su Mac

| Componente | Requisiti |
|---------|---------|
|Computer e processore    | Processore Intel Core Duo |
|Memoria     |   4,0 GB di RAM|
|Disco rigido    |   1,5 GB di spazio disponibile su disco      |
|Schermo    | Risoluzione 1280 × 800 o superiore    |
|Sistema operativo  |    Una delle tre versioni più recenti di macOS. È possibile trovare informazioni sulle versioni più recenti di macOS e come aggiornare la propria versione di macOS [qui](https://support.apple.com/en-us/HT201260). Ad esempio, quando viene rilasciata una nuova versione di macOS, la nuova versione e le due immediatamente precedenti diventano le versioni supportate.      |
|Video  |    Compatibilità con webcam     |
|Opzioni vocali    |  Compatibilità con microfoni e altoparlanti, auricolari con microfono o dispositivi equivalenti       |
|Videochiamate e riunioni | <ul><li>Richiede un processore a due core. Per una risoluzione e una frequenza fotogrammi di condivisione video/schermo più elevate, si consiglia un processore a quattro core o superiore. </li><li>La funzionalità di partecipazione a una riunione tramite il rilevamento di prossimità in una sala riunioni di Microsoft Teams non è disponibile su macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisiti hardware per Teams su Linux

| Componente | Requisiti |
|---------|---------|
|Computer e processore    | 1,6 GHz o superiore (32 bit o 64 bit), dual core        |
|Memoria     |    4,0 GB di RAM |
|Disco rigido    | 3,0 GB di spazio disponibile su disco        |
|Schermo    |   Risoluzione dello schermo 1024 x 768 |
|Hardware grafico |  128 MB di memoria grafica
|Sistema operativo  | Distribuzione Linux in grado di installare DEB o RPM. |
|Video    |  Videocamera USB 2.0       |
|Dispositivi    |   Videocamera, microfono e altoparlanti standard del portatile    |
|Opzioni vocali    |  Compatibilità con microfoni e altoparlanti, auricolari con microfono o dispositivi equivalenti       |
|Videochiamate e riunioni | <ul><li>Richiede un processore a due core. Per una risoluzione e una frequenza fotogrammi di condivisione video/schermo più elevate, si consiglia un processore a quattro core o superiore.</li><li>La funzionalità di partecipazione a una riunione tramite il rilevamento di prossimità in una sala riunioni di Microsoft Teams non è disponibile su Linux.</li></ul>
|Distribuzioni Linux supportate | Ubuntu 18.04 LTS, 20.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|Ambiente desktop supportato | GNOME, KDE       |
|Server di visualizzazione supportato | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisiti hardware per Teams su dispositivi mobili

È possibile usare Teams sulle piattaforme mobili seguenti:

- Android: compatibilità con telefoni e tablet Android.

  Il supporto è limitato alle **ultime quattro** versioni principali di Android. Ad esempio, quando viene rilasciata una nuova versione principale di Android, il requisito Android è la nuova versione e le tre versioni più recenti che la precedono.

- iOS: compatibilità con iPhone, iPad e iPod touch.

  Il supporto è limitato alle ultime **due** versioni principali di iOS. Ad esempio, quando viene rilasciata una nuova versione principale di iOS, il requisito iOS è la nuova versione e le versioni più recenti che la precedono. L'effetto video opzionale **Sfocatura dello sfondo** su iOS richiede un sistema operativo iOS 12 o successivo, compatibile con i seguenti dispositivi: iPhone 7 o successivo, iPad 2018 (6a generazione) o successivo e iPod touch 2019 (7a generazione).

> [!Note]
> Per un'esperienza ottimale di Teams, usare le versioni di Android e iOS più recenti.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisiti hardware per Teams in un ambiente VDI (Virtual Desktop Infrastructure)

Per i requisiti per l'esecuzione di Teams in un ambiente virtualizzato, vedere [Teams per Virtual Desktop Infrastructure](teams-for-vdi.md).

### <a name="related-topics"></a>Argomenti correlati

- [Ottenere le app di Teams](get-clients.md)
- [Microsoft Teams su dispositivi mobili](https://support.microsoft.com/office/set-up-your-teams-mobile-apps-1ba8dce3-1122-47f4-8db6-00a4f93117e8)
- [Installare l'app Microsoft Teams usando un MSI](msi-deployment.md)
- [Limiti e specifiche per Microsoft Teams](limits-specifications-teams.md)
