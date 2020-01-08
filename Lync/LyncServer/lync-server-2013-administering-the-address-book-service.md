---
title: 'Lync Server 2013: amministrazione del servizio Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8acf59a898f8da14b9c5c4151728206cc501ceaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Amministrazione del servizio Rubrica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-05_

Come parte della distribuzione di Lync Server, Enterprise Edition o Standard Edition Server, il servizio Rubrica viene installato per impostazione predefinita. Il database usato dal servizio Rubrica-RTCab-viene creato in SQL Server (per Enterprise Edition, questo è il server SQL back-end; per il server Standard Edition, il server SQL collocato).

<div>


> [!NOTE]  
> Per informazioni sull'uso di <STRONG>ADSI Edit</STRONG> per modificare gli attributi degli oggetti dei servizi di dominio Active Directory, vedere <A href="http://go.microsoft.com/fwlink/?linkid=330427">Modifica ADSI</A>. Per informazioni su uno strumento nel Resource Kit specifico per il servizio Rubrica, vedere strumenti del <A href="http://go.microsoft.com/fwlink/?linkid=330429">Resource Kit di Microsoft Lync Server 2013</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalizzazione numero di telefono del server rubrica

Lync Server richiede numeri di telefono RFC 3966/E. 164 standardizzati. Per usare numeri di telefono non strutturati o formattati in modo incoerente, Lync Server si basa sul server della Rubrica per preelaborare i numeri di telefono prima che vengano consegnati alle regole di normalizzazione. Quando viene usato un numero di telefono dalla Rubrica e viene applicata la regola di normalizzazione, i client, ad esempio Lync Phone Edition e Lync mobile, possono usare questi numeri normalizzati.

Le regole di normalizzazione usate nelle versioni precedenti potrebbero non funzionare correttamente senza alcune modifiche. Poiché gli spazi vuoti e i caratteri non obbligatori vengono rimossi prima delle regole di normalizzazione, se l'espressione Regex Cerca specificamente un trattino o un altro carattere rimosso, la regola di normalizzazione potrebbe non riuscire. È necessario rivedere le regole di normalizzazione per verificare che non siano alla ricerca di questi caratteri non obbligatori oppure che la regola non venga eseguita correttamente e che il carattere non sia presente in cui la regola lo prevede.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Server di replica utenti e Rubrica

Il server rubrica usa i dati forniti da User Replicator per aggiornare le informazioni ottenute inizialmente dall'elenco indirizzi globale (GAL). User Replicator scrive gli attributi dei servizi di dominio Active Directory per ogni utente, contatto e gruppo nella tabella AbUserEntry del database e il server della rubrica sincronizza i dati utente del database in file nell'archivio file della Rubrica e nel database della rubrica RTCab. Lo schema per la tabella AbUserEntry usa due colonne, **UserGuid** e **UserData**. **UserGuid** è la colonna index e contiene il GUID a 16 byte dell'oggetto Active Directory. **UserData** è una colonna di immagini che contiene tutti gli attributi di servizi di dominio Active Directory menzionati in precedenza per il contatto.

User Replicator determina gli attributi di Active Directory da scrivere leggendo una tabella di configurazione situata nella stessa istanza basata su SQL Server della tabella AbUserEntry. La tabella AbAttribute contiene tre colonne, **ID**, **Name**, **Flags**e **Enable**. La tabella viene creata durante la configurazione del database. Se la tabella AbAttribute è vuota, User Replicator ignora la logica di elaborazione della tabella AbUserEntry. Gli attributi del server della Rubrica sono dinamici e vengono recuperati dalla tabella AbAttribute, che inizialmente viene scritta dal server della Rubrica quando il server della Rubrica viene attivato.

L'attivazione del server rubrica viene popolata dalla tabella AbAttribute con i valori visualizzati nella tabella seguente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Nome</th>
<th>Flag</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Titolo</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Società</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>Dispositivi mobili</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Posta</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Dipartimento</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17</p></td>
<td><p>Descrizione</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


