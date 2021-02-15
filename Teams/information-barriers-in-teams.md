---
title: Barriere di informazioni in Microsoft Teams
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
description: Questo articolo spiega cosa sono le barriere di informazioni in Microsoft Teams e come possono influenzare Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 94e0117e1f0956d8e3e9ae8e6bafc7feabcdf237
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196460"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barriere di informazioni in Microsoft Teams

Le barriere di informazioni sono criteri che un amministratore può configurare per impedire a singoli utenti o gruppi di comunicare tra loro. Gli ABS sono utili, ad esempio, se un reparto gestisce informazioni che non devono essere condivise con altri reparti. Sono utili anche quando un gruppo deve essere isolato o impedito di comunicare con chiunque all'esterno del gruppo.

> [!NOTE]
> - Non è possibile creare barriere di informazioni tra tenant.
> - L'uso di bot, app di Azure Active Directory (Azure AD) e alcune API per aggiungere utenti non è supportato nella versione 1.
> - I canali privati sono conformi ai criteri IB che si configurano.
> - Nuovo: per informazioni sul supporto per le barriere per i siti di SharePoint connessi a Teams, vedi [Segmenti associati ai siti di Microsoft Teams.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

I criteri IB impediscono anche ricerche e individuazione. Se tenti di comunicare con qualcuno con cui non dovresti comunicare, non lo troverai nella selezione utenti.

## <a name="background"></a>Sfondo

Il driver principale per gliBS proviene dal settore dei servizi finanziari. La FINRA (Financial Industry Regulatory[Authority)]( https://www.finra.org)esamina i crediti e i conflitti di interesse all'interno di società di membri e fornisce indicazioni sulla gestione di tali conflitti (FINRA 2241, Nota normativa sulla ricerca di debito [15-31).](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)


Tuttavia, dal momento dell'introduzione degli IBs, molte altre aree le hanno riscontrate come utili. Altri scenari comuni includono:

- Istruzione: gli studenti di un istituto di istruzione non possono cercare i dettagli di contatto degli studenti di altri istituti di istruzione.

- Legale: mantenere la riservatezza dei dati ottenuti dalla famiglia di clienti impedendo l'accesso da parte di una società che rappresenta un cliente diverso.

- Enti pubblici: l'accesso e il controllo delle informazioni sono limitati in reparti e gruppi.

- Servizi professionali: un gruppo di persone in un'azienda può chattare con un cliente o un cliente specifico solo attraverso l'accesso guest durante l'interazione con il cliente.

Ad esempio, Cita appartiene al segmento Banking e Pradeep al segmento Financial advisor. Più e Pradeep non possono comunicare tra loro perché i criteri IB dell'organizzazione bloccano la comunicazione e la collaborazione tra questi due segmenti. Tuttavia, Lee e Pradeep possono comunicare con Lee nelle risorse umane.

![Esempio che illustra le barriere di informazioni che impediscono la comunicazione tra segmenti](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quando usare le barriere di informazioni

È consigliabile usare gli IBs in situazioni come queste:

- A un team deve essere impedito di comunicare o condividere i dati con un altro team specifico.
- Un team non deve comunicare o condividere dati con persone esterne al team.

Il servizio di valutazione dei criteri di protezione delle informazioni (INFORMATION Barrier Policy Evaluation Service) determina se una comunicazione è conforme ai criteri IB.

## <a name="managing-information-barrier-policies"></a>Gestione dei criteri di protezione delle informazioni

I criteri IB vengono gestiti nel Centro conformità di Microsoft 365 con i cmdlet di PowerShell. Per altre informazioni, vedere Definire [i criteri per le barriere di informazioni.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

> [!IMPORTANT]
> Prima di impostare o definire criteri, è necessario abilitare la ricerca nella directory con ambito in Microsoft Teams. Attendere almeno alcune ore dopo l'abilitazione della ricerca nella directory con ambito prima di configurare o definire criteri per le barriere di informazioni. Per altre informazioni, vedere [Definire i criteri di protezione delle informazioni.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites)

## <a name="information-barriers-administrator-role"></a>Ruolo amministratore degli ostacoli alle informazioni

Il ruolo Gestione conformità IB è responsabile della gestione dei criteri IB. Per altre informazioni su questo ruolo, vedere Autorizzazioni nel Centro conformità di [Microsoft 365.](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Trigger delle barriere di informazioni

I criteri IB vengono attivati quando si verificano i seguenti eventi di Teams:

- **I membri vengono aggiunti a** un team- Ogni volta che si aggiunge un utente a un team, i criteri dell'utente devono essere valutati in base ai criteri IB degli altri membri del team. Dopo l'aggiunta, l'utente può eseguire tutte le funzioni nel team senza ulteriori controlli. Se i criteri dell'utente bloccano l'aggiunta al team, l'utente non verrà visualizzato nella ricerca.

    ![Screenshot della ricerca di un nuovo membro da aggiungere a un team e della ricerca di nessuna corrispondenza](media/information-barriers-add-members.png)

- Viene richiesta una nuova **chat-** Ogni volta che un utente richiede una nuova chat con uno o più utenti, la chat viene valutata per assicurarsi che non violi i criteri IB. Se la conversazione viola i criteri IB, la conversazione non viene avviata.

    Ecco un esempio di chat 1:1.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra le comunicazioni bloccate in una chat 1:1](media/information-barriers-one-one-chat.png)

    Ecco un esempio di chat di gruppo.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra la chat di gruppo](media/information-barriers-group-chat.png)

- **Un utente** viene invitato a partecipare a una riunione- Quando un utente viene invitato a partecipare a una riunione, il criterio IB applicabile all'utente viene valutato in base ai criteri IB applicabili agli altri membri del team. In caso di violazione, l'utente non sarà autorizzato a partecipare alla riunione.

    ![Screenshot che mostra un utente bloccato da una riunione](media/information-barriers-meeting.png)

- **Uno schermo** viene condiviso tra due o più utenti- Quando un utente condivide uno schermo con altri utenti, la condivisione deve essere valutata per assicurarsi che non violi i criteri IB di altri utenti. Se un criterio IB viene violato, la condivisione dello schermo non è consentita. 
 
    Ecco un esempio di condivisione dello schermo prima dell'applicazione del criterio. 

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra una chat utente](media/ib-before-screen-share-policy.png)

    Ecco un esempio di condivisione dello schermo dopo l'applicazione del criterio. Le icone di condivisione dello schermo e chiamata non sono visibili.

    > [!div class="mx-imgBorder"]
    > ![Screenshot showing user char with blocked settings](media/ib-after-screen-share-policy.png)

- Un utente effettua una chiamata telefonica **in Teams:** ogni volta che un utente avvia una chiamata vocale (tramite VOIP) a un altro utente o gruppo di utenti, la chiamata viene valutata per assicurarsi che non violi i criteri IB degli altri membri del team. In caso di violazione, la chiamata vocale viene bloccata.

- **Guest in Teams** - Le politiche IB si applicano anche ai guest in Teams. Se i guest devono essere individuabili nell'elenco indirizzi globale dell'organizzazione, vedere Gestire l'accesso guest nei gruppi [di Microsoft 365.](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups) Una volta individuabili i guest, è possibile [definire i criteri IB.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

## <a name="how-policy-changes-impact-existing-chats"></a>Impatto delle modifiche dei criteri sulle chat esistenti

Quando l'amministratore dei criteri IB apporta modifiche a un criterio o quando viene attivata una modifica ai criteri a causa di una modifica apportata al profilo di un utente, ad esempio per una modifica di un processo, il servizio di valutazione dei criteri per le barriere alle informazioni esegue automaticamente ricerche nei membri per assicurarsi che la loro appartenenza al team non violi alcun criterio.

Se esiste una chat o un'altra comunicazione tra utenti e viene impostato un nuovo criterio o se ne modifica uno esistente, il servizio valuta le comunicazioni esistenti per assicurarsi che le comunicazioni siano ancora consentite. 

- **Chat 1:1** - Se la comunicazione tra due utenti non è più consentita (a causa dell'applicazione a uno o a entrambi gli utenti di un criterio che blocca le comunicazioni), le ulteriori comunicazioni vengono bloccate. Le conversazioni in chat esistenti diventano di sola lettura. 

    Ecco un esempio che mostra che la chat è visibile.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra che la chat dell'utente è disponibile](media/ib-before-1-1chat-policy.png)

    Ecco un esempio che mostra che la chat è disabilitata.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra che la chat dell'utente è disabilitata](media/ib-after-1-1chat-policy.png)

- Chat di gruppo **-** Se le comunicazioni da un utente a un gruppo non sono più consentite (ad esempio perché un utente ha modificato i processi), l'utente, insieme agli altri utenti la cui partecipazione viola i criteri, potrebbe essere rimossa dalla chat di gruppo e non saranno consentite ulteriori comunicazioni con il gruppo. L'utente potrà comunque vedere le vecchie conversazioni, ma non potrà visualizzare o partecipare a nuove conversazioni con il gruppo. Se il criterio nuovo o modificato che impedisce la comunicazione viene applicato a più utenti, gli utenti interessati dal criterio potrebbero essere rimossi dalla chat di gruppo. Possono ancora vedere le vecchie conversazioni.

  In questo esempio, Isoto si è spostato in un reparto diverso all'interno dell'organizzazione e viene rimosso dalla chat di gruppo.

  ![Screenshot di una chat di gruppo da cui un utente è stato rimosso](media/information-barriers-user-changes-job.png)

  Non può più inviare messaggi alla chat di gruppo.

  ![Screenshot che mostra come non è possibile inviare messaggi alla chat di gruppo perché l'utente è stato rimosso dal gruppo](media/information-barriers-user-changes-job-2.png)

- **Team:** tutti gli utenti che sono stati rimossi dal gruppo vengono rimossi dal team e non potranno vedere o partecipare a conversazioni nuove o esistenti.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scenario: un utente in una chat esistente viene bloccato

Attualmente, gli utenti verificano gli scenari seguenti se un criterio IB blocca un altro utente:

- **Scheda Persone:** un utente non può vedere gli utenti bloccati nella **scheda** Persone.

- **Selezione utenti:** gli utenti bloccati non saranno visibili nella selezione utenti.

    ![Screenshot di Teams che avvisa l'utente che il criterio impedisce la visualizzazione delle informazioni di un altro utente](media/information-barriers-people-picker.png)
    
- **Scheda Attività:** se un utente visita la **scheda** Attività di un utente bloccato, non verrà visualizzato alcun post. La **scheda Attività** mostra solo i post del canale e non esisterebbero canali comuni tra i due utenti.

    Ecco un esempio di visualizzazione della scheda attività bloccata.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra la scheda attività bloccata](media/ib-after-activity-tab-policy.png)


- **Organigrammi:** se un utente accede a un organigramma in cui viene visualizzato un utente bloccato, non verrà visualizzato nell'organigramma. Verrà invece visualizzato un messaggio di errore.

- **Scheda Persone** - Se un utente partecipa a una conversazione e in seguito viene bloccato, gli altri utenti visualizzano un messaggio di errore al posto della scheda Persone quando passano il mouse sul nome dell'utente bloccato. Le azioni elencate sulla scheda (come chiamate e chat) non saranno disponibili.

- **Contatti suggeriti:** gli utenti bloccati non vengono visualizzati nell'elenco di contatti suggeriti (l'elenco di contatti iniziale visualizzato per i nuovi utenti).

- **Contatti chat** : un utente può vedere gli utenti bloccati nell'elenco contatti chat, ma gli utenti bloccati vengono identificati. L'unica azione che l'utente può eseguire sugli utenti bloccati è eliminarli. L'utente può anche fare clic su di essi per visualizzare le conversazioni passate.

- **Contatti chiamate:** un utente può vedere gli utenti bloccati nell'elenco dei contatti chiamate, ma gli utenti bloccati vengono identificati. L'unica azione che l'utente può eseguire sul blocco è eliminarla.

    Ecco un esempio di utente bloccato nell'elenco dei contatti chiamate.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra la chat utente](media/ib-before-chat-contacts-policy.png)

    Ecco un esempio di disattivazione della chat per un utente nell'elenco dei contenuti delle chiamate.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra un utente bloccato dalla chat](media/ib-after-chat-contacts-policy.png)

- **Migrazione da Skype** a Teams - Durante una migrazione da Skype for Business a Teams, tutti gli utenti, anche quelli bloccati dai criteri IB, verranno migrati a Teams. Tali utenti vengono quindi gestiti come descritto in precedenza.

## <a name="teams-policies-and-sharepoint-sites"></a>Criteri di Teams e siti di SharePoint

Quando viene creato un team, viene effettuato il provisioning di un sito di SharePoint e associato a Microsoft Teams per l'esperienza dei file. I criteri IB non vengono applicati al sito e ai file di SharePoint per impostazione predefinita. Per abilitare i criteri IB, l'amministratore ha già compilato un modulo per richiedere che i  criteri IB siano abilitati in SharePoint e OneDrive (vedere la sezione Prerequisiti in Barriere delle [informazioni).](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites) Se il criterio IB è attivato in SharePoint e OneDrive, i criteri IB funzionano nei siti di SharePoint di cui viene eseguito il provisioning quando viene creato un team con Microsoft Teams.

Esempio di criteri IB nel sito **di SharePoint** di un team: in Contoso Bank Corporation, l'utente "Sesha@contosobank.onmicrosoft.com" appartiene al segmento Investment Banking e l'utente "Nikita@contosobank.onmicrosoft.com" appartiene al segmento Advisory. Il criterio IB dell'organizzazione blocca la comunicazione e la collaborazione tra questi due segmenti.
Quando l'utente Sesha crea un team per il segmento Investment Banking, il team e il sito di SharePoint che lo esegue saranno accessibili solo agli utenti di Investment Banking. L'utente Nikita non può accedere al sito anche se ha il collegamento di sito.

Per altre informazioni, vedere [Usare le barriere di informazioni con SharePoint.](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites)

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

Per altre informazioni su licenze e autorizzazioni, inclusi piani e prezzi, vedere le indicazioni sulle licenze di [Microsoft 365](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)per informazioni sulla sicurezza & conformità.

## <a name="known-issues"></a>Problemi noti
- Gli utenti non possono partecipare a riunioni ad hoc: se sono abilitati i criteri IB, gli utenti non sono autorizzati a partecipare alle riunioni se le dimensioni **dell'elenco** riunioni sono superiori ai limiti di partecipazione alle [riunioni.](limits-specifications-teams.md) La causa principale è che i controlli IB si basano sulla presenza di utenti che possono essere aggiunti a un elenco chat della riunione e solo quando possono essere aggiunti all'elenco dei partecipanti sono autorizzati a partecipare alla riunione. Un utente che partecipa a una riunione una volta aggiunge l'utente all'elenco dei partecipanti; Di conseguenza, per le riunioni ricorrenti, l'elenco dei partecipanti può riempirsi rapidamente. Quando l'elenco chat raggiunge i limiti [di partecipazione](limits-specifications-teams.md)alla riunione, non è possibile aggiungere altri utenti alla riunione. Se IB è abilitato per il tenant e l'elenco chat è pieno per una riunione, i nuovi utenti (utenti che non sono già nell'elenco) non sono autorizzati a partecipare alla riunione. Se tuttavia IB non è abilitato per il tenant e l'elenco chat della riunione è pieno, i nuovi utenti (utenti che non sono ancora nell'elenco) possono partecipare alla riunione, anche se non vedranno l'opzione chat nella riunione. Una soluzione a breve termine consiste nel rimuovere i membri inattivi dall'elenco chat della riunione per fare spazio ai nuovi utenti. Tuttavia, in futuro verranno aumentate le dimensioni dei roster delle chat delle riunioni.

- **Gli utenti non possono** partecipare alle riunioni di canale: se i criteri IB sono abilitati, gli utenti non sono autorizzati a partecipare alle riunioni di canale se non sono membri del team. La causa principale è che i controlli IB si basano sulla presenza di utenti che possono essere aggiunti a un elenco chat della riunione e solo quando possono essere aggiunti all'elenco dei partecipanti sono autorizzati a partecipare alla riunione. Il thread della chat in una riunione del canale è disponibile solo per i membri del team o del canale e gli utenti non membri non possono vedere o accedere al thread di chat. Se IB è abilitato per il tenant e un membro non del team tenta di partecipare a una riunione di canale, quell'utente non è autorizzato a partecipare alla riunione. Tuttavia, se IB non è abilitato per il tenant e un membro non del team tenta di partecipare a una riunione di canale, l'utente è autorizzato a partecipare alla riunione, ma non vede l'opzione chat nella riunione. 

## <a name="more-information"></a>Altre informazioni

- Per altre informazioni sugli IBs, vedere [Barriere stradali.](https://docs.microsoft.com/office365/securitycompliance/information-barriers)

- Per configurare criteri IB, vedere [Definire i criteri per le barriere di informazioni.](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Per modificare o rimuovere i criteri IB, vedere [Modificare (o rimuovere)](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies)i criteri di protezione delle informazioni.

## <a name="availability"></a>Disponibilità
- La funzionalità è disponibile nel cloud pubblico; Nel mese di gennaio 2021 sono stati implementare gli ostacoli alle informazioni nel cloud GCC.
- Questa funzionalità non è ancora disponibile nei cloud MCCH e DOD.
