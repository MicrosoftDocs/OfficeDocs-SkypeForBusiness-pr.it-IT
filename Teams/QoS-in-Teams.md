---
title: Implementare la qualità del servizio in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Informazioni su come preparare la rete dell'organizzazione per la qualità del servizio (QoS) in Microsoft teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5bbb66b99a061648c4c12b7611fc7054a4044c6f
ms.sourcegitcommit: f9860dbf3c719fec5ffc1874b503b6db252afe10
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/13/2020
ms.locfileid: "43237889"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementare la qualità del servizio (QoS) in Microsoft Teams

Questo articolo consente di preparare la rete dell'organizzazione per la qualità del servizio (QoS) in Microsoft teams. Se si supporta un numero elevato di utenti e si verificano i problemi descritti di seguito, è probabilmente necessario implementare QoS. Una piccola azienda con pochi utenti potrebbe non avere bisogno di QoS, ma anche lì dovrebbe essere utile.

QoS è un modo per consentire il traffico di rete in tempo reale (come i flussi di voce o video) che è sensibile ai ritardi di rete per "tagliare in linea" davanti al traffico meno sensibile (come scaricare una nuova app, in cui un altro secondo da scaricare non è un problema). QoS identifica e contrassegna tutti i pacchetti in flussi in tempo reale (usando gli oggetti Criteri di gruppo di Windows e una caratteristica di routing denominata elenchi di controllo di accesso basati su porta, maggiori informazioni su queste sono di seguito) che consente quindi alla rete di fornire flussi di condivisione di voce, video e schermo una porzione dedicata della larghezza di banda della rete.

Senza una qualche forma di QoS, è possibile che vengano visualizzati i problemi di qualità seguenti in voce e video:

- Jitter: i pacchetti multimediali che arrivano a tariffe diverse, che possono determinare la mancanza di parole o sillabe nelle chiamate.
- Perdita di pacchetti: i pacchetti sono stati eliminati, il che può anche causare una qualità vocale inferiore e un discorso difficile da capire.
- Ritardo di andata e ritorno (RTT)-pacchetti multimediali che impiegano molto tempo per raggiungere le proprie destinazioni, che causano ritardi evidenti tra due parti in una conversazione, facendo in modo che le persone possano comunicare tra loro.

Il modo meno complesso per risolvere questi problemi consiste nell'aumentare le dimensioni delle connessioni dati, sia internamente che in Internet. Poiché spesso il costo è proibitivo, QoS consente di gestire in modo più efficace le risorse disponibili invece di aggiungere nuove risorse. Per risolvere completamente i problemi di qualità che userai QoS in tutta l'implementazione, Aggiungi la connettività solo dove è assolutamente necessario.

Affinché il QoS sia efficace, le impostazioni QoS coerenti saranno applicate alla fine dell'organizzazione, perché qualsiasi parte del percorso che non supporta le priorità QoS può degradare la qualità delle condivisioni delle chiamate, del video e dello schermo. Questo include l'applicazione di impostazioni a tutti i PC o dispositivi utente, switch di rete, router a Internet e il servizio teams online.

_Figura 1. Relazione tra le reti di un'organizzazione e i servizi di Office 365_

![Illustrazione della relazione tra reti e servizi](media/Qos-in-Teams-Image1.png "Relazione tra le reti di un'organizzazione e i servizi di Office 365: la rete locale e i dispositivi si connettono a una rete di interconnessione, che a sua volta si connette con i servizi di conferenza telefonica cloud e audio di Office 365.")

Nella maggior parte dei casi, la rete che connette l'azienda al cloud sarà una rete non gestita in cui non sarà possibile impostare in modo affidabile le opzioni QoS. Una scelta disponibile per l'indirizzo QoS end-to-end è [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), ma è comunque consigliabile implementare QoS nella rete locale per il traffico in ingresso e in uscita. In questo modo, aumenta la qualità dei carichi di lavoro delle comunicazioni in tempo reale durante la distribuzione e allevia chokepoints.

## <a name="verify-your-network-is-ready"></a>Verificare che la rete sia pronta

