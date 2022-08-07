---
title: Gestione partner per i clienti
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.date: 06/09/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: gestione dei partner per i clienti.
f1keywords: ''
ms.openlocfilehash: 9ac7e01de1f9a9e620afa665298d8f3746319db2
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271371"
---
# <a name="partner-management-for-customers"></a>Gestione partner per i clienti

La gestione dei partner nel servizio Teams Rooms Managed (TRM) consente ai clienti di delegare facilmente l'accesso e le responsabilità a una o più organizzazioni partner. I partner possono gestire solo le chat room a cui sono assegnate.

## <a name="on-boarding-partners"></a>Partner d'imbarco
   Invitare i partner tramite il portale TRM per stabilire la relazione tra l'organizzazione e il tenant dell'organizzazione partner.

### <a name="invitation-to-partner"></a>Invito al partner

   In questo metodo è necessario conoscere il nome di dominio del partner, ad esempio Contoso.com.

**Per avviare l'invito** 

1. Accedere al portale Teams Rooms Managed come amministratore del servizio gestito.
1. Vai a **Impostazioni >** **Partner**, quindi seleziona **Aggiungi partner.**
1. Immettere il nome di dominio nella prima riga.
1. Configurare il numero di giorni fino alla scadenza dell'invito immettendo un numero intero compreso tra 1 e 30.
1. Configurare gli eventi che richiedono l'approvazione di un controllo delle modifiche. Per impostazione predefinita, tutti i controlli sono impostati su **Approvazione automatica.**

   > [!NOTE]
   > *Al momento è disponibile solo l'approvazione automatica.*
   > 
   >  1.  *Approvazione manuale:* Quando il partner esegue l'azione, viene generata una richiesta di approvazione che il cliente può esaminare e approvare. L'azione non viene implementata finché la richiesta non viene approvata.
   >  
   >  1. *Approvazione automatica:* Quando il partner esegue l'azione, non viene generata alcuna richiesta di approvazione e l'azione viene implementata immediatamente.
     
1. Selezionare **Avanti.**
1. Assegna chat room che il partner gestirà, quindi seleziona **Avanti.**
1. Per continuare, esamina le condizioni e seleziona **Accetto.**
1. Rivedere i dettagli dell'invito.
1. Selezionare **Aggiungi partner** per inviare l'invito.

L'invito viene inviato ai responsabili tenant nell'istanza del partner per la revisione. Il primo utente partner che accetta l'invito stabilirà il collegamento tra il partner e il tenant e assegnerà gli amministratori primari. Non esiste alcuna associazione speciale con l'utente che stabilisce il collegamento, che consente la flessibilità nel caso in cui l'utente venga riassegnato. Il ruolo di amministratore principale deve sempre essere almeno un utente.

Per gestire gli utenti con il ruolo di amministratore principale, vedere [Gestione di più tenant per partner](multi-tenant-management-partner.md).

## <a name="off-boarding-partners"></a>Partner off-boarding

**Per rimuovere un partner**

1. Accedi al portale TRM-MTM come amministratore di MMR.
1. Passare a **Impostazioni > Partner.**
1. Seleziona il partner che vuoi rimuovere.
1. Nel riquadro dei dettagli del cliente selezionare **Rimuovi partner.**
1. Selezionare **Elimina**. 
1. Alla richiesta di conferma di terminare l'associazione tra l'utente e il tenant del cliente, selezionare **Elimina**.

## <a name="managing-partner-roles"></a>Gestione dei ruoli dei partner

I ruoli partner consentono al partner di delegare più granularmente le responsabilità a personale aggiuntivo. Il concetto di questi ruoli è lo stesso descritto in [Controllo degli accessi basato sui](microsoft-teams-rooms-premium-rbac.md) ruoli. È importante notare che i ruoli partner sono distinti dai ruoli personalizzati. 

Il ruolo **di amministratore principale** è l'unico ruolo predefinito per ogni partner aggiunto. Questo ruolo ha quasi tutte le autorizzazioni per le chat room assegnate al partner per il servizio TRM (vedere [tabella 1](#table-1)). Ad esempio, se si hanno sale in tutto il mondo e si assegna un partner per gestire Tutte le chat room negli Stati Uniti, l'amministratore principale sarà in grado solo di gestire e delegare le autorizzazioni per tali chat room. In questo caso, gli amministratori principali di questo Partner non hanno visibilità su alcuna chat room al di fuori degli Stati Uniti. 

