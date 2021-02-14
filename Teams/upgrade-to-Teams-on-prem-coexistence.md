---
title: Coesistenza con Microsoft Teams e Skype for Business
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Eseguire l'aggiornamento da Skype for Business a Teams - Coesistenza
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0690af8226f3f992dcc12f68c6135c953eb043f5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533613"
---
# <a name="coexistence-with-teams-and-skype-for-business"></a>Coesistenza con Teams e Skype for Business

In questo articolo sono riepilogati i comportamenti che possono verificarsi quando si eseguono client Teams e Skype for Business nella stessa organizzazione, indipendentemente dalla modalità e dal metodo di aggiornamento utilizzato:

- [Riunioni](#meetings)
- [Interoperabilità](#interoperability)
- [Conversazioni di Teams e thread nativi](#teams-conversations---interop-versus-native-threads)
- [Icone di presenza](#presence)
- [Federazione](#federation)
- [Contatti](#contacts)



## <a name="meetings"></a>Riunioni

Indipendentemente dalla modalità, gli utenti possono sempre partecipare a qualsiasi tipo di riunione a cui sono stati invitati, che si tratta di Skype for Business o Teams.  Tuttavia, gli utenti devono partecipare alla riunione con un client corrispondente corrispondente al tipo di riunione:

- Se la riunione è una riunione di Teams, tutti i partecipanti (che siano utenti TeamsOnly, Islands o Skype for Business) usano il client Teams per partecipare alla riunione. Se Teams non è installato, l'utente verrà indirizzato sul Web, quando tenta di partecipare a una riunione.

- Se la riunione è una riunione Skype for Business, tutti i partecipanti (che si tratta di utenti TeamsOnly, Islands o Skype for Business) usano il client Skype for Business per partecipare alla riunione. Se il client Skype for Business non è installato, l'utente verrà indirizzato sul Web per partecipare tramite l'app Riunione Skype.

Quando si organizzano riunioni, il tipo di riunione programmato dipende dalla modalità dell'organizzatore, come illustrato nella tabella seguente:

| Modalità di organizzazione    |      Comportamento |
| :------------------ | :---------------- |
| TeamsOnly, SfbWithTeamsCollabAndMeetings |    Tutte le riunioni pianificate in Teams. Il componente aggiuntivo di Skype for Business non è disponibile in Outlook. | 
| SfbWithTeamsCollab, SfbOnly   | Tutte le riunioni pianificate in Skype for Business. Il componente aggiuntivo di Teams non è disponibile in Outlook. | 
| Isole | Per impostazione predefinita, le riunioni possono essere pianificate sia in Skype for Business che in Teams. Entrambi i componenti aggiuntivi sono disponibili in Outlook. Tuttavia, è possibile richiedere agli utenti delle isole di pianificare sempre riunioni in Teams assegnando loro un'istanza di TeamsMeetingPolicy con PreferredMeetingProviderForIslandsMode=Teams.| 


## <a name="interoperability"></a>Interoperabilità

Teams supporta l'interoperabilità ("interoperabilità") con Skype for Business in alcuni scenari. Per comunicazione interoperabile si intende una chat o una chiamata tra un utente di Skype for Business e un utente di Teams.  La comunicazione di interoperabilità è possibile solo tra due utenti; chat/chiamate tra più utenti o l'aggiunta di altri utenti non è supportato.

Viene creata una chat o una chiamata di interoperabilità tra due utenti quando ognuno dei seguenti valori è vero:

- Un utente usa Teams e l'altro usa Skype for Business.

- La modalità del destinatario della comunicazione iniziale NON è Isole (altrimenti la comunicazione dovrebbe essere nello stesso client) se entrambi gli utenti si trovano nella stessa organizzazione. Negli scenari federati, l'utente mittente usa Teams e il destinatario non è in modalità TeamsOnly. 

- L'utente di Teams NON ha anche un account Skype for Business ospitata in locale. 

All'interno della comunicazione di interoperabilità, la chat è solo in testo normale. Inoltre, la condivisione di file e la condivisione dello schermo non sono possibili *nella chat di interoperabilità stessa.* Tuttavia, gli utenti in una conversazione di interoperabilità possono ottenere facilmente la condivisione di file e/o schermo creando una riunione su richiesta dall'interno della chat di interoperabilità, come descritto di seguito:

- Se l'utente di Teams prova a condividere lo schermo, viene creata automaticamente una riunione di Teams su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente di Skype for Business. Facendo clic sul collegamento, l'utente di Skype for Business aprirà Teams e si unirà alla riunione. Entrambi gli utenti sono ora in una riunione di Teams e possono condividerli in base alle esigenze.

- Se l'utente di Skype for Business usa un client 2018 o versione successiva e prova a condividere qualsiasi contenuto, viene creata automaticamente una riunione Skype for Business su richiesta e viene inviato un collegamento di invito alla riunione al client dell'utente di Teams. Facendo clic sul collegamento, l'utente di Teams tenterà di partecipare alla riunione Skype for Business. Se l'utente di Teams ha installato il client Skype for Business, verrà aperto e all'utente verrà richiesto di eseguire l'accesso (se non è già stato effettuato l'accesso).  Se l'utente di Teams non ha installato il client Skype for Business, all'utente verrà richiesto di usare la versione Web. Una volta che entrambi gli utenti hanno eseguito l'accesso, sono in una riunione Skype for Business e possono condividerli in base alle esigenze.

## <a name="teams-conversations---interop-versus-native-threads"></a>Conversazioni di Teams - Interoperabilità e thread nativi

Poiché le comunicazioni interoperabili non supportano tutte le funzionalità della conversazione nativa di Teams, il client Teams mantiene thread di conversazione separati per le comunicazioni Teams-to-Teams e Teams-to-Skype for Business. Il rendering di queste conversazioni nell'interfaccia utente è diverso: I thread di interoperabilità possono essere differenziati da un normale thread nativo di Teams:

- Mancanza di controlli per RTF, condivisione di file/schermo, impossibilità di aggiungere utenti.
- Una modifica all'icona dell'utente di destinazione, con una "S" per Skype for Business.

Queste differenze sono mostrate negli screenshot seguenti:

Una conversazione nativa tra Teams e Teams con User G3 Test

![Diagramma che mostra una conversazione nativa tra Teams e Teams](media/teams-upgrade-native-thread.png)

Una conversazione di interoperabilità con lo stesso test User G3

![Diagramma che mostra una conversazione tra Teams e Teams interoperabile](media/teams-upgrade-interop-thread.png)

Una volta creato un thread di conversazione, il suo tipo non cambia mai. Una volta creato, un thread di interoperabilità in Teams verrà sempre instradato al client Skype for Business dell'utente di destinazione. Un thread nativo verrà sempre instradato al client Teams dell'utente di destinazione.  Se la modalità di un utente del destinatario cambia, i thread esistenti di Teams per tale utente non funzioneranno più e nella chat verrà visualizzata una nota con un collegamento per avviare una nuova conversazione nativa, come illustrato nello screenshot seguente.


![Diagramma che mostra una chat con un utente Skype for Business aggiornato](media/teams-upgrade-chat-with-upgraded-sfb-user.png)

## <a name="presence"></a>Icone di presenza

La presenza per un determinato utente si basa sull'attività dell'utente nel servizio tramite il client. La presenza viene quindi pubblicata in modo che gli altri utenti lo vedano.  Skype for Business e Teams sono servizi distinti con client separati, quindi ogni servizio ha il proprio stato presenza per un utente.   C'è anche la sincronizzazione tra i servizi di presenza in Teams e in Skype for Business online.  In questo modo un servizio può pubblicare potenzialmente la presenza dell'utente dall'altro servizio, se necessario. 

Il comportamento di pubblicazione della presenza si basa sulla modalità dell'utente. Esistono tre casi di base:

- Se un utente è in modalità TeamsOnly, tutti gli altri utenti vedono la presenza di Teams per quell'utente, indipendentemente dal client che usano.

- Se un utente è in una delle modalità Skype for Business, tutti gli altri utenti vedono la presenza di Skype for Business per quell'utente, indipendentemente dal client che usano.

- Se un utente è in modalità Isole, la presenza pubblicata in Skype for Business e Teams è indipendente, quindi la presenza mostrata agli utenti all'interno della stessa organizzazione dipenderà dal client dell'altro utente. Gli utenti di organizzazioni federate potranno vedere la sua presenza in base all'attività di Skype for Business, perché il traffico federato verso una modalità isole è atterra a Skype for Business.

Si supponga ad esempio che l'utente A sia in modalità Isole. Se l'Utente A è attivo in Teams ma non ha effettuato l'accesso a Skype for Business, gli altri utenti vedono l'Utente A come attivo dal proprio client Teams, ma nel client Skype for Business vedono l'Utente A come offline. Si tratta di un'operazione da progettazione, perché l'utente A non può essere raggiunto se non esegue il client. 


## <a name="federation"></a>Federazione

La federazione da Teams a un altro utente che usa Skype for Business richiede che l'utente di Teams sia ospitata online in Skype for Business. TeamsUpgradePolicy regola il routing per le chiamate e le chat federate in arrivo. Il comportamento di routing federato è uguale a quello degli scenari con lo stesso tenant, ad eccezione della modalità Isole. Quando i destinatari sono in modalità Isole:

- Le chat e le chiamate avviate da Teams vengono effettuate in Skype for Business se il destinatario è in un tenant federato.
- Le chat e le chiamate avviate da Teams vengono effettuate in Teams se il destinatario si trova nello stesso tenant.
- Le chat e le chiamate avviate da Skype for Business vengono sempre effettuate in Skype for Business.

Una chat federata può essere un thread nativo o un thread di interoperabilità. Visualizzare [le conversazioni di Teams ---interop-versus-native-threads.](#teams-conversations---interop-versus-native-threads)

- Se il destinatario e il mittente sono entrambi in modalità di aggiornamento di TeamsOnly, la conversazione sarà un'esperienza di chat nativa che include tutte le funzionalità avanzate di messaggistica e chiamata. Per altre informazioni, vedere [Esperienza di chat nativa per utenti esterni (federati) in Teams.](native-chat-for-external-users.md) 

- Se uno dei partecipanti alla conversazione NON è in modalità di aggiornamento di TeamsOnly, la conversazione rimane un'esperienza di interoperabilità con messaggi solo di testo. L'interfaccia utente espone le chat federate in modo simile ai thread di interoperabilità dello stesso tenant, con la differenza che esiste una nota che indica che l'utente è esterno.

Per maggiori dettagli, consulta [Gestire l'accesso](manage-external-access.md) esterno in Microsoft Teams e l'esperienza di chat nativa per [utenti esterni (federati) in Teams.](native-chat-for-external-users.md)

## <a name="contacts"></a>Contatti

Teams e Skype for Business dispongono di elenchi separati di contatti. Questo significa che le aggiunte, la rimozione e le modifiche dei contatti apportate in un sistema non vengono sincronizzate con l'altro sistema. Tuttavia, i contatti di Skype for Business vengono copiati automaticamente in Teams quando si verifica uno dei due eventi specifici: 

- Per qualsiasi utente di Skype for Business online, la prima volta che accede a Teams, i contatti da Skype for Business verranno copiati in Teams.  Questo comportamento non è disponibile per gli utenti con un account locale in Skype for Business Server.  

- Dopo l'aggiornamento a TeamsOnly (tramite l'assegnazione di TeamsUpgradePolicy o tramite Move-CsUser -MoveToTeams), la volta successiva che un utente accede a Teams, i contatti esistenti in Skype for Business verranno uniti a quelli già presenti in Teams. Questo comportamento si verifica sia che l'account Skype for Business dell'utente sia ospitata in locale o online. 

In entrambi i casi, il trasferimento dei contatti da Skype for Business a Teams è asincrono, quindi potrebbe essere necessario qualche minuto prima che i contatti vengano visualizzati in Teams. I due eventi precedenti attivano la copia.  

## <a name="related-links"></a>Collegamenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](migration-interop-guidance-for-teams-with-skype.md) 

[Configurare la connettività ibrida tra Skype for Business Server e Microsoft 365 o Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Spostare utenti tra locale e cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Impostazione delle impostazioni di coesistenza e aggiornamento](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Uso del servizio MMS (Meeting Migration Service)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

