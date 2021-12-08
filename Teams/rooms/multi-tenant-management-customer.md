---
title: Gestione dei partner per i clienti
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: gestione dei partner per i clienti.
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331235"
---
# <a name="partner-management-for-customers"></a>Gestione dei partner per i clienti


La gestione dei partner nel servizio Teams Rooms Managed (TRM) consente ai clienti di delegare facilmente l'accesso e le responsabilità a una o più organizzazioni partner. I partner possono gestire solo le chat room a cui sono assegnati. 

## <a name="on-boarding-partners"></a>Partner di on-boarding
   Invitare i partner tramite il portale TRM per stabilire la relazione tra l'organizzazione e il tenant dell'organizzazione partner. 

### <a name="invitation-to-partner"></a>Invito al partner

   In questo metodo, il partner deve fornire gli *UPN* degli utenti che saranno gli amministratori principali assegnati all'utente. 

**Per avviare l'invito** 

1. Accedere al portale Teams Rooms gestito come amministratore MMR.
1. Vai a **Impostazioni >** **partner**, quindi seleziona **Aggiungi partner.**
1. Immettere il nome e l'UPN degli amministratori principali nella prima riga.
1. Selezionare **Aggiungi contatto** per confermare.
1. Eseguire una delle operazioni seguenti:
   - Per aggiungere un altro utente, ripetere il passaggio 4.
   - Per eliminare un utente, selezionare l'icona del bin a destra dell'utente.

    > [!NOTE]
    > Non è possibile usare gruppi o liste di distribuzione perché l'invito è collegato all'UPN.

1. Selezionare **Avanti.**
1. Configurare gli eventi che richiederanno l'approvazione del controllo delle modifiche. Per impostazione predefinita, tutti i controlli sono impostati su **Approvazione automatica.**

   > [!NOTE]
   > *Al momento è disponibile solo l'approvazione automatica.*
   > 
   >  1.  *Approvazione manuale:* Quando il partner esegue l'azione, viene generata una richiesta di approvazione che il cliente può rivedere e approvare. L'azione non viene implementata finché la richiesta non viene approvata.
   >  
   >  1. *Approvazione automatica:* Quando il partner esegue l'azione, non viene generata alcuna richiesta di approvazione e l'azione viene implementata immediatamente.
     
1. Selezionare **Avanti.**
1. Assegna le chat room che il partner gestirà, quindi seleziona **Avanti.**
1. Per continuare, rivedi le condizioni e seleziona **Accetto.**
1. Esaminare i dettagli dell'invito.
1. Selezionare **Aggiungi partner per** inviare l'invito.

L'invito è univoco per ogni utente ed è indipendente. Il primo utente partner che accetta l'invito stabilirà il collegamento tra il partner e il tenant. Non esiste alcuna associazione speciale con l'utente che stabilisce il collegamento, che consente la flessibilità nel caso in cui l'utente sia riassegnato. Gli utenti successivi da accettare verranno assegnati automaticamente al ruolo di amministratori principali. Deve essere sempre presente almeno un utente nel ruolo di amministratore principale.

Per gestire gli utenti con il ruolo di amministratore principale, vedere [Gestione multi-tenant per i partner.](multi-tenant-management-partner.md)


## <a name="off-boarding-partners"></a>Partner di off-boarding

**Per rimuovere un partner**

1. Accedere al portale TRM-MTM come amministratore mmR.
1. Passare a Impostazioni > **partner.**
1. Selezionare il partner da rimuovere.
1. Nel riquadro dei dettagli del cliente selezionare **Rimuovi partner.**
1. Selezionare **Elimina**. 
1. Alla richiesta di conferma per terminare l'associazione tra il tenant e il tenant del cliente, selezionare **Elimina**.

## <a name="managing-partner-roles"></a>Gestione dei ruoli dei partner

