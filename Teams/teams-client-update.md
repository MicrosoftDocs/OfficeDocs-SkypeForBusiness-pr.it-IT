---
title: Aggiornamenti di Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: In questo articolo viene illustrato il processo alla base dell'aggiornamento del client desktop di Microsoft Teams.
localization_priority: Priority
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 96077e5b50dff12f29f6e1ccf903cd0f7de96352dacf0d8b3c2cc7406750737e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321138"
---
# <a name="teams-update-process"></a>Processo di aggiornamento di Teams

L'app Web di Teams viene aggiornata ogni settimana.

Gli aggiornamenti del client desktop di Teams vengono rilasciati ogni due settimane dopo un rigoroso controllo interno e la convalida tramite il Programma di adozione della tecnologia (Technology Adoption Program, TAP). L'aggiornamento viene in genere eseguito il martedì. Se è necessario un aggiornamento critico, Teams ignorerà la pianificazione e rilascerà l'aggiornamento non appena disponibile.

Il client desktop si aggiorna automaticamente. Teams verifica la disponibilità di aggiornamenti in background, li scarica e quindi attende il periodo di inattività sul computer prima di installare automaticamente l'aggiornamento.

Gli utenti possono anche scaricare manualmente gli aggiornamenti selezionando **Verifica disponibilità aggiornamenti** nel menu a discesa **Profilo** in alto a destra nell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

Gli utenti devono eseguire l'accesso per scaricare gli aggiornamenti.

A partire dal 31 luglio 2019, gli aggiornamenti del client di Teams usano una larghezza di banda di rete inferiore durante l'aggiornamento. Questo aggiornamento è attivato per impostazione predefinita e non richiede alcuna azione da parte degli amministratori o degli utenti.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>E gli aggiornamenti a Microsoft 365 Apps for enterprise?

Teams viene installato per impostazione predefinita con le nuove installazioni di Microsoft 365 Apps for enterprise come descritto in [Distribuire Microsoft Teams con Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).

Teams segue il proprio processo di aggiornamento, come descritto in precedenza. Teams non segue il processo di aggiornamento per le altre app di Office, come Word ed Excel. Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus).

## <a name="what-about-updates-to-teams-on-vdi"></a>E gli aggiornamenti a Teams in VDI?


I client Teams su Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come i client Teams non VDI. È necessario aggiornare l'immagine della macchina virtuale installando una nuova MSI come descritto nelle istruzioni per [Installare Teams in VDI](teams-for-vdi.md). È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Gli amministratori possono distribuire gli aggiornamenti invece dell'aggiornamento automatico di Teams?

Teams non offre agli amministratori la possibilità di distribuire gli aggiornamenti tramite meccanismi di recapito.

## <a name="servicing-agreement"></a>Contratto di manutenzione

Come servizio online moderno, il client di Teams si aggiorna automaticamente ogni due settimane. Poiché Teams è regolato dai criteri del ciclo di vita moderno, è previsto che gli utenti abbiano la versione più aggiornata del client desktop. Gli aggiornamenti automatici assicurano che gli utenti dispongano delle funzionalità più recenti, dei miglioramenti delle prestazioni, della sicurezza e dell'affidabilità del servizio.

Per identificare se i client desktop non sono aggiornati, l'app mostrerà un avviso se la versione corrente dell'utente ha tra uno e tre mesi ed è disponibile una nuova versione. Questi messaggi in-app incoraggiano gli utenti ad aggiornare Teams alla versione più recente o, se necessario, a contattare l'amministratore IT per fare ciò. I clienti desktop di Teams che hanno più di tre mesi visualizzeranno una pagina di blocco che fornisce opzioni per l'aggiornamento immediato, per contattare l'amministratore IT o continuare a usare Teams sul Web.

I client desktop di Teams nei cloud per enti pubblici al momento sono esclusi da questo contratto di servizio fino a nuovo avviso.

Per informazioni sui rilasci di nuove versioni, vedere il [Centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o passare a **Guida** > **Novità** nel client.
