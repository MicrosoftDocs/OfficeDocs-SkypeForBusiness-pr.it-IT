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
ms.openlocfilehash: ba5a7e9067e4cd59ca42e60c620dbb4e8ee5b901
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762104"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-locations-for-elin-gateways-in-lync-server-2013"></a>Gestione delle posizioni per i gateway ELIN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-02_

Per consentire a Lync Server di specificare automaticamente le posizioni per i client all'interno di una rete, è necessario eseguire le attività seguenti:

  - Compilare il database del servizio informazioni sulla posizione con un wiremap di rete e includere i numeri di identificazione della posizione di emergenza (ELINs) nel campo CompanyName.

  - Pubblicare i percorsi in modo che siano disponibili per i client della rete.

  - Caricare il numero ELINs nel database di identificazione automatica della posizione del vettore (PSTN) del gestore della rete telefonica pubblica.

Per informazioni dettagliate su come eseguire queste attività, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

<div>


> [!NOTE]  
> I percorsi aggiunti al database della posizione centrale non sono disponibili per il client finché non sono stati pubblicati usando un comando Lync Server Management Shell e vengono replicati negli archivi locali del pool. Per informazioni dettagliate, vedere <A href="lync-server-2013-publish-the-location-database.md">pubblicare il database della posizione da Lync Server 2013</A> nella documentazione relativa alla distribuzione.



</div>

Questa sezione descrive le informazioni da considerare quando si prevede di aggiornare e gestire il database della posizione.

<div>

## <a name="planning-emergency-locations"></a>Pianificazione delle posizioni di emergenza

Quando si usano i gateway ELIN, si popola il database del servizio informazioni sulla posizione con l'indirizzo civico, una posizione specifica all'interno di un edificio e almeno un ELIN per ogni posizione. Durante la fase di pianificazione, è consigliabile decidere come assegnare un nome alle posizioni e come assegnarle.

<div>

## <a name="planning-location-names"></a>Pianificazione dei nomi delle posizioni

Il campo **percorso** del servizio informazioni posizione, che contiene la posizione specifica all'interno di un edificio, ha una lunghezza massima di 20 caratteri (inclusi gli spazi). In tale lunghezza limitata, provare a includere le operazioni seguenti:

  - Un nome di facile comprensione che identifica la posizione del chiamante di 911 per evitare che i soccorritori di emergenza trovino la posizione specifica subito quando arrivano all'indirizzo civico. Questo nome di posizione può includere un numero di edificio, un numero di piano, un designatore alare, un numero di camera e così via. Evitare i soprannomi noti solo ai dipendenti, in modo che i soccorritori di emergenza possano accedere alla posizione errata.

  - Un identificatore di posizione che consente agli utenti di vedere facilmente che il client Lync ha rilevato la posizione corretta. Il client Lync concatena automaticamente e visualizza la **posizione** e i campi della **città** individuati nella relativa intestazione. Una buona procedura consiste nell'aggiungere l'indirizzo di strada dell'edificio a ogni identificatore di posizione, ad esempio "numero \<\>civico 1 ° piano". Senza l'indirizzo stradale, un identificatore di posizione generico come "primo piano" può essere applicato a qualsiasi edificio della città.

  - Se la posizione è approssimativa perché è determinata da un punto di accesso wireless, è consigliabile aggiungere la parola Near, ad esempio "near 1 ° piano 1234".

</div>

<div>

## <a name="planning-elins"></a>Pianificazione di ELINs

Dopo aver deciso in che modo si vuole dividere lo spazio per l'edificio in posizioni, è necessario decidere il numero di ELIN da assegnare a ogni posizione. Ad esempio, in un edificio multipiano o multitenant, è possibile assegnare aree di emergenza diverse nell'edificio. In genere, ogni piano di un edificio viene designato come posizione. A ogni posizione viene quindi assegnato uno o più ELIN, che vengono usati come numeri di chiamata durante una chiamata di emergenza. Contattare il gestore PSTN per i numeri di telefono che è possibile usare per gli ELIN. La tabella seguente contiene un esempio di posizioni per un indirizzo di strada specifico.

### <a name="sample-location-and-elin-assignments"></a>Posizione di esempio e assegnazioni ELIN

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Area edifici</th>
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


I percorsi definiti devono soddisfare i requisiti seguenti:

  - Rispettare le normative locali e nazionali/regionali in termini di area massima per località e numero di posizioni per indirizzo stradale.

  - Sono sufficientemente specifici per facilitare l'individuazione del chiamante di emergenza.

</div>

</div>

<div>

## <a name="populating-the-location-database"></a>Popolamento del database della posizione

Le domande seguenti consentiranno di determinare come popolare il database della posizione.

  - **Quale processo verrà usato per popolare il database della posizione?**  
    Dove sono i dati e quali sono i passaggi da eseguire per convertire i dati nel formato richiesto dal database della posizione? Si aggiungono percorsi singolarmente o in blocco usando un file CSV?

<!-- end list -->

  - **Si dispone di un database di terze parti che contiene già una mappatura delle posizioni?**  
    Se si usa l'opzione del servizio informazioni posizione secondaria di Lync Server per connettersi a un database di terze parti, è possibile raggruppare e gestire le posizioni usando una piattaforma offline. Un vantaggio per questo approccio è che, oltre ad associare le posizioni agli identificatori di rete, è possibile associare le posizioni a un utente. Ciò significa che il servizio informazioni sulla posizione può restituire più indirizzi, provenienti dal servizio informazioni posizione secondaria, a un client Lync Server. L'utente può quindi scegliere la posizione più appropriata.
    
    Per l'integrazione con il servizio informazioni sulla posizione, il database di terze parti deve seguire lo schema di richiesta/risposta della posizione del server Lync. Per informazioni dettagliate, <http://go.microsoft.com/fwlink/p/?linkid=213819>vedere. Per informazioni dettagliate sulla distribuzione di un servizio di informazioni sulla posizione secondaria, vedere [configurare un servizio informazioni sulla posizione secondaria in Lync Server 2013](lync-server-2013-configure-a-secondary-location-information-service.md) nella documentazione relativa alla distribuzione.

Per informazioni dettagliate sulla compilazione del database della posizione, vedere [configurare il database della posizione in Lync Server 2013](lync-server-2013-configure-the-location-database.md) nella documentazione relativa alla distribuzione.

</div>

<div>

## <a name="maintaining-the-location-database"></a>Manutenzione del database della posizione

Dopo aver popolato il database della posizione, è necessario sviluppare una strategia per l'aggiornamento del database durante la modifica della configurazione della rete. Le domande seguenti consentono di determinare come gestire il database della posizione.

  - **Come si aggiorna il database della posizione?**  
    Esistono diversi scenari che richiedono un aggiornamento al database della posizione, tra cui l'aggiunta di punti di accesso wireless (WAP), il ricablaggio di Office (con le diverse assegnazioni di switch) e l'espansione della subnet. Si aggiorna direttamente ogni singola posizione o si esegue un aggiornamento in blocco di tutte le posizioni usando un file CSV?

<!-- end list -->

  - **Si utilizzerà un'applicazione SNMP per corrispondere agli indirizzi MAC client di Lync alla porta e agli identificatori di switch?**  
    Se si usa un'applicazione SNMP, è necessario sviluppare un processo manuale che contenga la coerenza tra l'applicazione SNMP e il database della posizione e le informazioni sulla porta. Se l'applicazione SNMP restituisce un indirizzo IP dello chassis o un ID di porta non incluso nel database, il servizio informazioni sulla posizione non sarà in grado di restituire una posizione al client.

</div>

</div>

<span> </span>

</div>

</div>

</div>

