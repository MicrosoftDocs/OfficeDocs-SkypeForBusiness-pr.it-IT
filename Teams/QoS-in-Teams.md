---
title: Implementare la qualità del servizio in Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Informazioni su come preparare la rete dell'organizzazione per la qualità del servizio (QoS) in Microsoft teams.
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

La qualità del servizio (QoS) in Microsoft teams consente il traffico di rete in tempo reale sensibile ai ritardi di rete, ad esempio i flussi vocali o video, per "tagliare in linea" di fronte al traffico meno sensibile (come scaricare una nuova app, in cui un altro secondo da scaricare non è un affare di grandi dimensioni). QoS usa gli oggetti Criteri di gruppo di Windows e gli elenchi di controllo di accesso basati su porte per identificare e contrassegnare tutti i pacchetti in flussi in tempo reale. In questo modo, la rete consente di dare ai flussi di condivisione di voce, video e schermo una parte dedicata della larghezza di banda della rete.

Se si supporta un numero elevato di utenti che stanno riscontrando uno dei problemi descritti in questo articolo, è probabilmente necessario implementare QoS. Una piccola azienda con pochi utenti potrebbe non avere bisogno di QoS, ma anche lì dovrebbe essere utile.

Senza una qualche forma di QoS, è possibile che vengano visualizzati i problemi di qualità seguenti in voce e video:

- Jitter: i pacchetti multimediali che arrivano a tariffe diverse, che possono risultare in parole o sillabe mancanti nelle chiamate
- Perdita di pacchetti: pacchetti eliminati, che possono anche determinare una qualità vocale inferiore e un discorso difficile da comprendere
- Ritardo di andata e ritorno (RTT)-pacchetti multimediali che impiegano molto tempo per raggiungere le proprie destinazioni, che causano ritardi evidenti tra due parti in una conversazione e causano l'intervento degli altri utenti

Il modo meno complesso per risolvere questi problemi consiste nell'aumentare le dimensioni delle connessioni dati, sia internamente che in Internet. Dato che spesso è proibitivo, QoS consente di gestire in modo più efficace le risorse disponibili invece di aggiungere larghezza di banda. Per risolvere i problemi di qualità, è consigliabile usare il QoS prima di tutto, quindi aggiungere la larghezza di banda solo se necessario.

Affinché la QoS sia efficace, è necessario applicare le impostazioni QoS coerenti in tutta l'organizzazione. Qualsiasi parte del percorso che non supporta le priorità QoS può degradare la qualità delle chiamate, del video e della condivisione dello schermo. Questo include l'applicazione di impostazioni a tutti i PC o dispositivi utente, switch di rete, router a Internet e il servizio teams.

_Figura 1. Relazione tra le reti di un'organizzazione e i servizi Microsoft 365 o Office 365_

![Illustrazione della relazione tra reti e servizi](media/Qos-in-Teams-Image1.png "La relazione tra le reti di un'organizzazione e i servizi Microsoft 365 o Office 365: la rete locale e i dispositivi si connettono a una rete di interconnessione, che a sua volta si connette a Microsoft 365 o ai servizi di conferenza telefonica e audio di Office 365 cloud.")

## <a name="qos-implementation-checklist"></a>Elenco di controllo di implementazione QoS

Ad alto livello, eseguire le operazioni seguenti per implementare QoS:

