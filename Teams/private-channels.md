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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i canali privati in Microsoft Teams.
ms.openlocfilehash: 769fd2b489d65b276823abd7c3ff8f579100617a
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637935"
---
# <a name="private-channels-in-microsoft-teams"></a>Canali privati in Microsoft Teams

I canali privati di Microsoft Teams creano spazi dedicati per la collaborazione all'interno dei team. Solo gli utenti proprietari del team o membri del canale privato possono accedere al canale. Tutti gli utenti, inclusi gli utenti guest, possono essere aggiunti come membri a un canale privato, purché siano già membri del team.

È possibile usare un canale privato se si vuole limitare la collaborazione agli utenti che hanno la necessità acquisire competenze o se si vuole agevolare le comunicazioni tra un gruppo di persone assegnato a un progetto specifico, senza dover gestire un altro team.

Ad esempio, un canale privato è utile negli scenari seguenti:

- Un gruppo di persone in un team desidera uno spazio mirato per collaborare senza dover creare un team distinto.
- Un sottoinsieme di persone in un team vuole un canale privato per discutere di informazioni riservate, come budget, gestione delle risorse, posizionamento strategico e così via.

Un'icona a forma di lucchetto indica un canale privato. Solo i membri dei canali privati possono visualizzare e partecipare ai canali privati a cui vengono aggiunti.

![Schermata di canali privati in un team](media/private-channels-in-teams.png)

## <a name="what-you-need-to-know-about-private-channels"></a>Informazioni necessarie riguardo ai canali privati

Attualmente, i canali privati supportano i connettori e le schede, ad eccezione di Stream, Planner e Forms. Stiamo lavorando per fornire un supporto completo delle app per i canali privati, tra cui le estensioni per la messaggistica e i bot.

Ogni team può avere un massimo di 30 canali privati e ogni canale privato può avere un massimo di 250 membri. Il limite di 30 canali privati si aggiunge al limite di 200 standard per ogni team.

> [!NOTE]
> Vengono aggiunte continuamente funzionalità ai canali privati, ritornare per le informazioni più aggiornate relative ad app, riunioni di canale ed estensione dei canali privati per i team di grandi dimensioni.

## <a name="when-to-create-a-private-channel"></a>Quando creare un canale privato

Per determinare se un canale privato è la soluzione adeguata, valutare le domande seguenti su chi deve collaborare e sull’oggetto della collaborazione.

|Esiste già un team che ha queste persone come membri?  |Il lavoro deve essere mantenuto privato rispetto agli altri utenti?  |Gli argomenti di discussione sono molteplici?  |Consiglio  |
|---------|---------|---------|---------|
|Sì      |Sì         |Sì         |Creare un canale privato nel team esistente o considerare la possibilità di creare canali privati dedicati per ogni argomento.         |
|Sì     |Sì         |No         |Creare un canale privato nel team esistente.         |
|Sì     |No         |No         |Creare un canale nel team esistente.         |
|No     |No         |No         |È consigliabile creare un nuovo team.         |
|No     |No         |Sì         |È consigliabile creare un nuovo team e quindi, in base alla riservatezza di ogni argomento, creare canali standard o privati distinti per ogni argomento.         |
|No     |Sì         |No         |Creare un nuovo team e prendere in considerazione la creazione di un canale privato.         |

Quando viene creato un canale privato, questo viene collegato al team padre e non può essere spostato in un altro team. Inoltre, i canali privati non possono essere convertiti in canali standard e viceversa.

## <a name="private-channel-creation-and-membership"></a>Creazione e appartenenza a un canale privato

### <a name="who-can-create-private-channels"></a>Chi può creare i canali privati?

Per impostazione predefinita, tutti i proprietari o i membri del team possono creare un canale privato. Gli utenti guest non possono crearli. La possibilità di creare canali privati può essere gestita a livello di team e a livello di organizzazione.

> 1. Accedere all'interfaccia di amministrazione <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

> 2. Usare i [criteri](teams-policies.md) per controllare gli utenti dell'organizzazione che possono creare canali privati.
    Dopo aver impostato i criteri, i proprietari del team possono disattivare o attivare la possibilità per i membri di creare canali privati nella scheda **Impostazioni** di un team.

La persona che crea un canale privato è il proprietario del canale privato e solo il proprietario del canale privato può aggiungere o rimuovere direttamente le persone da quest'ultimo. Il proprietario di un canale privato può aggiungere qualsiasi membro del team a un canale privato creato, inclusi gli utenti guest. I membri di un canale privato dispongono di uno spazio di conversazione sicuro e, quando vengono aggiunti nuovi membri, questi possono vedere tutte le conversazioni nel canale privato, anche quelle avvenute in precedenza.

### <a name="what-happens-when-a-team-member-leaves-or-is-removed-from-a-team"></a>Cosa succede quando un membro del team lascia o viene rimosso da un team?

