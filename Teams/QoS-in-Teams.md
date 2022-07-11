---
title: Implementare la qualità del servizio in Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Informazioni su come preparare la rete dell'organizzazione per la qualità del servizio (QoS) in Microsoft Teams.
ms.localizationpriority: medium
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
ms.openlocfilehash: 5b9c049942808da9b2df97d031ff850949bca211
ms.sourcegitcommit: 8d7a926758971bee491d24f23b1ad14f5e5c6f7f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/11/2022
ms.locfileid: "66713314"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementare la qualità del servizio (QoS) in Microsoft Teams

La qualità del servizio (QoS) in Microsoft Teams consente al traffico di rete in tempo reale sensibile ai ritardi di rete (ad esempio, flussi vocali o video) di "tagliare in linea" davanti al traffico meno sensibile (come il download di una nuova app, in cui un secondo in più da scaricare non è una grande offerta). QoS utilizza Oggetti di Windows Criteri di gruppo ed elenchi di Controllo di accesso basati su porte per identificare e contrassegnare tutti i pacchetti in flussi in tempo reale. In questo modo la rete può fornire ai flussi voce, video e condivisione dello schermo una parte dedicata della larghezza di banda di rete.

Se si supporta un numero elevato di utenti che hanno uno dei problemi descritti in questo articolo, probabilmente è necessario implementare QoS. Una piccola azienda con pochi utenti potrebbe non aver bisogno di QoS, ma anche lì dovrebbe essere utile.

Senza una qualche forma di QoS, potresti vedere i seguenti problemi di qualità in voce e video:

- Jitter: pacchetti multimediali che arrivano a velocità diverse, il che può comportare la mancanza di parole o sillabe nelle chiamate
- Perdita di pacchetti: pacchetti eliminati, che possono anche causare una qualità della voce inferiore e una difficile comprensione del parlato
- Tempo di round trip ritardato ( RTT): i pacchetti multimediali che impiegano molto tempo per raggiungere le loro destinazioni, il che comporta notevoli ritardi tra due parti in una conversazione e fa sì che le persone parlino tra loro

Il modo meno complesso per risolvere questi problemi consiste nell'aumentare le dimensioni delle connessioni dati, sia internamente che su Internet. Poiché spesso ciò è proibitivo a livello di costi, la QoS consente di gestire in modo più efficace le risorse disponibili invece di aggiungere larghezza di banda. Per risolvere i problemi di qualità, è consigliabile usare prima la QoS, quindi aggiungere la larghezza di banda solo se necessario.

Affinché QoS sia efficace, è necessario applicare impostazioni QoS coerenti in tutta l'organizzazione. Qualsiasi parte del percorso che non supporta le priorità QoS può compromettere la qualità di chiamate, video e condivisione dello schermo. Ciò include l'applicazione di impostazioni a tutti i PC o dispositivi utente, switch di rete, router a Internet e al servizio Teams.

_Figura 1. La relazione tra le reti di un'organizzazione e Microsoft 365 o i servizi di Office 365_

![Illustrazione della relazione tra reti e servizi.](media/Qos-in-Teams-Image1.png "La relazione tra le reti di un'organizzazione e i servizi di Microsoft 365 o Office 365: la rete locale e i dispositivi si connettono a una rete di connessione, che a sua volta si connette a Microsoft 365 o Office 365 servizi di audioconferenza e Cloud Voice.")

## <a name="qos-implementation-checklist"></a>Elenco di controllo per l'implementazione QoS

A un livello elevato, eseguire le operazioni seguenti per implementare la QoS:

