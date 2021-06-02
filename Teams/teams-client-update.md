---
title: Teams aggiornamenti
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
description: In questo articolo verrà illustrata la procedura per l'aggiornamento del client desktop Microsoft Teams desktop.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717897"
---
# <a name="teams-update-process"></a>Teams di aggiornamento

L Teams app Web viene aggiornata settimanalmente.

Teams gli aggiornamenti dei client desktop vengono rilasciati ogni due settimane dopo rigorosi test interni e convalida tramite il programma Technology Adoption Program (TAP). L'aggiornamento avviene in genere il martedì. Se è necessario un aggiornamento critico, Teams ignora questa pianificazione e rilascia l'aggiornamento non appena sarà disponibile.

Il client desktop si aggiorna automaticamente. Teams gli aggiornamenti ogni poche ore dietro le quinte, lo scarica e quindi attende che il computer sia inattivo prima di installare automaticamente l'aggiornamento.

Gli utenti possono anche scaricare manualmente gli  aggiornamenti **selezionando** Controlla aggiornamenti nel menu a discesa Profilo nell'angolo in alto a destra dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

Gli utenti devono essere connessi per poter scaricare gli aggiornamenti.

A partire dal 31 luglio 2019, Teams client usano una larghezza di banda di rete inferiore durante l'aggiornamento. Questo aggiornamento è attivato per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Per quanto riguarda gli aggiornamenti Microsoft 365 Apps for enterprise?

Teams viene installato per impostazione predefinita con le nuove installazioni di Microsoft 365 Apps for enterprise come descritto in Distribuire Microsoft Teams [con Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).

Teams il processo di aggiornamento come descritto sopra. Teams non segue il processo di aggiornamento per le altre app di Office, ad esempio Word e Excel. Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Per quanto riguarda gli aggiornamenti Teams in VDI?


Teams client in Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come i client non VDI Teams client. È necessario aggiornare l'immagine della macchina virtuale installando un nuovo file MSI come descritto nelle istruzioni per installare Teams [in VDI.](teams-for-vdi.md) È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Gli amministratori possono distribuire gli aggiornamenti invece Teams l'aggiornamento automatico?

Teams non consente agli amministratori di distribuire gli aggiornamenti tramite alcun meccanismo di recapito.

## <a name="servicing-agreement"></a>Contratto di manutenzione

Come servizio online moderno, il client Teams aggiornamenti automatici ogni due settimane. Poiché Teams è disciplinato dai criteri relativi al ciclo di vita moderno, è previsto che gli utenti rimangano nella versione più aggiornata del client desktop. Gli aggiornamenti automatici assicurano agli utenti le funzionalità più recenti, i miglioramenti delle prestazioni, la sicurezza e l'affidabilità dei servizi.

Per identificare quando i client desktop non sono aggiornati, verrà visualizzato un avviso in-app se la versione corrente dell'utente è compresa tra uno e tre mesi e se è disponibile una nuova versione. Questa messaggistica in-app incoraggia gli utenti a eseguire l'aggiornamento all'ultima versione di Teams o, se necessario, a contattare l'amministratore IT per farlo. Gli utenti Teams client desktop che hanno più di tre mesi di età visualizzano una pagina di blocco che offre le opzioni per l'aggiornamento, contattare l'amministratore IT o continuare a Teams sul Web.

Teams client desktop nei cloud governativi hanno attualmente un'eccezione a questo contratto di manutenzione fino a nuovo avviso.

Per informazioni sulle nuove versioni, controllare  [il Centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o passare alla Guida Novità  >   del client.
