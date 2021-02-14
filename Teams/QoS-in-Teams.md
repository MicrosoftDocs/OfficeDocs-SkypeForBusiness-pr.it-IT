---
title: Implementare la qualità del servizio in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Informazioni su come preparare la rete dell'organizzazione per la qualità del servizio (QoS) in Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766579"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementare la qualità del servizio (QoS) in Microsoft Teams

La qualità del servizio (QoS) in Microsoft Teams consente al traffico di rete in tempo reale sensibile ai ritardi di rete (ad esempio, flussi vocali o video) di "tagliare in linea" di fronte al traffico meno sensibile (come il download di una nuova app, in cui un secondo aggiuntivo da scaricare non è un problema). QoS usa oggetti Criteri di gruppo di Windows ed elenchi di controllo di accesso basati su porta per identificare e contrassegnare tutti i pacchetti in flussi in tempo reale. In questo modo la rete può offrire flussi vocali, video e di condivisione dello schermo per una parte dedicata della larghezza di banda di rete.

Se si supporta un gruppo ampio di utenti che riscontrano uno dei problemi descritti in questo articolo, probabilmente è necessario implementare la QoS. Una piccola azienda con pochi utenti potrebbe non avere bisogno di QoS, ma anche lì dovrebbe essere utile.

Senza una qualche forma di QoS, potrebbero verificarsi i problemi di qualità seguenti per voce e video:

- Instabilità: pacchetti multimediali che arrivano a tariffe diverse, il che può comportare la mancanza di parole o sillabe nelle chiamate
- Perdita di pacchetti: pacchetti eliminati, che possono anche comportare una qualità vocale inferiore e un riconoscimento vocale difficile da capire
- Tempo di round trip ritardato (RTT, Delayed Round Trip Time): i pacchetti multimediali che durano molto tempo per raggiungere le loro destinazioni, causando ritardi evidenti tra due parti in una conversazione e causando una conversazione tra le persone

Il modo meno complesso per risolvere questi problemi è quello di aumentare le dimensioni delle connessioni dati, sia interne che esterne a Internet. Poiché si tratta spesso di una limitazione dei costi, la QoS consente di gestire in modo più efficace le risorse disponibili invece di aggiungere larghezza di banda. Per risolvere i problemi di qualità, è consigliabile usare prima la QoS, quindi aggiungere la larghezza di banda solo quando necessario.

Per applicare la QoS in modo efficace, è necessario applicare impostazioni QoS coerenti in tutta l'organizzazione. Qualsiasi parte del percorso che non supporta le priorità QoS può peggiorare la qualità di chiamate, video e condivisione dello schermo. Ciò include l'applicazione delle impostazioni a tutti i PC o dispositivi degli utenti, agli switch di rete, ai router a Internet e al servizio Teams.

_Figura 1. La relazione tra le reti di un'organizzazione e i servizi di Microsoft 365 o Office 365_

![Illustrazione della relazione tra reti e servizi](media/Qos-in-Teams-Image1.png "La relazione tra le reti di un'organizzazione e i servizi di Microsoft 365 o Office 365: le reti locali e i dispositivi si connettono a una rete interconnessa, che a sua volta si connette con Microsoft 365 o i servizi cloud voce e audioconferenza di Office 365.")

## <a name="qos-implementation-checklist"></a>Elenco di controllo per l'implementazione QoS

In alto, eseguire le operazioni seguenti per implementare la QoS:

1. [Verificare che la rete sia pronta](#make-sure-your-network-is-ready)

1. [Selezionare un metodo di implementazione QoS](#select-a-qos-implementation-method)

1. [Scegliere gli intervalli di porta iniziali per ogni tipo di supporto](#choose-initial-port-ranges-for-each-media-type)

1. Implementare le impostazioni QoS:
   1. Nei client che usano un oggetto Criteri di gruppo per impostare intervalli di porte e [contrassegni dei dispositivi client](QoS-in-Teams-clients.md)
   2. Sui router (vedere la documentazione del produttore) o su altri dispositivi di rete. Questo può includere elenchi di controllo di accesso basati su porta (ACL) o semplicemente la definizione delle code QoS e dei contrassegni DSCP o tutti questi elementi.

      > [!IMPORTANT]
      > È consigliabile implementare questi criteri QoS usando le porte di origine client e un indirizzo IP di origine e destinazione "qualsiasi". In questo modo viene intercettato il traffico multimediale sia in ingresso che in uscita sulla rete interna.  

   3. [Impostare come gestire il traffico multimediale per le riunioni di Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Convalidare l'implementazione QoS](#validate-your-qos-implementation) analizzando il traffico di Teams sulla rete.

Mentre ci si prepara a implementare la QoS, tenere presenti le linee guida seguenti:

- Il percorso più breve per Microsoft 365 è migliore
- La chiusura delle porte porterà solo a una riduzione della qualità
- Non è consigliabile creare ostacoli tra l'altro, ad esempio i proxy.
- Limitare il numero di hop:
  - Edge client-rete - 3-5 hop
  - Dall'ISP all'Edge della rete di Microsoft - 3 hop
  - Edge della rete Microsoft alla destinazione finale: irrilevante

Per informazioni sulla configurazione delle porte del firewall, vedere URL e [intervalli IP per Office 365.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Verificare che la rete sia pronta

Se si sta valutando un'implementazione QoS, si dovrebbero già aver determinato i requisiti di larghezza di banda e altri [requisiti di rete.](prepare-network.md)
  
La congestione del traffico su una rete inciderà notevolmente sulla qualità multimediale. La mancanza di larghezza di banda causa una riduzione delle prestazioni e una scarsa esperienza utente. Man mano che aumentano l'adozione e l'utilizzo di Teams, usa i [report,](use-call-analytics-to-troubleshoot-poor-call-quality.md)l'analisi delle chiamate per utente e [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) per identificare i problemi e quindi apportare modifiche utilizzando QoS e l'aggiunta selettiva della larghezza di banda.

### <a name="vpn-considerations"></a>Considerazioni sulle VPN

La QoS funziona come previsto solo se implementata su tutti i collegamenti tra i chiamanti. Se si usa QoS in una rete interna e un utente accede da una posizione remota, è possibile assegnare priorità solo all'interno della rete gestita interna. Anche se le posizioni remote possono ricevere una connessione gestita implementando una rete privata virtuale (VPN), una VPN aggiunge implicitamente un sovraccarico dei pacchetti e causa ritardi nel traffico in tempo reale. Ti consigliamo di evitare di eseguire traffico per comunicazioni in tempo reale su una VPN.

In un'organizzazione globale con collegamenti gestiti che attraversano continenti, si consiglia vivamente la QoS perché la larghezza di banda per tali collegamenti è limitata rispetto alla LAN.

## <a name="introduction-to-qos-queues"></a>Introduzione alle code QoS

Per fornire la QoS, i dispositivi di rete devono avere un modo per classificare il traffico e devono essere in grado di distinguere voce o video da altro traffico di rete.

Quando il traffico di rete entra in un router, il traffico viene inserito in una coda. Se non sono configurati criteri QoS, esiste una sola coda e tutti i dati vengono trattati come primo accesso e primo accesso con la stessa priorità. Questo significa che il traffico vocale, molto sensibile ai ritardi, potrebbe rimanere bloccato sul traffico, dove un ritardo di alcuni millisecondi in più non sarebbe un problema.

Quando si implementa la QoS, si definiscono più code utilizzando una delle diverse caratteristiche di gestione della congestione, come l'accodamento prioritario di Cisco e l'Equa ponderata in coda basata sulla classe [(CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) e le caratteristiche di evitanza della congestione, come il rilevamento anticipato casuale ponderato [(WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figura 2. Esempi di code QoS_

![Illustrazione delle code QoS e della divisione della larghezza di banda](media/Qos-in-Teams-Image2.png "La larghezza di banda totale disponibile è divisa tra più code, audio, video e altro traffico, a cui sono state assegnate diverse priorità.")

Una semplice analogia è che QoS crea "corsi di pool di auto" virtuali nella rete dati, in modo che alcuni tipi di dati non si verifichino mai o raramente ritardi. Dopo aver creato questi corsi, è possibile modificarne le dimensioni relative e gestire in modo molto più efficace la larghezza di banda della connessione disponibile, fornendo al contempo esperienze di livello aziendale per gli utenti dell'organizzazione.

## <a name="select-a-qos-implementation-method"></a>Selezionare un metodo di implementazione QoS

È possibile implementare la QoS tramite tagging basato su porta, usando gli elenchi di controllo di accesso (ACL) sui router della rete. Il tagging basato su porta è il metodo più affidabile perché funziona in ambienti misti Windows, Mac e Linux ed è il più semplice da implementare. I client mobili non forniscono un meccanismo per contrassegnare il traffico usando valori DSCP, quindi richiedono questo metodo.  

Usando i tag basati su porta, il router della rete esamina un pacchetto in ingresso e, se è arrivato tramite una determinata porta o intervallo di porte, lo identifica come un determinato tipo di supporto e lo inserisce nella coda per quel tipo, aggiungendo un contrassegno [DSCP](https://tools.ietf.org/html/rfc2474) predeterminato all'intestazione del pacchetto IP in modo che altri dispositivi possano riconoscere il tipo di traffico e assegnargli la priorità nella coda.

Anche se il tagging basato su porta funziona su più piattaforme, contrassegna solo il traffico all'edge WAN (non fino al computer client) e crea un sovraccarico di gestione. Per istruzioni sull'implementazione di questo metodo, fare riferimento alla documentazione fornita dal produttore del router.

### <a name="insert-dscp-markers"></a>Inserire indicatori DSCP

È anche possibile implementare la QoS usando un oggetto Criteri di gruppo per indirizzare i dispositivi client all'inserimento di un indicatore DSCP nelle intestazioni dei pacchetti IP che lo identifica come tipo di traffico specifico (ad esempio voce). I router e gli altri dispositivi di rete possono essere configurati per riconoscerlo e inserire il traffico in una coda separata con priorità più alta.

Anche se questo scenario è completamente valido, funziona solo per i client Windows aggiunti a un dominio. Tutti i dispositivi che non sono client Windows aggiunti a un dominio non verranno abilitati per l'aggiunta di tag DSCP. I client come Mac OS hanno tag hard coded e contrassegneranno sempre il traffico.

Inoltre, il controllo del contrassegno DSCP tramite l'oggetto Criteri di gruppo assicura che tutti i computer aggiunti a un dominio ricevano le stesse impostazioni e che possano essere gestiti solo da un amministratore. I client che possono usare l'oggetto Criteri di gruppo verranno contrassegnati nel dispositivo di origine e i dispositivi di rete configurati potranno riconoscere il flusso in tempo reale tramite il codice DSCP e assegnargli una priorità appropriata.

### <a name="best-practice"></a>Procedura consigliata

È consigliabile una combinazione di contrassegni DSCP all'endpoint e ACL basati su porta sui router, se possibile. L'uso di un oggetto Criteri di gruppo per intercettare la maggior parte dei client e anche l'uso dei contrassegni DSCP basati su porta garantirà che il trattamento QoS per dispositivi mobili, Mac e altri client continuerà ad essere utilizzato (almeno parzialmente).

I contrassegni DSCP possono essere simili a timbri che indicano ai dipendenti postali quanto è urgente il recapito e come ordinarli per velocizzare la consegna. Dopo aver configurato la rete per dare la priorità agli stream multimediali in tempo reale, i pacchetti persi e gli ultimi pacchetti dovrebbero ridurre notevolmente.

Quando tutti i dispositivi nella rete usano le stesse classificazioni, contrassegni e priorità, è possibile ridurre o eliminare ritardi, pacchetti eliminati e instabilità modificando le dimensioni degli intervalli di porte assegnati alle code usate per ogni tipo di traffico. Dal punto di vista di Teams, il passaggio di configurazione più importante è la classificazione e il contrassegno dei pacchetti. Tuttavia, per il successo della QoS end-to-end, è necessario anche allineare attentamente la configurazione dell'applicazione alla configurazione di rete sottostante. Una volta implementata la QoS, la gestione continua è una questione di modifica degli intervalli di portabilità assegnati a ogni tipo di traffico in base alle esigenze e all'utilizzo effettivo dell'organizzazione.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Scegliere gli intervalli di porta iniziali per ogni tipo di supporto

Il valore DSCP indica alla rete corrispondente la priorità da assegnare a un pacchetto o a uno stream, indicando se il contrassegno DSCP viene assegnato dai client o dalla rete stessa in base alle impostazioni ACL. Ogni carico di lavoro multimediale ha un proprio valore DSCP univoco (altri servizi potrebbero consentire ai carichi di lavoro di condividere un contrassegno DSCP, Teams non lo fa) e un intervallo di porta definito e separato utilizzato per ogni tipo di supporto. Altri ambienti potrebbero avere già una strategia QoS, che consente di determinare la priorità dei carichi di lavoro di rete.

La dimensione relativa degli intervalli di porte per i diversi carichi di lavoro di streaming in tempo reale imposta la proporzione della larghezza di banda totale disponibile dedicata a tale carico di lavoro. Per tornare all'analogia postale precedente: una lettera con un timbro "Air Mail" potrebbe essere scattata entro un'ora all'aeroporto più vicino, mentre un piccolo pacco contrassegnato come "Posta in massa" può aspettare un giorno prima di viaggiare su una serie di carrelli.

_Intervalli di porta iniziali consigliati_

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Quando si usano queste impostazioni, tenere presente quanto segue:

- Se si prevede di implementare ExpressRoute in futuro e la QoS non è ancora stata implementata, è consigliabile seguire le indicazioni in modo che i valori DSCP siano gli stessi da mittente a destinatario.
- Tutti i client, compresi i client mobili e i dispositivi Teams, useranno questi intervalli di porte e saranno interessati da qualsiasi criterio DSCP implementato che usa questi intervalli di porte di origine. Gli unici client che continueranno a usare porte dinamiche sono i client basati su browser, ovvero client che consentono ai partecipanti di partecipare alle riunioni tramite i loro browser.
- Anche se il client Mac usa gli stessi intervalli di porta, usa anche valori hard coded per audio (EF) e video (AF41). Questi valori non sono configurabili.
- Se in seguito sarà necessario modificare gli intervalli di porta per migliorare l'esperienza utente, gli intervalli di porta non possono sovrapporsi e devono essere adiacenti.

## <a name="migrate-qos-to-teams"></a>Eseguire la migrazione di QoS a Teams

Se hai già distribuito Skype for Business online, inclusi i tagging QoS e gli intervalli di porte, e ora stai distribuendo. Teams, Teams rispetta la configurazione esistente e userà gli stessi intervalli di porta e gli stessi tag del client Skype for Business. Nella maggior parte dei casi non sono necessarie altre operazioni di configurazione.

> [!NOTE]
> Se si usa il tagging QoS di Nome applicazione tramite Criteri di gruppo, è necessario aggiungere Teams.exe come nome dell'applicazione.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementare QoS in Teams su Windows con PowerShell

**Impostare la QoS per l'audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Impostare la QoS per il video**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Impostare la QoS per la condivisione**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestione delle porte di origine nell'interfaccia di amministrazione di Teams

In Teams, le porte di origine QoS usate dai diversi carichi di lavoro devono essere gestite attivamente e modificate secondo le necessità. Facendo riferimento alla tabella in Scegli intervalli di [porta](#choose-initial-port-ranges-for-each-media-type)iniziali per ogni tipo di supporto, gli intervalli di porta sono regolabili, ma i contrassegni DSCP non sono configurabili. Dopo aver implementato queste impostazioni, è possibile che siano necessarie più o meno porte per un determinato tipo di supporto. [L'analisi](use-call-analytics-to-troubleshoot-poor-call-quality.md) delle chiamate per utente [e Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) devono essere utilizzati per prendere una decisione di modificare gli intervalli di portabilità dopo l'implementazione di Teams e periodicamente in base alle esigenze.

> [!NOTE]
> Se hai già configurato QoS in base agli intervalli di porta di origine e ai contrassegni DSCP per Skype for Business online, la stessa configurazione verrà applicata a Teams e non saranno necessarie ulteriori modifiche di client o rete alla mappatura, anche se potresti doverti impostare gli intervalli utilizzati [in Teams in](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) modo che corrispondano a quanto configurato per Skype for Business online.

Se hai già distribuito Skype for Business Server in locale, potresti dover esaminare nuovamente i criteri QoS. Modificare i criteri in modo che corrispondano alle impostazioni dell'intervallo di porte verificato per offrire un'esperienza utente di qualità per Teams.

## <a name="validate-your-qos-implementation"></a>Convalidare l'implementazione QoS

Per poter essere efficace, il valore DSCP impostato dall'oggetto Criteri di gruppo deve essere presente a entrambe le estremità della chiamata. Analizzando il traffico generato dal client Teams, è possibile verificare che il valore DSCP non sia modificato o privato quando il traffico del carico di lavoro di Teams si sposta attraverso la rete.

Preferibilmente, il traffico viene catturato nel punto di uscita della rete. Per risolvere questo problema, è possibile usare il mirroring della porta su uno switch o router.

## <a name="implement-qos-for-other-devices"></a>Implementare QoS per altri dispositivi

Leggere questi argomenti per informazioni sull'implementazione della QoS per Intune, Surface, iOS, Android e Mac

- [QoS per Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS per Surface Hub](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS per iOS, Android e Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Argomenti correlati

- [Video: Pianificazione della rete](https://aka.ms/teams-networking)

- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md)

- [Implementare QoS nel client di Teams](QoS-in-Teams-clients.md)