Se si sta valutando un'implementazione QoS, è necessario che siano già stati determinati i requisiti di larghezza di banda e altri [requisiti di rete](prepare-network.md). 
  
  La congestione del traffico in una rete avrà un impatto notevole sulla qualità dei contenuti multimediali. La mancanza di larghezza di banda comporta un peggioramento delle prestazioni e un'esperienza utente scadente. Man mano che l'adozione e l'utilizzo di teams aumentano, USA Reporting, [chiama Analytics e Call Quality dashboard](difference-between-call-analytics-and-call-quality-dashboard.md) per identificare i problemi e quindi apportare modifiche usando QoS e aggiunte selettive per la larghezza di banda.

### <a name="vpn-considerations"></a>Considerazioni su VPN

Il QoS funziona solo come previsto quando viene implementato in tutti i collegamenti tra i chiamanti. Se si usa QoS in una rete interna e un utente accede da una posizione remota, è possibile dare la priorità solo all'interno della rete gestita interna. Anche se le posizioni remote possono ricevere una connessione gestita implementando una rete privata virtuale (VPN), una VPN aggiunge in modo intrinseco il sovraccarico del pacchetto e crea ritardi nel traffico in tempo reale. È consigliabile evitare di eseguire il traffico di comunicazioni in tempo reale tramite una rete VPN.

In un'organizzazione globale con collegamenti gestiti che si estendono in continenti consigliamo vivamente QoS perché la larghezza di banda per tali collegamenti è limitata rispetto alla rete LAN.

## <a name="introduction-to-qos-queues"></a>Introduzione alle code QoS

Per specificare il QoS, i dispositivi di rete devono avere la possibilità di classificare il traffico e devono essere in grado di distinguere la voce o il video da un altro traffico di rete.

Quando il traffico di rete entra in un router, il traffico viene inserito in una coda. Se un criterio QoS non è configurato, esiste una sola coda e tutti i dati vengono trattati come First-in, First-out con la stessa priorità. Questo significa che il traffico vocale (molto sensibile ai ritardi) potrebbe rimanere bloccato dietro il traffico in cui un ritardo di alcuni millisecondi aggiuntivi non è un problema.

Quando implementi QoS, Definisci più code usando una delle varie funzionalità di gestione della congestione, ad esempio l'accodamento prioritario di Cisco e le caratteristiche di evasione ponderata di [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)per la classe e la prevenzione della congestione, ad esempio i [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)di rilevamento rapido ponderato.

_Figura 2. Esempi di code QoS_

![Illustrazione delle code QoS e della divisione larghezza di banda](media/Qos-in-Teams-Image2.png "La larghezza di banda disponibile totale è divisa tra più code, ad esempio audio, video e altro traffico, a cui sono state assegnate priorità diverse.")

Una semplice analogia consiste nel fatto che QoS crea una "corsia di carpooling" virtuale nella rete dati in modo che alcuni tipi di dati non incontrino mai o raramente un ritardo. Dopo aver creato tali corsie, è possibile modificare le dimensioni relative e gestire in modo più efficace la larghezza di banda della connessione, garantendo comunque esperienze di livello aziendale per gli utenti dell'organizzazione.

## <a name="select-a-qos-implementation-method"></a>Selezionare un metodo di implementazione QoS

Puoi implementare il QoS tramite tagging basato su porta, usando gli elenchi di controllo di accesso (ACL) nei router della rete. La codifica basata su porta è il metodo più affidabile perché funziona in ambienti Windows, Mac e Linux misti ed è la soluzione più semplice da implementare. I client mobili non offrono un meccanismo per contrassegnare il traffico usando i valori DSCP, quindi richiedono questo metodo.  

