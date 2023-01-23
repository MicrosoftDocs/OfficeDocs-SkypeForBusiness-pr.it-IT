---
title: Richiedere una filigrana per le riunioni sensibili di Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: Informazioni su come abilitare o richiedere filigrane sul video dei partecipanti e sui contenuti condivisi nelle riunioni sensibili di Teams.
ms.openlocfilehash: 6037bc6e9dbe79d9ecee10666f4c34e4e778216a
ms.sourcegitcommit: 5e0900ed7a21ed4e854cc00dbfb4ae4ff2372262
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2023
ms.locfileid: "69950503"
---
# <a name="require-a-watermark-for-sensitive-teams-meetings"></a>Richiedere una filigrana per le riunioni sensibili di Teams

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

È possibile abilitare la visualizzazione di una filigrana nelle riunioni di Teams sia per il contenuto condiviso sullo schermo che per il video dei partecipanti. La filigrana visualizza l'indirizzo di posta elettronica del partecipante alla riunione. I partecipanti alla riunione non possono disattivare la filigrana.

Le filigrane sono supportate in Teams per desktop e dispositivi mobili. Persone partecipare a riunioni da piattaforme non supportate avrà un'esperienza solo audio.

I partecipanti che partecipano da [Cloud Video Interop (CVI)](cloud-video-interop.md) potranno vedere il contenuto senza filigrane.

I partecipanti seguenti hanno un'esperienza solo audio quando una filigrana è in uso:

- Partecipanti che usano il client Web di Teams
- partecipanti Virtual Desktop Infrastructure (VDI)
- Partecipanti anonimi
- Partecipanti in overflow
- Microsoft Teams Rooms in Windows e Microsoft Teams Rooms su Surface Hub
- Microsoft Teams Rooms su Android
- Client di Teams meno recenti
- [Partecipazione guest diretta su dispositivi Microsoft Teams Rooms](/microsoftteams/rooms/third-party-join)

> [!Note]
> Le impostazioni delle riunioni in etichette di riservatezza, modelli di riunione personalizzati e filigrane richiedono Teams Premium.

Le filigrane per le riunioni sono abilitate nell'interfaccia di amministrazione di Teams. Possono quindi essere aggiunti dall'organizzatore della riunione o applicati da un modello o da un'etichetta di riservatezza.

La tabella seguente mostra dove sono configurate le filigrane:

|Impostazione|criteri di Amministrazione|Etichetta di riservatezza|Modello|Organizzatore della riunione|
|:------|:----------:|:---------------:|:------:|:---------------:|
|Applicare una filigrana al contenuto condiviso|Sì|Sì|Sì|Sì|
|Applicare una filigrana al feed video di tutti gli utenti|Sì|Sì|Sì|Sì|

Quando si usa una filigrana in una riunione, le caratteristiche seguenti sono disattivate:

- Registrazione della riunione, inclusa la registrazione automatica

- Raccolta di grandi dimensioni

- Modalità Insieme

- PowerPoint Live

- Whiteboard

- Contenuto dalla fotocamera

## <a name="watermarks-for-sensitive-and-highly-sensitive-meetings"></a>Filigrane per riunioni sensibili e altamente sensibili

Le filigrane possono essere utili per proteggere le informazioni riservate condivise nelle riunioni. Questa opzione è particolarmente utile quando si condividono informazioni con utenti che normalmente non hanno accesso alle informazioni. Ad esempio, un membro dell'organizzazione finanziaria potrebbe usare filigrane quando condivide le stime trimestrali con i responsabili di divisioni diverse.

Poiché le filigrane sono progettate per ridurre le possibilità che le informazioni riservate vengano esfiltrate, usarle nelle riunioni in cui tutti i partecipanti hanno accesso diretto al contenuto condiviso, potrebbero non aumentare la sicurezza.

Per informazioni sull'uso di filigrane con altre funzionalità per le riunioni per proteggere le informazioni riservate nelle riunioni, vedere [Configurare le riunioni di Teams con la protezione dei dati altamente sensibili](/microsoftteams/configure-meetings-highly-sensitive-protection).

## <a name="enable-watermarks"></a>Abilitare le filigrane

Affinché le filigrane siano disponibili nei modelli e nelle etichette di riservatezza e per l'organizzatore della riunione, devono essere abilitate nell'interfaccia di amministrazione di Teams.

Per abilitare le filigrane per le riunioni

1. Nell'interfaccia di amministrazione di Teams espandere **Riunioni** e selezionare **Criteri riunione**.

1. Selezionare il criterio da aggiornare.

1. Per abilitare la filigrana nel video dei partecipanti, impostare **Video filigrana** **su Attivato**.

1. Per abilitare la filigrana per il contenuto condiviso sullo schermo in una riunione, impostare **Filigrana contenuto condiviso** **su Attivato**.

    ![Screenshot dei criteri di amministrazione di Teams per le filigrane](media/watermark-admin-policy.png)

1. Per vedere come apparirà la filigrana su desktop e dispositivi mobili, seleziona **Anteprima**.

1. Selezionare **Salva**.

È anche possibile abilitare o disabilitare le filigrane con PowerShell. Utilizzare il cmdlet [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) con i `-AllowWatermarkForCameraVideo` parametri e `-AllowWatermarkForScreenSharing` .

Ad esempio:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForCameraVideo $True 

Set-CsTeamsMeetingPolicy -Identity Global -AllowWatermarkForScreenSharing $True 
```

## <a name="related-topics"></a>Argomenti correlati

[Configurare le riunioni di Teams con tre livelli di protezione](configure-meetings-three-tiers-protection.md)

[Usare i modelli di riunione di Teams, le etichette di riservatezza e i criteri di amministrazione insieme per le riunioni riservate](meeting-templates-sensitivity-labels-policies.md)
