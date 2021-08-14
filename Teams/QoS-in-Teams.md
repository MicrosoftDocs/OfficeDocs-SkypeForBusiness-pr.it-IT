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
ms.openlocfilehash: b5bdfb924376170540985c586ac21c17f09ad978303ea9790d63563ec686b727
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326192"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a>Implementare la qualità del servizio (QoS) in Microsoft Teams

La qualità del servizio (QoS) in Microsoft Teams consente al traffico di rete in tempo reale sensibile ai ritardi della rete (ad esempio, flussi vocali o video) di "tagliare in linea" davanti al traffico meno sensibile(ad esempio il download di una nuova app, in cui un secondo in più per il download non è un problema). QoS usa Windows oggetti Criteri di gruppo ed elenchi di controllo di accesso basati su porta per identificare e contrassegnare tutti i pacchetti in flussi in tempo reale. In questo modo la rete è in grado di offrire flussi vocali, video e di condivisione dello schermo in una parte dedicata della larghezza di banda della rete.

Se si supporta un gruppo di utenti di grandi dimensioni che riscontrano uno dei problemi descritti in questo articolo, è probabile che sia necessario implementare QoS. Una piccola azienda con pochi utenti potrebbe non aver bisogno di QoS, ma anche lì dovrebbe essere utile.

Senza una qualche forma di QoS, potrebbero verificarsi i problemi di qualità seguenti in voce e video:

- Instabilità: pacchetti multimediali che arrivano a tariffe diverse, il che può comportare la mancanza di parole o sillabe nelle chiamate
- Perdita di pacchetti: pacchetti eliminati, che possono anche comportare una qualità vocale inferiore e un riconoscimento vocale difficile da comprendere
- Tempo di andata e ritorno (RTT) ritardato: i pacchetti multimediali che durano molto tempo per raggiungere le loro destinazioni, causando notevoli ritardi tra due parti in una conversazione e causando la conversazione tra le persone

Il modo meno complesso per risolvere questi problemi è aumentare le dimensioni delle connessioni dati, sia interne che esterne a Internet. Poiché questo è spesso un costo proibitivo, QoS consente di gestire in modo più efficace le risorse disponibili invece di aggiungere larghezza di banda. Per risolvere i problemi di qualità, è consigliabile usare prima QoS e quindi aggiungere larghezza di banda solo se necessario.

Per essere efficace, è necessario applicare impostazioni QoS coerenti in tutta l'organizzazione. Qualsiasi parte del percorso che non supporta le priorità QoS può ridurre la qualità delle chiamate, dei video e della condivisione dello schermo. Ciò include l'applicazione di impostazioni a tutti i PC o dispositivi degli utenti, agli switch di rete, ai router a Internet e al servizio Teams internet.

_Figura 1. La relazione tra le reti di un'organizzazione e Microsoft 365 o Office 365 servizi_

![Illustrazione della relazione tra reti e servizi](media/Qos-in-Teams-Image1.png "La relazione tra le reti di un'organizzazione e i servizi Microsoft 365 o Office 365: la rete locale e i dispositivi si connettono a una rete di interconnessione, che a sua volta si connette con i servizi di audioconferenza Microsoft 365 o Office 365 Cloud Voice.")

## <a name="qos-implementation-checklist"></a>Elenco di controllo per l'implementazione QoS

Per implementare QoS, eseguire le operazioni seguenti:

