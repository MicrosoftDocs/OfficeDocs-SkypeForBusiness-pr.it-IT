---
title: Configurare le analisi delle chiamate per Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
description: Configurare le analisi delle chiamate per utente per identificare e risolvere i problemi di qualità delle chiamate di Microsoft teams.
ms.openlocfilehash: 233d91a60ea783238e10ed1baa02334494ef6e08
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085312"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurare le analisi delle chiamate per Microsoft Teams

Come amministratore di Microsoft teams, puoi usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate dei team e per i **singoli utenti**. Per sfruttare al meglio l'analisi delle chiamate, configurare le operazioni seguenti:
  
- Assegnare ruoli di supporto specializzati alle persone, ad esempio gli agenti dell'helpdesk, per consentire loro di visualizzare le analisi delle chiamate per gli utenti. Questi ruoli di supporto non possono accedere al resto dell'interfaccia di amministrazione di teams. 
    
- Aggiungere informazioni su edifici, siti e tenant a analisi delle chiamate per utente tramite il caricamento di un file di dati con estensione TSV o CSV.
    
Quando si è pronti per iniziare a usare l'analisi delle chiamate per utente, leggere [usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md).
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Concedere l'autorizzazione per il supporto e il personale dell'helpdesk

L'amministratore di Teams ha accesso completo alle informazioni di analisi delle chiamate per tutti gli utenti. È stato creato un certo ruolo di Azure Active Directory specializzato che è possibile assegnare al personale di supporto e agli agenti dell'helpdesk in modo che possano accedere anche all'analisi delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams). Assegna il ruolo di **specialista delle comunicazioni teams** agli utenti che dovrebbero avere una visione limitata dell'analisi delle chiamate per utente (supporto di Tier 1). Assegnare il ruolo di **Assistente tecnico comunicazioni teams** agli utenti che hanno bisogno di un accesso completo all'analisi delle chiamate per utente (supporto di Tier 2). Nessun ruolo ha accesso al resto dell'interfaccia di amministrazione di teams.

Per informazioni su cosa fa ognuno di questi ruoli, leggere [cosa fa il ruolo di supporto di ogni team](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)?

Per altre informazioni sui ruoli di amministratore di teams, vedere [usare i ruoli di amministratore di teams per gestire teams](using-admin-roles.md). Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere [visualizzare e assegnare ruoli in Azure Active Directory](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal).

Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere [visualizzare e assegnare ruoli in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal).

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Caricare un file con estensione TSV o CSV per aggiungere informazioni su edifici, siti e tenant

È possibile aggiungere informazioni su edifici, siti e tenant a analisi delle chiamate per utente tramite il caricamento di un file CSV o TSV. Con tutte queste informazioni, Call Analytics può eseguire il mapping degli indirizzi IP alle posizioni fisiche. Gli amministratori e gli agenti dell'helpdesk possono usare queste informazioni per individuare le tendenze dei problemi di chiamata. Ad esempio, perché gli utenti nello stesso edificio hanno problemi di qualità delle chiamate simili? 

Se si è un team o un amministratore di Skype for business, è possibile usare un tenant e un file di dati di costruzione esistenti dal team o da Skype for business call Quality Dashboard (Call Quality Dashboard). Prima di tutto, si Scarica il file da Call Quality dashboard, quindi lo si carica in analisi chiamata. 

- Per scaricare un file di dati esistente, passa a **Microsoft teams Admin Center**  >  **Call Quality dashboard**  >  **Upload Now**. Nell'elenco **upload personali** fare clic su **Scarica** accanto al file desiderato. 

- Per caricare il nuovo file, accedere alle posizioni dell'interfaccia di **amministrazione di Microsoft teams**  >  **Locations**e quindi selezionare **Carica dati posizione** o **Sostituisci dati posizione**.
  
Se si sta creando il file TSV o CSV da zero, vedere caricare i [dati del tenant e della creazione](CQD-upload-tenant-building-data.md).
  
## <a name="related-topics"></a>Argomenti correlati

[Usare le analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
