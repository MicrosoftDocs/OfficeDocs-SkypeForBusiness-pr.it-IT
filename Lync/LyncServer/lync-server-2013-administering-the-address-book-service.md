---
title: 'Lync Server 2013: amministrazione del servizio Rubrica'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45dbc2c71cf34515f8f6176e4f579e6683ad319e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146259"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Amministrazione del servizio Rubrica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-05_

Come parte della distribuzione di Lync Server, Enterprise Edition o il server Standard Edition, il servizio Rubrica è installato per impostazione predefinita. Il database utilizzato dal servizio Rubrica – RTCab – viene creato in SQL Server (per Enterprise Edition, questo è il server SQL back-end, per il server Standard Edition, il server SQL collocato).

<div>


> [!NOTE]  
> Per informazioni sull'utilizzo di <STRONG>ADSI Edit</STRONG> per modificare gli attributi degli oggetti di servizi di dominio Active Directory, vedere <A href="https://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Per informazioni su uno strumento nel Resource Kit specifico per il servizio Rubrica, vedere <A href="https://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalizzazione dei numeri di telefono del server della Rubrica

Lync Server richiede numeri di telefono RFC 3966/E. 164 standardizzati. Per utilizzare numeri di telefono non strutturati o formattati in modo incoerente, Lync Server si basa sul server della Rubrica per preelaborare i numeri di telefono prima di essere trasportati alle regole di normalizzazione. Quando viene utilizzato un numero di telefono dalla Rubrica e viene applicata la regola di normalizzazione, i client, ad esempio Lync Phone Edition e Lync mobile, possono utilizzare questi numeri normalizzati.

Le regole di normalizzazione utilizzate nelle versioni precedenti potrebbero non funzionare correttamente senza alcune modifiche. Poiché gli spazi vuoti e i caratteri non obbligatori vengono rimossi prima delle regole di normalizzazione, se l'espressione regex cerca in modo specifico un trattino o un altro carattere che è stato rimosso, la regola di normalizzazione potrebbe non riuscire. È opportuno esaminare le regole di normalizzazione per garantire che non cerchino questi caratteri non obbligatori o che un errore della regola non impedisca la continuazione nel caso in cui il carattere non sia presente dove previsto dalla regola stessa.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>User Replicator e server della Rubrica

Il server della Rubrica utilizza i dati forniti da User Replicator per aggiornare le informazioni ottenute inizialmente dall'elenco indirizzi globale. User Replicator scrive gli attributi dei servizi di dominio Active Directory per ogni utente, contatto e gruppo nella tabella AbUserEntry del database e il server della rubrica sincronizza i dati degli utenti dal database in file nell'archivio file del server della Rubrica e nel database della rubrica RTCab. Lo schema per la tabella AbUserEntry prevede l'utilizzo di due colonne, **UserGuid** e **UserData**. **UserGuid** è la colonna di indice e contiene il GUID a 16 byte dell'oggetto Active Directory. **UserData** è una colonna di tipo immagine che contiene tutti gli attributi di servizi di dominio Active Directory descritti in precedenza per il contatto.

User Replicator determina quali attributi di Active Directory scrivere leggendo una tabella di configurazione che si trova nella stessa istanza basata su SQL Server della tabella AbUserEntry. La tabella AbAttribute contiene tre colonne, **ID**, **Name**, **Flags** e **Enable**. La tabella viene creata durante l'impostazione del database. Se la tabella AbAttribute è vuota,User Replicator ignora la logica di elaborazione della tabella AbUserEntry. Gli attributi del server della Rubrica sono dinamici e vengono recuperati dalla tabella AbAttribute, che viene inizialmente scritta dal server della Rubrica quando questo viene attivato.

L'attivazione del server rubrica inserisce nella tabella AbAttribute i valori riportati nella tabella seguente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Name</th>
<th>Bandiere</th>
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
<td><p>6 </p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7 </p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8 </p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9 </p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10 </p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11 </p></td>
<td><p>Cellulare</p></td>
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
<td><p>14 </p></td>
<td><p>Posta</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15 </p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16 </p></td>
<td><p>Reparto</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17 </p></td>
<td><p>Descrizione</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18 </p></td>
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


