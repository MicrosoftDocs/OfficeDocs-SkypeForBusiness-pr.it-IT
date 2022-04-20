---
title: Ostacoli all'informazione in Microsoft Teams
description: Questo articolo spiega come sono supportati gli ostacoli alle informazioni in Microsoft Teams.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e57686e2decb5b2d663f75f1ad7884220a9ff4c2
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922807"
---
# <a name="information-barriers-in-microsoft-teams"></a>Ostacoli all'informazione in Microsoft Teams

[Microsoft Purview Information Barriers](/microsoft-365/compliance/information-barriers) (IB) sono criteri che un amministratore può configurare per impedire a singoli utenti o gruppi di comunicare tra loro. Gli indirizzi IB sono utili, ad esempio, se un reparto gestisce informazioni che non devono essere condivise con altri reparti. Gli indirizzi IB sono utili anche quando un gruppo deve essere isolato o impedito di comunicare con chiunque all'esterno di tale gruppo. I canali condivisi in Microsoft Teams sono supportati da barriere informative. A seconda del tipo di condivisione, i criteri sugli ostacoli alle informazioni possono limitare la condivisione in determinati modi. Per altre informazioni sul comportamento degli ostacoli ai canali condivisi e alle informazioni, vedere [Barriere alle informazioni e Canali condivisi](information-barriers-shared-channels.md).

Per Microsoft Teams, gli ostacoli alle informazioni possono determinare e impedire i seguenti tipi di collaborazione non autorizzata:

- Aggiunta di un utente a un team o a un canale
- Accesso degli utenti al contenuto del team o del canale
- Accesso degli utenti alle chat 1:1 e di gruppo
- Accesso degli utenti alle riunioni
- Impedisce ricerche e individuazione, gli utenti non saranno visibili nella selezione utenti.

