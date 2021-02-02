---
title: Barriere informative in Microsoft Teams
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: In questo articolo vengono illustrati gli ostacoli alle informazioni in Microsoft teams e come possono influire sui team.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95c3c2e854a22ff3ff74595a56f84edaaeb1c5f1
ms.sourcegitcommit: 7e673b88346e07f7c777710437b19d257ccecb1b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/01/2021
ms.locfileid: "50067151"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barriere informative in Microsoft Teams

Le barriere informative (IBs) sono criteri che possono essere configurati da un amministratore per impedire a singoli o gruppi di comunicare tra loro. Gli IBs sono utili se, ad esempio, un reparto sta gestendo informazioni che non devono essere condivise con altri reparti. Gli IBs sono utili anche quando un gruppo deve essere isolato o impedito di comunicare con altri utenti esterni a tale gruppo.

> [!NOTE]
> - Non è possibile creare gruppi di Information Barrier (IB) tra i tenant.
> - L'uso di bot, le app Azure Active Directory (Azure AD) e alcune API per l'aggiunta di utenti non è supportato nella versione 1.
> - I canali privati sono conformi ai criteri di IB configurati.
> - Novità: per informazioni sul supporto degli ostacoli per i siti di SharePoint connessi ai team, vedere [segmenti associati ai siti di Microsoft teams](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

I criteri IB impediscono anche ricerche e individuazione. Se tenti di comunicare con qualcuno con cui non dovresti comunicare, non troverai l'utente nella selezione persone.

## <a name="background"></a>Sfondo

Il driver principale per IBs proviene dal settore dei servizi finanziari. Il Financial Industry Regulatory Authority ([FINRA]( https://www.finra.org)) esamina l'IBS e i conflitti di interesse all'interno delle aziende membri e fornisce indicazioni sulla gestione di tali conflitti (FINRA 2241, [Nota di regolamentazione della ricerca del debito 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).


Tuttavia, dall'introduzione di IBs, molte altre aree li hanno trovati utili. Altri scenari comuni includono:

- Istruzione: gli studenti di una scuola non sono in grado di cercare informazioni di contatto per gli studenti di altre scuole.

- Legale: mantenere la riservatezza dei dati ottenuti dall'avvocato di un cliente e impedirne l'accesso da parte di un avvocato per la stessa azienda che rappresenta un cliente diverso.

- Governo: l'accesso e il controllo delle informazioni sono limitati tra reparti e gruppi.

- Servizi professionali: un gruppo di persone in un'azienda è in grado di chattare solo con un cliente o un cliente specifico tramite l'accesso guest durante l'impegno del cliente.

Ad esempio, Enrico appartiene al segmento Banking e Roberto fa parte del segmento Financial Advisor. Enrico e Roberto non possono comunicare tra loro perché i criteri IB dell'organizzazione bloccano la comunicazione e la collaborazione tra questi due segmenti. Tuttavia, Enrico e Roberto possono comunicare con Lee in HR.

![Esempio di informazioni sugli ostacoli che impediscono la comunicazione tra segmenti](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quando usare le barriere informative

È consigliabile usare IBs in situazioni come queste:

- Un team deve essere impedito di comunicare o condividere dati con un altro team specifico.
- Un team non deve comunicare o condividere dati con altri utenti esterni al team.

Il servizio di valutazione dei criteri barriera delle informazioni determina se una comunicazione è conforme ai criteri IB.

## <a name="managing-information-barrier-policies"></a>Gestione dei criteri di barriera delle informazioni

I criteri IB vengono gestiti nel centro conformità Microsoft 365 (SCC) usando i cmdlet di PowerShell. Per altre informazioni, vedere [definire i criteri per le barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Prima di configurare o definire i criteri, è necessario abilitare la ricerca di directory con ambito in Microsoft teams. Attendere almeno qualche ora dopo l'abilitazione della ricerca nell'ambito della directory prima di configurare o definire i criteri per le barriere informative. Per altre informazioni, vedere [definire i criteri di barriera delle informazioni](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Ruolo amministratore barriere informative

Il ruolo Gestione conformità IB è responsabile della gestione dei criteri IB. Per altre informazioni su questo ruolo, vedere [autorizzazioni nel centro conformità Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Trigger della barriera delle informazioni

I criteri IB vengono attivati quando si verificano gli eventi team seguenti:

- I **membri vengono aggiunti a un team** : ogni volta che si aggiunge un utente a un team, il criterio dell'utente deve essere valutato in base ai criteri di IB degli altri membri del team. Dopo che l'utente è stato aggiunto correttamente, l'utente può eseguire tutte le funzioni del team senza ulteriori controlli. Se i criteri dell'utente li bloccano dall'aggiunta al team, l'utente non verrà visualizzato nella ricerca.

    ![Screenshot della ricerca di un nuovo membro da aggiungere a un team e di non trovare corrispondenze](media/information-barriers-add-members.png)

- **È richiesta una nuova chat** : ogni volta che un utente richiede una nuova chat con uno o più altri utenti, la chat viene valutata per verificare che non violi i criteri di IB. Se la conversazione viola un criterio IB, la conversazione non viene avviata.

    Ecco un esempio di chat di 1:1.

    > [!div class="mx-imgBorder"]
    > ![Schermata che mostra le comunicazioni bloccate nella chat di 1:1](media/information-barriers-one-one-chat.png)

    Ecco un esempio di chat di gruppo.

    > [!div class="mx-imgBorder"]
    > ![Schermata che mostra la chat di gruppo](media/information-barriers-group-chat.png)

- **Un utente è invitato a partecipare a una riunione** : quando un utente è invitato a partecipare a una riunione, il criterio IB che si applica all'utente viene valutato in base ai criteri di IB applicabili agli altri membri del team. Se c'è una violazione, l'utente non sarà autorizzato a partecipare alla riunione.

    ![Schermata che mostra l'utente bloccato dalla riunione](media/information-barriers-meeting.png)

- **Una schermata viene condivisa tra due o più utenti** : quando un utente condivide uno schermo con altri utenti, la condivisione deve essere valutata per verificare che non violi i criteri IB di altri utenti. Se un criterio IB viene violato, la condivisione dello schermo non sarà consentita. 
 
    Ecco un esempio di condivisione dello schermo prima che venga applicato il criterio. 

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra una chat utente](media/ib-before-screen-share-policy.png)

    Ecco un esempio di condivisione dello schermo dopo l'applicazione dei criteri. Le icone condivisione schermo e chiamata non sono visibili.

    > [!div class="mx-imgBorder"]
    > ![Schermata che mostra il carattere utente con le impostazioni bloccate](media/ib-after-screen-share-policy.png)

- **Un utente inserisce una chiamata telefonica in teams** -ogni volta che un utente avvia una chiamata vocale (tramite VoIP) a un altro utente o gruppo di utenti, la chiamata viene valutata per assicurarsi che non violi i criteri di IB degli altri membri del team. In caso di violazione, la chiamata vocale è bloccata.

- **Gli ospiti in teams** -IB Policy si applicano anche agli ospiti in teams. Se gli utenti devono essere individuabili nell'elenco indirizzi globale dell'organizzazione, vedere [gestire l'accesso guest nei gruppi di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Una volta individuabili gli utenti, è possibile [definire i criteri IB](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Modifica dell'impatto delle chat esistenti tra i criteri

Quando l'amministratore dei criteri IB apporta modifiche a un criterio o quando viene attivata una modifica dei criteri a causa di una modifica del profilo di un utente, ad esempio per una modifica del processo, il servizio di valutazione dei criteri barriera informazioni esegue automaticamente la ricerca nei membri per verificare che l'appartenenza al team non violi i criteri.

Se esiste una chat o altre comunicazioni esistenti tra gli utenti e viene impostato un nuovo criterio o viene modificato un criterio esistente, il servizio valuta le comunicazioni esistenti per verificare che le comunicazioni siano ancora consentite. 

- **chat di 1:1** -se la comunicazione tra due utenti non è più consentita (a causa di un'applicazione a uno o entrambi gli utenti di un criterio che blocca le comunicazioni), viene bloccata un'ulteriore comunicazione. Le conversazioni di chat esistenti diventano di sola lettura. 

    Ecco un esempio che mostra che la chat è visibile.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra che la chat utente è disponibile](media/ib-before-1-1chat-policy.png)

    Ecco un esempio che mostra che la chat è disabilitata.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra che la chat utente è disabilitata](media/ib-after-1-1chat-policy.png)

- **Chat di gruppo** : se la comunicazione da un utente a un gruppo non è più consentita, ad esempio perché un utente ha modificato i processi, l'utente, insieme agli altri utenti la cui partecipazione viola il criterio, potrebbe essere rimosso dalla chat di gruppo e non sarà possibile comunicare ulteriormente con il gruppo. L'utente può ancora vedere le conversazioni precedenti, ma non potrà vedere o partecipare a nuove conversazioni con il gruppo. Se il criterio nuovo o modificato che impedisce la comunicazione viene applicato a più utenti, gli utenti interessati dal criterio potrebbero essere rimossi da chat di gruppo. Possono ancora vedere le conversazioni precedenti.

  In questo esempio, Enrico si trasferisce in un altro reparto all'interno dell'organizzazione e viene rimosso dalla chat di gruppo.

  ![Screenshot di una chat di gruppo da cui è stato rimosso un utente](media/information-barriers-user-changes-job.png)

  Enrico non può più inviare messaggi alla chat di gruppo.

  ![Screenshot di non essere in grado di inviare messaggi a chat di gruppo perché l'utente è stato rimosso dal gruppo](media/information-barriers-user-changes-job-2.png)

- **Team** -tutti gli utenti rimossi dal gruppo vengono rimossi dal team e non potranno vedere o partecipare a conversazioni esistenti o nuove.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scenario: un utente in una chat esistente viene bloccato

Attualmente gli utenti avvertono gli scenari seguenti se un criterio IB blocca un altro utente:

- **Scheda persone** -un utente non può visualizzare gli utenti bloccati nella scheda **persone** .

- **Selezione persone** -gli utenti bloccati non saranno visibili nella selezione persone.

    ![Screenshot dei team che avvisano l'utente che il criterio impedisce la visualizzazione delle informazioni di un altro utente](media/information-barriers-people-picker.png)
    
- **Scheda attività** : se un utente visita la scheda **attività** di un utente bloccato, non verranno visualizzati messaggi. La scheda **attività** Visualizza solo i post di canale e non ci sarebbero canali comuni tra i due utenti.

    Ecco un esempio della visualizzazione della scheda attività bloccata.

    > [!div class="mx-imgBorder"]
    > ![Schermata che mostra la scheda attività bloccata](media/ib-after-activity-tab-policy.png)


- **Organigrammi: se** un utente accede a un organigramma in cui viene visualizzato un utente bloccato, l'utente bloccato non verrà visualizzato nell'organigramma. Verrà invece visualizzato un messaggio di errore.

- **Scheda persone** : se un utente partecipa a una conversazione e l'utente viene bloccato in seguito, verrà visualizzato un messaggio di errore al posto della scheda utenti quando passa il puntatore del mouse sul nome dell'utente bloccato. Le azioni elencate nella scheda, ad esempio le chiamate e le chat, non saranno disponibili.

- **Contatti suggeriti** : gli utenti bloccati non vengono visualizzati nell'elenco dei contatti suggeriti (l'elenco dei contatti iniziale visualizzato per i nuovi utenti).

- **Contatti chat** : un utente può visualizzare gli utenti bloccati nell'elenco contatti chat, ma gli utenti bloccati verranno identificati. L'unica azione che l'utente può eseguire sugli utenti bloccati consiste nell'eliminarli. L'utente può anche fare clic su di essi per visualizzare la conversazione passata.

- **Chiamate contatti** -un utente può vedere gli utenti bloccati nell'elenco contatti chiamate, ma gli utenti bloccati verranno identificati. L'unica azione che l'utente può eseguire sugli utenti di blocco consiste nell'eliminarli.

    Ecco un esempio di utente bloccato nell'elenco contatti chiamate.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra la chat utente dell'utente](media/ib-before-chat-contacts-policy.png)

    Ecco un esempio della chat che viene disabilitata per un utente nell'elenco di contenuto chiamate.

    > [!div class="mx-imgBorder"]
    > ![Schermata che mostra l'utente bloccato dalla chat](media/ib-after-chat-contacts-policy.png)

- **Migrazione di Skype to teams** -durante una migrazione da Skype for business a teams, tutti gli utenti, anche gli utenti bloccati da criteri IB, verranno migrati in teams. Gli utenti vengono quindi gestiti come descritto sopra.

## <a name="teams-policies-and-sharepoint-sites"></a>Criteri per i team e siti di SharePoint

Quando viene creato un team, viene effettuato il provisioning di un sito di SharePoint e si associa a Microsoft teams per l'esperienza dei file. I criteri IB non vengono rispettati per impostazione predefinita in questo sito e file di SharePoint. Per abilitare i criteri IB, l'amministratore ha già compilato un modulo, richiedendo l'abilitazione dei criteri IB in SharePoint e OneDrive (vedere la sezione *prerequisiti* in [barriere informative](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)). Se il criterio IB è attivato in SharePoint e OneDrive, i criteri di IB funzioneranno nei siti di SharePoint che vengono provisionati quando un team viene creato con Microsoft teams.

**Esempio di criteri IB nel sito di SharePoint di un team**: in Contoso Bank Corporation l'utente "Sesha@contosobank.onmicrosoft.com" appartiene al segmento di Investment Banking e l'utente "Nikita@contosobank.onmicrosoft.com" appartiene al segmento consultivo. I criteri IB dell'organizzazione bloccano la comunicazione e la collaborazione tra questi due segmenti.
Quando l'utente Seshe crea un team per il segmento investment banking, il team e il sito di SharePoint che lo appoggiano saranno accessibili solo agli utenti di Investment Banking. L'utente Nikita non può accedere al sito anche se ha il collegamento al sito.

Per altre informazioni, vedere [usare le barriere informative con SharePoint](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Per altre informazioni sulle licenze e le autorizzazioni, inclusi i piani e i prezzi, vedere [Guida alle licenze di Microsoft 365 per la sicurezza & conformità](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="known-issues"></a>Problemi noti
- **Gli utenti non possono partecipare a riunioni ad hoc**: se i criteri di IB sono abilitati, gli utenti non sono autorizzati a partecipare alle riunioni se le dimensioni del roster della riunione sono maggiori dei [limiti della frequenza di riunione](limits-specifications-teams.md). La causa principale è che i controlli IB si basano sul fatto che gli utenti possano essere aggiunti a un roster della chat di riunione e che solo quando possono essere aggiunti al roster sono autorizzati a partecipare alla riunione. Un utente che partecipa a una riunione aggiunge l'utente all'elenco; quindi, per le riunioni ricorrenti, il roster può riempirsi velocemente. Quando il roster della chat raggiunge i [limiti di partecipazione alla riunione](limits-specifications-teams.md), non è consentito aggiungere altri utenti alla riunione. Se IB è abilitato per il tenant e il roster della chat è completo per una riunione, i nuovi utenti (gli utenti che non sono già presenti nell'elenco) non sono autorizzati a partecipare alla riunione. Ma se IB non è abilitato per il tenant e il roster della chat di riunione è pieno, i nuovi utenti (gli utenti che non sono già presenti nel roster) possono partecipare alla riunione, anche se non vedranno l'opzione chat nella riunione. Una soluzione a breve termine consiste nel rimuovere i membri inattivi dal roster della chat di riunione per creare spazio per i nuovi utenti. Le dimensioni dei roster della chat di riunione verranno comunque aumentate in un secondo momento.

- **Gli utenti non possono partecipare a riunioni di canale**: se i criteri IB sono abilitati, gli utenti non sono autorizzati a partecipare a riunioni di canale se non sono membri del team. La causa principale è che i controlli IB si basano sul fatto che gli utenti possano essere aggiunti a un roster della chat di riunione e che solo quando possono essere aggiunti al roster sono autorizzati a partecipare alla riunione. Il thread di chat in una riunione di canale è disponibile solo per i membri del team/canale e i non membri non possono vedere o accedere al thread della chat. Se IB è abilitato per il tenant e un membro non del team tenta di partecipare a una riunione di canale, non è consentito che l'utente partecipi alla riunione. Tuttavia, se IB _non_ è abilitato per il tenant e un membro non del team tenta di partecipare a una riunione di canale, l'utente può partecipare alla riunione, ma non vedrà l'opzione chat nella riunione.

## <a name="more-information"></a>Altre informazioni

- Per ulteriori informazioni su IBs, vedere [barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Per configurare i criteri di IB, vedere [definire i criteri per le barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

- Per modificare o rimuovere i criteri IB, vedere [modificare o rimuovere i criteri di barriera delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).