Usando questo metodo, il router della rete esamina un pacchetto in arrivo e, se il pacchetto è arrivato usando una determinata porta o intervallo di porte, lo identifica come un determinato tipo di elemento multimediale e lo inserisce nella coda per il tipo, aggiungendo un contrassegno di [DSCP](https://tools.ietf.org/html/rfc2474) predeterminato all'intestazione del pacchetto IP in modo che altri dispositivi possano riconoscere il tipo di traffico e assegnargli la priorità nella coda.

Anche se questo funziona in tutte le piattaforme, contrassegna solo il traffico sul bordo WAN (non fino al computer client) e crea un sovraccarico di gestione. Devi fare riferimento alla documentazione fornita dal produttore del router per istruzioni sull'implementazione di questo metodo.

* * *

Puoi anche implementare QoS implementata usando un oggetto Criteri di gruppo per indirizzare i dispositivi client per inserire un indicatore DSCP nelle intestazioni di pacchetti IP che la identificano come tipo di traffico specifico (ad esempio, Voice). I router e altri dispositivi di rete possono essere configurati per riconoscerli e inserire il traffico in una coda separata con priorità più alta.

Anche se questo scenario è completamente valido, funzionerà solo per i client Windows collegati al dominio. Qualsiasi dispositivo che non sia un client Windows collegato al dominio non verrà abilitato per il tagging DSCP. I client, ad esempio Mac OS, hanno tag hardcoded e verranno sempre contrassegnati come traffico.

Sul lato positivo, il controllo della marcatura DSCP tramite GPO garantisce che tutti i computer aggiunti al dominio ricevano le stesse impostazioni e che solo un amministratore possa gestirli. I client che possono usare GPO verranno contrassegnati nel dispositivo di origine e i dispositivi di rete configurati possono riconoscere il flusso in tempo reale dal codice DSCP e assegnargli una priorità appropriata.

* * *

È consigliabile una combinazione di contrassegni DSCP presso gli elenchi ACL basati su porte e endpoint sui router, se possibile. L'uso di un oggetto Criteri di gruppo per catturare la maggior parte dei client e anche l'uso della codifica DSCP basata su porta garantisce che il dispositivo mobile, Mac e altri client ottengano comunque il trattamento QoS (almeno in parte).

I contrassegni DSCP possono essere paragonati ai francobolli che indicano agli addetti alle poste l'urgenza del parto e il modo migliore per ordinarlo per un parto rapido. Dopo aver configurato la rete per dare priorità ai flussi multimediali in tempo reale, i pacchetti persi e i pacchetti tardivi dovrebbero diminuire notevolmente.

Una volta che tutti i dispositivi della rete usano le stesse classificazioni, marcature e priorità, è possibile ridurre o eliminare ritardi, pacchetti eliminati e jitter modificando le dimensioni degli intervalli di porte assegnati alle code usate per ogni tipo di traffico. Dal punto di vista teams, il passaggio di configurazione più importante è la classificazione e la marcatura dei pacchetti, ma per il QoS end-to-end è anche necessario allineare accuratamente la configurazione dell'applicazione con la configurazione di rete sottostante. Una volta completata l'implementazione del QoS, la gestione continua è una questione di regolazione degli intervalli di porte assegnati a ogni tipo di traffico in base alle esigenze dell'organizzazione e all'uso effettivo.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Scegliere gli intervalli di porte iniziali per ogni tipo di elemento multimediale

Il valore DSCP indica a una rete configurata in modo corrispondente quale priorità assegnare a un pacchetto o a un flusso, se il contrassegno DSCP viene assegnato dai client o dalla rete stessa in base alle impostazioni ACL. Ogni carico di lavoro multimediale ottiene un valore DSCP univoco (altri servizi potrebbero consentire ai carichi di lavoro di condividere un contrassegno DSCP, teams not) e un intervallo di porte definito e separato usato per ogni tipo di elemento multimediale. In altri ambienti potrebbe essere presente una strategia QoS esistente che consente di determinare la priorità dei carichi di lavoro di rete.

La dimensione relativa degli intervalli di porta per i diversi carichi di lavoro in tempo reale in streaming imposta la percentuale di larghezza di banda disponibile totale dedicata a tale carico di lavoro. Per tornare all'analogia postale precedente: una lettera con un timbro "Air mail" potrebbe essere scattata entro un'ora dall'aeroporto più vicino, mentre un piccolo pacchetto contrassegnato come "posta in blocco" può attendere un giorno prima di spostarsi su una serie di camion.

La tabella seguente mostra i contrassegni di DSCP necessari e gli intervalli di porte multimediali suggeriti usati da teams e ExpressRoute. Questi intervalli potrebbero fungere da buon punto di partenza per i clienti che non sono sicuri di cosa usare nei propri ambienti. Per altre informazioni, leggere i [Requisiti QoS di ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos).

_Intervalli di porte iniziali consigliati_

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Quando si usano queste impostazioni, tenere presente quanto segue:

- Se si prevede di implementare ExpressRoute in futuro e non è ancora stato implementato QoS, è consigliabile seguire le indicazioni in modo che i valori di DSCP siano uguali da mittente a destinatario.
- Tutti i client, inclusi i client mobili e i dispositivi teams, useranno questi intervalli di porte e saranno interessati da qualsiasi criterio DSCP implementato che usa questi intervalli di porta di origine. Gli unici client che continueranno a usare le porte dinamiche sono i client basati su browser (ovvero i client che consentono ai partecipanti di partecipare alle riunioni usando i loro browser).
- Anche se il client Mac usa gli stessi intervalli di porte, USA anche valori hardcoded per l'audio (EF) e il video (AF41). Questi valori non sono configurabili.
- Se in seguito è necessario regolare gli intervalli di porte per migliorare l'esperienza utente, gli intervalli di porta non possono sovrapporsi e devono essere adiacenti.

## <a name="migrate-qos-to-teams"></a>Eseguire la migrazione di QoS ai team

Se hai distribuito in precedenza Skype for business online, inclusi i tag QoS e gli intervalli di porte e ora stai distribuendo teams, i team rispetteranno la configurazione esistente e useranno gli stessi intervalli di porte e le etichette come client Skype for business. Nella maggior parte dei casi non sarà necessaria alcuna configurazione aggiuntiva.

> [!NOTE]
> Se si usa la codifica QoS nome applicazione tramite criteri di gruppo, è necessario aggiungere teams. exe come nome dell'applicazione.

## <a name="qos-implementation-steps"></a>Passaggi di implementazione QoS

A livello molto elevato, l'implementazione di QoS richiede questi passaggi:

1. [Verificare che la rete sia pronta](#verify-your-network-is-ready)
2. [Selezionare un metodo di implementazione QoS](#select-a-qos-implementation-method)
3. [Scegliere gli intervalli di porte iniziali per ogni tipo di elemento multimediale](#choose-initial-port-ranges-for-each-media-type)
4. Implementare le impostazioni QoS:
   1. Sui client che usano un oggetto Criteri di [gruppo per impostare intervalli e contrassegni della porta del dispositivo client](QoS-in-Teams-clients.md)
   2. Nei router (Vedi la documentazione del produttore) o in altri dispositivi di rete. Può includere elenchi ACL basati su porta o semplicemente definire le code QoS e i contrassegni DSCP oppure tutti questi.

      > [!IMPORTANT]
      > È consigliabile implementare questi criteri QoS usando le porte di origine client e un indirizzo IP di origine e di destinazione "any". In questo modo verrà intercettato il traffico multimediale in entrata e in uscita nella rete interna.  

   3. Nell'interfaccia di [amministrazione di teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)
5. [Convalidare l'implementazione QoS](#validate-the-qos-implementation) analizzando il traffico di team in rete.

Mentre ti prepari ad implementare QoS, tieni presente le linee guida seguenti:

- Il percorso più breve di Office 365 è il migliore.
- Le porte di chiusura porteranno solo alla degradazione della qualità.
- Gli eventuali ostacoli interconnessi, ad esempio i proxy, non sono consigliati.
- Limitare il numero di hop:
  - Client a Edge della rete: da 3 a 5 hop.
  - ISP a Microsoft Network Edge-3 hop
  - Microsoft Network Edge to Final Destination-irrilevante

Per informazioni sulla configurazione delle porte del firewall, vedere [URL e intervalli di indirizzi IP di Office 365](office-365-urls-ip-address-ranges.md).

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestione delle porte di origine nell'interfaccia di amministrazione di Teams

In teams le porte di origine QoS usate dai diversi carichi di lavoro devono essere gestite in modo attivo e modificate in base alle esigenze. Facendo riferimento alla tabella in [Scegli intervalli di porte iniziali per ogni tipo](#choose-initial-port-ranges-for-each-media-type)di elemento multimediale, gli intervalli di porta sono regolabili, ma i contrassegni di DSCP non sono configurabili. Dopo aver implementato queste impostazioni, è possibile che siano necessarie più o meno porte per un tipo di elemento multimediale specifico. Per prendere una decisione per regolare gli intervalli di porte dopo l'implementazione di teams e per modificare periodicamente le esigenze, è consigliabile usare il dashboard per la chiamata [e la qualità](difference-between-call-analytics-and-call-quality-dashboard.md) delle chiamate.

> [!NOTE]
> Se la funzionalità QoS è già stata configurata in base a intervalli di porta di origine e contrassegni DSCP per Skype for business online, la stessa configurazione verrà applicata ai team e non saranno necessarie ulteriori modifiche al client o alla rete, ma potrebbe essere necessario [impostare gli intervalli usati nell'interfaccia di amministrazione di teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) in modo che corrispondano a quelli configurati per Skype for business online.

Se hai distribuito in precedenza Skype for Business Server in locale, potrebbe essere necessario riesaminare i criteri di QoS e regolarli in base alle esigenze per corrispondere alle impostazioni dell'intervallo di porte che hai verificato per consentire l'utilizzo di un'esperienza utente di qualità per i team.

## <a name="validate-the-qos-implementation"></a>Convalidare l'implementazione QoS

Affinché il QoS sia efficace, il valore DSCP impostato dall'oggetto Criteri di gruppo deve essere presente in entrambe le estremità di una chiamata. Analizzando il traffico generato dal client teams, è possibile verificare che il valore DSCP non venga modificato o rimosso quando il traffico del carico di lavoro di teams passa attraverso la rete.

È preferibile acquisire il traffico nel punto di uscita della rete. È possibile usare il mirroring della porta su uno switch o un router per aiutarlo.

### <a name="use-network-monitor-to-verify-dscp-values"></a>Usare Network Monitor per verificare i valori di DSCP

Network Monitor è uno strumento che puoi [scaricare da Microsoft](https://www.microsoft.com/download/4865) per analizzare il traffico di rete.

1. Nel PC che gestisce Network Monitor connettersi alla porta configurata per il mirroring della porta e avviare l'acquisizione di pacchetti.

2. Effettuare una chiamata tramite il client teams. Verificare che il supporto sia stato stabilito prima di sospendere la chiamata.

3. Interrompere l'acquisizione.

4. Nel campo **filtro visualizzazione** usare l'indirizzo IP di origine del PC che ha eseguito la chiamata e perfezionare il filtro definendo il valore DSCP 46 (Hex 0x2E) come criterio di ricerca, come illustrato nell'esempio seguente:

    Source = = "192.168.137.201" e IPv4. DifferentiatedServicesField = = 0x2E

    ![Filtri schermati nella finestra di dialogo filtro visualizzazione.](media/Qos-in-Teams-Image4.png "Finestra di dialogo filtro visualizzazione in Network Monitor che mostra i filtri da applicare.")

5. Selezionare **applica** per attivare il filtro.

6. Nella finestra **Riepilogo dei fotogrammi** selezionare il primo pacchetto UDP.

7. Nella finestra **Dettagli fotogrammi** espandere la voce di elenco IPv4 e prendere nota del valore alla fine della riga che inizia con **DSCP**.

    ![Screenshot che mostra le impostazioni di DSCP nella finestra di dialogo Dettagli fotogrammi.](media/Qos-in-Teams-Image5.png "Finestra di dialogo Dettagli cornice in Network Monitor, che evidenzia le impostazioni di DSCP.")

In questo esempio, il valore DSCP è impostato su 46. Questo è corretto, perché la porta di origine usata è 50019, che indica che si tratta di un carico di lavoro vocale.

Ripetere la verifica per ogni carico di lavoro contrassegnato dall'oggetto Criteri di ricerca.

## <a name="more-information"></a>Altre informazioni

[Video: pianificazione della rete](https://aka.ms/teams-networking)

[Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md)

[Requisiti QoS di ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
