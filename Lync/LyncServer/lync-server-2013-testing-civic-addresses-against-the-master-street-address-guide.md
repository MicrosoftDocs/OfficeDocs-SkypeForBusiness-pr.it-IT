---
title: Verifica degli indirizzi civici rispetto alla guida all'indirizzo Master Street
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f9115e6bc0c65f589effc08ecd5f7b681208a54
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Verifica degli indirizzi civici in base alla guida all'indirizzo Master Street in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Giornaliero</p></td>
</tr>
<tr class="even">
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsRegistration. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsLisCivicAddress viene utilizzato per verificare i percorsi aggiunti al database del servizio di informazioni sulla posizione. Il cmdlet funziona confrontando i percorsi con i percorsi trovati nella Master Street Address Guide (allo stradario generale) che appartiene al provider di routing di rete di E9-1-1. Se non si dispone di un provider di routing di rete o se non è possibile raggiungere il provider, i test avranno esito negativo.

Se si aggiunge il parametro facoltativo switch UpdateValidationStatus al comando, la proprietà corrispondente di database di MSAGValid verrà impostata su true per ogni indirizzo che passa il test.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Il cmdlet Test-CsLisCivicAddress può essere utilizzato per testare singoli indirizzi o per testare più indirizzi. Ad esempio, questo comando consente di testare un singolo indirizzo che si trova a Redmond, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

In base al confronto, questo comando verifica tutti gli indirizzi attualmente presenti nel database LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinazione dell'esito positivo o negativo

Test-CsLisCivicAddress riporterà l'esito positivo o negativo degli indirizzi forniti. Un test degli indirizzi avrà esito negativo se non è possibile trovare l'indirizzo o se non è possibile contattare il provider di servizi.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non avere avuto esito positivo

Di seguito sono riportate alcune ragioni comuni per cui Test-CsLisCivicAddress potrebbe non riuscire:

  - Il provider di servizi LIS potrebbe non essere disponibile. È possibile recuperare l'URL del provider di servizi LIS eseguendo il cmdlet Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    È quindi possibile eseguire il ping dell'URL per verificare che il provider di servizi sia disponibile.

</div>

</div>

<span> </span>

</div>

</div>

</div>

