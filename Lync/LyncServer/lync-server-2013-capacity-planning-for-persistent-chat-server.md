---
title: 'Lync Server 2013: pianificazione della capacità per il server di chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning for Persistent Chat Server
ms:assetid: 7a850cd5-c789-4795-a8ff-083be21ae784
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615006(v=OCS.15)
ms:contentKeyID: 48184580
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dde4bcb499e38e729850f06bb08590bf537696e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737026"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Pianificazione della capacità per il server di chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Il server di chat persistente può eseguire una chat in tempo reale multiutente che può essere mantenuta per il recupero e la ricerca futuri. A differenza della messaggistica istantanea di gruppo che viene salvata nella cassetta postale di un utente se è configurata la cronologia delle conversazioni, una sessione del server di chat persistente rimane aperta più a lungo e il contenuto viene salvato in un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di un conversazione in corso.

La pianificazione della capacità è una parte importante della preparazione alla distribuzione del server di chat persistente. Questo argomento fornisce informazioni dettagliate sulle topologie del server di chat persistente supportate e sulle tabelle di pianificazione della capacità che è possibile usare per determinare la configurazione migliore per la distribuzione. Descrive anche come gestire al meglio le distribuzioni del server della chat persistente che richiedono maggiore capacità nelle ore di punta.

Per scaricare il server di chat persistente, vedere "Microsoft Lync Server 13 Persistent [http://go.microsoft.com/fwlink/p/?linkId=209539](http://go.microsoft.com/fwlink/p/?linkid=209539)Chat Server" at.

Per informazioni dettagliate sull'installazione del server di chat persistente, vedere [installazione del server di chat persistente in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) e [configurazione del server di chat persistente in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) nella documentazione relativa alla distribuzione.

