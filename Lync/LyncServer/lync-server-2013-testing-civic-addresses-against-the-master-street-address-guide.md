---
title: Test degli indirizzi civici nella Guida all'indirizzo Master Street
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa4dd28ec05546366e029b6fb9fdf1c4b3ae310
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Test degli indirizzi civici nella Guida all'indirizzo Master Street in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Quotidiana</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsRegistration. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Test-CsLisCivicAddress viene usato per verificare le posizioni aggiunte al database del servizio informazioni sulla posizione. Il cmdlet funziona confrontando le posizioni in base alle posizioni trovate nella Guida di indirizzi master Street (stradario) che appartiene al provider di routing di rete E9-1-1. Se non si dispone di un provider di routing di rete o se non è possibile raggiungere il provider, i test avranno esito negativo.

Se si aggiunge il parametro facoltativo switch UpdateValidationStatus al comando, la proprietà del database MSAGValid corrispondente verrà impostata su true per ogni indirizzo che passa il test.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Il cmdlet Test-CsLisCivicAddress può essere usato per testare singoli indirizzi o per testare più indirizzi. Ad esempio, questo comando verifica un singolo indirizzo situato in Redmond, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

In base al confronto, questo comando verifica tutti gli indirizzi attualmente presenti nel database LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet [Test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinare l'esito positivo o negativo

Test-CsLisCivicAddress restituirà l'esito positivo o negativo degli indirizzi forniti. Un test di indirizzo non riesce se non è possibile trovare l'indirizzo o se il provider di servizi non può essere contattato.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivi per cui il test potrebbe non essere riuscito

Ecco alcuni motivi comuni per cui Test-CsLisCivicAddress potrebbe non riuscire:

  - Il provider di servizi LIS potrebbe non essere disponibile. Puoi recuperare l'URL del provider di servizi LIS eseguendo il cmdlet Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    Puoi quindi eseguire il ping dell'URL per verificare che il provider di servizi sia disponibile.

</div>

</div>

<span> </span>

</div>

</div>

</div>

