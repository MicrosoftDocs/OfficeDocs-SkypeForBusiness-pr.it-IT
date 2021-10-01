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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
description: Configurare l'analisi delle chiamate per utente per identificare e risolvere i Microsoft Teams di qualità delle chiamate.
ms.openlocfilehash: 1f4e3d6586c699a3f8d9fd0cd782f45361bc69d1
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2021
ms.locfileid: "60045552"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurare l'analisi delle chiamate per Microsoft Teams

L'amministratore Microsoft Teams, è possibile usare l'analisi delle chiamate per utente per risolvere Teams problemi di qualità delle chiamate e di connessione per **i singoli utenti.** Per sfruttare al meglio l'analisi delle chiamate, configurare quanto segue:
  
- Assegnare ruoli di supporto specializzati a persone, ad esempio agenti helpdesk, per consentire loro di visualizzare l'analisi delle chiamate per gli utenti. Questi ruoli di supporto non possono accedere al resto dell'interfaccia Teams di amministrazione. 
    
- Aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file di dati con estensione tsv o .csv dati.
    
Quando si è pronti per iniziare a usare l'analisi delle chiamate per utente, vedere Usare l'analisi delle chiamate per utente per risolvere i problemi relativi alla [scarsa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Concedere l'autorizzazione al personale del supporto tecnico e dell'helpdesk

L'amministratore Teams ha accesso completo alle informazioni di analisi per tutti gli utenti. Sono stati creati alcuni ruoli di Azure Active Directory specializzati che è possibile assegnare al personale di supporto e agli agenti dell'helpdesk in modo che possano accedere anche all'analisi delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams). Assegnare **il Teams** di supporto per le comunicazioni a utenti che devono avere una visualizzazione limitata dell'analisi delle chiamate per utente (supporto di livello 1). Assegnare il Teams tecnico del **supporto** per le comunicazioni agli utenti che hanno bisogno dell'accesso completo all'analisi delle chiamate per utente (supporto di livello 2). Nessuno dei due ruoli ha accesso al resto dell'Teams di amministrazione.

Per informazioni sulle funzioni di ognuno di questi ruoli, vedere Che cosa fa ogni Teams [di supporto tecnico?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Per altre informazioni sui ruoli Teams di amministratore, vedere Usare i ruoli di Teams [di amministratore](using-admin-roles.md)per gestire Teams . Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory](/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Upload un file con estensione tsv o .csv per aggiungere informazioni su edifici, siti e tenant

È possibile aggiungere informazioni su edifici, siti e tenant all'analisi delle chiamate per utente caricando un file .csv o tsv. Con tutte queste informazioni, l'analisi delle chiamate può mappare gli indirizzi IP alle posizioni fisiche. Gli amministratori e gli agenti dell'helpdesk possono usare queste informazioni per individuare le tendenze nei problemi di chiamata. Ad esempio, perché gli utenti dello stesso edificio hanno problemi simili di qualità delle chiamate? 

Gli amministratori di Teams o Skype for Business possono usare un tenant esistente e un file di dati di creazione dal Teams o Skype for Business Call Quality Dashboard (CQD). Prima di tutto, si scarica il file da CQD, quindi lo si carica per chiamare l'analisi. 

- Per scaricare un file di dati esistente, passare a Microsoft Teams di amministrazione  >  **Analytics & report** call quality  >  **dashboard** Upload  >  **now**. **Nell'elenco I miei caricamenti** fare clic **su Scarica** accanto al file desiderato. 

- Per caricare il nuovo file, passare Microsoft Teams percorsi **dell'interfaccia** di amministrazione e quindi selezionare Upload posizione o Sostituisci  >  dati **posizione.** 
  
Se si sta creando il file tsv o .csv file da zero, vedere Upload [tenant e dati di creazione.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Usare l'analisi delle chiamate per utente per risolvere i problemi relativi alla scarsa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Risoluzione dei problemi di Teams](/MicrosoftTeams/troubleshoot/teams)