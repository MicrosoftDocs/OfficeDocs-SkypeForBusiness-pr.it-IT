---
title: Indicazioni per larghezza di banda ridotta per Microsoft Teams per l'istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: jesegher
description: Articolo su Microsoft Teams per l'istruzione per risolvere i problemi di video e riunioni associati a una ridotta larghezza di banda. Genitori, educatori o amministratori IT hanno a disposizione varie opzioni per migliorare l'esperienza con Teams.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f34ea2e65906c648081a019d6acf8a3f8a5cd5
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/28/2020
ms.locfileid: "43034076"
---
# <a name="help-for-low-bandwidth-situations-for-teams-for-edu"></a>Indicazioni per le situazioni di larghezza di banda ridotta per Teams per l'istruzione

Quando si lavora in Microsoft Teams, molti elementi di rete possono incidere sulle prestazioni e la larghezza di banda ridotta è uno dei fattori che possono sembrare totalmente al di fuori del proprio controllo. Tenere in considerazione gli aspetti seguenti:

- Connessione Internet a bassa velocità per l'istituto di istruzione.
- Connessione Internet a bassa velocità per uno o più studenti.
- Orari in cui la larghezza di banda è ridotta a causa dell'utilizzo della rete in un'area.
- Periodi in cui la larghezza di banda si riduce a causa di interruzioni locali non dell'istituto di istruzione o degli studenti, ma che comunque incidono sulle prestazioni.
- Problemi che sono solo apparentemente associati alla larghezza di banda, ad esempio problemi hardware.

Questo articolo illustra le procedure consigliate da seguire per svariate attività di Teams quando si ha a che fare con un problema di larghezza di banda ridotta.

> [!IMPORTANT]
> Leggere le informazioni su [Come viene usata la memoria in Microsoft Teams](teams-memory-usage-perf.md). Ai problemi di larghezza di banda ridotta potrebbero infatti accompagnarsi problemi di risorse nel dispositivo. Se si cercano indicazioni sulla rete per Microsoft Teams, vedere [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md).

## <a name="resolving-low-bandwidth-issues-for-itadmins"></a>Risoluzione dei problemi di larghezza di banda ridotta per amministratori IT

Per gli amministratori IT, l'aspetto più importante da ricordare è che, sebbene esistano soluzioni rapide ai problemi di larghezza di banda estesi, è consigliabile valutare i casi con attenzione, perché alcuni problemi possono essere risolti a livello di singolo docente o anche di singolo studente o genitore.

In breve, agire come amministratore IT ha senso se i problemi di larghezza di banda riguardano un ampio gruppo di studenti e anche se le azioni intraprese a livello di studente o docente non sono state utili.

> [!NOTE]
> Se si ha tempo da investire, la [Guida sul controllo della qualità dell'esperienza](quality-of-experience-review-guide.md) è una lettura utile, che non è specifica per il settore dell'istruzione, ma offre comunque informazioni preziose. Questo permetterà agli amministratori IT esperti di analizzare a fondo l'esperienza dei propri insegnanti e studenti.

### <a name="meetings-and-video"></a>Riunioni e video

Una delle aree di attenzione principali per quanto riguarda i problemi di larghezza di banda sono le riunioni e in particolare il video nelle riunioni. Di seguito sono riportate alcune azioni che un amministratore IT può considerare per gestire i problemi segnalati da studenti o docenti e migliorare l'esperienza di riunione in un ambiente didattico.

#### <a name="meeting-policies"></a>Criteri di riunione

Per quanto riguarda le riunioni, l'area in cui si concentrano i problemi dovuti a larghezza di banda insufficiente è quella del video. Fortunatamente, Teams si adatta automaticamente alla larghezza di banda rilevata e l'amministratore IT può anche impostare opzioni dei criteri a livello di organizzatore e/o di utente, mirate a offrire a tutti la migliore esperienza possibile in base alla larghezza di banda disponibile in un determinato momento.

Alcuni degli elementi che è possibile impostare tramite criteri includono:

- Disabilitazione completa del video, in modo che nessuno possa abilitarlo.
- Velocità in bit dei contenuti multimediali (si imposta a livello di utente).

Per altre informazioni sulle opzioni disponibili e per informazioni dettagliate sui criteri che può essere necessario impostare per le riunioni e il video, vedere [Impostazioni dei criteri per le riunioni in Teams: audio e video](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).

#### <a name="screen-sharing-policies"></a>Criteri di condivisione dello schermo

In altri casi, è possibile che i docenti stiano condividendo l'intero schermo con gli studenti, mentre la condivisione deve essere limitata a un'applicazione rilevante per la lezione in corso. Questo può essere impostato anche tramite criteri, se è un metodo preferibile rispetto a lasciare la scelta ai singoli docenti.

Per informazioni sul modo in cui è possibile limitare la condivisione dello schermo con le impostazioni dei criteri, vedere [Impostazioni dei criteri per le riunioni in Teams: condivisione dello schermo](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams#meeting-policy-settings---audio--video).

#### <a name="dial-in-number-for-meetings"></a>Numero telefonico di accesso esterno per le riunioni

Per alcuni studenti potrebbe essere più facile accedere ad alcune sessioni della classe tramite telefono. È possibile fornire un numero di accesso esterno per le riunioni di Teams, in modo che gli studenti che riscontrano problemi possano telefonare in alternativa alla partecipazione a una riunione video.

Per altre informazioni, vedere [Impostare i numeri di telefono inclusi negli inviti in Microsoft Teams](set-the-phone-numbers-included-on-invites-in-teams.md).

## <a name="low-bandwidth-scenarios-as-an-educator"></a>Scenari di larghezza di banda ridotta come docenti

I docenti dovrebbero sentirsi autorizzati a intraprendere le azioni necessarie per risolvere i problemi di larghezza di banda. L'intervento dei docenti può essere una scelta migliore rispetto a quello dell'amministratore IT nelle situazioni seguenti:

- Se il problema è intermittente o relativamente transitorio.
- Se c'è un orario specifico in cui si può ipotizzare che si verifichino problemi o se il periodo di tempo in cui la larghezza di banda è ridotta ha una certa prevedibilità.

In questi casi, si possono compiere alcune azioni.

Per altre informazioni, vedere come [Usare Teams per la didattica quando la larghezza di banda è ridotta](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262).

## <a name="low-bandwidth-scenarios-as-a-parent-or-student"></a>Scenari di larghezza di banda ridotta come genitori o studenti

Ci sono anche situazioni, di cui è necessario discutere in modo proattivo con i docenti, in cui il problema della larghezza di banda può essere sul versante dello studente. Ad esempio, un numero elevato di studenti riesce a guardare le lezioni video senza problemi, mentre un numero limitato di studenti ha difficoltà.

Non è ragionevole aspettarsi che tutti i genitori siano in grado di risolvere questi problemi, inoltre i problemi di larghezza di banda ridotta possono essere al di fuori del controllo di uno studente o di un genitore. L'abitazione potrebbe non avere accesso alla banda larga, possono esserci molte persone nell'area immediatamente limitrofa che consumano larghezza di banda, potrebbe esserci instabilità della rete Internet e così via.

L'articolo [Usare Teams per la didattica quando la larghezza di banda è ridotta](https://support.office.com/article/use-teams-for-schoolwork-when-bandwidth-is-low-5c5675f7-1b55-471a-9daa-ec1e6df38262) raccoglie consigli utili per genitori e studenti, in caso di problemi.