Se un membro del team lascia o viene rimosso da un team, tale utente lascerà o verrà rimosso anche da tutti i canali privati del team. Se l'utente viene aggiunto di nuovo al team, sarà necessario aggiungerlo di nuovo ai canali privati del team.

### <a name="what-happens-when-a-private-channel-owner-is-removed-from-a-private-channel"></a>Cosa succede quando un proprietario di un canale privato viene rimosso da un canale privato?

Il proprietario di un canale privato non può essere rimosso tramite il client di Teams, se si tratta dell'ultimo proprietario di uno o più canali privati.

Se un proprietario di canale privato esce dall'organizzazione o se viene rimosso dal gruppo Microsoft 365 associato al team, un membro del canale privato viene automaticamente promosso come proprietario del canale privato.

### <a name="what-can-team-owners-and-team-members-see-in-a-private-channel"></a>Cosa possono visualizzare i proprietari e i membri del team in un canale privato?

I proprietari del team possono visualizzare i nomi di tutti i canali privati nel loro team nonché eliminare qualsiasi canale privato del team. È possibile ripristinare un canale privato entro 30 giorni dopo l’eliminazione. I proprietari dei team non possono visualizzare i file in un canale privato o le conversazioni e l'elenco dei membri di un canale privato, a meno che non siano membri di tale canale privato.

La tabella seguente mostra chi può visualizzare cosa in un canale privato.

|Elemento  |Il proprietario di un team può visualizzare |I membri di un team possono visualizzare |
|---------|---------|---------|
|Nome e descrizione    |Tutti i canali privati del team         |Solo i canali privati a cui sono stati aggiunti         |
|Conversazioni e schede     |Solo se aggiunto al canale privato         |Solo se aggiunto al canale privato         |
|File e contenuti    |Solo se aggiunto al canale privato        |Solo se aggiunto al canale privato         |
|Proprietario di un canale privato    |Tutti i canali privati del team        |Solo se aggiunto al canale privato         |
|Data e ora dell’ultima attività  |Tutti i canali privati del team       |Solo se aggiunto al canale privato         |

## <a name="manage-private-channels"></a>Gestire i canali privati

Nella tabella seguente sono illustrate le azioni che i proprietari, i membri e gli utenti guest possono eseguire nei canali privati.

|Azione  |Proprietario di un team|Membro di un team|Utente guest di un team|Proprietario di un canale privato|Membro di un canale privato|Utente guest di un canale privato|
|---------|---------|---------|---------|---------|---------|---------|
|Creare un canale privato|Sì<sup>1</sup>|Sì<sup>1,2</sup>|No|N/D|N/D|N/D|
|Eliminare un canale privato|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Lasciare un canale privato|N/D|N/D|N/D|Sì<sup>3</sup>|Sì|Sì|
|Modificare un canale privato|No|N/D|N/D|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Ripristinare un canale privato eliminato|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Aggiungere membri|No|N/D|N/D|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Modificare le impostazioni|No|N/D|N/D|Sì|Supporto per riunioni private con ID conferenza di riunione dinamici|No|
|Gestire schede e app|No|N/D|N/D|Sì<sup>4</sup>|Sì<sup>5</sup>|No|

<sup>1</sup> Presupponendo che i criteri configurati dall'amministratore consentano all'utente di creare canali privati.<br>
<sup>2</sup> Ogni team ha un'impostazione che può essere attivata o disattivata dai proprietari di un team per consentire ai membri di creare canali privati. I proprietari di un team possono sempre creare canali privati.<br>
<sup>3</sup> Presupponendo che il proprietario del canale privato non sia l'ultimo proprietario del canale. <br>
<sup>4</sup> È necessario che il team abbia installato un'app per usare un canale privato.<br>
<sup>5</sup> I proprietari di canali privati possono configurare questa opzione.

### <a name="manage-private-channel-membership-and-settings"></a>Gestire l'appartenenza e le impostazioni di un canale privato

Ogni canale privato ha impostazioni personalizzate, tra cui la possibilità di aggiungere e rimuovere membri, aggiungere schede e @menzioni per l'intero canale. Queste impostazioni sono indipendenti dalle impostazioni del team padre. Quando viene creato un canale privato, questo eredita le impostazioni del team padre, che possono in seguito essere modificate indipendentemente dalle impostazioni del team padre.

Il proprietario del canale privato può fare clic su **Gestisci canale** e quindi usare le schede **Membri** e **Impostazioni** per aggiungere o rimuovere membri e modificare le impostazioni.  

![Schermata delle impostazioni di un canale privato](media/private-channels-in-teams-channel-settings.png)

## <a name="manage-the-life-cycle-of-private-channels"></a>Gestire il ciclo di vita dei canali privati

