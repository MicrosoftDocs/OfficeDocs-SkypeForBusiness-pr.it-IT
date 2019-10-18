---
title: Barriere informative in Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.date: 07/08/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
description: Informazioni sulle barriere informative e sul loro impatto sui team.
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd9ac22a45d0e76e8f2d31c3d11be726148b3863
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572070"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barriere informative in Microsoft Teams

Gli ostacoli alle informazioni sono criteri che possono essere configurati da un amministratore per impedire agli utenti o ai gruppi di comunicare tra loro. Ciò è utile se, ad esempio, un reparto sta gestendo informazioni che non devono essere condivise con altri reparti o un gruppo deve essere impedito, o isolato, di comunicare con chiunque all'esterno di tale gruppo.

> [!NOTE]
> - Non è possibile creare gruppi di barriere informativi tra i tenant.
> - L'uso dei bot per l'aggiunta di utenti non è supportato nella versione 1.
> - Barriere informative la versione 1 non include il supporto per SharePoint e OneDrive for business. Stiamo lavorando per abilitare la funzionalità in SharePoint e comunicheremo quando sarà disponibile.

I criteri barriera delle informazioni impediscono anche ricerche e individuazione. Questo significa che se tenti di comunicare con qualcuno con cui non devi comunicare, non troverai l'utente nella selezione persone.

## <a name="background"></a>Sfondo

