---
title: Barriere informative in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: Informazioni sulle barriere informative e sul loro impatto sui team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3f4f7f256be21b9b3f8063ed34a25afb4af6971
ms.sourcegitcommit: 6cfaadec5782ca7316db36472bd0be20217da693
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/29/2020
ms.locfileid: "42341854"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barriere informative in Microsoft Teams

Le informazioni barriere (IB) sono criteri che possono essere configurati da un amministratore per impedire a singoli o gruppi di comunicare tra loro. Ciò è utile se, ad esempio, un reparto sta gestendo informazioni che non devono essere condivise con altri reparti o un gruppo deve essere impedito, o isolato, di comunicare con chiunque all'esterno di tale gruppo.

> [!NOTE]
> - Non è possibile creare gruppi di barriere informativi tra i tenant.
> - L'uso dei bot per l'aggiunta di utenti non è supportato nella versione 1.
> - I canali privati sono conformi ai criteri di barriera delle informazioni configurati.
> - Novità: il supporto delle informazioni barriera per il sito di SharePoint connesso a teams è ora in anteprima privata. Fare clic [qui](https://forms.office.com/Pages/ResponsePage.aspx?id=v4j5cvGGr0GRqy180BHbR3-O9WDTKhhDtgWfphwS9YhUM0hJNklNRkZKMlhLNDRZNzlEQlVDSjdZVi4u) per partecipare all'anteprima privata.

I criteri barriera delle informazioni impediscono anche ricerche e individuazione. Questo significa che se tenti di comunicare con qualcuno con cui non devi comunicare, non troverai l'utente nella selezione persone.

## <a name="background"></a>Sfondo

Il driver principale per gli ostacoli alle informazioni proviene dal settore dei servizi finanziari. Il Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) esamina le barriere di informazione e i conflitti di interesse nelle aziende membri e fornisce indicazioni su come gestire tali conflitti (FINRA 2241, [Nota di regolamentazione della ricerca del debito 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

Tuttavia, poiché l'introduzione di barriere informative, molti altri settori li hanno trovati come utili. Altri scenari comuni includono:

- Istruzione: gli studenti di una scuola non sono in grado di cercare informazioni di contatto per gli studenti di altre scuole.
- Legale: mantenere la riservatezza dei dati ottenuti dall'avvocato di un cliente dall'accesso di un avvocato per la stessa società che rappresenta un altro cliente.
- Governo: l'accesso e il controllo delle informazioni sono limitati tra reparti e gruppi.
- Servizi professionali: un gruppo di persone in una società può chattare solo con un cliente o un cliente specifico tramite la Federazione o l'accesso guest durante l'impegno del cliente.

## <a name="when-to-use-information-barriers"></a>Quando usare le barriere informative

Potresti voler usare le barriere informative in situazioni come queste:

- Un team deve essere impedito di comunicare o condividere dati con un altro team specifico.
- Un team non deve comunicare o condividere dati con altri utenti esterni al team.

Il servizio di valutazione dei criteri barriera delle informazioni determina se una comunicazione è conforme ai criteri barriera delle informazioni.

## <a name="managing-information-barrier-policies"></a>Gestione dei criteri di barriera delle informazioni

I criteri di barriera delle informazioni vengono gestiti nel centro protezione & conformità (SCC) di Office 365 tramite i cmdlet di PowerShell. Per altre informazioni, vedere [definire i criteri per le barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Prima di configurare o definire i criteri, **è necessario abilitare la ricerca di directory con ambito in Microsoft teams**. Attendere almeno 24 ore dopo l'abilitazione della ricerca nell'ambito della directory prima di configurare o definire i criteri per le barriere informative. Leggi [altre informazioni sui prerequisiti per le barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Ruolo amministratore barriere informative

Il ruolo Gestione conformità IB è responsabile della gestione dei criteri di barriera delle informazioni. Per altre informazioni su questo ruolo, vedere [autorizzazioni nel centro conformità & sicurezza di Office 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Trigger della barriera delle informazioni

I criteri di barriera delle informazioni vengono attivati quando si verificano gli eventi di Team seguenti:

- I **membri vengono aggiunti a un team** : ogni volta che si aggiunge un utente a un team, il criterio dell'utente deve essere valutato in base ai criteri di barriera delle informazioni di altri membri del team. Dopo che l'utente è stato aggiunto correttamente, l'utente può eseguire tutte le funzioni del team senza ulteriori controlli. Se i criteri dell'utente li bloccano dall'aggiunta al team, l'utente non verrà visualizzato nella ricerca.
- **È richiesta una nuova chat** : ogni volta che viene richiesta una nuova chat tra due o più utenti, la chat viene valutata per verificare che non violi i criteri di barriera delle informazioni. Se la conversazione viola un criterio di barriera delle informazioni, la conversazione non viene avviata.
- **Un utente è invitato a partecipare a una riunione** : quando un utente è invitato a partecipare a una riunione, i criteri dell'utente vengono valutati in base ai criteri di altri membri del team e, se c'è una violazione, l'utente non sarà autorizzato a partecipare alla riunione.
- **Una schermata viene condivisa tra due o più utenti** : ogni volta che viene condivisa una schermata tra due o più utenti, la condivisione dello schermo deve essere valutata per verificare che non violi i criteri di barriera delle informazioni di altri utenti. Se si violano i criteri di barriera delle informazioni, la condivisione dello schermo non sarà consentita.
- **Un utente inserisce una chiamata telefonica (VoIP) in teams** : ogni volta che viene avviata una chiamata vocale da un utente a un altro utente o gruppo di utenti, la chiamata viene valutata per assicurarsi che non violi i criteri di barriera delle informazioni di altri membri del team. In caso di violazione, la chiamata vocale è bloccata.
- **Utenti guest in teams** -i criteri barriera delle informazioni si applicano agli utenti guest anche in teams. Se gli utenti Guest devono essere individuabili nell'elenco indirizzi globale dell'organizzazione, vedere [gestire l'accesso guest nei gruppi di Office 365](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups?view=o365-worldwide#can-i-make-guest-objects-visible-in-the-global-address-list). Una volta individuabili gli utenti guest, puoi [definire i criteri di barriera delle informazioni](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Modifica dell'impatto delle chat esistenti tra i criteri

Quando l'amministratore dei criteri barriera delle informazioni apporta modifiche a un criterio o una modifica dei criteri viene applicata a causa di una modifica del profilo di un utente (ad esempio per una modifica del processo o un motivo simile), il servizio valutazione criteri barriera informazioni viene automaticamente Cerca i membri per verificare che i membri del team non violino i criteri.

Se esiste una chat o altre comunicazioni esistenti tra gli utenti e viene impostato un nuovo criterio o viene modificato un criterio esistente, il servizio valuta le comunicazioni esistenti per verificare che le comunicazioni siano ancora consentite.

- **chat di 1:1** -se la comunicazione tra i due utenti non è più consentita (se un criterio blocca la comunicazione viene applicato a uno o entrambi gli utenti), viene bloccata un'ulteriore comunicazione e la conversazione della chat diventa di sola lettura.
- **Chat di gruppo** : se la comunicazione di un utente al gruppo non è più consentita (ad esempio, se un utente modifica i processi), l'utente, insieme agli altri utenti che violano il criterio, potrebbe essere rimosso dalla chat di gruppo e non sarà possibile comunicare ulteriormente con il gruppo. L'utente può ancora vedere le vecchie conversazioni (che saranno di sola lettura), ma non sarà in grado di vedere o partecipare a nuove conversazioni con il gruppo. Se i criteri nuovi o modificati che impediscono la comunicazione vengono applicati a più utenti, gli utenti interessati dal criterio potrebbero essere rimossi da una chat di gruppo. Possono ancora vedere le conversazioni precedenti.
- **Team** -tutti gli utenti rimossi dal gruppo vengono rimossi dal team e non saranno in grado di vedere o partecipare a conversazioni esistenti o nuove.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scenario: un utente in una chat esistente viene bloccato

Attualmente gli utenti avvertono quanto segue se un criterio barriera informativo blocca un altro utente:

- **Scheda persone** -un utente non può visualizzare gli utenti bloccati nella scheda **persone** .
- **Selezione persone** -gli utenti bloccati non saranno visibili nella selezione persone.
- **Scheda attività** : se un utente visita la scheda **attività** di un utente bloccato, non verranno visualizzati messaggi. La scheda **attività** Visualizza solo i post di canale e non ci sarebbero canali comuni tra i due utenti.
- **Organigrammi: se** un utente accede a un organigramma in cui viene visualizzato un utente bloccato, l'utente bloccato non verrà visualizzato nell'organigramma e verrà visualizzato un messaggio di errore.
- **Scheda persone** : se un utente partecipa a una conversazione e l'utente viene bloccato in seguito, gli altri utenti vedranno un messaggio di errore al posto della scheda persone quando passa il puntatore del mouse sul nome dell'utente bloccato. Le azioni elencate nella scheda, ad esempio le chiamate e le chat, non saranno disponibili.
- **Contatti suggeriti** : gli utenti bloccati non vengono visualizzati nell'elenco dei contatti suggeriti (l'elenco dei contatti iniziale visualizzato per i nuovi utenti).
- **Contatti chat** : un utente può visualizzare gli utenti bloccati nell'elenco contatti chat, ma gli utenti bloccati verranno identificati e l'unica azione che l'utente può eseguire è eliminarli. L'utente può anche fare clic su di essi per visualizzare la conversazione passata.
- **Chiamate contatti** -un utente può vedere gli utenti bloccati nell'elenco contatti chiamate, ma gli utenti bloccati verranno identificati e l'unica azione che l'utente può eseguire è eliminarli.
- **Migrazione di Skype to teams** -durante una migrazione di Skype for business a teams, tutti gli utenti, anche quelli bloccati da criteri di barriera delle informazioni, verranno migrati in teams e verranno gestiti come descritto sopra.

## <a name="teams-policies-and-sharepoint-sites"></a>Criteri per i team e siti di SharePoint

Quando viene creato un team, viene eseguito il provisioning di un sito di SharePoint e viene associato al team per l'esperienza dei file. L'accesso a questo sito e ai file di SharePoint rende omaggio alla IB dell'organizzazione, ovvero solo gli utenti il cui segmento IB corrisponde al criterio IB sono autorizzati ad accedere. Anche al momento della condivisione di file, viene rispettato il criterio IB.

Ad esempio: in Contoso Bank Corporation, l'utente "Sesha@contosobank.onmicrosoft.com" appartiene al segmento di Investment Banking e l'utente "Nikita@contosobank.onmicrosoft.com" appartiene al segmento Advisory. I criteri IB dell'organizzazione bloccano la comunicazione e la collaborazione tra questi due segmenti.
Quando l'utente Seshe crea un team per il segmento investment banking, il team e il sito di SharePoint che lo appoggiano saranno accessibili solo agli utenti del segmento investment banking. L'utente Nikita non può accedere al sito anche se ha il collegamento al sito.

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Per altri dettagli, inclusi i piani e i prezzi, vedere indicazioni per le [licenze](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="more-information"></a>Altre informazioni

- Per ulteriori informazioni sulle barriere informative, vedere [barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Per configurare i criteri di barriera delle informazioni, vedere [definire i criteri per le barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

- Per modificare o rimuovere i criteri di barriera delle informazioni, vedere [modificare o rimuovere i criteri di barriera delle informazioni](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies.md)