Gli strumenti di supporto, ad esempio lo strumento di pianificazione di Lync Server, possono aiutare ulteriormente la pianificazione della capacità. Per informazioni dettagliate sullo strumento di pianificazione, vedere [inizio del processo di pianificazione per Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologie supportate dal server di chat persistente

È possibile distribuire il server di chat persistente in pool a server singolo o a più server e con una topologia a pool singolo o multiplo.

Ora è anche supportato il server di chat persistente sul server Standard Edition per le nuove distribuzioni di Lync Server 2013. Tuttavia, le prestazioni e la scala saranno interessate e, poiché non esiste un'opzione di disponibilità elevata per questa nuova distribuzione, ci aspettiamo che tu usi questo aspetto principalmente ai fini della prova del concetto, della valutazione e così via.

<div>


> [!NOTE]  
> Per informazioni dettagliate su entrambe le topologie, vedere <A href="lync-server-2013-planning-for-persistent-chat-server.md">pianificazione del server di chat persistente in Lync server 2013</A> in questa documentazione e <A href="lync-server-2013-deploying-persistent-chat-server.md">distribuzione del server di chat persistente in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="single-server-topology"></a>Topologia a server singolo

La configurazione minima e la distribuzione più semplice per il server di chat persistente è una singola topologia del server front end del server di chat persistente. Questa distribuzione richiede un singolo server che esegue il server di chat persistente (che facoltativamente esegue il servizio di conformità, se è abilitata la conformità), un server che ospita sia il database di SQL Server che se è necessaria la conformità, il database di SQL Server per archiviare il dati sulla conformità.

<div>


> [!IMPORTANT]  
> Non è possibile aggiungere altri server a un pool di server di chat persistente avviato come distribuzione a server singolo in Generatore di topologie. È consigliabile usare la topologia di pool a più server, anche se si usa un singolo server. In questo modo potrai aggiungere più server in un secondo momento, se necessario. 


</div>

La figura seguente mostra tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end del server di chat persistente con conformità.

**Singolo server di chat persistente**

![Topologia a un solo server con Compliance Service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia a un solo server con Compliance Service")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia a più server

Per avere maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [pianificazione per il server di chat persistente in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologia a più server può includere fino a quattro computer attivi che eseguono il server di chat persistente (le configurazioni ad alta disponibilità e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le rimanenti quattro in standby). Ogni server può supportare tutti gli utenti simultanei di 20.000, per un totale di 80.000 utenti simultanei connessi a un pool di server di chat persistente con 4 server. Una topologia a più server è uguale alla topologia a server singolo, ad eccezione del fatto che più server ospitano il server di chat persistente e possono essere ridimensionati in modo più elevato. Più computer che eseguono il server di chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory di Lync Server e nel servizio conformità.

La figura seguente mostra tutti i componenti di una topologia a più server con più computer che eseguono il server di chat persistente, il servizio di conformità facoltativo e un database di conformità separato.

**Più server di chat persistenti**

![Topologia a più server](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia a più server")

In una distribuzione di server di chat persistente con quattro server, in cui gli utenti di 80.000 possono essere connessi simultaneamente e usando la chat persistente, il carico viene distribuito uniformemente in 20.000 utenti per server. Se un server non è disponibile, gli utenti connessi al server perderanno l'accesso al server di chat persistente. Gli utenti disconnessi verranno trasferiti automaticamente ai server rimanenti finché non viene ripristinato il server non disponibile. A seconda della quantità di traffico di chat persistente nella rete, questo trasferimento può richiedere qualche minuto o più. Poiché ognuno dei server rimanenti può ospitare fino a 30.000 utenti, è consigliabile ripristinare il server non disponibile il più rapidamente possibile per evitare problemi di prestazioni. In caso contrario, è possibile rendere disponibile un altro server di chat persistente usando il generatore di topologia o il cmdlet di Windows PowerShell, **Set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Pianificazione della capacità del server di chat persistente

Le tabelle seguenti possono essere utili per la pianificazione della capacità per il server della chat persistente. Modellano la modalità di modifica delle varie impostazioni del server di chat persistente sulle capacità.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Pianificazione della capacità massima per il server di chat persistente

Usare la tabella di esempio seguente per determinare il numero di utenti che sarà in grado di supportare.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Esempio di capacità massima del pool di server di chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Istanze del servizio chat persistenti attive</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Istanze del servizio chat persistente</p></td>
<td><p><em>8 (4 deve essere inattivo; solo un massimo di 4 può essere attivo)</em></p></td>
</tr>
<tr class="odd">
<td><p>Utenti attivi connessi</p></td>
<td><p><em>80.000</em></p></td>
</tr>
<tr class="even">
<td><p>Totale utenti con provisioning</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Numero di endpoint</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


Nell'esempio precedente il piano consiste nel supportare il numero massimo di utenti che il server di chat persistente consente: quattro server/istanze del servizio di chat persistente (può avere quattro server più passivi che gestiscono il server di chat persistente per l'elevata disponibilità e il ripristino di emergenza) e gli utenti di 20.000 per server, per un totale di 80.000 utenti attivi.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Pianificazione della capacità per la gestione dell'accesso alla chat room persistente

La tabella di esempio seguente può essere utile per pianificare la gestione dell'accesso delle chat room permanenti in un pool di server di chat persistente.

### <a name="managing-chat-room-access-sample"></a>Esempio di accesso alla chat room

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Piccole chat room</th>
<th>Chat room di medie dimensioni</th>
<th>Chat room di grandi dimensioni</th>
<th>Totale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimensioni delle chat room (numero di utenti connessi)</p></td>
<td><p>30 per camera</p></td>
<td><p>150 per camera</p></td>
<td><p>16.000 per camera</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chat room</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% delle sale che sono Auditorium</p></td>
<td><p>1</p></td>
<td><p>1</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% delle camere aperte</p></td>
<td><p>3</p></td>
<td><p>3</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Aprire le sale (nessuna appartenenza esplicita)</p></td>
<td><p>960</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td><p>997</p></td>
</tr>
<tr class="even">
<td><p>Camere non aperte (camere normali con appartenenza esplicita)</p></td>
<td><p>31.040</p></td>
<td><p>1,035</p></td>
<td><p>5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Sale Auditorium (voce relatori aggiunti)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Sale gestite da un abbonamento diretto</p></td>
<td><p>50%</p></td>
<td><p>10</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Sale gestite da gruppi di utenti</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le camere aperte (non specificato in modo esplicito)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti nell'elenco di appartenenza di ogni chat room per le camere non aperte</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le camere non aperte</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti e gruppi utenti nell'elenco Manager di ogni chat room (per le sale aperte e non aperte)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utenti e gruppi utenti nell'elenco relatori di ogni chat room dell'Auditorium (per le sale aperte e non aperte)</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entità di appartenenza basate sull'utente in tutte le camere non aperte</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entità di appartenenza basate su gruppi di utenti in tutte le camere non aperte</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti e gruppi utente basati su entità in tutte le chat room di Auditorium</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gli utenti e le entità di gestione basate su gruppi utente in tutti gli elenchi di Manager di chat room</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti attivi per chat room</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chat room per utente</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Gruppi di utenti nell'elenco di appartenenza di ogni chat room</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Sale gestite da gruppi di utenti</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entità di appartenenza basate su gruppi di utenti in tutte le chat room</p></td>
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entità di appartenenza basate sull'utente in tutte le chat room</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti e gruppi utenti negli elenchi Manager, relatore e ambito di ogni chat room</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td><p>6</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utenti e gruppi utenti in tutte le chat room Manager, relatore e elenchi di ambiti</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Voci di controllo di Access</p></td>
<td><p>704.160</p></td>
<td><p>26.768</p></td>
<td><p>160</p></td>
<td><p>731.088</p></td>
</tr>
<tr class="even">
<td><p>Voci di controllo di accesso massimo</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 milioni</p></td>
</tr>
</tbody>
</table>


Nell'esempio precedente, quando si distribuiscono i server di chat persistenti in base alle linee guida consigliate, è possibile gestire fino a 80.000 utenti attivi in un pool di quattro server con conformità abilitata.

Questo esempio mostra le chat room categorizzate come piccole (30 utenti attivi in qualsiasi momento), medie (utenti attivi di 150) e grandi (16.000 utenti attivi). Il numero di chat room di una determinata dimensione viene calcolato in base al numero totale di:

  - Utenti attivi nel sistema

  - Utenti attivi nelle chat room delle dimensioni specificate

  - Chat room con le dimensioni specificate a cui è associato un singolo utente

Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci assegnate direttamente alla chat room. È possibile controllare l'accesso alle singole chat room usando gli elenchi di controllo di accesso (ACL). È anche possibile controllare l'accesso a livello di categoria. In un ACL una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente. Puoi definire le voci di controllo di accesso per i responsabili delle chat room, i relatori e i membri.

<div>


> [!IMPORTANT]  
> Nella pianificazione della strategia per la gestione delle chat room, tieni presente che il numero totale di voci di controllo di accesso consentite è 2 milioni. Se le voci di controllo di accesso calcolate superano 2 milioni, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, se possibile, verificare che le voci di controllo di accesso siano gruppi di utenti anziché singoli.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Pianificazione della capacità per la gestione dell'accesso alle chat room tramite invito

È possibile usare la tabella di pianificazione della capacità seguente per comprendere il numero di inviti che il server di chat persistente crea e archivia nel database della chat persistente quando è configurato per l'invio di inviti. Puoi gestire gli inviti per la categoria usando la pagina **Impostazioni categoria chat room** nel pannello di controllo di Lync Server oppure usando il cmdlet di Windows PowerShell, **set-csPersistentChatCategory**. È possibile gestire gli inviti in una chat room (in linea con ciò che la categoria consente) usando la pagina **gestione sala** avviata dal client Lync o usando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom**.

I dati di esempio nella tabella seguente presuppongono che, nella pagina **delle impostazioni della chat room** per 50% di tutte le chat room, l'opzione **inviti** sia impostata su **Sì**.

<div>


> [!IMPORTANT]  
> Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare in modo significativo. Per evitare questo problema, assicurati di ridurre al minimo il numero di chat room configurate per l'invio di inviti o per limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Accesso alla chat room tramite l'esempio di invito

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Piccole chat room</th>
<th>Chat room di medie dimensioni</th>
<th>Chat room di grandi dimensioni</th>
<th>Totale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti che possono accedere alla chat room</p></td>
<td><p>30 per camera</p></td>
<td><p>150 per camera</p></td>
<td><p>16.000 per camera</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Percentuale di camere con inviti</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Chat room configurate per l'invio di inviti</p></td>
<td><p><em>16.000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utenti che possono accedere alla chat room</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Inviti generati dal server di chat persistente</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80.000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Numero massimo di inviti consentiti</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 milioni</p></td>
</tr>
<tr class="odd">
<td><p>Modello 1-iniziare con il numero di messaggi previsto per ogni camera al giorno</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Tasso di chat per camera (per giorno)</p></td>
<td><p>50</p></td>
<td><p>500</p></td>
<td><p>100</p></td>
<td><p>650</p></td>
</tr>
<tr class="odd">
<td><p>Velocità di chat (al secondo) in tutte le sale</p></td>
<td><p>55,56</p></td>
<td><p>18,52</p></td>
<td><p>0,03</p></td>
<td><p>74</p></td>
</tr>
<tr class="even">
<td><p>Modello 2-inizio con il numero di messaggi pubblicati per utente per giorno</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Tasso di chat per utente per giorno</p></td>
<td><p>15</p></td>
<td><p>5</p></td>
<td><p>0,1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Tasso di chat per camera (per giorno)</p></td>
<td><p>38</p></td>
<td><p>375</p></td>
<td><p>800</p></td>
<td><p>1.213</p></td>
</tr>
<tr class="odd">
<td><p>Velocità di chat (al secondo) in tutte le sale</p></td>
<td><p>41,67</p></td>
<td><p>13,89</p></td>
<td><p>0,28</p></td>
<td><p>56</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="persistent-chat-server-performance-user-model"></a>Modello utente delle prestazioni del server di chat persistente

La tabella seguente descrive il modello di utente per il server di chat persistente. Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con utenti simultanei di 80.000 su quattro server.

### <a name="persistent-chat-server-performance-user-model"></a>Modello utente delle prestazioni del server di chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Numero di utenti attivi connessi</p></td>
<td><p>80.000</p></td>
</tr>
<tr class="even">
<td><p>Numero di istanze del servizio server Chat persistente</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>Dimensioni delle piccole chat room</p></td>
<td><p>30 utenti</p></td>
</tr>
<tr class="even">
<td><p>Dimensioni delle chat room medie</p></td>
<td><p>utenti di 150</p></td>
</tr>
<tr class="odd">
<td><p>Dimensioni delle chat room di grandi dimensioni</p></td>
<td><p>utenti di 16.000</p></td>
</tr>
<tr class="even">
<td><p>Numero totale di chat room</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat room di piccole dimensioni</p></td>
<td><p>32.000</p></td>
</tr>
<tr class="even">
<td><p>Numero di chat room di medie dimensioni</p></td>
<td><p>1.067</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat room di grandi dimensioni</p></td>
<td><p>10</p></td>
</tr>
<tr class="even">
<td><p>Numero totale di chat room per utente</p></td>
<td><p>16</p></td>
</tr>
<tr class="odd">
<td><p>Numero di piccole chat room per utente</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Numero di chat room medie per utente</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat room di grandi dimensioni per utente</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Numero di sale Unite per utente</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Tasso di partecipazione di picco</p></td>
<td><p>10/secondo</p></td>
</tr>
<tr class="even">
<td><p>Tasso di chat totale</p></td>
<td><p>24/secondo</p></td>
</tr>
<tr class="odd">
<td><p>Tariffa chat per piccole chat room</p></td>
<td><p>22.22/second</p></td>
</tr>
<tr class="even">
<td><p>Tasso di chat per le chat room di medie dimensioni</p></td>
<td><p>1.67/Second</p></td>
</tr>
<tr class="odd">
<td><p>Tasso di chat per le chat room di grandi dimensioni</p></td>
<td><p>~ 0.15/secondo</p></td>
</tr>
<tr class="even">
<td><p>Percentuale di chat room configurate per gli inviti</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Percentuale di appartenenze dirette</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Percentuale di appartenenze ai gruppi</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Numero medio di affiliazioni predecessore in servizi di dominio Active Directory</p></td>
<td><p>100-200</p></td>
</tr>
<tr class="even">
<td><p>Numero di contatti sottoscritti per utente</p></td>
<td><p>80</p></td>
</tr>
<tr class="odd">
<td><p>Numero medio di endpoint per utente</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="even">
<td><p>Numero medio di chat room visibili per endpoint</p></td>
<td><p>1,5</p></td>
</tr>
<tr class="odd">
<td><p>Numero medio di chat room visibili per utente</p></td>
<td><p>2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 camere aperte, una per ogni monitor</p></td>
</tr>
<tr class="even">
<td><p>Numero di partecipanti interrogati per intervallo</p></td>
<td><p>25 per la chat room visibile</p></td>
</tr>
<tr class="odd">
<td><p>Lunghezza dell'intervallo di polling</p></td>
<td><p>5 minuti</p></td>
</tr>
<tr class="even">
<td><p>Numero di partecipanti a polling al secondo</p></td>
<td><p>15.000</p></td>
</tr>
<tr class="odd">
<td><p>Numero di modifiche alla presenza per ora per utente</p></td>
<td><p>6</p></td>
</tr>
<tr class="even">
<td><p>Numero di modifiche alla presenza al secondo</p></td>
<td><p>133,33</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

