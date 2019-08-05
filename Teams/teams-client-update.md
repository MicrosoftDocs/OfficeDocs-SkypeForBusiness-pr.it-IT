---
title: Aggiornamenti di Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: Informazioni sulla modalità di aggiornamento del client desktop teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184762"
---
# <a name="teams-update-process"></a>Processo di aggiornamento di Teams

L'app teams Web viene aggiornata settimanalmente.

Gli aggiornamenti del client desktop di teams vengono rilasciati ogni due settimane dopo un rigoroso test e convalida interni tramite il programma di adozione della tecnologia (TAP). Questo avviene di solito in un martedì. Se è necessario un aggiornamento critico, teams ignorerà questa programmazione e rilascerà l'aggiornamento non appena sarà disponibile.

Il client desktop si aggiorna automaticamente. Teams verifica la disponibilità di aggiornamenti ogni poche ore dietro le quinte, la Scarica e quindi attende che il computer sia inattivo prima di installare l'aggiornamento in modo invisibile all'utente.

Gli utenti possono anche scaricare gli aggiornamenti manualmente facendo clic su **Controlla aggiornamenti** nel menu a discesa **profilo** nell'angolo in alto a destra dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

Gli utenti devono essere connessi per l'accesso agli aggiornamenti da scaricare. 

A partire dal 9 luglio 2019, gli aggiornamenti del client teams usano una larghezza di banda di rete significativamente inferiore durante l'aggiornamento. Questa opzione è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.


## <a name="what-about-updates-to-office-365-proplus"></a>Informazioni sugli aggiornamenti di Office 365 ProPlus

Per impostazione predefinita, teams viene installato con le nuove installazioni di Office 365 ProPlus, come descritto in [distribuire Microsoft teams con office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams segue il proprio processo di aggiornamento come descritto sopra e non il processo di aggiornamento per le altre app di Office, come Word ed Excel. Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Informazioni sugli aggiornamenti di teams su VDI

I client teams su Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come non sono i client di team non VDI. È necessario aggiornare l'immagine della VM installando un nuovo MSI, come descritto nelle istruzioni per [installare teams in VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Gli amministratori possono distribuire gli aggiornamenti invece dell'aggiornamento automatico dei team?

Teams non dà agli amministratori la possibilità di distribuire gli aggiornamenti attraverso qualsiasi meccanismo di recapito.