>[!NOTE]
>- I gruppi di barriera delle informazioni non possono essere creati tra tenant.
>- L'uso di bot, app Azure Active Directory (Azure AD), API per inviare notifiche di feed attività e alcune API per aggiungere utenti non è supportato nella versione 1.
>- I canali privati sono conformi ai criteri di barriere alle informazioni configurati.
>- Per informazioni sul supporto delle barriere per i siti SharePoint connessi a Teams, vedi [Segmenti associati ai siti Microsoft Teams](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

## <a name="background"></a>Sfondo

Il driver principale per gli IB proviene dal settore dei servizi finanziari. L'Autorità di regolamentazione del settore finanziario ([FINRA]( https://www.finra.org)) esamina gli IB e i conflitti di interesse all'interno delle imprese aderenti e fornisce indicazioni sulla gestione di tali conflitti (FINRA 2241, [comunicazione normativa sulla ricerca del debito 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)).

Tuttavia, dopo l'introduzione deibs, molte altre aree le hanno trovate utili. Altri scenari comuni includono:

- **Istruzione**: gli studenti di un istituto di istruzione non sono in grado di cercare i dettagli di contatto per gli studenti di altri istituti di istruzione.
- **Legale**: mantenere la riservatezza dei dati ottenuti dall'avvocato di un cliente e impedirne l'accesso da parte di un avvocato dello stesso studio che rappresenta un cliente diverso.
- **Enti pubblici**: l'accesso e il controllo delle informazioni sono limitati in più reparti e gruppi.
- **Professional servizi**: un gruppo di persone in un'azienda può chattare solo con un cliente o un cliente specifico tramite l'accesso guest durante l'interazione con il cliente.

Ad esempio, Enrico appartiene al segmento Banking e Pradeep appartiene al segmento Financial advisor. Enrico e Pradeep non riescono a comunicare tra loro perché i criteri IB dell'organizzazione bloccano la comunicazione e la collaborazione tra questi due segmenti. Tuttavia, Enrico e Pradeep possono comunicare con Lee nelle Risorse Umane.

![Esempio che mostra gli ostacoli alle informazioni che impediscono la comunicazione tra segmenti.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quando usare le barriere informative

Potresti voler usare ibs in situazioni come queste:

- È necessario impedire a un team di comunicare o condividere dati con un altro team specifico.
- Un team non deve comunicare o condividere dati con utenti esterni al team.

Il servizio di valutazione dei criteri information barrier determina se una comunicazione è conforme alle politiche IB.

## <a name="managing-information-barrier-policies"></a>Gestione dei criteri di barriera delle informazioni

I criteri IB vengono gestiti nel portale di conformità Di Microsoft Purview (SCC) usando i cmdlet di PowerShell. Per altre informazioni, vedere [Definire i criteri per gli ostacoli alle informazioni](/office365/securitycompliance/information-barriers-policies).

>[!IMPORTANT]
>Prima di configurare o definire criteri, è necessario abilitare la ricerca nella directory con ambito in Microsoft Teams. Attendere almeno alcune ore dopo aver abilitato la ricerca nella directory con ambito prima di configurare o definire i criteri per le barriere informative. Per altre informazioni, vedere [Definire criteri di barriera delle informazioni](/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Ruolo di amministratore degli ostacoli alle informazioni

Il ruolo Gestione conformità IB è responsabile della gestione dei criteri IB. Per altre informazioni su questo ruolo, vedere [Autorizzazioni nel portale di conformità Microsoft Purview](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Attivazioni di barriere informative

I criteri IB vengono attivati quando si verificano gli eventi di Teams seguenti:

- **I membri vengono aggiunti a un team**: ogni volta che si aggiunge un utente a un team, i criteri dell'utente devono essere valutati rispetto ai criteri IB di altri membri del team. Dopo l'aggiunta dell'utente, l'utente può eseguire tutte le funzioni del team senza ulteriori controlli. Se i criteri dell'utente ne impediscono l'aggiunta al team, l'utente non verrà visualizzato nella ricerca.

    ![Screenshot che mostra come cercare un nuovo membro da aggiungere a un team e non trovare corrispondenze.](media/information-barriers-add-members.png)

- **Viene richiesta una nuova chat**: ogni volta che un utente richiede una nuova chat con uno o più utenti, la chat viene valutata in modo da non violare alcun criterio IB. Se la conversazione viola un criterio IB, la conversazione non viene avviata.

    Ecco un esempio di chat 1:1.

    ![Screenshot che mostra le comunicazioni bloccate nella chat 1:1.](media/information-barriers-one-one-chat.png)

    Ecco un esempio di chat di gruppo.

    ![Screenshot che mostra la chat di gruppo.](media/information-barriers-group-chat.png)

- **Un utente viene invitato a partecipare a una riunione**: quando un utente viene invitato a partecipare a una riunione, il criterio IB applicabile all'utente viene valutato rispetto ai criteri IB applicabili agli altri membri del team. In caso di violazione, l'utente non potrà partecipare alla riunione.

    ![Screenshot che mostra l'utente bloccato dalla riunione.](media/information-barriers-meeting.png)

- **Una schermata viene condivisa tra due o più utenti**: quando un utente condivide uno schermo con altri utenti, la condivisione deve essere valutata per assicurarsi che non violi i criteri IB di altri utenti. Se viene violato un criterio IB, la condivisione dello schermo non sarà consentita.

    Ecco un esempio di condivisione dello schermo prima dell'applicazione dei criteri.

    ![Screenshot che mostra una chat utente.](media/ib-before-screen-share-policy.png)

    Ecco un esempio di condivisione dello schermo dopo l'applicazione dei criteri. Le icone di condivisione dello schermo e di chiamata non sono visibili.

    ![Screenshot che mostra il carattere dell'utente con le impostazioni bloccate.](media/ib-after-screen-share-policy.png)

- **Un utente effettua una chiamata telefonica in Teams**: ogni volta che un utente avvia una chiamata vocale (tramite VOIP) a un altro utente o gruppo di utenti, la chiamata viene valutata in modo da non violare i criteri IB di altri membri del team. Se c'è una violazione, la chiamata vocale viene bloccata.

- **Guest in Teams**: le politiche IB si applicano anche ai guest in Teams. Se i guest devono essere individuabili nell'elenco indirizzi globale dell'organizzazione, vedere [Gestire l'accesso guest in Gruppi di Microsoft 365](/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Una volta individuabili gli utenti guest, è possibile [definire le politiche IB](/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Impatto delle modifiche ai criteri nelle chat esistenti

Quando l'amministratore dei criteri IB apporta modifiche a un criterio o quando viene attivata una modifica dei criteri a causa di una modifica al profilo di un utente (ad esempio per un cambio di processo), il servizio di valutazione dei criteri Information Barrier cerca automaticamente i membri per assicurarsi che la loro appartenenza al team non violi i criteri.

Se c'è una chat esistente o un'altra comunicazione tra gli utenti e viene impostato un nuovo criterio o se viene modificato un criterio esistente, il servizio valuta le comunicazioni esistenti per assicurarsi che le comunicazioni siano ancora consentite. 

- **Chat 1:1**: se la comunicazione tra due utenti non è più consentita (a causa dell'applicazione a uno o a entrambi gli utenti di un criterio che blocca la comunicazione), ulteriori comunicazioni vengono bloccate. Le conversazioni chat esistenti diventano di sola lettura.

    Ecco un esempio che mostra che la chat è visibile.

    ![Screenshot che mostra che la chat utente è disponibile.](media/ib-before-1-1chat-policy.png)

    Ecco un esempio che mostra che la chat è disabilitata.

    ![Screenshot che mostra che la chat utente è disabilitata.](media/ib-after-1-1chat-policy.png)

- **Chat di gruppo**: se la comunicazione da un utente a un gruppo non è più consentita (ad esempio perché un utente ha cambiato lavoro), l'utente, insieme agli altri utenti la cui partecipazione viola i criteri, potrebbe essere rimosso dalla chat di gruppo e non saranno consentite ulteriori comunicazioni con il gruppo. L'utente può ancora vedere le vecchie conversazioni, ma non potrà vedere o partecipare a nuove conversazioni con il gruppo. Se i criteri nuovi o modificati che impediscono la comunicazione vengono applicati a più utenti, gli utenti interessati dal criterio potrebbero essere rimossi dalla chat di gruppo. Possono ancora vedere vecchie conversazioni.

  In questo esempio, Enrico si è trasferito in un altro reparto all'interno dell'organizzazione e viene rimosso dalla chat di gruppo.

  ![Screenshot di una chat di gruppo da cui un utente è stato rimosso.](media/information-barriers-user-changes-job.png)

  Enrico non può più inviare messaggi alla chat di gruppo.

  ![Screenshot che mostra che non è possibile inviare messaggi alla chat di gruppo perché l'utente è stato rimosso dal gruppo.](media/information-barriers-user-changes-job-2.png)

- **Team**: tutti gli utenti che sono stati rimossi dal gruppo vengono rimossi dal team e non potranno visualizzare o partecipare a conversazioni esistenti o nuove.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scenario: un utente in una chat esistente viene bloccato

Attualmente, gli utenti provano gli scenari seguenti se un criterio IB blocca un altro utente:

- **Scheda Persone**: gli utenti bloccati non possono vedere gli utenti bloccati nella scheda **Persone** .

- **Selezione utenti**: gli utenti bloccati non saranno visibili nella selezione utenti.

    ![Screenshot di Teams che avvisa l'utente che i criteri impediscono la visualizzazione delle informazioni di un altro utente.](media/information-barriers-people-picker.png)

- **Scheda Attività**: se un utente visita la scheda **Attività** di un utente bloccato, non verrà visualizzato alcun post. La scheda **Attività** mostra solo i post del canale e non ci sono canali comuni tra i due utenti.

    Ecco un esempio di visualizzazione della scheda attività bloccata.

    ![Screenshot che mostra la scheda attività bloccata.](media/ib-after-activity-tab-policy.png)

- **Organigrammi**: se un utente accede a un organigramma in cui viene visualizzato un utente bloccato, l'utente bloccato non verrà visualizzato nell'organigramma. Verrà invece visualizzato un messaggio di errore.

- **Scheda Persone**: se un utente partecipa a una conversazione e successivamente viene bloccato, gli altri utenti vedranno un messaggio di errore invece della scheda persone quando posizionano il puntatore del mouse sul nome dell'utente bloccato. Le azioni elencate nella scheda (ad esempio chiamate e chat) non saranno disponibili.

- **Contatti suggeriti**: gli utenti bloccati non vengono visualizzati nell'elenco dei contatti suggeriti ( l'elenco contatti iniziale visualizzato per i nuovi utenti).

- **Contatti chat**: un utente può vedere gli utenti bloccati nell'elenco contatti chat, ma gli utenti bloccati verranno identificati. L'unica azione che l'utente può eseguire sugli utenti bloccati è eliminarli. L'utente può anche selezionarlo per visualizzare la conversazione precedente.

- **Contatti di chiamata**: un utente può vedere gli utenti bloccati nell'elenco contatti chiamate, ma gli utenti bloccati verranno identificati. L'unica azione che l'utente può eseguire sugli utenti bloccati è eliminarli.

    Ecco un esempio di utente bloccato nell'elenco contatti chiamate.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra la chat dell'utente.](media/ib-before-chat-contacts-policy.png)

    Ecco un esempio di disabilitazione della chat per un utente nell'elenco dei contenuti delle chiamate.

    > [!div class="mx-imgBorder"]
    > ![Screenshot che mostra l'utente bloccato dalla chat.](media/ib-after-chat-contacts-policy.png)

- **Skype alla migrazione Teams**: durante una migrazione da Skype for Business a Teams, verrà eseguita la migrazione in Teams tutti gli utenti, anche quelli bloccati dai criteri IB. Tali utenti vengono quindi gestiti come descritto in precedenza.

## <a name="teams-policies-and-sharepoint-sites"></a>Criteri di Teams e siti di SharePoint

Quando viene creato un team, viene eseguito il provisioning di un sito SharePoint e associato a Microsoft Teams per l'esperienza dei file. I criteri di barriera delle informazioni non vengono rispettati in questo SharePoint sito e file per impostazione predefinita. Per abilitare gli ostacoli alle informazioni in SharePoint e OneDrive, seguire le indicazioni e i passaggi descritti nell'articolo [Usare le barriere alle informazioni con SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) articolo.

## <a name="information--barrier-modes-and-teams"></a>Modalità di barriera dell'informazione e Teams

La modalità Barriere informazioni consente di rafforzare gli utenti che possono essere aggiunti o rimossi da un team. Quando si usano barriere informative con Teams, sono supportate le seguenti modalità IB:

- **Aperta**: questa configurazione è la modalità IB predefinita per tutti i gruppi esistenti di cui è stato eseguito il provisioning prima dell'abilitazione delle barriere alle informazioni. In questa modalità non sono applicabili criteri IB.
- **Implicito**: questa configurazione è la modalità IB predefinita quando viene eseguito il provisioning di un team dopo l'abilitazione delle barriere di informazioni. La modalità implicita consente di aggiungere tutti gli utenti compatibili nel gruppo.
- **Owner Moderated**: questa modalità è impostata in un team quando si vuole consentire la collaborazione tra utenti di segmento incompatibili che sono moderata dal proprietario. Il proprietario del team può aggiungere nuovi membri in base ai criteri IB.

Teams creati prima di attivare un criterio di barriera delle informazioni nel tenant vengono impostati automaticamente sulla modalità *Di apertura* per impostazione predefinita. Dopo aver attivato i criteri IB nel tenant, è necessario aggiornare la modalità dei team esistenti in *Modo implicito* per assicurarsi che i team esistenti siano conformi a IB.

Utilizzare il cmdlet [Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) con il parametro *InformationBarrierMode* che corrisponde alla modalità che si desidera utilizzare per i segmenti. L'elenco di valori consentiti per il parametro *InformationBarrierMode* è *Open*, *Implicit* e *Owner Moderated*.

Ad esempio, per configurare la modalità *implicita* per un gruppo di Microsoft 365, usare il comando di PowerShell seguente:

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

Per aggiornare la modalità da Aperta a Implicita per tutti i team esistenti, usare questo [script di PowerShell](information-barriers-mode-script.md).

Se si modifica la configurazione della modalità Aperta nei gruppi Teams connessi esistenti per soddisfare i requisiti di conformità per l'organizzazione, sarà necessario [aggiornare le modalità IB](/sharepoint/information-barriers#view-and-manage-ib-modes-as-an-administrator-with-sharepoint-powershell) per i siti SharePoint associati connessi al team di Teams.

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni necessarie

Per altre informazioni su licenze e autorizzazioni, piani e prezzi, vedere [Microsoft 365 le linee guida sulle licenze per la sicurezza & la conformità](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="known-issues"></a>Problemi noti

- **Gli utenti non possono partecipare a riunioni ad hoc**: se sono abilitati i criteri IB, gli utenti non sono autorizzati a partecipare alle riunioni se le dimensioni dell'elenco dei partecipanti alla riunione sono maggiori dei [limiti di partecipazione alle riunioni](limits-specifications-teams.md). La causa principale è che i controlli IB si basano sul fatto che gli utenti possano essere aggiunti a un roster della chat della riunione e solo quando possono essere aggiunti all'elenco sono autorizzati a partecipare alla riunione. Un utente che partecipa a una riunione una volta aggiunge l'utente all'elenco dei partecipanti; quindi per le riunioni ricorrenti, l'elenco può riempirsi rapidamente. Quando l'elenco dei partecipanti alla chat raggiunge [i limiti di partecipazione alla riunione](limits-specifications-teams.md), non è possibile aggiungere altri utenti alla riunione. Se L'IB è abilitato per l'organizzazione e l'elenco delle chat è pieno per una riunione, i nuovi utenti (quelli che non sono già presenti nell'elenco) non sono autorizzati a partecipare alla riunione. Se invece L'IB non è abilitato per l'organizzazione e l'elenco dei partecipanti alla chat della riunione è pieno, i nuovi utenti (gli utenti che non sono già presenti nell'elenco) possono partecipare alla riunione, anche se non vedranno l'opzione di chat nella riunione. Una soluzione a breve termine consiste nel rimuovere i membri inattivi dal roster della chat della riunione per fare spazio ai nuovi utenti. Tuttavia, le dimensioni dei registri della chat delle riunioni verranno aumentate in un secondo momento.
- **Gli utenti non possono partecipare alle riunioni del canale**: se sono abilitati i criteri IB, gli utenti non sono autorizzati a partecipare alle riunioni del canale se non sono membri del team. La causa principale è che i controlli IB si basano sul fatto che gli utenti possano essere aggiunti a un roster della chat della riunione e solo quando possono essere aggiunti all'elenco sono autorizzati a partecipare alla riunione. Il thread della chat in una riunione del canale è disponibile solo per i membri del team o del canale e gli utenti non membri non possono visualizzare o accedere al thread della chat. Se IB è abilitato per l'organizzazione e un non membro del team tenta di partecipare a una riunione di canale, l'utente non è autorizzato a partecipare alla riunione. Tuttavia, se IB non è abilitato* per l'organizzazione e un non membro del team tenta di partecipare a una riunione di canale, l'utente è autorizzato a partecipare alla riunione, ma non vedrà l'opzione di chat nella riunione.
- **Numero massimo di segmenti consentiti in un'organizzazione**: ogni organizzazione può configurare fino a 100 segmenti durante la configurazione dei criteri IB. Il numero di criteri che è possibile configurare non è limitato.
- **I criteri IB non funzionano per gli utenti federati**: se si consente la federazione con organizzazioni esterne, gli utenti di tali organizzazioni non saranno limitati dai criteri IB. Se gli utenti dell'organizzazione partecipano a una chat o a una riunione organizzata da utenti federati esterni, anche i criteri IB non limitano le comunicazioni tra gli utenti dell'organizzazione.

## <a name="more-information"></a>Altre informazioni

- Per altre informazioni sugli IB, vedere [Barriere alle informazioni](/office365/securitycompliance/information-barriers).
- Per configurare i criteri IB, vedere [Attività iniziali con barriere informative](/office365/securitycompliance/information-barriers-policies).
- Per modificare o rimuovere i criteri IB, vedere [Gestire i criteri di barriera delle informazioni](/microsoft-365/compliance/information-barriers-edit-segments-policies).
- [Barriere informative e canali condivisi](information-barriers-shared-channels.md)

## <a name="availability"></a>Disponibilità

Gli ostacoli alle informazioni in Teams sono disponibili in cloud pubblico, GCC, GCC - elevati e DOD.