Per informazioni su come gestire il ciclo di vita dei canali privati nell'organizzazione, vedere [Gestire il ciclo di vita dei canali privati in Teams](private-channels-life-cycle-management.md). Sono incluse informazioni su come controllare se gli utenti dell'organizzazione possono creare canali privati, come creare un canale privato per conto del proprietario del team, come ottenere un elenco di tutti i messaggi del canale privato a scopo di archiviazione e controllo e altre attività di gestione.  

## <a name="private-channel-sharepoint-sites"></a>Siti di SharePoint del canale privato

Ogni canale privato dispone di una raccolta siti di SharePoint ottimizzata per la condivisione di file e il provisioning rapido. La raccolta siti separata consente di garantire l'accesso ai file del canale privato solo ai membri del canale privato, diversamente dal sito del team in cui i proprietari del team hanno accesso a tutte le risorse della raccolta siti. Queste raccolte siti vengono create con una raccolta documenti per impostazione predefinita e possono essere facilmente migliorate per ottenere una raccolta siti completa tramite l'[interfaccia di gestione dei siti](https://support.office.com/article/Enable-or-disable-site-collection-features-A2F2A5C2-093D-4897-8B7F-37F86D83DF04). Ogni raccolta siti viene creata nella stessa area geografica della raccolta siti del team padre. Questi siti semplificati hanno un ID modello personalizzato, "TEAMCHANNEL#0", per semplificare la gestione con PowerShell e API Graph.  Per impostazione di progettazione, non sono visibili nell'interfaccia di amministrazione di SharePoint.

Per ospitare un maggior numero di raccolte siti per tenant, il limite è stato aumentato da 500.000 a 2 milioni. Una raccolta siti di un canale privato sincronizza la classificazione dei dati ed eredita le autorizzazioni di accesso guest dalla raccolta siti del team padre.  L'appartenenza ai gruppi dei membri e di proprietari della raccolta siti viene mantenuta sincronizzata con quella ai canali privati in Teams. Le modifiche apportate all'appartenenza ai gruppi di membri o di proprietari in SharePoint Online verranno trasferite automaticamente all'appartenenza ai canali privati entro quattro ore. Negli scenari in cui alcuni utenti hanno l'esigenza di accedere ai documenti senza bisogno di accedere ai messaggi del canale privato, è possibile aggiungerli al gruppo Visitatori nel sito o a un nuovo gruppo distinto da quelli di Proprietari e Membri.

Teams gestisce il ciclo di vita della raccolta siti di SharePoint del canale privato. Se la raccolta siti viene eliminata all'esterno di Teams, un processo in background ripristina il sito entro quattro ore, a condizione che il canale privato sia ancora attivo. Se il sito viene eliminato ed eliminato definitivamente, viene eseguito il provisioning di una nuova raccolta siti per il canale privato.

Se un canale privato o un team che contiene un canale privato viene ripristinato, le raccolte siti vengono ripristinate con esso. Se viene ripristinata una raccolta siti del canale privato al di là del periodo di eliminazione temporanea di 30 giorni per il canale privato, la raccolta siti funziona come raccolta siti autonoma.

## <a name="private-channel-message-compliance-records"></a>Record di conformità dei messaggi del canale privato

I record per i messaggi inviati in un canale privato vengono recapitati nella cassetta postale di tutti i membri del canale privato, anziché in una cassetta postale di gruppo. I titoli dei record vengono formattati in modo da indicare da quale canale privato sono stati inviati.

Per altre informazioni su come eseguire una ricerca di eDiscovery per i messaggi del canale privato, vedere [eDiscovery di canali privati](ediscovery-investigation.md#ediscovery-of-private-channels).

## <a name="considerations-around-access-in-private-channels"></a>Considerazioni sull'accesso nei canali privati

Quando viene creato un nuovo blocco appunti di OneNote in un canale privato, altri utenti possono comunque ottenere l’accesso al blocco appunti poiché si tratta di un comportamento equivalente alla condivisione con un utente dell'accesso a qualsiasi altro elemento in un sito di SharePoint di un canale privato.

Se a un utente viene concesso l'accesso a un blocco appunti in un canale privato tramite SharePoint, la rimozione dell'utente dal team o dal canale privato non rimuove l'accesso di tale utente al blocco appunti.

Se un blocco appunti esistente viene aggiunto come scheda a un canale privato, l'accesso al canale privato non viene modificato. Questo significa che:

- Non tutti i membri del canale privato avranno accesso al blocco appunti per impostazione predefinita. Questo è dovuto al fatto che potrebbero non avere accesso al percorso in cui è ospitato il blocco appunti, ad esempio il sito di SharePoint di un altro team.
- Utenti non membri del canale privato possono visualizzare il blocco appunti.  

## <a name="related-topics"></a>Argomenti correlati

- [Panoramica su team e canali in Teams](teams-channels-overview.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Usare l'API Microsoft Graph per lavorare con Teams](https://docs.microsoft.com/graph/api/resources/teams-api-overview?view=graph-rest-1.0)