Il driver principale per gli ostacoli alle informazioni proviene dal settore dei servizi finanziari. Il Financial Industry Regulatory Authority ([FINRA]( http://www.finra.org)) esamina le barriere di informazione e i conflitti di interesse nelle aziende membri e fornisce indicazioni su come gestire tali conflitti (FINRA 2241, [Nota di regolamentazione della ricerca del debito 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

## <a name="when-should-i-use-information-barriers"></a>Quando usare le barriere informative

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

## <a name="when-are-information-barrier-policies-checked"></a>Quando vengono controllati i criteri barriera delle informazioni?

I criteri di barriera delle informazioni vengono controllati quando si verificano gli eventi di Team seguenti:

- I **membri vengono aggiunti a un team** : ogni volta che si aggiunge un utente a un team, il criterio dell'utente deve essere valutato in base ai criteri di barriera delle informazioni di altri membri del team. Dopo che l'utente è stato aggiunto correttamente, l'utente può eseguire tutte le funzioni del team senza ulteriori controlli. Se i criteri dell'utente li bloccano dall'aggiunta al team, l'utente non verrà visualizzato nella ricerca.
- **È richiesta una nuova chat** : ogni volta che viene richiesta una nuova chat tra due o più utenti, la chat viene valutata per verificare che non violi i criteri di barriera delle informazioni. Se la conversazione viola un criterio di barriera delle informazioni, la conversazione non viene avviata.
- **Un utente è invitato a partecipare a una riunione** : quando un utente è invitato a partecipare a una riunione, i criteri dell'utente vengono valutati in base ai criteri di altri membri del team e, se c'è una violazione, l'utente non sarà autorizzato a partecipare alla riunione.
- **Una schermata viene condivisa tra due o più utenti** : ogni volta che viene condivisa una schermata tra due o più utenti, la condivisione dello schermo deve essere valutata per verificare che non violi i criteri di barriera delle informazioni di altri utenti. Se si violano i criteri di barriera delle informazioni, la condivisione dello schermo non sarà consentita.
- **Un utente inserisce una chiamata telefonica (VoIP) in teams** : ogni volta che viene avviata una chiamata vocale da un utente a un altro utente o gruppo di utenti, la chiamata viene valutata per assicurarsi che non violi i criteri di barriera delle informazioni di altri membri del team. In caso di violazione, la chiamata vocale è bloccata.

## <a name="what-happens-to-existing-chat-threads-when-a-policy-is-changed"></a>Cosa succede ai thread di chat esistenti quando viene modificato un criterio?

Quando l'amministratore dei criteri barriera delle informazioni apporta modifiche a un criterio o una modifica dei criteri viene applicata a causa di una modifica del profilo di un utente (ad esempio per una modifica del processo o un motivo simile), il servizio valutazione criteri barriera informazioni viene automaticamente Cerca i membri per verificare che i membri del team non violino i criteri.

Se esiste una chat o altre comunicazioni esistenti tra gli utenti e viene impostato un nuovo criterio o viene modificato un criterio esistente, il servizio valuta le comunicazioni esistenti per verificare che le comunicazioni siano ancora consentite. 

- **chat di 1:1** -se la comunicazione tra i due utenti non è più consentita (se un criterio blocca la comunicazione viene applicato a uno o entrambi gli utenti), viene bloccata un'ulteriore comunicazione e la conversazione della chat diventa di sola lettura.
- **Chat di gruppo** : se la comunicazione di un utente al gruppo non è più consentita (ad esempio, se un utente cambia lavoro), l'utente insieme agli altri utenti che violano il criterio potrebbe essere rimosso dalla chat di gruppo e altre comunicazioni con il gruppo non saranno consentiti. L'utente può ancora vedere le vecchie conversazioni (che saranno di sola lettura), ma non sarà in grado di vedere o partecipare a nuove conversazioni con il gruppo. Se i criteri nuovi o modificati che impediscono la comunicazione vengono applicati a più utenti, gli utenti interessati dal criterio potrebbero essere rimossi da una chat di gruppo. Possono ancora vedere le conversazioni precedenti. 
- **Team** -tutti gli utenti rimossi dal gruppo vengono rimossi dal team e non saranno in grado di vedere o partecipare a conversazioni esistenti o nuove.

## <a name="what-will-users-experience-if-another-user-is-blocked"></a>Che cosa faranno gli utenti se un altro utente è bloccato?

Attualmente gli utenti avvertono quanto segue se un criterio barriera informativo blocca un altro utente:

- **Scheda persone** -un utente può visualizzare alcuni utenti bloccati nella scheda **persone** . L'utente può selezionare gli utenti bloccati.
- **Scheda attività** : se un utente visita la scheda **attività** di un utente bloccato, non verranno visualizzati messaggi. La scheda **attività** Visualizza solo i post di canale e non ci sarebbero canali comuni tra i due utenti.
- **Organigrammi: se** un utente accede a un organigramma in cui viene visualizzato un utente bloccato, l'utente verrà visualizzato nel grafico e sarà possibile fare clic su azioni nel grafico, ma le azioni (ad esempio le chiamate) non verranno passate.
- **Scheda persone** : se un utente partecipa a una conversazione e viene successivamente bloccato, gli altri utenti possono ancora vedere la scheda persone per l'utente bloccato. Tutte le azioni elencate nella scheda, ad esempio le chiamate e le chat, saranno disponibili, ma le azioni non verranno superate.
- **Contatti suggeriti** : nell'elenco contatti suggeriti (elenco contatti iniziale visualizzato per i nuovi utenti) gli utenti possono visualizzare tutti i contatti suggeriti (inclusi gli utenti bloccati). Tuttavia, se un utente fa clic sul nome di un utente bloccato per aprire il riquadro chat, il messaggio verrà bloccato.
- **Contatti chat** : un utente può visualizzare gli utenti bloccati nell'elenco contatti chat.
- **Chiamate contatti** -un utente può visualizzare gli utenti bloccati nell'elenco di contatti delle chiamate e vengono visualizzate azioni come chiamate e messaggi, ma quando l'utente prova a chiamare o a inviare un messaggio all'utente bloccato, la chiamata o il messaggio non passerà.
- **Migrazione di Skype to teams** -durante una migrazione di Skype for business a teams, tutti gli utenti, anche quelli bloccati da criteri di barriera delle informazioni, verranno migrati in teams e verranno gestiti come descritto sopra.

In arrivo: gli utenti sperimenteranno quanto segue se un criterio barriera informativo blocca un altro utente:

- **Scheda persone** -un utente non può visualizzare gli utenti bloccati nella scheda **persone** .
- **Scheda attività** : se un utente visita la scheda **attività** di un utente bloccato, non verranno visualizzati messaggi. La scheda **attività** Visualizza solo i post di canale e non ci sarebbero canali comuni tra i due utenti.
- **Organigrammi: se** un utente accede a un organigramma in cui viene visualizzato un utente bloccato, l'utente bloccato non verrà visualizzato nell'organigramma e verrà visualizzato un messaggio di errore.
- **Scheda persone** : se un utente partecipa a una conversazione e l'utente viene bloccato in seguito, gli altri utenti vedranno un messaggio di errore al posto della scheda persone quando passa il puntatore del mouse sul nome dell'utente bloccato. Le azioni elencate nella scheda, ad esempio le chiamate e le chat, non saranno disponibili.
- **Contatti suggeriti** : gli utenti bloccati non vengono visualizzati nell'elenco dei contatti suggeriti (l'elenco dei contatti iniziale visualizzato per i nuovi utenti).
- **Contatti chat** -un utente non può visualizzare gli utenti bloccati nell'elenco contatti chat.
- **Chiamate contatti** -un utente può vedere gli utenti bloccati nell'elenco contatti chiamate, ma gli utenti bloccati verranno identificati e l'unica azione che l'utente può eseguire è eliminarli.
- **Migrazione di Skype to teams** -durante una migrazione di Skype for business a teams, tutti gli utenti, anche quelli bloccati da criteri di barriera delle informazioni, verranno migrati in teams e verranno gestiti come descritto sopra.

## <a name="required-licenses-and-permissions"></a>Licenze e autorizzazioni obbligatorie

Gli ostacoli alle informazioni stanno per essere implementati e sono inclusi negli abbonamenti, ad esempio:

- Microsoft 365 E5
- Office 365 E5
- Conformità avanzata di Office 365
- Conformità a Microsoft 365 E5

Per altri dettagli, inclusi i piani e i prezzi, Vedi soluzioni per la [conformità](https://products.office.com/business/security-and-compliance/compliance-solutions?rtc=1).

## <a name="more-information"></a>Ulteriori informazioni

- Per ulteriori informazioni sulle barriere informative, vedere [barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Per configurare i criteri di barriera delle informazioni, vedere [definire i criteri per le barriere informative](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies)

- Per modificare o rimuovere i criteri di barriera delle informazioni, vedere [modificare o rimuovere i criteri di barriera delle informazioni](https://docs.microsoft.com/office365/securitycompliance/information-barriers-edit-segments-policies.md)