1. [Assicurati che la rete sia pronta](#make-sure-your-network-is-ready).

1. [Selezionare un metodo di implementazione QoS](#select-a-qos-implementation-method).

1. [Scegliere gli intervalli di porte iniziali per ogni tipo di supporto](#choose-initial-port-ranges-for-each-media-type).

1. Implementare le impostazioni QoS:
   1. Nei client che usano un oggetto Criteri di gruppo (GPO) per [impostare intervalli di porte e contrassegni per i dispositivi client](QoS-in-Teams-clients.md).
   2. Nei router (vedi la documentazione del produttore) o in altri dispositivi di rete. Ciò potrebbe includere elenchi di Controllo di accesso basati sulle porte o definire semplicemente le code QoS e i contrassegni DSCP o tutti questi elementi.

      > [!IMPORTANT]
      > È consigliabile implementare questi criteri QoS usando le porte di origine client e un indirizzo IP di origine e di destinazione "any". Il traffico multimediale in ingresso e in uscita verrà intercetto nella rete interna.  

   3. [Impostare come gestire il traffico multimediale per le riunioni di Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).

5. [Convalidare l'implementazione QoS](#validate-your-qos-implementation) analizzando il traffico di Teams sulla rete.

Mentre ti prepari all'implementazione della QoS, tieni presente le seguenti linee guida:

- Il percorso più breve per Microsoft 365 è il migliore.
- La chiusura delle porte comporterà solo un peggioramento della qualità.
- Non sono consigliati eventuali ostacoli tra loro, ad esempio proxy.
- Limitare il numero di hop:
  - Dall'edge client a rete: da 3 a 5 hop
  - Dall'ISP all'edge della rete Di Microsoft - 3 passaggi
  - Edge della rete Microsoft verso la destinazione finale - irrilevante

Per informazioni sulla configurazione delle porte del firewall, vedere [Office 365 URL e intervalli IP](office-365-urls-ip-address-ranges.md).

## <a name="make-sure-your-network-is-ready"></a>Assicurati che la rete sia pronta

Se si sta valutando un'implementazione QoS, è necessario aver già determinato i requisiti di larghezza di banda e altri [requisiti di rete](prepare-network.md).
  
La congestione del traffico attraverso una rete influirà notevolmente sulla qualità multimediale. La mancanza di larghezza di banda comporta una riduzione delle prestazioni e un'esperienza utente scadente. Man mano che l'adozione e l'utilizzo di Teams aumentano, usare la creazione di report, [l'analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md) e [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) per identificare i problemi e quindi apportare modifiche usando la QoS e le aggiunte selettive di larghezza di banda.

### <a name="vpn-considerations"></a>Considerazioni sulla VPN

La QoS funziona come previsto solo se implementata in tutti i collegamenti tra i chiamanti. Se si usa QoS in una rete interna e un utente accede da una posizione remota, è possibile assegnare priorità solo all'interno della rete interna gestita. Anche se le posizioni remote possono ricevere una connessione gestita implementando una rete privata virtuale (VPN), una VPN aggiunge intrinsecamente l'overhead dei pacchetti e crea ritardi nel traffico in tempo reale. Ti consigliamo di evitare di eseguire traffico di comunicazione in tempo reale su una VPN.

In un'organizzazione globale con collegamenti gestiti che si estendono su continenti, è consigliabile QoS perché la larghezza di banda per tali collegamenti è limitata rispetto alla LAN.

## <a name="introduction-to-qos-queues"></a>Introduzione alle code QoS

Per fornire la QoS, i dispositivi di rete devono avere un modo per classificare il traffico e devono essere in grado di distinguere voce o video da altro traffico di rete.

Quando il traffico di rete entra in un router, il traffico viene inserito in coda. Se un criterio QoS non è configurato, esiste una sola coda e tutti i dati vengono trattati come first-in e first-out con la stessa priorità. Questo significa che il traffico vocale (molto sensibile ai ritardi) potrebbe rimanere bloccato dietro il traffico in cui un ritardo di alcuni millisecondi in più non sarebbe un problema.

Quando si implementa la QoS, si definiscono più code utilizzando una delle diverse funzionalità di gestione della congestione, ad esempio l'accodamento prioritario di Cisco e [il CBWFQ (Class-Based Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) e le funzionalità di prevenzione della congestione, ad esempio il [rilevamento precoce ponderato casuale (WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figura 2. Esempi di code QoS_

![Illustrazione delle code QoS e della divisione della larghezza di banda.](media/Qos-in-Teams-Image2.png "La larghezza di banda totale disponibile è suddivisa tra più code, audio, video e altro traffico, a cui sono state assegnate priorità diverse.")

Una semplice analogia è che QoS crea "corsie di carpooling" virtuali nella rete dati in modo che alcuni tipi di dati non riscontrano mai o raramente un ritardo. Dopo aver creato queste corsie, è possibile modificarne le dimensioni relative e gestire in modo molto più efficace la larghezza di banda di connessione disponibile, offrendo allo stesso tempo esperienze di livello aziendale per gli utenti dell'organizzazione.

## <a name="select-a-qos-implementation-method"></a>Selezionare un metodo di implementazione QoS

È possibile implementare la QoS tramite il tagging basato su porte, utilizzando Controllo di accesso List (ACL) nei router della rete. Il tagging basato sulle porte è il metodo più affidabile perché funziona in ambienti windows, Mac e Linux misti ed è il più semplice da implementare. I client mobili non forniscono un meccanismo per contrassegnare il traffico utilizzando valori DSCP, quindi richiedono questo metodo.  

Usando il tagging basato su porte, il router della rete esamina un pacchetto in arrivo e, se il pacchetto è arrivato utilizzando una determinata porta o intervallo di porte, lo identifica come un determinato tipo di supporto e lo inserisce nella coda per quel tipo, aggiungendo un contrassegno [DSCP](https://tools.ietf.org/html/rfc2474) predeterminato all'intestazione del pacchetto IP in modo che altri dispositivi possano riconoscerne il tipo di traffico e assegnargli la priorità nella coda.

Anche se i tag basati su porta funzionano su più piattaforme, contrassegna solo il traffico sul bordo WAN (non fino al computer client) e crea un sovraccarico di gestione. Fai riferimento alla documentazione fornita dal produttore del router per istruzioni sull'implementazione di questo metodo.

### <a name="insert-dscp-markers"></a>Inserire marcatori DSCP

È anche possibile implementare la QoS utilizzando un oggetto Criteri di gruppo (GPO) per indirizzare i dispositivi client a inserire un marcatore DSCP nelle intestazioni dei pacchetti IP identificandolo come particolare tipo di traffico (ad esempio, voce). I router e altri dispositivi di rete possono essere configurati per riconoscere questo e inserire il traffico in una coda separata con priorità più alta.

Anche se questo scenario è completamente valido, funziona solo per i client Windows aggiunti a un dominio. Qualsiasi dispositivo che non è un client Windows aggiunto a un dominio non verrà abilitato per l'aggiunta di tag DSCP. Altri client, ad esempio quelli che eseguono macOS, hanno tag hardcoded e contrassegnano sempre il traffico.

Sul lato plus, il controllo del contrassegno DSCP tramite oggetto Criteri di gruppo assicura che tutti i computer aggiunti a un dominio ricevano le stesse impostazioni e che solo un amministratore possa gestirle. I client che possono usare l'oggetto Criteri di gruppo verranno contrassegnati nel dispositivo di origine e quindi configurati i dispositivi di rete potranno riconoscere lo stream in tempo reale dal codice DSCP e assegnargli una priorità appropriata.

### <a name="best-practice"></a>Procedure consigliate

Se possibile, è consigliabile una combinazione di contrassegni DSCP sull'endpoint e ACL basati su porte nei router. L'uso di un oggetto Criteri di gruppo per catturare la maggior parte dei clienti e l'uso di tag DSCP basati su porte garantirà che i clienti mobili, Mac e altri riceveranno ancora il trattamento QoS (almeno parzialmente).

I contrassegni DSCP possono essere paragonati a francobolli che indicano ai dipendenti postali quanto sia urgente la consegna e come ordinarla al meglio per una consegna rapida. Dopo aver configurato la rete in modo da dare priorità ai flussi multimediali in tempo reale, i pacchetti persi e i pacchetti in ritardo dovrebbero diminuire notevolmente.

Una volta che tutti i dispositivi della rete utilizzano le stesse classificazioni, contrassegni e priorità, è possibile ridurre o eliminare ritardi, pacchetti interrotti e instabilità modificando le dimensioni degli intervalli di porte assegnati alle code usate per ogni tipo di traffico. Dal punto di vista di Teams, il passaggio di configurazione più importante è la classificazione e il contrassegno dei pacchetti. Tuttavia, affinché la QoS end-to-end abbia esito positivo, è necessario allineare con attenzione la configurazione dell'applicazione alla configurazione di rete sottostante. Una volta implementata completamente la QoS, la gestione continua consiste nell'adattare gli intervalli di porte assegnati a ogni tipo di traffico in base alle esigenze e all'utilizzo effettivo dell'organizzazione.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Scegliere gli intervalli di porte iniziali per ogni tipo di supporto

Il valore DSCP indica a una rete configurata in modo corrispondente quale priorità assegnare a un pacchetto o a uno stream, se il contrassegno DSCP è assegnato dai client o dalla rete stessa in base alle impostazioni ACL. Ogni carico di lavoro multimediale ottiene il proprio valore DSCP univoco (altri servizi potrebbero consentire ai carichi di lavoro di condividere un contrassegno DSCP, Teams no) e un intervallo di porte definito e separato usato per ogni tipo di supporto. Altri ambienti potrebbero avere una strategia QoS esistente, che consente di determinare la priorità dei carichi di lavoro di rete.

La dimensione relativa degli intervalli di porte per i diversi carichi di lavoro di streaming in tempo reale imposta la proporzione della larghezza di banda totale disponibile dedicata a tale carico di lavoro. Per tornare alla precedente analogia postale: una lettera con un francobollo "Air Mail" potrebbe essere portata entro un'ora all'aeroporto più vicino, mentre un piccolo pacchetto contrassegnato come "Bulk Mail" può aspettare un giorno prima di viaggiare su una serie di camion.

_Intervalli di porte iniziali consigliati_

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Quando si usano queste impostazioni, tenere presente quanto segue:

- Se prevedi di implementare ExpressRoute in futuro e non hai ancora implementato la QoS, ti consigliamo di seguire le indicazioni in modo che i valori DSCP siano uguali da mittente a destinatario.

- Tutti i client, inclusi i client mobili e i dispositivi Teams, utilizzeranno questi intervalli di porte e saranno interessati da eventuali criteri DSCP implementati che usano questi intervalli di porte di origine. Gli unici client che continueranno a usare le porte dinamiche sono i client basati su browser, ovvero client che consentono ai partecipanti di partecipare alle riunioni tramite i browser.

- Sebbene il client Mac usi gli stessi intervalli di porte, usa anche valori hardcoded per audio (EF) e video e condivisione applicazioni/schermo (AF41). Questi valori non sono configurabili.

- Se in seguito è necessario modificare gli intervalli di porte per migliorare l'esperienza utente, gli intervalli di porte non possono sovrapporsi e devono essere adiacenti.

## <a name="migrate-qos-to-teams"></a>Eseguire la migrazione di QoS a Teams

Se in precedenza è stato distribuito Skype for Business Online, inclusi l'aggiunta di tag QoS e intervalli di porte, e ora è in fase di distribuzione. Teams, Teams rispetterà la configurazione esistente e utilizzerà gli stessi intervalli di porte e l'aggiunta di tag del client Skype for Business. Nella maggior parte dei casi non è necessaria alcuna configurazione aggiuntiva.

> [!NOTE]
> Se si usa il tag QoS nome applicazione tramite Criteri di gruppo, è necessario aggiungere Teams.exe come nome dell'applicazione.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementare QoS in Teams in Windows con PowerShell

**Impostare QoS per l'audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Impostare la QoS per il video**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Impostare QoS per la condivisione**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestione delle porte di origine nell'interfaccia di amministrazione di Teams

In Teams, le porte di origine QoS usate dai diversi carichi di lavoro devono essere gestite attivamente e modificate in base alle esigenze. Facendo riferimento alla tabella in [Scegliere gli intervalli di porte iniziali per ogni tipo di supporto](#choose-initial-port-ranges-for-each-media-type), gli intervalli di porte sono modificabili, ma i contrassegni DSCP non sono configurabili. Dopo aver implementato queste impostazioni, è possibile che siano necessarie più o meno porte per un determinato tipo di supporto. [L'analisi delle chiamate per utente](use-call-analytics-to-troubleshoot-poor-call-quality.md) e [call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) devono essere usate per prendere una decisione per modificare gli intervalli di porte dopo l'implementazione di Teams e periodicamente in base alle esigenze.

> [!NOTE]
> Se la QoS è già stata configurata in base a intervalli di porte di origine e contrassegni DSCP per Skype for Business Online, la stessa configurazione verrà applicata a Teams e non saranno necessarie ulteriori modifiche al mapping del client o della rete, anche se potrebbe essere necessario [impostare gli intervalli usati in Teams in](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) modo che corrispondano a quanto configurato per Skype for Business Online.

Se in precedenza sono stati distribuiti Skype for Business Server locale, potrebbe essere necessario riesaminare i criteri QoS. Modificare i criteri in modo che corrispondano alle impostazioni dell'intervallo di porte verificate forniscono un'esperienza utente di qualità per Teams.

## <a name="validate-your-qos-implementation"></a>Convalidare l'implementazione QoS

Affinché QoS sia efficace, il valore DSCP impostato dall'oggetto Criteri di gruppo deve essere presente a entrambe le estremità di una chiamata. Analizzando il traffico generato dal client Teams, è possibile verificare che il valore DSCP non sia cambiato o rimosso quando il traffico del carico di lavoro di Teams si sposta attraverso la rete.

Preferibilmente, acquisisci il traffico nel punto di uscita della rete. È possibile usare il mirroring della porta su un commutatore o un router per facilitare questa operazione.

## <a name="implement-qos-for-other-devices"></a>Implementare QoS per altri dispositivi

Leggi questi argomenti per informazioni sull'implementazione di QoS per Intune, Surface, iOS, Android e Mac

- [QoS per Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS per Surface Hub](/surface-hub/surface-hub-qos)

- [QoS per iOS, Android e Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Argomenti correlati

- [Video: Pianificazione della rete](https://aka.ms/teams-networking)

- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md)

- [Implementare QoS nel client di Teams](QoS-in-Teams-clients.md)
