---
title: Identità, ambiti e tenant in Skype for business online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981020"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identità, ambiti e tenant in Skype for business online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-03-09_

Molti dei cmdlet di Windows PowerShell usati per gestire Skype for business online richiedono di essere molto specifici sull'elemento che si sta cercando di gestire. Ad esempio, quando si esegue il cmdlet [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , è necessario indicare l'utente che si vuole gestire. Questo ha senso. A meno che non si informi in modo specifico il cmdlet che l'account utente deve gestire, il cmdlet **Set-CsUserAcp** non ha idea delle informazioni sui servizi di audioconferenza dell'utente da modificare. Per questo motivo, ogni volta che si esegue il cmdlet **Set-CsUserAcp** , è necessario includere il parametro Identity, seguito dall'identità dell'account utente da modificare:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Se l' *identità* del termine si riferisce sempre all'identità di un account utente, la confusione potrebbe causare scarsità. Quando si hanno a che fare con persone (utenti, contatti e così via), le identità si riferiscono ai singoli utenti. Tuttavia, gli elementi diversi dagli account utente hanno anche le identità. Quando hai a che fare con i componenti del servizio Skype for business online: criteri, impostazioni di configurazione e così via, l'identità del termine indica un aspetto leggermente diverso. Consideriamo ad esempio questo comando:

    Get-CsMeetingConfiguration -Identity "global"

In questo caso, l'identità "globale" si riferisce all'ambito delle impostazioni di configurazione della riunione. L' *ambito* è un termine usato in Skype for business online (e in Lync Server) per designare le sfere di gestione. Per impostazione predefinita, i criteri e le impostazioni hanno sempre un ambito globale. Quando si configura per la prima volta l'account Skype for business online, per impostazione predefinita è disponibile una raccolta di criteri e impostazioni globali, ossia le impostazioni di configurazione della riunione globale, un criterio di accesso esterno globale, un dial plan globale e così via.

Questi criteri e impostazioni globali sono stati introdotti in Microsoft Lync Server 2010 per garantire che tutti gli utenti e tutti i componenti vengano sempre gestiti in qualche modo. Questo non è necessariamente vero in Microsoft Office Communicator 2007 R2. A seconda del modo in cui è stato eseguito l'accesso al sistema, è possibile che si sia potuto finire in uno stato in gran parte non gestito, in genere perché non è stato possibile applicare criteri di gruppo al proprio account utente. Al contrario, in Lync Server e in Skype for business online, nulla viene mai lasciato non gestito. Questo perché, al posto di qualsiasi altra cosa, verranno sempre applicati i criteri globali e le impostazioni.

Cosa si intende per "al posto di qualcos'altro"? Beh, nel caso di Skype for business online, è possibile creare criteri in *ambito tag*o sfera di gestione. I criteri creati nell'ambito del tag (noto anche come *ambito per utente*) hanno priorità sui criteri creati nell'ambito globale. In altre parole, un criterio per utente avrà sempre la precedenza su un criterio globale. Ad esempio, potresti avere due criteri di accesso degli utenti esterni. Il criterio globale impedisce agli utenti di comunicare con persone che hanno account su provider di messaggistica istantanea pubblici, ad esempio Windows Live. Il criterio per utente, AllowPublicIMCommunication, consente la comunicazione con i provider di messaggistica istantanea pubblici.

Si potrebbero anche avere due utenti: Ken e Pilar Ackerman. A Ken è stato assegnato il criterio per utente. A Pilar Ackerman non è stato assegnato un criterio per utente; in altre condizioni, viene gestita dal criterio di accesso esterno globale. La tabella seguente mostra l'eventuale utente che può comunicare con i provider di messaggistica istantanea pubblici:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazioni dei criteri</th>
<th>Ken</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Impostazione di criteri globali per i provider di messaggistica istantanea pubblici</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Impostazione dei criteri per utente per i provider di messaggistica istantanea pubblici</p></td>
<td><p>Sì</p></td>
<td><p>Supporto per riunioni private con ID conferenza di riunione dinamici</p></td>
</tr>
<tr class="odd">
<td><p>L'utente può comunicare con i provider di messaggistica istantanea pubblici</p></td>
<td><p>Sì</p></td>
<td><p>Supporto per riunioni private con ID conferenza di riunione dinamici</p></td>
</tr>
</tbody>
</table>


Come puoi vedere, Ken è autorizzato a comunicare con i provider di messaggistica istantanea pubblici. Il motivo è che le impostazioni dei criteri per utente assegnate agli utenti eseguono l'override delle impostazioni nel criterio globale. Pilar Ackerman non riesce a comunicare con i provider di messaggistica istantanea pubblici. Questo perché è gestita dal criterio globale e il criterio globale vieta tali comunicazioni.

I criteri per utente devono essere creati per il supporto di Office 365. Dopo la creazione dei criteri, è possibile assegnarli agli utenti usando il cmdlet **Grant-CS** appropriato, ad esempio [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy). I criteri per utente sono facili da identificare perché l'identità dei criteri inizia sempre con il **prefisso**di tag. Ad esempio:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Il <STRONG>prefisso</STRONG> di tag risale ai giorni di sviluppo iniziali di Lync Server 2010. In questi giorni i criteri per utente venivano definiti criteri di <EM>tag</EM> e venivano identificati dal <STRONG>prefisso</STRONG>di tag. Questi criteri vengono ora definiti in modo più accurato come <EM>criteri per utente</EM>e l'ambito del tag viene indicato in modo più accurato come <EM>ambito per utente</EM>. Tuttavia, per motivi tecnici, il <STRONG>prefisso</STRONG> del contrassegno non è mai stato modificato.



</div>

Un altro termine chiave usato quando si lavora con Skype for business online e Windows PowerShell è *tenant*. Quando si configura un account Skype for business online, alla nuova distribuzione viene assegnato un numero di ID tenant, un identificatore univoco globale (GUID) simile al seguente:

    bf19b7db-6960-41e5-a139-2aa373474354

Alcuni dei cmdlet di Skype for business online richiedono di immettere l'ID tenant ogni volta che si esegue il cmdlet. È necessario immettere l'ID tenant anche se è stato effettuato l'accesso e solo un tenant. Fortunatamente, non è necessario memorizzare l'ID tenant. Puoi recuperare l'ID tenant in qualsiasi momento eseguendo il comando di Windows PowerShell seguente:

    Get-CsTenant | Select-Object TenantId

Naturalmente, conoscere elementi come la differenza tra l'ambito globale e l'ambito per utente (o l'ambito del tag) è solo metà della battaglia. È anche importante sapere quando (o anche se) è possibile usare questi ambiti. Lo stesso vale per le identità e per il parametro tenant. Gli argomenti seguenti descrivono in che modo i diversi cmdlet Skype for business online usano identità, ambiti e il parametro tenant:

  - [Cmdlet in Skype for business online che usano solo l'ambito globale](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlet in Skype for business online che usano l'ambito globale e l'ambito dei tag](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlet in Skype for business online che usano un'identità utente](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlet in Skype for business online che usano l'identità dell'utente e l'ambito dei tag](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlet in Skype for business online che usano il parametro tenant](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlet in Skype for business online che usano l'identità di un provider di servizi di conferenza](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlet in Skype for business online che non usano un ambito o un'identità](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

