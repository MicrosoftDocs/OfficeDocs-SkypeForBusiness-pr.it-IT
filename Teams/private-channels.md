---
title: Canali privati in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i canali privati in Microsoft teams.
ms.openlocfilehash: d7a491a64e32edef61b067c864c21f41e19f267d
ms.sourcegitcommit: c15ab82834005b9a19247e06488f1f21161fc426
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/13/2019
ms.locfileid: "40020050"
---
# <a name="private-channels-in-microsoft-teams"></a>Canali privati in Microsoft Teams

I canali privati in Microsoft teams creano spazi focalizzati per la collaborazione all'interno del team. Solo gli utenti del team proprietari o membri del canale privato possono accedere al canale. Tutti gli utenti, inclusi gli ospiti, possono essere aggiunti come membri di un canale privato, purché siano già membri del team.

È consigliabile usare un canale privato se si vuole limitare la collaborazione a coloro che hanno bisogno di sapere o se si vuole facilitare la comunicazione tra un gruppo di persone assegnato a un progetto specifico, senza dover creare un team aggiuntivo da gestire.

Ad esempio, un canale privato è utile in questi scenari:

- Un gruppo di persone in un team vuole uno spazio concentrato per collaborare senza dover creare un team separato.
- Un sottoinsieme di persone in un team vuole un canale privato per discutere le informazioni riservate, come i bilanci, il resourcing, il posizionamento strategico e così via.

Un'icona di blocco indica un canale privato. Solo i membri dei canali privati possono vedere e partecipare ai canali privati a cui vengono aggiunti.

