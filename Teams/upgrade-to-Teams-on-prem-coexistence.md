---
title: Eseguire l'aggiornamento a teams da una distribuzione locale di Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 10/22/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aggiornamento da Skype for Business a Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11252c916224393c19ebc11c4c40faceab02342c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940717"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coesistenza con teams e Skype for business

Questo articolo riepiloga il comportamento che può essere sperimentato quando si esegue sia i team che i client Skype for business nella stessa organizzazione, indipendentemente dalla modalità e dal metodo di aggiornamento usato:

- [Riunioni](#meetings)
- [Interoperabilità](#interoperability)
- [Conversazioni in teams-interoperabilità contro thread nativi](#teams-conversations---interop-versus-native-threads)
- [Icone di presenza](#presence)
- [Federazione](#federation)
- [Contatti](#contacts)



## <a name="meetings"></a>Riunioni

Indipendentemente dalla modalità, gli utenti possono sempre partecipare a qualsiasi tipo di riunione a cui sono invitati, che si tratti di Skype for business o teams.  Gli utenti devono tuttavia partecipare alla riunione con un client corrispondente che corrisponda al tipo di riunione:

- Se la riunione è una riunione di teams, tutti i partecipanti (sia TeamsOnly, Islands o Skype for Business Users) usano il client teams per partecipare alla riunione. Se teams non è installato, l'utente verrà indirizzato al Web, dopo aver tentato di partecipare a una riunione.

- Se la riunione è una riunione Skype for business, tutti i partecipanti (che si tratti di TeamsOnly, isole o utenti Skype for business) usano il client Skype for business per partecipare alla riunione. Se il client Skype for business non è installato, l'utente verrà indirizzato al Web per partecipare tramite l'app riunione Skype.

Durante l'organizzazione delle riunioni, il tipo di riunione che viene programmato si basa sulla modalità dell'organizzatore, come illustrato nella tabella seguente:

| Modalità di organizzazione    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Tutte le riunioni programmate in teams. Il componente aggiuntivo Skype for business non è disponibile in Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Tutte le riunioni programmate in Skype for business. Il componente aggiuntivo teams non è disponibile in Outlook. | 
| Isole | Per impostazione predefinita, le riunioni possono essere programmate sia in Skype for business che in teams. In Outlook sono disponibili entrambi i componenti aggiuntivi. Tuttavia, puoi facoltativamente richiedere che gli utenti in Isole impegnino sempre le riunioni in teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode = teams.| 


## <a name="interoperability"></a>Interoperabilità

Teams supporta l'interoperabilità ("Interop") con Skype for business in alcuni scenari. Interoperabilità comunicazioni fa riferimento a una chat o a una chiamata tra un utente di Skype for business e un utente di teams.  Le comunicazioni di interoperabilità sono possibili solo tra due utenti; la chat/chiamata multiparte o l'aggiunta di altri utenti non è supportata.

Una chat di interoperabilità o una chiamata tra due utenti viene creata quando ognuna delle condizioni seguenti è vera:

- Un utente usa teams e l'altro usa Skype for business.

- La modalità del destinatario della comunicazione iniziale non è Islands (in caso contrario la comunicazione atterrerà nello stesso client) se entrambi gli utenti si trovano nella stessa organizzazione. Negli scenari federati l'utente mittente USA teams e il destinatario non è in modalità TeamsOnly. 

- L'utente teams non ha anche un account Skype for business ospitato in locale. 

Nella comunicazione di interoperabilità la chat è solo testo normale. Inoltre, la condivisione di file e la condivisione dello schermo non sono possibili *nella chat di interoperabilità*. Gli utenti di una conversazione di interoperabilità possono tuttavia raggiungere facilmente la condivisione di file e/o dello schermo creando una riunione su richiesta, dall'interno della chat di interoperabilità, come descritto di seguito:

- Se l'utente teams tenta di condividere lo schermo, viene creata automaticamente una riunione di Team su richiesta e viene inviato un collegamento invita alla riunione al client dell'utente di Skype for business. Dopo aver fatto clic sul collegamento, l'utente di Skype for business aprirà teams e parteciperà alla riunione. Entrambi gli utenti si trovano ora in una riunione di teams e possono essere condivisi in base alle esigenze.

- Se l'utente di Skype for business usa un client da 2018 o versione successiva e tenta di condividere qualsiasi contenuto, viene creata automaticamente una riunione Skype for business su richiesta e viene inviato un collegamento invita alla riunione al client dell'utente del team. Dopo aver fatto clic sul collegamento, l'utente del team tenterà di partecipare alla riunione Skype for business. Se l'utente di Teams ha installato il client Skype for business, viene aperto e viene richiesto di accedere (se non è già stato effettuato l'accesso).  Se l'utente teams non ha installato il client Skype for business, all'utente verrà richiesto di usare la versione Web. Una volta che entrambi gli utenti hanno eseguito l'accesso, si trovano in una riunione Skype for business e possono essere condivisi in base alle esigenze.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversazioni in teams-interoperabilità contro thread nativi

Poiché le comunicazioni di interoperabilità non supportano tutte le funzionalità della conversazione di Team nativi, il client teams mantiene i thread di conversazione separati per le comunicazioni team-to-teams e teams-to-Skype for business. Queste conversazioni vengono visualizzate in modo diverso nell'interfaccia utente: i thread di interoperabilità possono essere differenziati da un normale thread nativo di teams:

- Mancanza di controlli per il testo RTF, la condivisione di file/schermi, l'impossibilità di aggiungere utenti.
- Una modifica all'icona dell'utente di destinazione, che mostra una "S" per Skype for business.

Queste differenze sono illustrate negli screenshot seguenti:

Una conversazione nativa teams-to-teams con test utente G3

![Diagramma che mostra una conversazione nativa teams-to-Teams](media/teams-upgrade-native-thread.png)

Una conversazione di interoperabilità con lo stesso test utente G3

![Diagramma che mostra una conversazione di interoperabilità teams-to-Teams](media/teams-upgrade-interop-thread.png)

Dopo aver creato un thread di conversazione, il tipo non cambia mai. Una volta creato, un thread di interoperabilità in teams verrà sempre indirizzato al client Skype for business dell'utente di destinazione. Un thread nativo verrà sempre indirizzato al client Teams dell'utente di destinazione.  Se la modalità di un utente del destinatario cambia, i thread di team esistenti non funzioneranno più e verrà visualizzata una nota in quella chat con un collegamento per avviare una nuova conversazione nativa, come illustrato nello screenshot seguente.


![Diagramma che mostra una chat con l'utente Skype for business aggiornato](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Icone di presenza

La presenza di un utente specifico si basa sulle attività dell'utente nel servizio tramite il client. La presenza viene quindi pubblicata per consentire ad altri utenti di visualizzarla.  Skype for business e teams sono servizi distinti con client distinti, quindi ogni servizio ha un proprio stato di presenza per un utente.   Esiste anche la sincronizzazione tra i servizi di presenza in teams e in Skype for business online.  Ciò consente a un servizio di pubblicare potenzialmente la presenza dell'utente dall'altro servizio, se necessario. 

Il comportamento di pubblicazione della presenza si basa sulla modalità dell'utente. Sono disponibili tre casi di base:

- Se un utente è in modalità TeamsOnly, tutti gli altri utenti vedranno la presenza di team per quell'utente, indipendentemente dal client che usano.

- Se un utente si trova in una delle modalità Skype for business, tutti gli altri utenti vedranno la presenza di Skype for business per l'utente, indipendentemente dal client che usano.

- Se un utente è in modalità isole, la presenza pubblicata in Skype for business e teams è indipendente, quindi la presenza mostrata agli utenti all'interno della stessa organizzazione dipende dal client dell'altro utente. Gli utenti delle organizzazioni federate vedranno la presenza dell'utente in base alle attività di Skype for business, poiché il traffico federato verso un utente in modalità isole atterra in Skype for business.

Supponiamo ad esempio che l'utente A sia in modalità isole. Se l'utente A è attivo in teams ma non ha eseguito l'accesso a Skype for business, altri utenti vedranno l'utente come attivo dal client teams, ma nel client Skype for business vedranno l'utente come offline. In base alla progettazione, poiché l'utente A non può essere raggiunto se non esegue il client. 


## <a name="federation"></a>Federazione

La Federazione da Teams a un altro utente che usa Skype for business richiede che l'utente dei team sia ospitato online in Skype for business. TeamsUpgradePolicy regola il routing per le chiamate e le Chat federate in arrivo. Il comportamento di routing federato è lo stesso per gli scenari dello stesso tenant, ad eccezione della modalità isole. Quando i destinatari sono in modalità isole:

- Chat e chiamate avviate da teams atterrano in Skype for business se il destinatario si trova in un tenant federato.
- Chat e chiamate avviate da teams atterrano in teams se il destinatario si trova nello stesso tenant.
- Chat e chiamate avviate da Skype for business sempre atterrano in Skype for business.

Una chat federata può essere un thread nativo o un thread di interoperabilità. Vedere [conversazioni di team---i thread di interoperabilità rispetto a quelli nativi](#teams-conversations---interop-versus-native-threads).

- Se il destinatario e il mittente sono entrambi in modalità di aggiornamento di TeamsOnly, la conversazione sarà un'esperienza di chat nativa che include tutte le funzionalità di messaggistica e chiamata avanzate. Per altre informazioni, leggere l' [esperienza di chat nativa per gli utenti esterni (federati) in teams](native-chat-for-external-users.md). 

- Se uno dei partecipanti alla conversazione non è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con i messaggi di solo testo. L'interfaccia utente espone le Chat federate in modo simile ai thread di interoperabilità dello stesso tenant, ad eccezione di una nota che indica che l'utente è esterno.

Per altre informazioni, vedere [gestire l'accesso esterno in Microsoft teams e l'](manage-external-access.md) [esperienza di chat nativa per utenti esterni (federati) in teams](native-chat-for-external-users.md).

## <a name="contacts"></a>Contatti

I team e Skype for business hanno elenchi separati di contatti. Ciò significa che le aggiunte di contatti, la rimozione e le modifiche apportate in un sistema non vengono sincronizzate con l'altro sistema. Tuttavia, i contatti di Skype for business vengono copiati automaticamente in teams quando si verifica uno di questi due eventi specifici: 

- Per tutti gli utenti di Skype for business online, la prima volta che accedono ai team, i contatti di Skype for business verranno copiati in teams.  Questo comportamento non è disponibile per gli utenti con un account locale in Skype for Business Server.  

- Dopo l'aggiornamento di un utente a TeamsOnly (tramite l'assegnazione di TeamsUpgradePolicy o tramite Move-CsUser-MoveToTeams), la volta successiva che un utente accede a teams, i contatti esistenti in Skype for business verranno uniti ai contatti esistenti già presenti in teams. Questo comportamento si verifica se l'account Skype for business dell'utente è ospitato in locale o online. 

In entrambi i casi, il trasferimento di contatti da Skype for business a teams è asincrono, quindi potrebbero essere pochi minuti prima che i contatti vengano visualizzati in teams. I due eventi descritti sopra sono quelli che innescano la copia.  

## <a name="related-links"></a>Collegamenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio di migrazione delle riunioni (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