1. [Verificare che la rete sia pronta](#make-sure-your-network-is-ready)

1. [Selezionare un metodo di implementazione QoS](#select-a-qos-implementation-method)

1. [Scegliere gli intervalli di porte iniziali per ogni tipo di elemento multimediale](#choose-initial-port-ranges-for-each-media-type)

1. Implementare le impostazioni QoS:
   1. Nei client che usano un oggetto Criteri di gruppo per [impostare intervalli e contrassegni della porta del dispositivo client](QoS-in-Teams-clients.md)
   2. Nei router (Vedi la documentazione del produttore) o in altri dispositivi di rete. Questo potrebbe includere elenchi di controllo di accesso basati su porta (ACL) o semplicemente definire le code QoS e i contrassegni DSCP oppure tutti questi elementi.

      > [!IMPORTANT]
      > È consigliabile implementare questi criteri QoS usando le porte di origine client e un indirizzo IP di origine e di destinazione "any". In questo modo verrà intercettato il traffico multimediale in entrata e in uscita nella rete interna.  

   3. [Impostare il modo in cui si vuole gestire il traffico multimediale per le riunioni Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Convalidare l'implementazione QoS](#validate-your-qos-implementation) analizzando il traffico di team in rete.

Mentre ti prepari ad implementare QoS, tieni presente le linee guida seguenti:

- Il percorso più breve per Microsoft 365 è migliore
- Le porte di chiusura porteranno solo alla degradazione della qualità
- Gli eventuali ostacoli in mezzo, ad esempio i proxy, non sono consigliati
- Limitare il numero di hop:
  - Client a Edge della rete da 3 a 5 hop
  - ISP a Microsoft Network Edge-3 hop
  - Microsoft Network Edge to Final Destination-irrilevante

Per informazioni sulla configurazione delle porte del firewall, vedere [URL e intervalli di indirizzi IP di Office 365](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Verificare che la rete sia pronta

Se si sta valutando un'implementazione QoS, è necessario che siano già stati determinati i requisiti di larghezza di banda e altri [requisiti di rete](prepare-network.md).
  
La congestione del traffico in una rete avrà un impatto notevole sulla qualità dei contenuti multimediali. La mancanza di larghezza di banda comporta un peggioramento delle prestazioni e un'esperienza utente scadente. Man mano che l'adozione e l'utilizzo di teams aumentano, USA Reporting, [analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md)e [dashboard qualità chiamata (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md) per identificare i problemi e quindi apportare modifiche usando QoS e aggiunte selettive per la larghezza di banda.

### <a name="vpn-considerations"></a>Considerazioni su VPN

Il QoS funziona solo come previsto quando viene implementato in tutti i collegamenti tra i chiamanti. Se si usa QoS in una rete interna e un utente accede da una posizione remota, è possibile dare la priorità solo all'interno della rete gestita interna. Anche se le posizioni remote possono ricevere una connessione gestita implementando una rete privata virtuale (VPN), una VPN aggiunge in modo intrinseco il sovraccarico del pacchetto e crea ritardi nel traffico in tempo reale. È consigliabile evitare di eseguire il traffico di comunicazioni in tempo reale tramite una rete VPN.

In un'organizzazione globale con collegamenti gestiti che si estendono in continenti consigliamo vivamente QoS perché la larghezza di banda per tali collegamenti è limitata rispetto alla rete LAN.

## <a name="introduction-to-qos-queues"></a>Introduzione alle code QoS

Per specificare il QoS, i dispositivi di rete devono avere la possibilità di classificare il traffico e devono essere in grado di distinguere la voce o il video da un altro traffico di rete.

Quando il traffico di rete entra in un router, il traffico viene inserito in una coda. Se un criterio QoS non è configurato, esiste una sola coda e tutti i dati vengono trattati come First-in, First-out con la stessa priorità. Questo significa che il traffico vocale (molto sensibile ai ritardi) potrebbe rimanere bloccato dietro il traffico in cui un ritardo di alcuni millisecondi aggiuntivi non è un problema.

Quando implementi QoS, Definisci più code usando una delle varie funzionalità di gestione della congestione, ad esempio l'accodamento prioritario di Cisco e le caratteristiche di evasione [ponderata (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) e la funzionalità di prevenzione della congestione, ad esempio il [rilevamento precoce ponderato di un caso (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).

_Figura 2. Esempi di code QoS_

![Illustrazione delle code QoS e della divisione larghezza di banda](media/Qos-in-Teams-Image2.png "La larghezza di banda disponibile totale è divisa tra più code, ad esempio audio, video e altro traffico, a cui sono state assegnate priorità diverse.")

Una semplice analogia consiste nel fatto che QoS crea una "corsia di carpooling" virtuale nella rete dati in modo che alcuni tipi di dati non incontrino mai o raramente un ritardo. Dopo aver creato tali corsie, è possibile modificare le dimensioni relative e gestire in modo più efficace la larghezza di banda della connessione, garantendo comunque esperienze di livello aziendale per gli utenti dell'organizzazione.

## <a name="select-a-qos-implementation-method"></a>Selezionare un metodo di implementazione QoS

Puoi implementare il QoS tramite tagging basato su porta, usando gli elenchi di controllo di accesso (ACL) nei router della rete. La codifica basata su porta è il metodo più affidabile perché funziona in ambienti Windows, Mac e Linux misti ed è la soluzione più semplice da implementare. I client mobili non prevedono un meccanismo per contrassegnare il traffico usando i valori DSCP, quindi richiedono questo metodo.  

Usando il contrassegno basato su porta, il router della rete esamina un pacchetto in arrivo e, se il pacchetto è arrivato usando una determinata porta o intervallo di porte, lo identifica come un determinato tipo di elemento multimediale e lo inserisce nella coda per quel tipo, aggiungendo un contrassegno di [DSCP](https://tools.ietf.org/html/rfc2474) predeterminato all'intestazione del pacchetto IP in modo che altri dispositivi possano riconoscere il tipo di traffico e assegnargli la priorità.

Anche se il tagging basato su porta funziona in più piattaforme, contrassegna solo il traffico sul bordo WAN (non fino al computer client) e crea un sovraccarico di gestione. Vedere la documentazione fornita dal produttore del router per istruzioni sull'implementazione di questo metodo.

### <a name="insert-dscp-markers"></a>Inserire indicatori DSCP

Puoi anche implementare QoS usando un oggetto Criteri di gruppo per indirizzare i dispositivi client per inserire un indicatore DSCP nelle intestazioni di pacchetti IP che la identificano come particolare tipo di traffico, ad esempio Voice. I router e altri dispositivi di rete possono essere configurati per riconoscerli e inserire il traffico in una coda separata con priorità più alta.

Anche se questo scenario è completamente valido, funzionerà solo per i client Windows collegati al dominio. Qualsiasi dispositivo che non sia un client Windows collegato al dominio non verrà abilitato per il tagging DSCP. I client, ad esempio Mac OS, hanno tag hardcoded e verranno sempre contrassegnati come traffico.

Sul lato positivo, il controllo della marcatura DSCP tramite GPO garantisce che tutti i computer aggiunti al dominio ricevano le stesse impostazioni e che solo un amministratore possa gestirli. I client che possono usare GPO verranno contrassegnati nel dispositivo di origine e i dispositivi di rete configurati possono riconoscere il flusso in tempo reale dal codice DSCP e assegnargli una priorità appropriata.

### <a name="best-practice"></a>Procedure consigliate

È consigliabile una combinazione di contrassegni DSCP presso gli elenchi ACL basati su porte e endpoint sui router, se possibile. L'uso di un GPO per catturare la maggior parte dei client e anche l'uso della codifica DSCP basata su porta garantirà che il dispositivo mobile, Mac e altri client continuino a ricevere il trattamento QoS (almeno parzialmente).

I contrassegni DSCP possono essere paragonati ai francobolli che indicano agli addetti alle poste l'urgenza del parto e il modo migliore per ordinarlo per un parto rapido. Dopo aver configurato la rete per dare priorità ai flussi multimediali in tempo reale, i pacchetti persi e i pacchetti tardivi dovrebbero diminuire notevolmente.

Una volta che tutti i dispositivi della rete usano le stesse classificazioni, marcature e priorità, è possibile ridurre o eliminare ritardi, pacchetti eliminati e jitter modificando le dimensioni degli intervalli di porte assegnati alle code usate per ogni tipo di traffico. Dal punto di vista teams, il passaggio di configurazione più importante è la classificazione e la marcatura dei pacchetti. Tuttavia, per avere successo il QoS end-to-end, devi anche allineare con attenzione la configurazione dell'applicazione con la configurazione di rete sottostante. Una volta completata l'implementazione del QoS, la gestione continua è una questione di regolazione degli intervalli di porte assegnati a ogni tipo di traffico in base alle esigenze dell'organizzazione e all'uso effettivo.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Scegliere gli intervalli di porte iniziali per ogni tipo di elemento multimediale

Il valore DSCP indica a una rete configurata in modo corrispondente quale priorità assegnare a un pacchetto o a un flusso, se il contrassegno DSCP viene assegnato dai client o dalla rete stessa in base alle impostazioni ACL. Ogni carico di lavoro multimediale ottiene un valore DSCP univoco (altri servizi potrebbero consentire ai carichi di lavoro di condividere un contrassegno DSCP, teams not) e un intervallo di porte definito e separato usato per ogni tipo di elemento multimediale. In altri ambienti potrebbe essere presente una strategia QoS esistente che consente di determinare la priorità dei carichi di lavoro di rete.

La dimensione relativa degli intervalli di porta per i diversi carichi di lavoro in tempo reale in streaming imposta la percentuale di larghezza di banda disponibile totale dedicata a tale carico di lavoro. Per tornare all'analogia postale precedente: una lettera con un timbro "Air mail" potrebbe essere scattata entro un'ora dall'aeroporto più vicino, mentre un piccolo pacchetto contrassegnato come "posta in blocco" può attendere un giorno prima di spostarsi su una serie di camion.

_Intervalli di porte iniziali consigliati_

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Quando si usano queste impostazioni, tenere presente quanto segue:

- Se si prevede di implementare ExpressRoute in futuro e non è ancora stato implementato QoS, è consigliabile seguire le indicazioni in modo che i valori di DSCP siano uguali da mittente a destinatario.
- Tutti i client, inclusi i client mobili e i dispositivi teams, useranno questi intervalli di porte e saranno interessati da qualsiasi criterio DSCP implementato che usa questi intervalli di porta di origine. Gli unici client che continueranno a usare le porte dinamiche sono i client basati su browser (client che consentono ai partecipanti di partecipare alle riunioni usando i loro browser).
- Anche se il client Mac usa gli stessi intervalli di porte, USA anche valori hardcoded per l'audio (EF) e il video (AF41). Questi valori non sono configurabili.
- Se in seguito è necessario regolare gli intervalli di porte per migliorare l'esperienza utente, gli intervalli di porta non possono sovrapporsi e devono essere adiacenti.

## <a name="migrate-qos-to-teams"></a>Eseguire la migrazione di QoS ai team

Se in precedenza è stato distribuito Skype for business online, inclusi i contrassegni QoS e gli intervalli di porte e ora si distribuiscono. Teams, teams rispetterà la configurazione esistente e userà gli stessi intervalli di porte e i contrassegni come client Skype for business. Nella maggior parte dei casi non sarà necessaria alcuna configurazione aggiuntiva.

> [!NOTE]
> Se si usa la codifica QoS nome applicazione tramite criteri di gruppo, è necessario aggiungere Teams.exe come nome dell'applicazione.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementare QoS in teams in Windows tramite PowerShell

**Impostare QoS per l'audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Impostare QoS per il video**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Impostare QoS per la condivisione**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestione delle porte di origine nell'interfaccia di amministrazione di Teams

In teams le porte di origine QoS usate dai diversi carichi di lavoro devono essere gestite in modo attivo e modificate in base alle esigenze. Facendo riferimento alla tabella in [Scegli intervalli di porte iniziali per ogni tipo](#choose-initial-port-ranges-for-each-media-type)di elemento multimediale, gli intervalli di porta sono regolabili, ma i contrassegni di DSCP non sono configurabili. Dopo aver implementato queste impostazioni, è possibile che siano necessarie più o meno porte per un tipo di elemento multimediale specifico. Le [analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md) e il [dashboard di qualità delle chiamate (Call Quality Dashboard)](turning-on-and-using-call-quality-dashboard.md) devono essere usate per prendere una decisione per regolare gli intervalli di porte dopo l'implementazione di teams e periodicamente come le esigenze cambiano.

> [!NOTE]
> Se la funzionalità QoS è già stata configurata in base a intervalli di porta di origine e contrassegni DSCP per Skype for business online, la stessa configurazione verrà applicata ai team e non saranno necessarie ulteriori modifiche al client o alla rete, ma potrebbe essere necessario [impostare gli intervalli usati in teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) in modo che corrispondano a quelli configurati per Skype for business online.

Se in precedenza è stata distribuita in locale Skype for Business Server, potrebbe essere necessario riesaminare i criteri QoS. Modificare i criteri in base alle impostazioni dell'intervallo di porte che hai verificato fornisci un'esperienza utente di qualità per i team.

## <a name="validate-your-qos-implementation"></a>Convalidare l'implementazione QoS

Affinché il QoS sia efficace, il valore DSCP impostato dall'oggetto Criteri di gruppo deve essere presente in entrambe le estremità di una chiamata. Analizzando il traffico generato dal client teams, è possibile verificare che il valore DSCP non venga modificato o rimosso quando il traffico del carico di lavoro teams passa attraverso la rete.

È preferibile acquisire il traffico nel punto di uscita della rete. È possibile usare il mirroring della porta su uno switch o un router per aiutarlo.

## <a name="implement-qos-for-other-devices"></a>Implementare QoS per altri dispositivi

Leggere questi argomenti per informazioni sull'implementazione di QoS per Intune, Surface, iOS, Android e Mac

- [QoS per Surface Hub 2S](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [QoS per hub Surface](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [QoS per iOS, Android e Mac](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Argomenti correlati

- [Video: pianificazione della rete](https://aka.ms/teams-networking)

- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md)

- [Implementare QoS nel client Teams](QoS-in-Teams-clients.md)