I numeri nella colonna **ID** devono essere univoci e non devono mai essere riutilizzati. Inoltre, il mantenimento dei valori ID in 256 consente di risparmiare spazio nei file di output scritti dal server rubrica. Tuttavia, il valore ID massimo è 65535. La colonna **Name** corrisponde al nome dell'attributo Active Directory che User Replicator deve inserire nella tabella AbUserEntry per ogni contatto. Il valore nella colonna **Flags** viene usato per definire il tipo di attributo. I seguenti tipi di attributi del server della Rubrica sono riconosciuti da User Replicator, indicato dal byte basso del valore nella colonna **Contrassegni** .


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>Un attributo String. User Replicator converte questo tipo in UTF-8 prima di archiviarlo nella tabella AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Un attributo binario. User Replicator archivia questo contenuto nel BLOB senza alcuna conversione.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Un attributo String, ma è incluso solo se il valore dell'attributo inizia &quot;con Tel&quot;:. Questo vale principalmente per gli attributi di stringa multivalore, in particolare <strong>proxyAddresses</strong>. In questo caso, il server della Rubrica è interessato solo alle voci di <strong>proxyAddresses</strong> che &quot;iniziano con&quot;Tel:. Pertanto, nell'interesse del salvataggio dello spazio, User Replicator archivia solo le voci che iniziano con &quot;Tel:&quot;.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Un attributo stringa booleano, che se TRUE fa in modo che User Replicator non includa questo contatto nella tabella AbUserEntry. Se FALSE, fa sì che User Replicator includa gli attributi per il contatto nella tabella AbUserEntry, ma non l'attributo specifico con questo contrassegno. Si tratta di un altro tipo di caso speciale principalmente per l'attributo <strong>msExchHideFromAddressLists</strong> .</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia &quot;con SMTP&quot; : e include &quot; @ &quot; il simbolo.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Un attributo String, ma è incluso solo se il valore dell'attributo inizia con &quot;Tel:&quot; o &quot;SMTP:&quot; e include il &quot; @ &quot; simbolo.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Se impostato, si tratta di un attributo multivalore che può essere visualizzato più volte per ogni contatto.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Se impostato, identifica l'attributo del nome dell'account utente di posta elettronica per un contatto. Il server della rubrica usa questo contrassegno per identificare il valore di attributo da visualizzare nella voce del log eventi di normalizzazione del telefono.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Se impostato, identifica un attributo obbligatorio per un contatto. Il server rubrica include un utente nella tabella AbUserEntry solo se è presente un valore per questo attributo in Active Directory. Se è presente più di un attributo obbligatorio, è necessario che solo uno di essi abbia un valore per includere l'utente nella tabella AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Se impostato, il server della rubrica normalizza sempre il valore di questo attributo.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Se impostato, il server della rubrica usa il numero normalizzato di <strong>proxyAddresses</strong>, se l'impostazione di <strong>USENORMALIZATIONRULES</strong> CMS è falsa; in caso contrario, si comporta come quando il bit del contrassegno è 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se impostato, il server rubrica non include oggetti nella tabella AbUserEntry con questo valore per l'attributo specificato. Se ad esempio l'attributo <strong>msRTCSIP-PrimaryUserAddress</strong> è impostato su un bit di flag, i contatti che hanno questo attributo non vengono scritti nel database.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se impostato, il server rubrica non include oggetti nella tabella AbUserEntry che non hanno questo valore per l'attributo specificato. Se entrambi i bit del flag 0x4000 e 0x8000 sono impostati su un oggetto, l'attributo con il valore del bit di flag impostato su 0x4000 ha la precedenza e l'oggetto viene escluso dalla tabella AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Se impostato, rappresenta un oggetto Group. User Replicator usa questo bit di flag per includere i contatti con l'attributo <strong>GroupType</strong> la cui presenza indica un gruppo, ad esempio una lista di distribuzione o un gruppo di sicurezza.</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Se impostato, User Replicator usa questo bit di flag per includere questo attributo nei file del server della rubrica specifica del dispositivo, ovvero i file con estensione. DAB.</p></td>
</tr>
</tbody>
</table>


Nelle versioni precedenti di Lync Server, quando si applica una modifica a Active Directory, è necessario che l'amministratore esegua **Update-CSUserDatabase** e **Update-CSAddressBook** i cmdlet di Windows PowerShell per mantenere immediatamente la modifica al database utente di Lync Server e al database di RTCab. In Lync Server 2013 Lync Server User Replicator rileverà le modifiche da Active Directory e aggiornerà il database degli utenti di Lync Server in base a un intervallo configurato. Lync Server User Replicator propagherà rapidamente le modifiche al database di RTCab senza che l'amministratore debba eseguire Update-CSAddressBook. Se la query Web della Rubrica è abilitata, le modifiche verranno applicate ai risultati della ricerca da parte dei client Lync. Gli amministratori dovranno eseguire solo Update-CSAddressBook se è abilitato il download di file della Rubrica.

<div>


> [!NOTE]  
> Per impostazione predefinita, Lync Server User Replicator viene eseguito automaticamente ogni 5 minuti. Puoi configurare questo intervallo usando set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtrare la Rubrica

Gli utenti che popolano i file del server della rubrica possono essere controllati in base a determinati attributi di servizi di dominio Active Directory elencati nella tabella AbAttribute. Un attributo di questo tipo usato per filtrare è l'attributo **msExchangeHideFromAddressBook** . Questo è un attributo utente aggiunto dallo schema di Exchange. Se il valore di questo attributo è TRUE, Exchange Server usa questo attributo per nascondere il contatto dall'elenco indirizzi globale di Outlook. Allo stesso modo, se il valore di questo attributo è TRUE, User Replicator non include l'utente nella tabella AbUserEntry e l'utente non sarà presente nei file del server della Rubrica.