I numeri nella colonna **ID** devono essere univoci e non devono mai essere riutilizzati. Inoltre, mantenendo i valori ID inferiori a 256, si risparmia spazio nei file di output scritti dal server della Rubrica. Tuttavia, il valore ID massimo è 65535. La colonna **Name** corrisponde al nome di attributo di Active Directory che User Replicator deve inserire nella tabella AbUserEntry per ogni contatto. Il valore nella colonna **Flags** è utilizzato per definire il tipo di attributo. I tipi seguenti di attributi del server della Rubrica sono riconosciuti da User Replicator, indicati dal bit basso del valore nella colonna **Flags**.


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
<td><p>Attributo stringa. Questo tipo viene convertito da User Replicator in formato UTF-8 prima dell'archiviazione nella tabella AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Attributo binario. Viene archiviato da User Replicator nell'oggetto blob senza alcuna conversione.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia &quot;con Tel&quot;:. È utilizzato principalmente per attributi stringa multivalore, in particolare <strong>proxyAddresses</strong>. In questo caso, il server della Rubrica è interessato solo alle voci di <strong>proxyAddresses</strong> che &quot;iniziano con&quot;Tel:. Pertanto, nell'interesse di risparmiare spazio, User Replicator archivia solo le voci che iniziano con &quot;Tel:.&quot;</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Attributo stringa booleano. Se l'impostazione è TRUE, il contatto non viene incluso da User Replicator nella tabella AbUserEntry. Se l'impostazione è FALSE, gli attributi per il contatto vengono inclusi da User Replicator nella tabella AbUserEntry, ad eccezione dell'attributo specifico con questo flag. Si tratta di un altro tipo di caso speciale utilizzato principalmente per l'attributo <strong>msExchHideFromAddressLists</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia &quot;con SMTP&quot; : e include &quot; @ &quot; il simbolo.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Un attributo stringa, ma è incluso solo se il valore dell'attributo inizia con &quot;Tel:&quot; o &quot;SMTP:&quot; e include il &quot; @ &quot; simbolo.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>Se impostato, si tratta di un attributo multivalore che può essere presente più volte per ogni contatto.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Se impostato, identifica l'attributo del nome account utente di posta elettronica per un contatto. Questo flag viene utilizzato dal server della Rubrica per identificare il valore di attributo da visualizzare nella voce del registro eventi di normalizzazione del telefono.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Se impostato, identifica un attributo obbligatorio per un contatto. Il server della Rubrica include un utente nella tabella AbUserEntry solo se è presente un valore per questo attributo in Active Directory. Se sono presenti più attributi obbligatori, è necessario che solo uno di essi disponga di un valore per includere l'utente nella tabella AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>Se impostato, il valore di questo attributo viene sempre normalizzato dal server della Rubrica.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>Se impostato, il server della Rubrica utilizza il numero normalizzato di <strong>proxyAddresses</strong>, se l'impostazione CMS di <strong>UseNormalizationRules</strong> è FALSE; in caso contrario, il comportamento corrisponde a quello che si verifica quando il bit di flag è 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se impostato, il server della Rubrica non include nella tabella AbUserEntry oggetti con questo valore per l'attributo specificato. Se, ad esempio, per l'attributo <strong>msRTCSIP-PrimaryUserAddress</strong> è impostato questo bit di flag, i contatti con questo attributo non vengono scritti nel database.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se impostato, il server della Rubrica non include nella tabella AbUserEntry oggetti che non hanno questo valore per l'attributo specificato. Se entrambi i bit di flag 0x4000 e 0x8000 sono impostati in un oggetto, l'attributo con il valore del bit di flag impostato su 0x4000 ha la precedenza e l'oggetto viene escluso dalla tabella AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Se impostato, rappresenta un oggetto gruppo. Questo bit di flag viene utilizzato da User Replicator per includere i contatti con l'attributo <strong>groupType</strong>, la cui presenza indica un gruppo (ad esempio, una lista di distribuzione o un gruppo di sicurezza).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>Se impostato, questo bit di flag viene utilizzato da User Replicator per includere questo attributo nei file del server della Rubrica specifici del dispositivo, ovvero file con estensione dabs.</p></td>
</tr>
</tbody>
</table>


Nelle versioni precedenti di Lync Server, quando si applicava una modifica ad Active Directory, l'amministratore sarebbe stato tenuto a eseguire i cmdlet **Update-CSUserDatabase** e **Update-CSAddressBook** di Windows PowerShell per rendere permanenti le modifiche apportate al database utente di Lync Server e al database di RTCab. In Lync Server 2013, Lync Server User Replicator rileverà le modifiche da Active Directory e aggiornerà il database degli utenti di Lync Server in base a un intervallo configurato. Lync Server User Replicator propagherà rapidamente le modifiche apportate al database di RTCab senza che l'amministratore debba eseguire Update-CSAddressBook. Se la query Web della Rubrica è abilitata, le modifiche verranno applicate ai risultati della ricerca da parte dei client Lync. Gli amministratori devono solo eseguire Update-CSAddressBook se il download dei file della Rubrica è abilitato.

<div>


> [!NOTE]  
> Per impostazione predefinita, Lync Server User Replicator viene eseguito automaticamente ogni 5 minuti. È possibile configurare questo intervallo utilizzando set-CSUserReplicatorConfiguration-ReplicationCycleInterval &lt; &gt;.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtro della Rubrica

Gli utenti inseriti nei file del server della rubrica possono essere controllati in base a determinati attributi di servizi di dominio Active Directory elencati nella tabella AbAttribute. Uno di questi attributi utilizzato per il filtro è **msExchangeHideFromAddressBook **. Si tratta di un attributo utente aggiunto dallo schema di Exchange. Se il valore di questo attributo è TRUE, questo attributo viene utilizzato da Exchange Server per nascondere il contatto dall'elenco indirizzi globale di Outlook. Analogamente, se il valore di questo attributo è TRUE, tale utente non viene incluso da User Replicator nella tabella AbUserEntry e l'utente non sarà presente nei file del server della Rubrica.

