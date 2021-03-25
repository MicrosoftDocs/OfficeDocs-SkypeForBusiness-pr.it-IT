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
description: In questo articolo verrà illustrata la procedura per l'aggiornamento del client desktop di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119245"
---
# <a name="teams-update-process"></a>Processo di aggiornamento di Teams

L'app Web di Teams viene aggiornata settimanalmente.

Gli aggiornamenti dei client desktop di Teams vengono rilasciati ogni due settimane dopo rigorosi test interni e convalida tramite il programma TAP (Technology Adoption Program). L'aggiornamento avviene in genere il martedì. Se è necessario un aggiornamento critico, Teams ignora questa pianificazione e rilascia l'aggiornamento non appena è disponibile.

Il client desktop si aggiorna automaticamente. Teams controlla la disponibilità di aggiornamenti ogni poche ore dietro le quinte, lo scarica e quindi attende che il computer sia inattivo prima di installare automaticamente l'aggiornamento.

Gli utenti possono anche scaricare manualmente gli  aggiornamenti **selezionando** Controlla aggiornamenti nel menu a discesa Profilo nell'angolo in alto a destra dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

Gli utenti devono essere connessi per poter scaricare gli aggiornamenti.

A partire dal 31 luglio 2019, gli aggiornamenti dei client di Teams usano una larghezza di banda di rete inferiore durante l'aggiornamento. Questo aggiornamento è attivato per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Per quanto riguarda gli aggiornamenti alle app di Microsoft 365 per le aziende?

Teams viene installato per impostazione predefinita con le nuove installazioni di Microsoft 365 Apps per le aziende, come descritto in [Distribuire Microsoft Teams con Microsoft 365 Apps per le aziende](/DeployOffice/teams-install).

Teams segue il proprio processo di aggiornamento, come descritto sopra. Teams non segue il processo di aggiornamento per le altre app di Office, ad esempio Word ed Excel. Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per Le app di Microsoft 365 per le aziende](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>E gli aggiornamenti di Teams in VDI?


I client di Teams in Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come i client non VDI Teams. È necessario aggiornare l'immagine della macchina virtuale installando un nuovo file MSI come descritto nelle istruzioni per [installare Teams in VDI.](teams-for-vdi.md) È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Gli amministratori possono distribuire gli aggiornamenti invece dell'aggiornamento automatico di Teams?

Teams non consente agli amministratori di distribuire gli aggiornamenti tramite alcun meccanismo di recapito.

## <a name="servicing-agreement"></a>Contratto di manutenzione

Come servizio online moderno, il client Teams si aggiorna automaticamente ogni due settimane. Poiché Teams è disciplinato dai criteri moderni relativi al ciclo di vita, è previsto che gli utenti rimangano nella versione più aggiornata del client desktop. Gli aggiornamenti automatici assicurano agli utenti le funzionalità più recenti, i miglioramenti delle prestazioni, la sicurezza e l'affidabilità dei servizi.

Per identificare quando i client desktop non sono aggiornati, verrà visualizzato un avviso in-app se la versione corrente dell'utente è compresa tra uno e tre mesi e se è disponibile una nuova versione. Questa messaggistica in-app incoraggia gli utenti a eseguire l'aggiornamento alla versione più recente di Teams o, se necessario, a contattare l'amministratore IT per farlo. Gli utenti dei client desktop di Teams che hanno più di tre mesi di età visualizzano una pagina di blocco che offre le opzioni per l'aggiornamento, contattare l'amministratore IT o continuare a utilizzare Teams sul Web.

Le versioni client desktop che hanno più di tre mesi alla prima installazione e/o prima esecuzione di Teams hanno un periodo di tolleranza di 28 giorni prima di riscontrare le informazioni di manutenzione menzionate sopra. Durante questo periodo, il processo di aggiornamento automatico aggiornerà il client di Teams. Se non viene aggiornato, gli utenti riceveranno un avviso in-app che li incoraggia a eseguire manualmente l'aggiornamento alla versione più recente di Teams. Agli utenti potrebbe essere richiesto di contattare l'amministratore IT per eseguire l'aggiornamento. Sono inclusi gli utenti che usano il client desktop di Teams nell'ambito del bundle App di Microsoft 365 per le aziende.

I client desktop di Teams nei cloud governativi hanno attualmente un'eccezione a questo contratto di manutenzione fino a nuovo avviso.

Per informazioni sulle nuove versioni, controllare  [il Centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o passare alla Guida Novità  >   del client.