### <a name="adding-primary-admins-to-partner"></a>Aggiunta di amministratori primari ai partner

Se è già stato inviato un invito a un partner e si desidera delegare più chat room, è possibile aggiungere chat room al ruolo di amministratore del partner.

**Per aggiungere nuove chat room a un partner esistente**

1. Accedi al portale TRM-MTM come amministratore di MMR.
1. Passare a **Impostazioni > ruoli.**
1. Selezionare  **Ruoli partner.** 
1. Selezionare il ruolo **di amministratore principale** per il nome partner corrispondente.
1. Nel riquadro dei ruoli selezionare **Assegnazioni**.
1. Selezionare l'assegnazione **Amministratori assegnati** .
1. Nel riquadro delle assegnazioni Amministratori assegnati selezionare **Ambito**.
1. Selezionare **Modifica**.
1. Cerca le stanze che desideri aggiungere e seleziona la stanza desiderata.
1. Per confermare le modifiche, selezionare **Salva**.

### <a name="table-1"></a>Tabella 1

|Funzionalità|Autorizzazione|**Amministrazione MMR**|**Cliente potenziale del sito**|**Tech del sito**|**Amministratore partner**|
| :- | :- | :- | :- | :- | :- |
|Camere|Visualizzare| &#10004;|&#10004;|&#10004;|&#10004;|
||Modificare|&#10004;|&#10004;|&#10004;|&#10004;|
||Tasto REIMPOSTA|&#10004;||||
||Chiave di download|&#10004;|&#10004;|&#10004;||
||Annullare la registrazione|&#10004;|&#10004;|&#10004;||
||Create |&#10004;|&#10004;|||
|Gestione dei gruppi|Visualizzare|&#10004;|&#10004;||&#10004;|
||Modificare|&#10004;|&#10004;|||
||Create |&#10004;|&#10004;|||
|Gestione dell'anello di aggiornamento|Visualizzare|&#10004;|&#10004;||&#10004;|
||Modificare|&#10004;|&#10004;||&#10004;|
|Rapporti|Visualizzare|&#10004;|&#10004;||&#10004;|
||Crea evento imprevisto del cliente|&#10004;|&#10004;|&#10004;|&#10004;|
|Gestione biglietti|Visualizzare|&#10004;|&#10004;|&#10004;|&#10004;|
||Aggiornamento|&#10004;|&#10004;|&#10004;|&#10004;|
|Impostazioni MMR|Visualizzare|&#10004;||||
||Modificare|&#10004;||||
|Gestione dei ruoli|Visualizzare |&#10004;|||&#10004;|
||Modificare|&#10004;|||&#10004;|

## <a name="security"></a>Sicurezza

In qualità di cliente finale, l'utente mantiene il controllo sull'accesso ai propri dati e può rimuovere completamente un partner in qualsiasi momento. 

Con la funzionalità di accesso delegato, un partner non ottiene altri privilegi al di fuori del portale del servizio TRM. Tuttavia, tutti i dati presenti nel servizio TRM derivati da altri prodotti Microsoft sono considerati dati nel servizio TRM. Ad esempio, mentre i rapporti sulla qualità delle chiamate derivano dai dati sulla qualità delle chiamate di Teams, tutti i dati nel portale TRM rientrano nell'ambito delle autorizzazioni. 

Nessuna autorizzazione viene concessa ad AAD o a Teams Amministrazione Center o a qualsiasi altro prodotto Microsoft. Inoltre, i partner non hanno accesso alla visualizzazione o alla modifica di chat room non definite nell'ambito dell'invito. 

I dati si trovano nel tenant del cliente e non vengono copiati nel tenant del partner. 

Il portale MTM usa l'autenticazione di Azure AD per convalidare le credenziali di accesso del partner. Si noti che al momento, i criteri di autenticazione del cliente non si applicano al partner. Ad esempio, se il cliente ha un criterio di autenticazione a più fattori, non si traduce nel partner. 

Per recuperare i log sull'attività dei partner, vedere [Controllo](multi-tenant-auditing.md). 

> [!NOTE]
> Il controllo di AAD e di O365 non acquisisce i log dal portale TRM. 
