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
description: In questo articolo si apprenderà il processo alla base dell'aggiornamento del client desktop di Microsoft Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f8681f3f4cc7c25e9499e25e3978848084086a2a
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031882"
---
# <a name="teams-update-process"></a>Processo di aggiornamento di Teams

L'app Web di Teams viene aggiornata ogni settimana.

Gli aggiornamenti del client desktop di Teams vengono rilasciati ogni due settimane dopo un rigoroso test e convalida interni tramite il nostro programma Technology Adoption Program (TAP). In genere questo avviene martedì. Se è necessario un aggiornamento critico, Teams ignora questa pianificazione e rilascia l'aggiornamento non appena sarà disponibile.

Il client desktop si aggiorna automaticamente. Teams verifica la presenza di aggiornamenti a poche ore dietro le quinte, lo scarica e quindi attende che il computer sia inattivo prima di installare automaticamente l'aggiornamento.

Gli utenti possono anche scaricare manualmente gli  aggiornamenti facendo **clic su** Controlla aggiornamenti nel menu a discesa Profilo nell'angolo in alto a destra dell'app. Se è disponibile un aggiornamento, verrà scaricato e installato automaticamente quando il computer è inattivo.

Per scaricare gli aggiornamenti, è necessario che gli utenti siano connessi. 

A partire dal 31 luglio 2019, gli aggiornamenti del client Teams usano larghezza di banda di rete notevolmente inferiore durante l'aggiornamento. Questa opzione è attivata per impostazione predefinita e non richiede alcuna azione da parte di amministratori o utenti.

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a>Informazioni sugli aggiornamenti alle app di Microsoft 365 per le aziende

Teams è installato per impostazione predefinita con nuove installazioni di Microsoft 365 Apps for enterprise, come descritto in Distribuire Microsoft Teams con [Microsoft 365 Apps for enterprise.](https://docs.microsoft.com/DeployOffice/teams-install) 

Teams segue il proprio processo di aggiornamento, come descritto in precedenza, e non per le altre app di Office, come Word ed Excel. Per altre informazioni, vedere [Panoramica dei canali di aggiornamento per Microsoft 365 Apps for Enterprise](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)

## <a name="what-about-updates-to-teams-on-vdi"></a>Informazioni sugli aggiornamenti di Teams in VDI

I client di Teams in Virtual Desktop Infrastructure (VDI) non vengono aggiornati automaticamente come i client non VDI Teams. È necessario aggiornare l'immagine della macchina virtuale installando un nuovo file MSI come descritto nelle istruzioni per installare [Teams in VDI.](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi) È necessario disinstallare la versione corrente per eseguire l'aggiornamento a una versione più recente.

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a>Gli amministratori possono distribuire gli aggiornamenti invece dell'aggiornamento automatico di Teams?

Teams non consente agli amministratori di distribuire gli aggiornamenti con alcun meccanismo di distribuzione.

## <a name="servicing-agreement"></a>Contratto di manutenzione

Come servizio online moderno, il client Teams si aggiorna automaticamente ogni due settimane. Poiché Teams è disciplinato dai criteri relativi al ciclo di vita moderno, è previsto che gli utenti rimangano nella versione più aggiornata del client desktop. In questo modo gli utenti potranno disporre delle funzionalità più recenti, dei miglioramenti delle prestazioni, della sicurezza e dell'affidabilità dei servizi.

Per iniziare a identificare quando i client desktop non sono aggiornati, verrà visualizzato un avviso nell'app se la versione corrente dell'utente ha un'età compresa tra uno e tre mesi e se è disponibile una nuova versione. Questa messaggistica in-app incoraggia gli utenti ad eseguire l'aggiornamento all'ultima versione di Teams o, se necessario, a contattare l'amministratore IT per farlo. Gli utenti di client desktop di Teams che hanno più di tre mesi di età vedono una pagina di blocco che offre le opzioni per eseguire subito l'aggiornamento, contattare l'amministratore IT o continuare a utilizzare Teams sul Web.

Le versioni client desktop che hanno più di tre mesi alla prima installazione e/o prima esecuzione di Teams hanno un periodo di tolleranza di 28 giorni prima di riscontrare le informazioni di manutenzione citate. Durante questo periodo, il processo di aggiornamento automatico aggiornerà il client di Teams. Se non viene aggiornato, gli utenti riceveranno un avviso in-app che li incoraggia ad eseguire manualmente l'aggiornamento all'ultima versione di Teams o, se necessario, a contattare l'amministratore IT per farlo. Ciò include gli utenti che usano il client desktop di Teams come parte del bundle di Microsoft 365 Apps for Enterprise.

I client desktop di Teams su Government Clouds hanno attualmente un'eccezione a questo contratto di manutenzione fino a ulteriore avviso.

Per informazioni sui rilasci delle nuove versioni, consultare il [Centro](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) messaggi o passare alla Guida  >  **sulle novità** del client.