È possibile utilizzare alcuni bit di flag per definire un filtro da utilizzare per gli attributi del server della Rubrica. La presenza di alcuni bit di flag consente, ad esempio, di identificare un attributo come attributo di inclusione o di esclusione. User Replicator consente di escludere tramite filtro i contatti che contengono un attributo di esclusione e quelli che non contengono un attributo di inclusione.

<div>


> [!WARNING]  
> Per ulteriori informazioni sul filtraggio della Rubrica, vedere <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlet del server della Rubrica in Lync server 2013</A>e <A href="https://go.microsoft.com/fwlink/?linkid=330430">filtrare la rubrica di Lync 2013</A>



</div>

Attualmente, sono disponibili tre diversi filtri, elencati nella tabella seguente.


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
<td><p>Se impostato, identifica un attributo obbligatorio per un contatto. Questo bit di flag viene utilizzato da User Replicator per escludere tramite filtro i contatti che non includono almeno un attributo obbligatorio. OuPathId è un attributo obbligatorio, che è sempre impostato. È pertanto necessario che sia impostato almeno un altro degli attributi obbligatori. In caso contrario, il contatto (ovvero con il valore dell'attributo obbligatorio OuPathId) non sarà scritto nel database. Se, ad esempio, <strong>telephoneNumber</strong> e <strong>homePhone</strong> sono definiti come attributi obbligatori, solo i contatti che dispongono di almeno uno di questi attributi vengono scritti nel database.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Se impostato, identifica un attributo di esclusione. Questo bit di flag viene utilizzato da User Replicator per escludere tramite filtro i contatti che contengono questo attributo. Se, ad esempio, <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo di esclusione, i contatti che dispongono di questo attributo non vengono scritti nel database.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Se impostato, identifica un attributo di inclusione. Questo bit di flag viene utilizzato da User Replicator per escludere tramite filtro i contatti che non contengono questo attributo. Se, ad esempio, <strong>msRTCSIP-PrimaryUserAddress</strong> è definito come attributo di inclusione, solo i contatti che dispongono di questo attributo vengono scritti nel database.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Se vengono impostati entrambi i bit di flag, 0x4000 (attributo di esclusione) e 0x8000 (attributo di inclusione), il bit 0x4000 ha la precedenza su 0x8000 e il contatto viene escluso.



</div>

Sebbene sia possibile filtrare la Rubrica per includere solo determinati utenti, la limitazione delle voci non implica una limitazione della possibilità da parte di altri utenti di contattare gli utenti esclusi tramite filtro o di visualizzare il loro stato presenza. Gli utenti possono sempre trovare gli utenti non inclusi nella Rubrica, inviare loro manualmente messaggi istantanei o avviare manualmente chiamate verso tali utenti, immettendo il nome di accesso completo dell'utente. Le informazioni sul contatto per un utente sono inoltre disponibili anche in Outlook.

Anche se i record dei contatti completi nei file della rubrica consentono di utilizzare Lync Server per avviare messaggi di posta elettronica, telefonici o VoIP aziendale (ovvero se VoIP aziendale è abilitato sul server) con gli utenti non configurati per l'avvio della sessione Protocol (SIP), alcune organizzazioni preferiscono includere solo gli utenti abilitati per SIP nelle voci del server della Rubrica. È possibile filtrare la Rubrica per includere solo gli utenti abilitati per SIP cancellando il bit 0x800 nella colonna **Flags** per gli attributi obbligatori seguenti: **mailNickname**, **telephoneNumber**, **homePhone** e **mobile**. È inoltre possibile filtrare la Rubrica per includere solo utenti abilitati per SIP impostando 0x8000 (attributo di inclusione) nella colonna **Flags** dell'attributo **msRTCSIP-PrimaryUserAddress**. In questo modo vengono inoltre esclusi gli account del servizio dai file della Rubrica.

Dopo aver modificato la tabella AbAttribute, è possibile aggiornare i dati nella tabella AbUserEntry eseguendo il cmdlet **Update-CsUserDatabase**. Al termine della replica di User Replicator, è possibile aggiornare il file dell'archivio file del server della Rubrica eseguendo manualmente il cmdlet **UpdateCsAddressBook**.

<div>


> [!NOTE]  
> Il front end server che il server della Rubrica è posizionato non è configurabile amministrativamente. Uno viene scelto durante la distribuzione, in genere il primo front end server distribuito. In caso di errore, il servizio Rubrica verrà spostato in un altro front end server e non richiede alcuna attenzione amministrativa.



</div>

<div>


> [!IMPORTANT]  
> Se l'infrastruttura è stata consolidata o modificata in altro modo da una distribuzione a più foreste o da una distribuzione padre/figlio, ad esempio il consolidamento dell'infrastruttura prima di passare a Lync Server, potrebbe essere possibile che il download del servizio Rubrica e la query Web della Rubrica non siano in grado di soddisfare alcuni utenti. In una distribuzione con più domini o foreste, l'attributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> viene popolato negli oggetti utente in cui si presenta il problema. Per risolvere il problema, l'attributo <STRONG>MsRTCSIP-OriginatorSid</STRONG> deve essere impostato su NULL in questi oggetti.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

