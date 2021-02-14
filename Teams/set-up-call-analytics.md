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
ms.openlocfilehash: f1ea46f275dfbbe5ea7f6cd40d8c06fba2b5e00f
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581107"
---
# <a name="set-up-call-analytics-for-microsoft-teams"></a>Configurare l'analisi delle chiamate per Microsoft Teams

Come amministratore di Microsoft Teams, puoi usare l'analisi delle chiamate per utente per risolvere i problemi di qualità delle chiamate e di connessione di Teams **per i singoli utenti.** Per sfruttare al meglio i dati analitici delle chiamate, configura quanto segue:
  
- Assegnare ruoli speciali di supporto alle persone, ad esempio agenti helpdesk, per consentire loro di visualizzare i dati analitici delle chiamate per gli utenti. Questi ruoli di supporto non possono accedere al resto dell'interfaccia di amministrazione di Teams. 
    
- Aggiungi informazioni a livello di edificio, sito e tenant all'analisi delle chiamate per utente caricando un file di dati .tsv o .csv.
    
Quando sei pronto a iniziare a usare l'analisi delle chiamate per utente, leggi Usa l'analisi delle chiamate per utente per risolvere i problemi di [bassa qualità delle chiamate.](use-call-analytics-to-troubleshoot-poor-call-quality.md)
  
## <a name="give-permission-to-support-and-helpdesk-staff"></a>Concedere l'autorizzazione al personale del supporto tecnico

Come amministratore di Teams, hai accesso completo alle informazioni di analisi delle chiamate per tutti gli utenti. Abbiamo creato alcuni ruoli speciali di Azure Active Directory che puoi assegnare al personale di supporto e agli agenti helpdesk in modo che possano anche accedere ai dati analitici delle chiamate per utente (senza avere accesso al resto dell'interfaccia di amministrazione di Teams). Assegnare il **ruolo di esperto** del supporto per le comunicazioni di Teams agli utenti che devono avere una visualizzazione limitata dell'analisi delle chiamate per utente (supporto di Livello 1). Assegnare il ruolo di tecnico **del supporto per le** comunicazioni di Teams agli utenti che hanno bisogno dell'accesso completo all'analisi delle chiamate per utente (supporto di Livello 2). Nessuno dei due ruoli ha accesso al resto dell'interfaccia di amministrazione di Teams.

Per sapere cosa fa ciascuno di questi ruoli, leggere Cosa fa ogni ruolo di [supporto di Teams?](use-call-analytics-to-troubleshoot-poor-call-quality.md#what-does-each-teams-support-role-do)

Per altre informazioni sui ruoli di amministratore di Teams, vedere [Usare i ruoli di amministratore di Teams per gestire Teams.](using-admin-roles.md) Per informazioni su come assegnare ruoli di amministratore in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory.](https://docs.microsoft.com/Azure/active-directory/users-groups-roles/directory-manage-roles-portal)

Per informazioni su come assegnare ruoli amministrativi in Azure Active Directory, vedere Visualizzare e [assegnare ruoli in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="upload-a-tsv-or-csv-file-to-add-building-site-and-tenant-information"></a>Caricare un file con estensione tsv o csv per aggiungere informazioni relative a edifici, siti e tenant

Puoi aggiungere informazioni a livello di edificio, sito e tenant alle analisi delle chiamate per utente caricando un file CSV o TSV. Con tutte queste informazioni, l'analisi delle chiamate può mappare gli indirizzi IP alle posizioni fisiche. Amministratori e agenti helpdesk possono usare queste informazioni per individuare tendenze nei problemi di chiamata. Ad esempio, perché gli utenti nello stesso edificio hanno problemi simili di qualità delle chiamate? 

Se sei un amministratore di Teams o Skype for Business, puoi utilizzare un tenant esistente e creare un file di dati da Teams o Skype for Business Call Quality Dashboard (CQD). Prima di tutto, scarica il file da Call Call Analytics, quindi caricalo nell'analisi delle chiamate. 

- Per scaricare un file di dati esistente, vai all'interfaccia **di amministrazione di Microsoft Teams** Call Quality  >  **Dashboard**  >  **Carica ora.** **Nell'elenco Caricamenti** fare clic su **Scarica** accanto al file desiderato. 

- Per caricare il nuovo file, passare a Percorsi dell'interfaccia di amministrazione di **Microsoft Teams** e quindi selezionare Carica dati posizione o Sostituisci dati  >  sulla **posizione.** 
  
Se si sta creando il file TSV o CSV da zero, vedere [Caricare i dati del tenant e della creazione.](CQD-upload-tenant-building-data.md)
  
## <a name="related-topics"></a>Argomenti correlati

[Usare l'analisi delle chiamate per utente per risolvere i problemi di bassa qualità delle chiamate](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
