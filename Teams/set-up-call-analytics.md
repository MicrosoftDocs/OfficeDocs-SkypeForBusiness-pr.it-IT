---
title: Configurare l'analisi delle chiamate per Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: fbf7247a-84ae-46cc-9204-2c45b1c734cd
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurare l'analisi delle chiamate per utente per identificare e risolvere i problemi di qualità delle chiamate di Microsoft Teams.
ms.openlocfilehash: bcfe39ccdd9a1a751b49cdc8d0f433e3707635e3
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789941"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurare l'analisi delle chiamate per Microsoft Teams

Gli amministratori di Microsoft Teams possono usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate e di connessione di Teams per **i singoli utenti**. Per sfruttare al meglio l'analisi delle chiamate, configurare quanto segue:
  
- Assegnare ruoli di supporto specializzati alle persone, ad esempio agenti helpdesk, per consentire loro di visualizzare l'analisi delle chiamate per gli utenti. Questi ruoli di supporto non possono accedere al resto dell'interfaccia di amministrazione di Teams. 
    
- Aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file di dati con estensione tsv o .csv.
    
Quando sei pronto per iniziare a usare l'analisi delle chiamate per utente, leggi [Usare l'analisi delle chiamate per utente per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Concedere l'autorizzazione al personale di supporto e helpdesk

L'amministratore di Teams ha accesso completo alle informazioni di analisi delle chiamate per tutti gli utenti. Abbiamo creato alcuni ruoli specializzati di Azure Active Directory che è possibile assegnare al supporto del personale e agli agenti helpdesk in modo che possano anche accedere all'analisi delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams). Assegnare il ruolo **di specialista del supporto per le comunicazioni di Teams** agli utenti che dovrebbero avere una visualizzazione limitata dell'analisi delle chiamate per utente (supporto di Livello 1). Assegnare il ruolo di **ingegnere del supporto per le comunicazioni di Teams** agli utenti che hanno bisogno dell'accesso completo all'analisi delle chiamate per utente (supporto di Livello 2). Nessun ruolo ha accesso al resto dell'interfaccia di amministrazione di Teams.

Per informazioni sulle funzioni di ognuno di questi ruoli, leggere [Cosa fa ogni ruolo di supporto di Teams](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Teams per gestire Teams](using-admin-roles.md). Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [Visualizzare e assegnare ruoli in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere [Visualizzare e assegnare ruoli in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Caricare un file con estensione tsv o .csv per aggiungere informazioni su edifici, siti e tenant

È possibile aggiungere informazioni relative a edifici, siti e tenant all'analisi delle chiamate per utente caricando un file di .csv o tsv. Con tutte queste informazioni, l'analisi delle chiamate può mappare gli indirizzi IP alle posizioni fisiche. Gli amministratori e gli agenti helpdesk possono usare queste informazioni per individuare le tendenze nei problemi di chiamata. Ad esempio, perché gli utenti nello stesso edificio hanno problemi di qualità delle chiamate simili? 

Se sei un amministratore di Teams o di Skype for Business, puoi usare un file di dati del tenant e dell'edificio esistente da Teams o Skype for Business Call Quality Dashboard (CQD). Prima di tutto, scaricare il file da Call Quality Dashboard, quindi caricarlo per chiamare l'analisi. 

- Per scaricare un file di dati esistente, vai **all'interfaccia** >  di amministrazione di Microsoft Teams **Analytics & segnala** > **caricamento call quality dashboard** > **ora**. Nell'elenco **Caricamenti personali** fare clic su **Scarica** accanto al file desiderato. 

- Per caricare il nuovo file, vedere [Aggiungere e aggiornare le etichette dei report](/microsoftteams/learn-more-about-site-upload).
  
Se si sta creando il file con estensione tsv o .csv da zero, vedere [Caricare i dati del tenant e dell'edificio](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Usare l'analisi delle chiamate per utente per risolvere problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)
