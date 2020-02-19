---
title: 'Lync Server 2013: pianificazione della capacità per il server Chat persistente'
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
ms.openlocfilehash: d0cd27f961d3b4857cf13d5786897bd29a657851
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135563"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-persistent-chat-server-in-lync-server-2013"></a>Pianificazione della capacità per il server Chat persistente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Il server Chat persistente può eseguire chat in tempo reale multiutente che può persistere per il recupero e la ricerca futuri. A differenza della messaggistica istantanea di gruppo che viene salvata nella cassetta postale dell'utente se la cronologia delle conversazioni è configurata, una sessione del server Chat persistente resta aperta più a lungo e il contenuto viene salvato in un server, insieme ai messaggi, ai file, agli URL e ad altri dati che fanno parte di un conversazione continua.

La pianificazione della capacità è una parte importante della preparazione per la distribuzione del server Chat persistente. In questo argomento vengono fornite informazioni dettagliate sulle tabelle di topologie del server Chat persistente supportate e sulla pianificazione della capacità che è possibile utilizzare per determinare la configurazione ottimale per la distribuzione. Viene inoltre descritto come gestire al meglio le distribuzioni di server Chat persistente che richiedono una maggiore capacità negli orari di punta.

Per scaricare il server Chat persistente, vedere "Microsoft Lync Server 13 Persistent Chat [https://go.microsoft.com/fwlink/p/?linkId=209539](https://go.microsoft.com/fwlink/p/?linkid=209539)server" all'indirizzo.

Per informazioni dettagliate sull'installazione del server Chat persistente, vedere [Installing Persistent Chat Server in Lync server 2013](lync-server-2013-installing-persistent-chat-server.md) e [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md) nella documentazione relativa alla distribuzione.

