---
title: 'Lync Server 2013: gestione delle posizioni per i gateway ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing locations for ELIN gateways
ms:assetid: ced79c13-4e7e-4034-95cd-6fc913f4f222
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205288(v=OCS.15)
ms:contentKeyID: 48185496
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88b27e325ba8990cf239548c689d4e021397858a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185619"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Gestione delle posizioni per i gateway ELIN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-02_

Affinché Lync Server fornisca automaticamente le posizioni per i client all'interno di una rete, è necessario eseguire le attività seguenti:

  - Popolare il database del servizio informazioni percorso con un wiremap di rete e includere i numeri di identificazione delle posizioni di emergenza (ELIN) nel campo CompanyName.

  - Pubblicare le posizioni in modo che siamo disponibili per i client nella rete.

  - Caricare i numeri ELIN nel database ALI (Automatic Location Identification) del gestore della rete PSTN (Public Switched Telephone Network).

Per informazioni dettagliate su come eseguire queste attività, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> I percorsi aggiunti al database delle posizioni centrali non sono disponibili per il client finché non sono stati pubblicati utilizzando un comando di Lync Server Management Shell e vengono replicati negli archivi locali del pool. Per ulteriori informazioni, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database delle posizioni da Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

In questa sezione vengono descritti gli aspetti da prendere in considerazione quando si pianificano l'aggiornamento e la gestione del database delle posizioni.

<div>

## <a name="planning-emergency-locations"></a>Pianificazione delle posizioni di emergenza

Quando si utilizzano i gateway ELIN, è possibile popolare il database del servizio informazioni percorso con l'indirizzo civico, una posizione specifica all'interno di un edificio e almeno un ELIN per ogni percorso. Durante la fase di pianificazione, è opportuno decidere come denominare le posizioni e come assegnare i numeri ELIN.

<div>

## <a name="planning-location-names"></a>Pianificazione dei nomi delle posizioni

Il campo percorso servizio **informazioni percorso,** che conserva la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). Tentare di includere gli elementi seguenti rispettando questi limiti di lunghezza:

  - Un nome di facile comprensione che identifichi la posizione del chiamante del servizio di emergenza (911), per consentire agli addetti del servizio di emergenza di trovare immediatamente la posizione specifica quando si recano all'indirizzo civico. Questo nome di posizione può includere il numero di edificio, l'indicazione della scala, il numero del piano, il numero di porta e così via. Evitare nomi alternativi noti solo ai dipendenti, altrimenti si rischia che gli addetti del servizio di emergenza si rechino nel luogo sbagliato.

  - Un identificatore di posizione che consenta agli utenti di verificare facilmente che il proprio client Lync abbia selezionato la posizione corretta. Il client Lync concatena e visualizza automaticamente i campi **Location** e **City** rilevati nell'intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo civico dell'edificio a ogni identificatore di posizione (ad esempio, "numero \<\>civico del primo piano"). Se non viene specificato l'indirizzo, un identificatore di posizione generico come "1° piano" potrebbe riferirsi a qualsiasi edificio della città.

  - Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è consigliabile aggiungere la parola Near Near, ad esempio "Near 1° piano 1234".

</div>

<div>

## <a name="planning-elins"></a>Pianificazione dei numeri ELIN

Dopo aver stabilito come suddividere lo spazio dell'edificio in posizioni, è necessario decidere quanti numeri ELIN assegnare a ogni posizione. In un edificio a più piani o con più occupanti ad esempio è possibile assegnare alle diverse aree dell'edificio diverse zone di emergenza. In genere, ogni piano di un edificio viene designato come posizione. A ogni posizione vengono quindi assegnati uno o più numeri ELIN, utilizzati come numeri chiamanti durante una chiamata di emergenza. Contattare il gestore PSTN per conoscere i numeri di telefono che è possibile utilizzare come numeri ELIN. Nella tabella seguente sono illustrati alcuni esempi di posizioni per un indirizzo specifico.

### <a name="sample-location-and-elin-assignments"></a>Posizioni e assegnazioni di numeri ELIN di esempio

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Area dell'edificio</th>
<th>Posizione</th>
<th>ELIN</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Primo piano</p></td>
<td><p>1</p></td>
<td><p>425-555-0100</p></td>
</tr>
<tr class="even">
<td><p>Secondo piano</p></td>
<td><p>2</p></td>
<td><p>425-555-0111</p></td>
</tr>
<tr class="odd">
<td><p>Terzo piano</p></td>
<td><p>3</p></td>
<td><p>425-555-0123</p></td>
</tr>
</tbody>
</table>


Le posizioni definite devono soddisfare i requisiti seguenti:

  - Essere conformi alle disposizioni locali e nazionali/regionali in termini di area massima per posizione e numero di posizioni per indirizzo.

  - Essere sufficientemente specifiche da consentire di individuare senza difficoltà la persona che effettua la chiamata di emergenza.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Popolamento del database delle posizioni

Le considerazioni seguenti possono essere utili per determinare come verrà popolato il database delle posizioni.

  - **Valutare quale processo verrà utilizzato per popolare il database delle posizioni.**  
    Esaminare dove si trovano i dati e quali operazioni è necessario eseguire per convertirli nel formato richiesto dal database delle posizioni. Considerare inoltre se le posizioni verranno aggiunte singolarmente o in gruppo tramite un file CSV.

<!-- end list -->

  - **Valutare se si dispone di un database di terze parti contenente già un mapping di posizioni.**  
    Se si utilizza l'opzione servizio informazioni percorso secondario di Lync Server per la connessione a un database di terze parti, è possibile raggruppare e gestire percorsi tramite una piattaforma offline. Uno dei vantaggi di questo approccio è che le posizioni possono essere associate non solo a identificatori di rete, ma anche a un utente. Questo significa che il servizio informazioni percorso può restituire più indirizzi, provenienti dal servizio informazioni percorso secondario, a un client di Lync Server. L'utente può quindi scegliere la posizione più appropriata.
    
    Per l'integrazione con il servizio informazioni percorso, è necessario che il database di terze parti segua lo schema di richiesta/risposta percorso di Lync Server. Per informazioni dettagliate, <https://go.microsoft.com/fwlink/p/?linkid=213819>vedere. Per informazioni dettagliate sulla distribuzione di un servizio informazioni percorso secondario, vedere [Configure a Secondary Location Information Service in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sul popolamento del database delle posizioni, vedere [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Gestione del database delle posizioni

Dopo aver popolato il database delle posizioni, è necessario sviluppare una strategia per aggiornarlo in base alle modifiche di configurazione della rete. Le considerazioni seguenti possono essere utili per determinare come verrà gestito il database delle posizioni.

  - **Valutare come verrà aggiornato il database delle posizioni.**  
    Esistono diversi scenari che richiedono un aggiornamento del database delle posizioni, tra cui l'aggiunta di punti di accesso wireless, il ricablaggio degli uffici (con assegnazioni diverse dei commutatori) e l'espansione delle subnet. Considerare se si prevede di aggiornare direttamente ogni singola posizione o di eseguire un aggiornamento in blocco delle posizioni mediante un file CSV.

<!-- end list -->

  - **Considerare se verrà utilizzata un'applicazione SNMP per creare una corrispondenza tra gli indirizzi MAC dei client Lync e gli identificatori di porte e commutatori,**  
    Se si utilizza un'applicazione SNMP, è necessario sviluppare un processo manuale per mantenere la coerenza a livello di informazioni su porte e chassis dei commutatori tra l'applicazione SNMP e il database delle posizioni. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni percorso non sarà in grado di restituire un percorso al client.

</div>

</div>

<span> </span>

</div>

</div>

</div>