I ruoli dei partner consentono al partner di delegare in modo più granulare le responsabilità a personale aggiuntivo. Il concetto di questi ruoli è lo stesso descritto in [Controllo dell'accesso basato sui ruoli.](microsoft-teams-rooms-premium-rbac.md) È importante notare che i ruoli dei partner sono distinti dai ruoli personalizzati. 

Il **ruolo amministratore** principale è l'unico ruolo predefinito per ogni partner aggiunto. Questo ruolo ha quasi tutte le autorizzazioni per le chat room assegnate al partner per il servizio TRM (vedere [la tabella 1).](#table-1) Ad esempio, se si hanno chat room in tutto il mondo e si assegna un partner per la gestione di tutte le chat room degli Stati Uniti, l'amministratore principale potrà gestire e delegare le autorizzazioni solo per tali chat room. In questo caso, gli amministratori principali di questo partner non hanno visibilità per le chat room al di fuori degli Stati Uniti. 

### <a name="adding-primary-admins-to-partner"></a>Aggiunta di amministratori principali al partner

Se è già stato inviato un invito a un partner e si vogliono aggiungere altri utenti all'amministratore, è possibile aggiungerli al ruolo di amministratore del partner. In questo modo viene inviato un invito agli utenti aggiunti.

**Per aggiungere nuovi utenti a un partner esistente**

1. Accedere al portale TRM-MTM come amministratore mmR.
1. Passare a **Impostazioni > ruoli.**
1. Selezionare  **Ruoli partner.** 
1. Selezionare il **ruolo di amministratore** principale per il nome del partner corrispondente.
1. Nel riquadro dei ruoli selezionare **Attività.**
1. Selezionare **l'attività Amministratori** invitati. 
1. Nel riquadro attività Amministratori invitati selezionare **Membri**.
1. Selezionare **Modifica**.
1. Immettere l'UPN del nuovo utente e selezionare **Aggiungi contatto.**
1. Per confermare le modifiche, selezionare **Salva.**

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>Tabella 1

|Funzionalità|Autorizzazione|**Amministratore MMR**|**Cliente potenziale del sito**|**Tech del sito**|**Amministratore del partner**|
| :- | :- | :- | :- | :- | :- |
|Sale|Visualizzare|||||
||Modifica|||||
||Chiave di reimpostazione|||||
||Chiave di download|||||
||Annullare la registrazione|||||
|Gestione dei gruppi|Create |||||
||Visualizzare|||||
||Modifica|||||
|Aggiornare la gestione degli anelli|Create |||||
||Visualizzare|||||
||Modifica|||||
|Report|Visualizzare|||||
|Gestione dei biglietti|Creare un evento imprevisto per i clienti|||||
||Visualizzare|||||
||Update|||||
|MmR Impostazioni|Visualizzare|||||
||Modifica|||||
|Gestione ruoli|Visualizzare |||||
||Modifica|||||





## <a name="security"></a>Sicurezza

Il cliente finale mantiene il controllo sull'accesso ai dati e può rimuovere completamente un partner in qualsiasi momento. 

Con la funzionalità di accesso con delega, un partner non acquisisce altri privilegi all'esterno del portale del servizio TRM. Tuttavia, tutti i dati presenti nel servizio TRM derivati da altri prodotti Microsoft vengono considerati dati nel servizio TRM. Ad esempio, mentre i report sulla qualità delle chiamate derivano Teams dati sulla qualità delle chiamate, tutti i dati nel portale TRM si trova nell'ambito delle autorizzazioni. 

Non vengono concesse autorizzazioni a AAD o all'interfaccia di amministrazione Teams o a qualsiasi altro prodotto Microsoft. Inoltre, i partner non hanno accesso per visualizzare o modificare le chat room non definite nell'ambito dell'invito. 

I dati risiedono nel tenant del cliente e non vengono copiati nel tenant del partner. 

Il portale MTM usa Azure AD autenticazione per convalidare le credenziali di accesso del partner. Tenere presente che al momento i criteri di autenticazione del cliente non si applicano al partner. Ad esempio, se il cliente ha un criterio di autenticazione a più fattori, non viene tradotto nel partner. 

Per tirare i log sull'attività dei partner, vedere [Controllo](multi-tenant-auditing.md). 

> [!NOTE]
> AAD controllo e il controllo di O365 non acquisiscono i log dal portale TRM. 