Gli strumenti di supporto, ad esempio lo strumento di pianificazione di Lync Server, sono in grado di facilitare la pianificazione della capacità. Per informazioni dettagliate sullo strumento di pianificazione, vedere [beginning the Planning Process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="persistent-chat-server-supported-topologies"></a>Topologie supportate dal server Chat persistente

È possibile distribuire il server Chat persistente in pool a server singolo o a più server e con topologia a pool singolo o a più pool.

Ora è supportato anche il server Chat persistente sul server Standard Edition per le nuove distribuzioni di Lync Server 2013. Tuttavia, le prestazioni e la scala saranno intaccate e poiché non esiste un'opzione di disponibilità elevata per la nuova distribuzione, si prevede di utilizzarla principalmente ai fini della prova del concetto, della valutazione e così via.

<div>


> [!NOTE]  
> Per ulteriori informazioni su entrambe le topologie, vedere <A href="lync-server-2013-planning-for-persistent-chat-server.md">Planning for Persistent Chat Server in Lync server 2013</A> in questa documentazione impostare e <A href="lync-server-2013-deploying-persistent-chat-server.md">Deploying Persistent Chat Server in Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

<div>

## <a name="single-server-topology"></a>Topologia a server singolo

La configurazione minima e la distribuzione più semplice per il server Chat persistente è una singola topologia del server front-end del server di chat persistente. Questa distribuzione richiede un singolo server che esegue il server Chat persistente (che facoltativamente esegue il servizio di conformità, se la conformità è abilitata), un server che ospita il database di SQL Server e, se è necessaria la conformità, il database di SQL Server per archiviare la dati di conformità.

<div>


> [!IMPORTANT]  
> Non è possibile aggiungere altri server a un pool di server Chat persistente avviato come distribuzione a server singolo in Generatore di topologie. È consigliabile utilizzare la topologia del pool a più server, anche se si utilizza un server singolo. In questo modo sarà possibile aggiungere altri server in un secondo momento, se necessario. 


</div>

Nella figura seguente vengono illustrati tutti i componenti obbligatori e facoltativi di una topologia per un singolo server front-end di Persistent Chat Server con conformità.

**Singolo server Persistent Chat**

![Topologia a server singolo con servizio di conformità](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Topologia a server singolo con servizio di conformità")

</div>

<div>

## <a name="multiple-server-topology"></a>Topologia a più server

Per garantire maggiore capacità e affidabilità, è possibile distribuire una topologia a più server, come descritto in [Planning for Persistent Chat Server in Lync server 2013](lync-server-2013-planning-for-persistent-chat-server.md). La topologia a più server può includere ben quattro computer attivi che eseguono il server Chat persistente (le configurazioni a disponibilità elevata e ripristino di emergenza consentiranno fino a otto, ma solo quattro possono essere attive e le restanti quattro in standby). Ogni server è in grado di supportare fino a 20.000 utenti simultanei, per un totale di 80.000 utenti simultanei connessi a un pool di server Chat persistente con 4 server. Una topologia a più server è identica alla topologia a server singolo, tranne per il fatto che più server ospitano il server Chat persistente e che possono aumentare la scalabilità verticale. Più computer che eseguono il server Chat persistente devono risiedere nello stesso dominio di servizi di dominio Active Directory come Lync Server e il servizio di conformità.

Nella figura seguente vengono illustrati tutti i componenti di una topologia a più server con più computer che eseguono il server Chat persistente, il servizio di conformità facoltativo e un database di conformità distinto.

**Più server Persistent Chat**

![Topologia a più server](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Topologia a più server")

In una distribuzione di server Chat persistente con quattro server, in cui 80.000 gli utenti possono essere contemporaneamente connessi a e utilizzando la chat persistente, il carico viene distribuito uniformemente a 20.000 utenti per server. Se un server non è disponibile, gli utenti che sono connessi a quel server perderanno l'accesso al server Chat persistente. Gli utenti disconnessi vengono automaticamente trasferiti ai server rimanenti fino a quando il server non disponibile non viene ripristinato. In base alla quantità di traffico di chat persistente sulla rete, il trasferimento può richiedere alcuni minuti o più. Poiché ognuno dei server rimanenti può ospitare fino a 30.000 utenti, è consigliabile ripristinare il server non disponibile il più velocemente possibile per evitare problemi di prestazioni. In caso contrario, è possibile rendere disponibile un altro server Chat persistente mediante il generatore di topologie o il cmdlet di Windows PowerShell, **Set-CsPersistentChatActiveServer**.

</div>

</div>

<div>

## <a name="persistent-chat-server-capacity-planning"></a>Pianificazione della capacità del server Chat persistente

Nelle tabelle seguenti è possibile ottenere informazioni sulla pianificazione della capacità per il server Chat persistente. Modellano la modalità di modifica delle varie impostazioni del server Chat persistente sulle funzionalità di capacità.

<div>

## <a name="planning-your-maximum-capacity-for-persistent-chat-server"></a>Pianificazione della capacità massima per il server Chat persistente

Utilizzare la tabella di esempio seguente per determinare il numero di utenti che sarà possibile supportare.

### <a name="persistent-chat-server-pool-maximum-capacity-sample"></a>Esempio di capacità massima del pool di server Chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Istanze del servizio Persistent Chat attiva</p></td>
<td><p><em>4</em></p></td>
</tr>
<tr class="even">
<td><p>Istanze del servizio chat persistente</p></td>
<td><p><em>8 (4 deve essere inattivo, solo un massimo di 4 può essere attivo)</em></p></td>
</tr>
<tr class="odd">
<td><p>Utenti attivi connessi</p></td>
<td><p><em>80,000</em></p></td>
</tr>
<tr class="even">
<td><p>Totale utenti di cui è stato effettuato il provisioning</p></td>
<td><p>150.000</p></td>
</tr>
<tr class="odd">
<td><p>Numero di endpoint</p></td>
<td><p>120.000</p></td>
</tr>
</tbody>
</table>


Nell'esempio precedente, il piano consiste nel supportare il numero massimo di utenti consentiti dal server Chat persistente: quattro server/istanze del servizio chat persistente (possono avere quattro server più passivi che eseguono il server Chat persistente per la disponibilità elevata e il ripristino di emergenza) e 20.000 utenti per server, per un totale di 80.000 utenti attivi.

</div>

<div>

## <a name="capacity-planning-for-managing-persistent-chat-room-access"></a>Pianificazione della capacità per la gestione dell'accesso alle chat room persistente

La tabella di esempio seguente può essere utile per pianificare la gestione dell'accesso alle chat permanenti in un pool di server Chat persistente.

### <a name="managing-chat-room-access-sample"></a>Esempio di gestione dell'accesso alle chat

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
<th>Chat di piccole dimensioni</th>
<th>Chat room di medie dimensioni</th>
<th>Chat di grandi dimensioni</th>
<th>Totale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimensioni delle chat room (numero di utenti connessi)</p></td>
<td><p>30 per stanza</p></td>
<td><p>150 per camera</p></td>
<td><p>16.000 per camera</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chat</p></td>
<td><p>32.000</p></td>
<td><p>1.067</p></td>
<td><p>10 </p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>% delle sale che sono Auditorium</p></td>
<td><p>1%</p></td>
<td><p>1%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>% di sale aperte</p></td>
<td><p>3%</p></td>
<td><p>3%</p></td>
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
<td><p>Sale non aperte (sale normali con appartenenza esplicita)</p></td>
<td><p>31.040</p></td>
<td><p>1,035</p></td>
<td><p>5</p></td>
<td><p>32.080</p></td>
</tr>
<tr class="odd">
<td><p>Sale Auditorium (ingresso altri relatori)</p></td>
<td><p>0</p></td>
<td><p>32</p></td>
<td><p>5</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Sale gestite dall'appartenenza diretta</p></td>
<td><p>50%</p></td>
<td><p>10%</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Chat gestite per gruppi di utenti</p></td>
<td><p>50%</p></td>
<td><p>90%</p></td>
<td><p>100%</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le sale aperte (non specificato in modo esplicito)</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td><p>0</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti nell'elenco di appartenenza di ogni chat room per le stanze non aperte</p></td>
<td><p>30</p></td>
<td><p>150</p></td>
<td><p>16.000</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gruppi di utenti nell'elenco di appartenenza di ogni chat room per le stanze non aperte</p></td>
<td><p>3</p></td>
<td><p>5</p></td>
<td><p>10 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Users and User Groups nell'elenco Manager di ogni chat room (per le sale aperte e non aperte)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gli utenti e i gruppi di utenti nell'elenco dei relatori di ogni sala chat dell'Auditorium (per le sale aperte e non aperte)</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entità di appartenenza basate sull'utente in tutte le sale non aperte</p></td>
<td><p>465.600</p></td>
<td><p>15.520</p></td>
<td><p>-</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entità di appartenenza basate sui gruppi di utenti in tutte le sale non aperte</p></td>
<td><p>46.560</p></td>
<td><p>4656</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti e gruppi utenti basati su entità in tutte le chat room di Auditorium</p></td>
<td><p>0</p></td>
<td><p>192</p></td>
<td><p>50</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gli utenti e i gruppi di utenti basati su entità Manager in tutti gli elenchi di gestione delle chat room</p></td>
<td><p>192.000</p></td>
<td><p>6.400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti attivi per chat</p></td>
<td><p><em>30</em></p></td>
<td><p><em>150</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chat per utente</p></td>
<td><p><em>12</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>2</em></p></td>
<td><p><em>16</em></p></td>
</tr>
<tr class="odd">
<td><p>Gruppi di utenti in ogni elenco di membri di una chat</p></td>
<td><p><em>10</em></p></td>
<td><p><em>10</em></p></td>
<td><p><em>15</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Chat gestite per gruppi di utenti</p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td><p><em>50%</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Entità di appartenenza basata sui gruppi di utenti in tutte le chat</p></td>
<td><p>155.200</p></td>
<td><p>5173</p></td>
<td><p>68</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Entità di appartenenza basata sugli utenti in tutte le chat</p></td>
<td><p>465.600</p></td>
<td><p>77.600</p></td>
<td><p>72.000</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Utenti e gruppi di utenti in ogni elenco dei gestori delle chat, dei relatori delle chat e degli ambiti</p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td><p>6 </p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Gli utenti e i gruppi di utenti di tutte le chat room ' Manager, relatore e gli elenchi di ambiti</p></td>
<td><p>192.000</p></td>
<td><p>6400</p></td>
<td><p>60</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Voci di controllo di accesso</p></td>
<td><p>704.160</p></td>
<td><p>26.768</p></td>
<td><p>160</p></td>
<td><p>731.088</p></td>
</tr>
<tr class="even">
<td><p>Voci di controllo di accesso massime</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 milioni</p></td>
</tr>
</tbody>
</table>


Nell'esempio precedente, quando si distribuiscono i server Chat persistente in base alle linee guida consigliate, è possibile gestire fino a 80.000 utenti attivi in un pool di quattro server con conformità abilitata.

In questo esempio vengono illustrate le chat room categorizzate come piccole (30 utenti attivi in un determinato momento), medie (150 utenti attivi) e grandi (16.000 utenti attivi). Il numero di chat di una determinata dimensione viene calcolato in base al numero totale di:

  - Utenti attivi nel sistema

  - Utenti attivi nelle chat delle dimensioni specificate

  - Chat delle dimensioni specificate cui partecipa ogni singole utente

Per ogni chat room, la tabella di pianificazione della capacità precedente specifica il numero di voci di controllo di accesso associate alla chat room, incluse le voci che vengono assegnate direttamente alla chat room. È possibile controllare l'accesso a singole chat tramite elenchi di controllo di accesso. È inoltre possibile controllare l'accesso a livello di categoria. In un ACL, una singola voce di controllo di accesso può essere un gruppo di utenti, ad esempio un gruppo di sicurezza, una lista di distribuzione o un singolo utente. È possibile definire voci di controllo di accesso per gestori, relatori e membri delle chat.

<div>


> [!IMPORTANT]  
> Nella pianificazione della strategia per la gestione delle chat room, tenere presente che il numero totale di voci di controllo di accesso consentito è 2 milioni. Se le voci di controllo di accesso calcolate superano 2 milioni, le prestazioni del server potrebbero peggiorare significativamente. Per evitare questo problema, quando possibile, assicurarsi che le voci di controllo di accesso siano gruppi di utenti anziché singoli.



</div>

</div>

<div>

## <a name="capacity-planning-for-managing-chat-room-access-by-invitation"></a>Pianificazione della capacità per la gestione dell'accesso alle chat in base a invito

È possibile utilizzare la seguente tabella di pianificazione della capacità per comprendere il numero di inviti che il server Chat persistente crea e archivia nel database di Persistent Chat quando è configurato per l'invio di inviti. È possibile gestire gli inviti per la categoria utilizzando la pagina **Impostazioni categoria chat room** nel pannello di controllo di Lync Server o utilizzando il cmdlet di Windows PowerShell, **set-csPersistentChatCategory**. È possibile gestire gli inviti in una chat room (in linea con la categoria consentita) utilizzando la pagina **gestione sala** avviata dal client Lync o utilizzando un cmdlet di Windows PowerShell, **set-csPersistentChatRoom**.

I dati di esempio riportati nella tabella seguente presuppongono che, nella pagina **Impostazioni chat room** per il 50% di tutte le chat room, l'opzione **inviti** è impostata su **Sì**.

<div>


> [!IMPORTANT]  
> Se il valore calcolato per il numero di inviti generati dal server supera 1 milione, le prestazioni del server potrebbero peggiorare significativamente. Per evitare questo problema, accertarsi di ridurre al minimo il numero di chat configurate per l'invio di inviti o limitare il numero di utenti che possono partecipare alle chat room configurate per l'invio di inviti.



</div>

### <a name="chat-room-access-by-invitation-sample"></a>Esempio di accesso alle chat in base a invito

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
<th>Chat di piccole dimensioni</th>
<th>Chat room di medie dimensioni</th>
<th>Chat di grandi dimensioni</th>
<th>Totale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Utenti che possono accedere a chat room</p></td>
<td><p>30 per stanza</p></td>
<td><p>150 per camera</p></td>
<td><p>16.000 per camera</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Percentuale di stanze con inviti</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td><p>50%</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Chat configurate per l'invio di inviti</p></td>
<td><p><em>16.000</em></p></td>
<td><p><em>533</em></p></td>
<td><p><em>5</em></p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Utenti che possono accedere alla chat</p></td>
<td><p><em>60</em></p></td>
<td><p><em>225</em></p></td>
<td><p><em>16.000</em></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Inviti generati dal server Chat persistente</p></td>
<td><p>960.000</p></td>
<td><p>120.000</p></td>
<td><p>80,000</p></td>
<td><p>1.160.000</p></td>
</tr>
<tr class="even">
<td><p>Numero massimo consentito di inviti</p></td>
<td></td>
<td></td>
<td></td>
<td><p>2 milioni</p></td>
</tr>
<tr class="odd">
<td><p>Modello 1-iniziare con il numero previsto di messaggi per stanza al giorno</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Frequenza chat per camera (al giorno)</p></td>
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
<td><p>Modello 2-iniziare con il numero di messaggi inviati per utente al giorno</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Frequenza di chat per utente al giorno</p></td>
<td><p>15 </p></td>
<td><p>5</p></td>
<td><p>0,1</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Frequenza chat per camera (al giorno)</p></td>
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

## <a name="persistent-chat-server-performance-user-model"></a>Modello utente per le prestazioni del server Chat persistente

Nella tabella seguente viene descritto il modello utente per il server Chat persistente. Fornisce la base per i requisiti di pianificazione della capacità e rappresenta un'organizzazione tipica con 80.000 utenti simultanei su quattro server.

### <a name="persistent-chat-server-performance-user-model"></a>Modello utente per le prestazioni del server Chat persistente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Numero di utenti attivi connessi</p></td>
<td><p>80,000</p></td>
</tr>
<tr class="even">
<td><p>Numero di istanze del servizio del server Chat persistente</p></td>
<td><p>4</p></td>
</tr>
<tr class="odd">
<td><p>Numero di utenti di chat di piccole dimensioni</p></td>
<td><p>30 utenti</p></td>
</tr>
<tr class="even">
<td><p>Numero di utenti di chat di medie dimensioni</p></td>
<td><p>150 utenti</p></td>
</tr>
<tr class="odd">
<td><p>Numero di utenti di chat di grandi dimensioni</p></td>
<td><p>16.000 utenti</p></td>
</tr>
<tr class="even">
<td><p>Numero totale di chat</p></td>
<td><p>33.077</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat di piccole dimensioni</p></td>
<td><p>32.000</p></td>
</tr>
<tr class="even">
<td><p>Numero di chat di medie dimensioni</p></td>
<td><p>1.067</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat di grandi dimensioni</p></td>
<td><p>10 </p></td>
</tr>
<tr class="even">
<td><p>Numero totale di chat per utente</p></td>
<td><p>16 </p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat di piccole dimensioni per utente</p></td>
<td><p>12</p></td>
</tr>
<tr class="even">
<td><p>Numero di chat di medie dimensioni per utente</p></td>
<td><p>2</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chat di grandi dimensioni per utente</p></td>
<td><p>2</p></td>
</tr>
<tr class="even">
<td><p>Numero di sale Unite per utente</p></td>
<td><p>24</p></td>
</tr>
<tr class="odd">
<td><p>Frequenza di partecipazione di punta</p></td>
<td><p>10/secondo</p></td>
</tr>
<tr class="even">
<td><p>Frequenza di chat totale</p></td>
<td><p>24/secondo</p></td>
</tr>
<tr class="odd">
<td><p>Frequenza di chat per chat di piccole dimensioni</p></td>
<td><p>22.22/secondo</p></td>
</tr>
<tr class="even">
<td><p>Frequenza di chat per chat di medie dimensioni</p></td>
<td><p>1.67/secondo</p></td>
</tr>
<tr class="odd">
<td><p>Frequenza di chat per chat di grandi dimensioni</p></td>
<td><p>~ 0.15/Second</p></td>
</tr>
<tr class="even">
<td><p>Percentuale di chat configurate per l'invio di inviti</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Percentuale di appartenenza diretta</p></td>
<td><p>50%</p></td>
</tr>
<tr class="even">
<td><p>Percentuale di appartenenza a gruppi</p></td>
<td><p>50%</p></td>
</tr>
<tr class="odd">
<td><p>Numero medio di affiliazioni degli antenati in servizi di dominio Active Directory</p></td>
<td><p>100 - 200</p></td>
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
<td><p>2,25 (50% per 1 sala e 50% per 2 sale); Fino a 6 sale aperte, una per ogni monitor</p></td>
</tr>
<tr class="even">
<td><p>Numero di partecipanti sottoposti a polling per intervallo</p></td>
<td><p>25 per chat room visibile</p></td>
</tr>
<tr class="odd">
<td><p>Durata dell'intervallo di polling</p></td>
<td><p>5 minuti</p></td>
</tr>
<tr class="even">
<td><p>Numero di partecipanti sottoposti a polling al secondo</p></td>
<td><p>15.000</p></td>
</tr>
<tr class="odd">
<td><p>Numero di modifiche delle informazioni sulla presenza all'ora per utente</p></td>
<td><p>6 </p></td>
</tr>
<tr class="even">
<td><p>Numero di modifiche delle informazioni sulla presenza al secondo</p></td>
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

