---
title: Aggiornamenti di Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: Informazioni sulla modalità di aggiornamento del client desktop teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a76fe4e0cfb896d1bd89a02acebc1c00dff8767
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776831"
---
# <a name="teams-update-process"></a>Processo di aggiornamento di Teams

L'app teams Web viene aggiornata settimanalmente.

Gli aggiornamenti del client desktop di teams vengono rilasciati ogni due settimane dopo un rigoroso test e convalida interni tramite il programma di adozione della tecnologia (TAP). Questo avviene di solito in un martedì. Se è necessario un aggiornamento critico, teams ignorerà questa programmazione e rilascerà l'aggiornamento non appena sarà disponibile.

Il client desktop si aggiorna automaticamente. Teams verifica la disponibilità di aggiornamenti ogni poche ore dietro le quinte, la Scarica e quindi attende che il computer sia inattivo prima di installare l'aggiornamento in modo invisibile all'utente.

Gli utenti possono anche scaricare gli aggiornamenti manualmente facendo clic su **Controlla aggiornamenti** nel menu a discesa **profilo** nell'angolo in alto a destra dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

Gli utenti devono essere connessi per l'accesso agli aggiornamenti da scaricare. 

A partire dal 31 luglio 2019, gli aggiornamenti del client teams usano una larghezza di banda di rete significativamente inferiore durante l'aggiornamento. Questa opzione è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Informazioni sugli aggiornamenti delle app Microsoft 365 per le aziende

Per impostazione predefinita, teams viene installato con le nuove installazioni delle app Microsoft 365 per le aziende, come descritto in [distribuire Microsoft teams con le app microsoft 365 per le aziende](https://docs.microsoft.com/DeployOffice/teams-install). 

Teams segue il proprio processo di aggiornamento come descritto sopra e non il processo di aggiornamento per le altre app di Office, come Word ed Excel. Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per le app Microsoft 365 per le aziende](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Informazioni sugli aggiornamenti di teams su VDI

I client teams su Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come non sono i client di team non VDI. È necessario aggiornare l'immagine della VM installando un nuovo MSI, come descritto nelle istruzioni per [installare teams in VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi). Devi disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Gli amministratori possono distribuire gli aggiornamenti invece dell'aggiornamento automatico dei team?

Teams non dà agli amministratori la possibilità di distribuire gli aggiornamenti attraverso qualsiasi meccanismo di recapito.

## <a name="servicing-agreement"></a>Contratto di manutenzione

Come servizio online moderno, il client teams si aggiorna automaticamente ogni due settimane. Poiché teams è regolato dai criteri di ciclo di vita moderni, è previsto che gli utenti rimangano nella versione più aggiornata del client desktop. Questo garantisce agli utenti le funzionalità più recenti, i miglioramenti delle prestazioni, la sicurezza e l'affidabilità dei servizi.

Per iniziare a fornire assistenza per identificare quando i client desktop non sono aggiornati, verrà visualizzato un avviso in-app se la versione corrente dell'utente è compresa tra uno e tre mesi e se è disponibile una nuova versione. Questa messaggistica in-app incoraggia gli utenti ad aggiornare l'ultima versione di teams o, se necessario, a raggiungere l'amministratore IT. Gli utenti dei client desktop di teams che hanno più di tre mesi vedranno una pagina di blocco che fornisce le opzioni per l'aggiornamento ora, per raggiungere l'amministratore IT o per continuare a teams sul Web.

Le versioni client desktop che hanno più di tre mesi prima dell'installazione e/o della prima esecuzione di teams hanno un periodo di tolleranza di 28 giorni prima di rispondere alle suddette informazioni sulla manutenzione. Durante questo periodo, il processo di aggiornamento automatico aggiornerà il client teams. Se non viene aggiornato, gli utenti vedranno un avviso in-app per incoraggiarli ad aggiornare manualmente l'ultima versione di teams o, se necessario, per contattare l'amministratore IT. Ciò include gli utenti che usano il client desktop teams come parte del bundle delle app Microsoft 365 per l'organizzazione.

I client desktop di teams su cloud governativi hanno attualmente un'eccezione a questo contratto di manutenzione fino a nuovo avviso.

Per informazioni sulle nuove versioni della versione, selezionare [centro messaggi](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) o Vai **alle** > **novità** del client.