![Screenshot dei canali privati in un team](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Informazioni utili sui canali privati

Attualmente i canali privati supportano connettori e schede (ad eccezione di stream, Planner e maschere). Stiamo lavorando al supporto delle app complete per i canali privati, incluse le estensioni di messaggistica e i bot.

Ogni team può avere un massimo di 30 canali privati e ogni canale privato può avere un massimo di 250 membri. Il limite di 30 canali privati è in aggiunta al limite di canale standard di 200 per Team.

> [!NOTE]
> Aggiungiamo continuamente funzionalità ai canali privati in modo da controllare le informazioni più aggiornate su app, riunioni di canale e scalare canali privati per i team di grandi dimensioni.

## <a name="when-to-create-a-private-channel"></a>Quando creare un canale privato

Per determinare se un canale privato è appropriato, prendere in considerazione le domande seguenti su chi deve collaborare e su quale sia la collaborazione.

|Esiste già un team che ha queste persone come membri del team?  |Questo lavoro deve essere mantenuto privato dagli altri utenti?  |Ci sono più argomenti distinti da discutere?  |Recommendation  |
|---------|---------|---------|---------|
|Sì      |Sì         |Supporto per più paesi         |Creare un canale privato nel team esistente o valutare la possibilità di creare canali privati dedicati per ogni argomento.         |
|Sì     |Sì         |Supporto per riunioni private con ID conferenza di riunione dinamici         |Creare un canale privato nel team esistente.         |
|Sì     |Supporto per riunioni private con ID conferenza di riunione dinamici         |No         |Creare un canale nel team esistente.         |
|No     |No         |No         |Valutare la possibilità di creare un nuovo team.         |
|No     |No         |Sì         |Valutare la possibilità di creare un nuovo team e quindi, in base alla riservatezza di ogni argomento, valutare la possibilità di creare canali separati standard o privati per ogni argomento.         |
|No     |Sì         |Supporto per riunioni private con ID conferenza di riunione dinamici         |Creare un nuovo team o creare un nuovo canale privato in un team esistente.         |

Quando viene creato un canale privato, è collegato al team padre e non può essere spostato in un team diverso. Inoltre, i canali privati non possono essere convertiti in canali standard e viceversa.

## <a name="private-channel-creation-and-membership"></a>Creazione e appartenenza a canali privati

### <a name="who-can-create-private-channels"></a>Chi può creare canali privati?

Per impostazione predefinita, qualsiasi proprietario del team o membro del team può creare un canale privato. Gli utenti non possono crearli. La possibilità di creare canali privati può essere gestita a livello di team e a livello di organizzazione:

- Nella scheda **Impostazioni** di un team i proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati.
- Come amministratore, puoi usare i [criteri](teams-policies.md) per controllare gli utenti dell'organizzazione autorizzati a creare canali privati.

La persona che crea un canale privato è il proprietario del canale privato e solo il proprietario del canale privato può aggiungere o rimuovere direttamente gli utenti. Un proprietario di canale privato può aggiungere qualsiasi membro del team a un canale privato creato, inclusi gli utenti. I membri di un canale privato hanno uno spazio di conversazione sicuro e quando vengono aggiunti nuovi membri possono vedere tutte le conversazioni (anche le conversazioni precedenti) nel canale privato.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>Cosa succede quando un membro del team esce o viene rimosso da un team?

Se un membro del team esce o viene rimosso da un team, l'utente può anche lasciare o essere rimosso da tutti i canali privati del team. Se l'utente viene aggiunto di nuovo al team, deve essere aggiunto di nuovo ai canali privati del team.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>Cosa succede quando un proprietario di canale privato viene rimosso da un canale privato?

Un proprietario di canale privato non può essere rimosso dal client teams se è l'ultimo proprietario di uno o più canali privati.

Se un proprietario di canale privato lascia l'organizzazione o se viene rimosso dal gruppo Office 365 associato al team, un membro del canale privato viene automaticamente innalzato di stato come proprietario del canale privato.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>Cosa possono vedere i proprietari e i membri del team in un canale privato?

I proprietari del team possono visualizzare i nomi di tutti i canali privati nel proprio team e possono anche eliminare qualsiasi canale privato nel team. (Un canale privato eliminato può essere ripristinato entro 30 giorni dopo l'eliminazione). I proprietari del team non possono visualizzare i file in un canale privato o le conversazioni e l'elenco dei membri di un canale privato, a meno che non siano membri del canale privato.

La tabella seguente mostra chi può vedere cosa c'è in un canale privato.

|Elemento  |Il proprietario del team può vedere |I membri del team possono vedere |
|---------|---------|---------|
|Nome e descrizione    |Tutti i canali privati del team         |Solo i canali privati a cui vengono aggiunti         |
|Conversazioni e schede     |Solo quando si aggiunge al canale privato         |Solo quando si aggiunge al canale privato         |
|File e contenuto    |Solo quando si aggiunge al canale privato        |Solo quando si aggiunge al canale privato         |
|Proprietario del canale privato    |Tutti i canali privati del team        |Solo quando si aggiunge al canale privato         |
|Indicatore di data ultima attività  |Tutti i canali privati del team       |Solo quando si aggiunge al canale privato         |

## <a name="manage-private-channels"></a>Gestire i canali privati

Nella tabella seguente sono illustrate le azioni che i proprietari, i membri e gli utenti possono eseguire nei canali privati.

|Azione  |Proprietario del team|Membro del team|Guest team|Proprietario del canale privato|Membro del canale privato|Guest Channel privato|
|---------|---------|---------|---------|---------|---------|---------|
|Creare un canale privato|Sì<sup>1</sup>|Sì<sup>1, 2</sup>|No|N/D|N/D|N/D|
|Eliminare un canale privato|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Uscire da un canale privato|N/D|N/D|N/D|Sì<sup>3</sup>|Sì|Supporto per più paesi|
|Modifica canale privato|No|N/D|N/D|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Ripristinare il canale privato eliminato|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Aggiungere membri|No|N/D|N/D|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Modificare le impostazioni|No|N/D|N/D|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Gestire le schede e le app|No|N/D|N/D|Sì<sup>4</sup>|Sì<sup>5</sup>|No|

<sup>1</sup> supponendo che il criterio configurato dall'amministratore consenta all'utente di creare canali privati.<br>
<sup>2</sup> ogni team ha un'impostazione che i proprietari del team possono attivare o disattivare per consentire ai membri del team di creare canali privati. I proprietari del team possono sempre creare canali privati.<br>
<sup>3</sup> supponendo che il proprietario del canale privato non sia l'ultimo proprietario del canale. <br>
<sup>4</sup> richiede al team di installare un'app per un canale privato per usarla.<br>
<sup>5</sup> i proprietari di canali privati possono configurare questo.

### <a name="manage-private-channel-membership-and-settings"></a>Gestire l'appartenenza e le impostazioni dei canali privati

Ogni canale privato ha le proprie impostazioni, inclusa la possibilità di aggiungere e rimuovere membri, aggiungere schede e @mentioning per l'intero canale. Queste impostazioni sono indipendenti dalle impostazioni del team padre. Quando viene creato un canale privato, eredita le impostazioni dal team padre, dopodiché le impostazioni possono essere modificate indipendentemente dalle impostazioni del team padre.

Il proprietario del canale privato può fare clic su **Gestisci canale**e quindi usare le schede **membri** e **Impostazioni** per aggiungere o rimuovere membri e modificare le impostazioni.  

![Screenshot delle impostazioni dei canali privati](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Gestire il ciclo di vita dei canali privati

Per informazioni su come gestire il ciclo di vita dei canali privati nell'organizzazione, vedere [gestire il ciclo di vita dei canali privati in teams](private-channels-life-cycle-management.md) . Questo include come controllare se gli utenti dell'organizzazione possono creare canali privati, come creare un canale privato per conto di un proprietario del team, come ottenere un elenco di tutti i messaggi di canale privato per scopi di archiviazione e controllo e altre attività di gestione.  

## <a name="private-channel-sharepoint-sites"></a>Siti di SharePoint per canali privati

Ogni canale privato ha una raccolta siti di SharePoint ottimizzata per la condivisione di file e il provisioning rapido. La raccolta siti separata consente di garantire l'accesso ai file di canale privato è limitato solo ai membri del canale privato rispetto al sito del team in cui i proprietari del team hanno accesso a tutti gli asset all'interno della raccolta siti. Queste raccolte siti vengono create con una raccolta documenti per impostazione predefinita e possono essere facilmente migliorate per una raccolta siti completa tramite l' [interfaccia di gestione del sito](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Ogni raccolta siti viene creata nella stessa area geografica della raccolta siti del team padre. Questi siti leggeri hanno un ID modello personalizzato, "TEAMCHANNEL # 0", per semplificare la gestione tramite le API PowerShell e Graph.

Per contenere un numero maggiore di raccolte siti per tenant, il limite è aumentato da 500.000 a 2 milioni. Una raccolta siti canale privato sincronizza la classificazione dei dati ed eredita le autorizzazioni di accesso guest dalla raccolta siti del team padre.  L'appartenenza al proprietario della raccolta siti e ai gruppi di membri viene mantenuta sincronizzata con l'appartenenza del canale privato all'interno di teams. Tutte le modifiche apportate all'appartenenza al proprietario o ai gruppi di membri in SharePoint Online verranno ripristinate automaticamente nell'appartenenza a un canale privato entro quattro ore. In scenari in cui alcuni utenti devono accedere ai documenti senza dover accedere ai messaggi del canale privato, aggiungerli al gruppo visitatori del sito o a un nuovo gruppo separato da proprietari e membri.

Teams gestisce il ciclo di vita della raccolta siti di SharePoint del canale privato. Se la raccolta siti viene eliminata all'esterno dei team, un processo in background ripristina il sito entro quattro ore, purché il canale privato sia ancora attivo. Se il sito viene eliminato e eliminato in maniera difficile, viene effettuato il provisioning di una nuova raccolta siti per il canale privato.

Se viene ripristinato un canale privato o un team che contiene un canale privato, le raccolte siti verranno ripristinate. Se viene ripristinata una raccolta siti del canale privato ed è oltre la finestra di eliminazione morbida di 30 giorni per il canale privato, la raccolta siti funziona come raccolta siti autonoma.

## <a name="private-channel-message-compliance-records"></a>Record di conformità dei messaggi del canale privato

I record per i messaggi inviati in un canale privato vengono recapitati alla cassetta postale di tutti i membri del canale privato, invece che a una cassetta postale del gruppo. I titoli dei record sono formattati per indicare il canale privato da cui sono stati inviati.

Per altre informazioni sull'esecuzione di una ricerca di eDiscovery per i messaggi di canale privato, vedere [eDiscovery di canali privati](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Considerazioni su Access in canali privati

Quando viene creato un nuovo blocco appunti di OneNote in un canale privato, gli altri utenti possono comunque accedere al blocco appunti perché il comportamento è uguale alla condivisione dell'accesso a qualsiasi altro elemento in un sito di SharePoint di un canale privato con un utente.

Se a un utente viene concesso l'accesso a un blocco appunti in un canale privato tramite SharePoint, la rimozione dell'utente dal team o dal canale privato non rimuoverà l'accesso dell'utente al blocco appunti.

Se un blocco appunti esistente viene aggiunto come scheda a un canale privato, l'accesso al canale privato non viene modificato. Questo significa quanto segue:

- Non tutti nel canale privato avranno accesso al blocco appunti per impostazione predefinita. Il motivo è che potrebbe non avere accesso alla posizione in cui è ospitato il blocco appunti, ad esempio il sito di SharePoint di un altro team.
- Gli utenti che non sono membri del canale privato possono visualizzare il blocco appunti.  

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica di team e canali in teams](teams-channels-overview.md)
- [Panoramica di PowerShell Teams](teams-powershell-overview.md)
- [Usare l'API Microsoft Graph per lavorare con i team](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