1. [Assicurarsi che la rete sia pronta.](#make-sure-your-network-is-ready)

1. [Selezionare un metodo di implementazione QoS.](#select-a-qos-implementation-method)

1. [Scegliere gli intervalli di porta iniziali per ogni tipo di supporto.](#choose-initial-port-ranges-for-each-media-type)

1. Implementare le impostazioni QoS:
   1. Nei client che usano un oggetto Criteri di gruppo (GPO) per impostare [gli intervalli e](QoS-in-Teams-clients.md)i contrassegni delle porte dei dispositivi client.
   2. Nei router (vedere la documentazione del produttore) o in altri dispositivi di rete. Può trattarsi di elenchi di controllo di accesso (ACL) basati su porta o semplicemente di definizione delle code QoS e dei contrassegni DSCP o di tutti questi elementi.

      > [!IMPORTANT]
      > È consigliabile implementare questi criteri QoS usando le porte di origine del client e un indirizzo IP di origine e di destinazione di "qualsiasi". In questo modo verrà intercettato sia il traffico multimediale in ingresso che quello in uscita nella rete interna.  

   3. [Impostare la modalità di gestione del traffico multimediale per le Teams riunioni.](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. [Convalidare l'implementazione di QoS](#validate-your-qos-implementation) analizzando Teams traffico sulla rete.

Mentre ci si prepara a implementare QoS, tenere presenti le linee guida seguenti:

- Il percorso più breve per Microsoft 365 è il migliore.
- La chiusura delle porte porterà solo a una riduzione della qualità.
- Gli eventuali ostacoli, ad esempio i proxy, non sono consigliati.
- Limitare il numero di hop:
  - Edge da client a rete : da 3 a 5 hop
  - Da ISP a Microsoft network edge - 3 hop
  - Edge di rete Microsoft alla destinazione finale - irrilevante

Per informazioni sulla configurazione delle porte del firewall, vedere Office 365 [URL e intervalli IP.](office-365-urls-ip-address-ranges.md)

## <a name="make-sure-your-network-is-ready"></a>Assicurarsi che la rete sia pronta

Se si sta valutando un'implementazione QoS, è necessario aver già determinato i requisiti di larghezza di banda e altri [requisiti di rete.](prepare-network.md)
  
La congestione del traffico in una rete inciderà notevolmente sulla qualità dei supporti multimediali. La mancanza di larghezza di banda comporta una riduzione delle prestazioni e una scarsa esperienza utente. Man mano Teams'adozione e l'utilizzo aumentano, usare la creazione di [report,](use-call-analytics-to-troubleshoot-poor-call-quality.md)l'analisi delle chiamate per utente e call [quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) per identificare i problemi e quindi apportare modifiche usando QoS e aggiunte selettive della larghezza di banda.

### <a name="vpn-considerations"></a>Considerazioni sulla VPN

QoS funziona come previsto solo se implementato in tutti i collegamenti tra chiamanti. Se si usa QoS in una rete interna e un utente accede da una posizione remota, è possibile assegnare priorità solo all'interno della rete interna gestita. Anche se le posizioni remote possono ricevere una connessione gestita implementando una rete privata virtuale (VPN), una VPN aggiunge intrinsecamente il sovraccarico dei pacchetti e crea ritardi nel traffico in tempo reale. È consigliabile evitare di eseguire il traffico di comunicazioni in tempo reale su una VPN.

In un'organizzazione globale con collegamenti gestiti che si estendono in continenti, è consigliabile usare QoS perché la larghezza di banda per tali collegamenti è limitata rispetto alla RETE LAN.

## <a name="introduction-to-qos-queues"></a>Introduzione alle code QoS

Per fornire QoS, i dispositivi di rete devono avere un modo per classificare il traffico e devono essere in grado di distinguere voce o video da altro traffico di rete.

Quando il traffico di rete entra in un router, il traffico viene inserito in una coda. Se non è configurato un criterio QoS, è presente una sola coda e tutti i dati vengono considerati first-in, first-out con la stessa priorità. Questo significa che il traffico vocale(che è molto sensibile ai ritardi) potrebbe rimanere bloccato dietro il traffico, dove un ritardo di alcuni millisecondi in più non sarebbe un problema.

Quando si implementa il QoS, si definiscono più code usando una delle diverse funzionalità di gestione della congestione, ad esempio l'accodamento prioritario di Cisco e la funzione [CBWFQ (Weighted Fair Queueing)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) basata su classi e le funzionalità di evitamento della congestione, ad esempio il rilevamento anticipato casuale ponderato [(WRED).](https://en.wikipedia.org/wiki/Weighted_random_early_detection)

_Figura 2. Esempi di code QoS_

![Illustrazione delle code QoS e della divisione della larghezza di banda](media/Qos-in-Teams-Image2.png "La larghezza di banda totale disponibile è suddivisa tra più code, ovvero audio, video e altro traffico, a cui sono state assegnate priorità diverse.")

Una semplice analogia è che QoS crea "corsie di carpooling" virtuali nella rete dati in modo che alcuni tipi di dati non si verifichino mai o raramente ritardi. Dopo aver creato queste corsie, è possibile modificarne le dimensioni relative e gestire in modo molto più efficace la larghezza di banda della connessione disponibile, offrendo al contempo esperienze di livello aziendale per gli utenti dell'organizzazione.

## <a name="select-a-qos-implementation-method"></a>Selezionare un metodo di implementazione QoS

È possibile implementare la QoS tramite tagging basato su porta, usando gli elenchi di controllo di accesso (ACL) nei router della rete. Il tagging basato su porta è il metodo più affidabile perché funziona in ambienti Windows misti, Mac e Linux ed è il più semplice da implementare. I client mobili non forniscono un meccanismo per contrassegnare il traffico usando i valori DSCP, quindi richiedono questo metodo.  

Usando il tagging basato su porta, il router della rete esamina un pacchetto in arrivo e, se il pacchetto è arrivato usando una determinata porta o intervallo di porte, lo identifica come un determinato tipo di supporto e lo inserisce nella coda per quel tipo, aggiungendo un contrassegno [DSCP](https://tools.ietf.org/html/rfc2474) predeterminato all'intestazione pacchetto IP in modo che altri dispositivi possano riconoscerne il tipo di traffico e assegnargli la priorità nella coda.

Anche se il tagging basato su porta funziona su più piattaforme, contrassegna solo il traffico all'edge WAN (non fino al computer client) e crea un sovraccarico di gestione. Per istruzioni sull'implementazione di questo metodo, vedere la documentazione fornita dal produttore del router.

### <a name="insert-dscp-markers"></a>Inserire indicatori DSCP

È anche possibile implementare la QoS usando un oggetto Criteri di gruppo (GPO) per indirizzare i dispositivi client a inserire un indicatore DSCP nelle intestazioni dei pacchetti IP che lo identificano come tipo specifico di traffico, ad esempio voce. I router e altri dispositivi di rete possono essere configurati per riconoscerlo e inserire il traffico in una coda separata con priorità più alta.

Anche se questo scenario è completamente valido, funziona solo per i client Windows dominio. Qualsiasi dispositivo che non fa parte di un client Windows non verrà abilitato per il tagging DSCP. Altri client, ad esempio quelli che eseguono macOS, hanno tag hard-coded e contrassegneranno sempre il traffico.

Inoltre, il controllo del contrassegno DSCP tramite l'oggetto Criteri di gruppo assicura che tutti i computer aggiunti al dominio ricevano le stesse impostazioni e che solo un amministratore possa gestirli. I client che possono usare l'oggetto Criteri di gruppo verranno contrassegnati nel dispositivo di origine e quindi i dispositivi di rete configurati possono riconoscere lo stream in tempo reale dal codice DSCP e assegnargli una priorità appropriata.

### <a name="best-practice"></a>Procedure consigliate

È consigliabile una combinazione di contrassegni DSCP nell'endpoint e, se possibile, elenchi di controllo di accesso basati su porta nei router. L'uso di un oggetto Criteri di gruppo per rilevare la maggior parte dei client e anche l'uso del tagging DSCP basato su porta garantirà che i dispositivi mobili, Mac e altri client otterrà comunque il trattamento QoS (almeno parzialmente).

I contrassegni DSCP possono essere paragonati a francobolli di spedizione che indicano agli operatori postali quanto è urgente la consegna e come ordinarli al meglio per una consegna rapida. Dopo aver configurato la rete in modo da assegnare la priorità ai flussi multimediali in tempo reale, i pacchetti persi e i pacchetti in ritardo dovrebbero diminuire notevolmente.

Quando tutti i dispositivi della rete usano le stesse classificazioni, contrassegni e priorità, è possibile ridurre o eliminare ritardi, pacchetti eliminati e instabilità modificando le dimensioni degli intervalli di porte assegnati alle code usate per ogni tipo di traffico. Dal punto Teams, il passaggio di configurazione più importante è la classificazione e il contrassegno dei pacchetti. Tuttavia, per il corretto completamento della QoS end-to-end, è anche necessario allineare con attenzione la configurazione dell'applicazione alla configurazione di rete sottostante. Una volta implementata completamente la QoS, la gestione continua è una questione di modificare gli intervalli di porta assegnati a ogni tipo di traffico in base alle esigenze e all'utilizzo effettivo dell'organizzazione.

## <a name="choose-initial-port-ranges-for-each-media-type"></a>Scegliere gli intervalli di porta iniziali per ogni tipo di supporto

Il valore DSCP indica a una rete configurata in modo corrispondente quale priorità assegnare a un pacchetto o a uno stream, se il contrassegno DSCP viene assegnato dai client o dalla rete stessa in base alle impostazioni ACL. Ogni carico di lavoro multimediale ottiene un valore DSCP univoco (altri servizi potrebbero consentire ai carichi di lavoro di condividere un contrassegno DSCP, Teams no) e un intervallo di porte definito e separato usato per ogni tipo di supporto. Altri ambienti potrebbero avere una strategia QoS esistente, che consente di determinare la priorità dei carichi di lavoro di rete.

Le dimensioni relative degli intervalli di porta per i diversi carichi di lavoro di streaming in tempo reale impostano la proporzione della larghezza di banda totale disponibile dedicata a tale carico di lavoro. Per tornare alla nostra precedente analogia postale: una lettera con un timbro "Posta aerea" potrebbe essere portata entro un'ora all'aeroporto più vicino, mentre un piccolo pacco contrassegnato come "Posta in blocco" può attendere un giorno prima di viaggiare su un terreno su una serie di camion.

_Intervalli di porta iniziali consigliati_

|Tipo di traffico multimediale| Intervallo di porte di origine client  |Protocollo|Valore DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50.000–50.019|TCP/UDP|46|Expedited Forwarding (EF)|
|Video| 50.020–50.039|TCP/UDP|34|Assured Forwarding (AF41)|
|Condivisione di applicazioni/schermi| 50.040–50.059|TCP/UDP|18|Assured Forwarding (AF21)|
||||||

Tenere presente quanto segue quando si usano queste impostazioni:

- Se si prevede di implementare ExpressRoute in futuro e non è ancora stato implementato QoS, è consigliabile seguire le indicazioni in modo che i valori DSCP siano gli stessi da mittente a destinatario.

- Tutti i client, inclusi i client mobili e i dispositivi Teams, useranno questi intervalli di porte e saranno interessati da qualsiasi criterio DSCP implementato che usa questi intervalli di porte di origine. Gli unici client che continueranno a usare porte dinamiche sono i client basati su browser, ovvero i client che consentono ai partecipanti di partecipare alle riunioni usando i browser.

- Anche se il client Mac usa gli stessi intervalli di porta, usa anche valori hard-coded per audio (EF) e video (AF41). Questi valori non sono configurabili.

- Se in seguito è necessario modificare gli intervalli di porta per migliorare l'esperienza utente, gli intervalli di porta non possono sovrapporsi e devono essere adiacenti.

## <a name="migrate-qos-to-teams"></a>Eseguire la migrazione di QoS a Teams

Se in precedenza è stata distribuita Skype for Business Online, inclusi i tag QoS e gli intervalli di porte, e ora è in esecuzione la distribuzione. Teams, Teams la configurazione esistente e userà gli stessi intervalli di porte e tag del client Skype for Business. Nella maggior parte dei casi non sarà necessaria alcuna configurazione aggiuntiva.

> [!NOTE]
> Se si usa il tagging QoS nome applicazione tramite Criteri di gruppo, è necessario aggiungere Teams.exe come nome dell'applicazione.

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a>Implementare QoS in Teams in Windows usando PowerShell

**Impostare QoS per l'audio**

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

**Impostare QoS per il video**

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

**Impostare QoS per la condivisione**

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a>Gestione delle porte di origine nell'interfaccia Teams di amministrazione

In Teams, le porte di origine QoS usate dai diversi carichi di lavoro devono essere gestite attivamente e modificate in base alle esigenze. Facendo riferimento alla tabella in Scegliere gli intervalli di [porta](#choose-initial-port-ranges-for-each-media-type)iniziali per ogni tipo di supporto, gli intervalli di porta sono regolabili, ma i contrassegni DSCP non sono configurabili. Dopo aver implementato queste impostazioni, è possibile che siano necessarie più o meno porte per un determinato tipo di supporto. [L'analisi](use-call-analytics-to-troubleshoot-poor-call-quality.md) delle chiamate per utente e il [call quality dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) devono essere usati per prendere una decisione per modificare gli intervalli di porte dopo l'implementazione di Teams e periodicamente in base alle esigenze.

> [!NOTE]
> Se la QoS è già stata configurata in base agli intervalli di porte di origine e ai contrassegni DSCP per Skype for Business Online, la stessa configurazione verrà applicata a Teams e non saranno necessarie altre modifiche del client o della rete al mapping, anche se potrebbe essere necessario impostare gli intervalli usati [in Teams in](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) modo che corrispondano a quanto configurato per Skype for Business Online.

Se in precedenza è stata distribuita Skype for Business Server locale, potrebbe essere necessario esaminare di nuovo i criteri di QoS. Modificare i criteri in modo che corrispondano alle impostazioni dell'intervallo di porte verificato per offrire un'esperienza utente di qualità Teams.

## <a name="validate-your-qos-implementation"></a>Convalidare l'implementazione QoS

Per essere efficace, il valore DSCP impostato dall'oggetto Criteri di gruppo deve essere presente a entrambe le estremità di una chiamata. Analizzando il traffico generato dal client Teams, è possibile verificare che il valore DSCP non sia modificato o privato quando il traffico del carico di lavoro di Teams si sposta attraverso la rete.

Preferibilmente, si acquisisce il traffico nel punto di uscita della rete. È possibile usare il mirroring delle porte su uno switch o un router per risolvere il problema.

## <a name="implement-qos-for-other-devices"></a>Implementare QoS per altri dispositivi

Leggere questi argomenti per informazioni sull'implementazione di QoS per Intune, Surface, iOS, Android e Mac

- [QoS per Surface Hub 2S](/surface-hub/surface-hub-2s-manage-intune)

- [QoS per Surface Hub](/surface-hub/surface-hub-qos)

- [QoS per iOS, Android e Mac](./meeting-settings-in-teams.md?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a>Argomenti correlati

- [Video: Pianificazione della rete](https://aka.ms/teams-networking)

- [Preparare la rete dell'organizzazione per Microsoft Teams](prepare-network.md)

- [Implementare QoS nel client Teams client](QoS-in-Teams-clients.md)