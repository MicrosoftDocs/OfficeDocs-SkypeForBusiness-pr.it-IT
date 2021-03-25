---
title: Configurare l'analisi delle chiamate per Microsoft Teams
ms.author: serdars
author: SerdarSoysal
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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurare l'analisi delle chiamate per utente per identificare e risolvere i problemi di qualità delle chiamate di Microsoft Teams.
ms.openlocfilehash: 209fcad851f5ba7b0183a9988372e249f99cc4fd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117134"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurare l'analisi delle chiamate per Microsoft Teams

Gli amministratori di Microsoft Teams possono usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate e di connessione di Teams per **i singoli utenti.** Per sfruttare al meglio l'analisi delle chiamate, configurare quanto segue:
  
- Assegnare ruoli di supporto specializzati a persone, ad esempio agenti helpdesk, per consentire loro di visualizzare l'analisi delle chiamate per gli utenti. Questi ruoli di supporto non possono accedere al resto dell'interfaccia di amministrazione di Teams. 
    
- Aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file di dati CON ESTENSIONE TSV o CSV.
    
Quando si è pronti per iniziare a usare l'analisi delle chiamate per utente, vedere Usare l'analisi delle chiamate per utente per risolvere i problemi relativi alla [scarsa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Concedere l'autorizzazione al personale del supporto tecnico e dell'helpdesk

L'amministratore di Teams ha accesso completo alle informazioni di analisi per tutti gli utenti. Sono stati creati alcuni ruoli specializzati di Azure Active Directory che è possibile assegnare al personale di supporto e agli agenti dell'helpdesk in modo che possano accedere anche all'analisi delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams). Assegnare il **ruolo di specialista** del supporto per le comunicazioni di Teams agli utenti che devono avere una visualizzazione limitata dell'analisi delle chiamate per utente (supporto di livello 1). Assegnare il ruolo di tecnico **del supporto per** le comunicazioni di Teams agli utenti che hanno bisogno dell'accesso completo all'analisi delle chiamate per utente (supporto di livello 2). Nessuno dei due ruoli ha accesso al resto dell'interfaccia di amministrazione di Teams.

Per informazioni sulle funzioni di ognuno di questi ruoli, vedere Che cosa fa ogni ruolo di supporto [di Teams?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Teams per gestire Teams.](using-admin-roles.md) Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [Visualizzare e assegnare ruoli in Azure Active Directory.](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere Visualizzare [e assegnare ruoli in Azure Active Directory.](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Caricare un file CON ESTENSIONE TSV o CSV per aggiungere informazioni su edifici, siti e tenant

È possibile aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file CSV o TSV. Con tutte queste informazioni, l'analisi delle chiamate può mappare gli indirizzi IP alle posizioni fisiche. Gli amministratori e gli agenti dell'helpdesk possono usare queste informazioni per individuare le tendenze nei problemi di chiamata. Ad esempio, perché gli utenti dello stesso edificio hanno problemi simili di qualità delle chiamate? 

Gli amministratori di Teams o Skype for Business possono usare un tenant esistente e creare un file di dati dal dashboard di qualità delle chiamate di Teams o Skype for Business. Prima di tutto, si scarica il file da CQD, quindi lo si carica per chiamare analytics. 

- Per scaricare un file di dati esistente, passare all'interfaccia di amministrazione di **Microsoft Teams** Call  >  **Quality Dashboard** Upload  >  **now**. **Nell'elenco I miei caricamenti** fare clic **su Scarica** accanto al file desiderato. 

- Per caricare il nuovo file, passare a **Percorsi dell'interfaccia** di amministrazione di Microsoft Teams e quindi selezionare Carica dati posizione o Sostituisci dati  >   **posizione.** 
  
Se si sta creando il file con estensione tsv o csv da zero, vedere Caricare i dati del [tenant e della creazione.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Usare l'analisi delle chiamate per utente per risolvere i problemi relativi alla scarsa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)