Puoi usare alcuni bit di flag per definire un filtro da usare negli attributi del server della Rubrica. Ad esempio, la presenza di alcuni bit di flag può identificare un attributo come attributo include o come attributo Exclude. User Replicator filtra i contatti che contengono un attributo Exclude e filtra i Contains che non contengono un attributo include.

<div>


> [!WARNING]  
> Per altre informazioni su come filtrare la Rubrica, vedere <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">cmdlet del server rubrica in Lync server 2013</A>e filtrare la <A href="http://go.microsoft.com/fwlink/?linkid=330430">rubrica di Lync 2013</A>



</div>

Attualmente esistono tre filtri diversi. Nella tabella seguente sono elencati questi filtri.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attributo</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Se impostato, identifica un attributo obbligatorio per un contatto. User Replicator usa questo bit di flag per filtrare i contatti che non contengono almeno un attributo obbligatorio. OuPathId è un attributo obbligatorio, che è sempre impostato. Quindi deve essere impostato almeno uno degli altri attributi obbligatori. In caso contrario, il contatto (ovvero, con il valore dell'attributo obbligatorio OuPathId) non verrà ancora scritto nel database. Se ad esempio <strong>telephoneNumber</strong> e <strong>HomePhone</strong> sono definiti come attributi obbligatori, nel database verranno scritti solo i contatti che hanno almeno uno di questi attributi.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se impostato, identifica un attributo Exclude. User Replicator usa questo bit di flag per filtrare i contatti che contengono questo attributo. Ad esempio, se <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo Exclude, i contatti che hanno questo attributo non vengono scritti nel database.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se impostato, identifica un attributo include. User Replicator usa questo bit di flag per filtrare i contatti che non contengono questo attributo. Ad esempio, se <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo include, nel database verranno scritti solo i contatti con questo attributo.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se sono impostati entrambi i bit di flag 0x4000 (Exclude Attribute) e 0x8000 (include Attribute), il bit 0x4000 esegue l'override del bit 0x8000 e il contatto viene escluso.



</div>

Anche se è possibile filtrare la Rubrica per includere solo determinati utenti, la limitazione delle voci non limita la possibilità di altri utenti di contattare gli utenti filtrati o di vederne lo stato presenza. Gli utenti possono sempre trovare, inviare manualmente messaggi istantanei o avviare manualmente le chiamate agli utenti non presenti nella rubrica immettendo il nome di accesso completo di un utente. Inoltre, le informazioni di contatto per un utente possono essere trovate anche in Outlook.

Pur avendo i record di contatto completo nei file della Rubrica, è possibile usare Lync Server per avviare la posta elettronica, il telefono o le chiamate vocali aziendali (ovvero, se Enterprise Voice è abilitato sul server) con utenti non configurati per l'avvio della sessione Protocol (SIP), alcune organizzazioni preferiscono includere solo gli utenti abilitati per SIP nelle voci del server rubrica. È possibile filtrare la Rubrica per includere solo gli utenti abilitati per SIP deselezionando il bit 0x800 nella colonna **Flags** degli attributi obbligatori seguenti: **mailNickname**, **telephoneNumber**, **HomePhone**e **mobile**. È anche possibile filtrare la Rubrica per includere solo gli utenti abilitati per SIP impostando 0x8000 (attributo include) nella colonna **Flags** dell'attributo **msRTCSIP-PrimaryUserAddress** . Questo consente inoltre di escludere gli account di servizio dai file della Rubrica.

Dopo aver modificato la tabella AbAttribute, è possibile aggiornare i dati nella tabella AbUserEntry eseguendo il comando **Update-CsUserDatabase** cmdlet. Dopo il completamento della replica UR, è possibile aggiornare il file nell'archivio file della rubrica eseguendo manualmente il comando **UpdateCsAddressBook** cmdlet.

<div>


> [!NOTE]  
> Il server front-end in cui è posizionato il server della Rubrica non è configurabile in termini amministrativi. Una viene scelta durante la distribuzione, in genere il primo server front-end distribuito. In caso di errore, il servizio Rubrica verrà spostato in un altro server front-end e non richiede alcuna attenzione amministrativa.



</div>

<div>


> [!IMPORTANT]  
> Se l'infrastruttura è stata consolidata o modificata in altro modo da una distribuzione a più foreste o da una distribuzione padre/figlio, ad esempio il consolidamento dell'infrastruttura prima di passare a Lync Server, è possibile che il download del servizio Rubrica e la query Web della Rubrica non siano disponibili per alcuni utenti. Quando si trova in una distribuzione con più domini o insiemi di foreste, l'attributo <STRONG>msRTCSIP-OriginatorSID</STRONG> viene popolato negli oggetti utente che presentano il problema. L'attributo <STRONG>msRTCSIP-OriginatorSID</STRONG> deve essere impostato su null per questi oggetti per risolvere il problema.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

