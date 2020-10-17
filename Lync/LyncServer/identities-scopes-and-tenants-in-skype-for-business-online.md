---
title: Identità, ambiti e tenant in Skype for business online
description: Identità, ambiti e tenant in Skype for business online.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00ab84c3ca83dea2e328315ae7e616ad7830c227
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552512"
---
# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identità, ambiti e tenant in Skype for business online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-03-09_

Molti dei cmdlet di Windows PowerShell utilizzati per gestire Skype for business online richiedono di essere molto specifici sull'elemento che si sta tentando di gestire. Ad esempio, quando si esegue il cmdlet [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , è necessario indicare l'utente che si sta tentando di gestire. Questo ha senso. A meno che non si dica specificatamente al cmdlet per la gestione dell'account utente, il cmdlet **Set-CsUserAcp** non ha alcuna idea di quali informazioni sull'audioconferenza dell'utente devono essere modificate. Per questo motivo, ogni volta che si esegue il cmdlet **Set-CsUserAcp** , è necessario includere il parametro Identity, seguito dall'identità dell'account utente da modificare:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Se l' *identità* del termine si riferisce sempre all'identità di un account utente, non vi sarebbe alcuna causa di confusione. Quando si ha a che fare con persone (utenti, contatti e così via), le identità si riferiscono ai singoli utenti stessi. Tuttavia, gli elementi diversi dagli account utente dispongono anche di identità. Quando si ha a che fare con i componenti del servizio Skype for business online, criteri, impostazioni di configurazione e così via, l'identità del termine significa qualcosa di leggermente diverso. Si consideri, ad esempio, il comando seguente:

    Get-CsMeetingConfiguration -Identity "global"

In questo caso, l'identità "globale" si riferisce all'ambito delle impostazioni di configurazione delle riunioni. *Scope* è un termine utilizzato in Skype for business online (e in Lync Server) per designare gli ambiti di gestione. Per impostazione predefinita, i criteri e le impostazioni hanno sempre un ambito globale. Quando si configura per la prima volta l'account Skype for business online, per impostazione predefinita, è disponibile un insieme di criteri e impostazioni globali, ovvero le impostazioni di configurazione della riunione globale, un criterio di accesso esterno globale, un dial plan globale e così via.

I criteri e le impostazioni globali sono stati introdotti in Microsoft Lync Server 2010 per garantire che tutti gli utenti e tutti i componenti vengano gestiti in modo sempre. Questo non è necessariamente vero in Microsoft Office Communicator 2007 R2. A seconda del modo in cui è stato eseguito l'accesso al sistema, è possibile che si possa finire in uno stato ampiamente non gestito (in genere, perché non è stato possibile applicare criteri di gruppo all'account utente). Al contrario, in Lync Server e in Skype for business online, non è mai rimasto nulla gestito. Ciò è dovuto al fatto che, in sostituzione di qualsiasi altra operazione, verranno sempre applicati i criteri globali e le impostazioni.

Cosa si intende per "invece di qualcos'altro"? Ebbene, nel caso di Skype for business online, è possibile creare criteri nell' *ambito del tag*o nella sfera di gestione. I criteri creati nell'ambito dei tag (noti anche come *ambito per utente*) hanno la priorità rispetto ai criteri creati nell'ambito globale. In altre parole, un criterio per utente avrà sempre la precedenza su un criterio globale. Ad esempio, potrebbe essere necessario disporre di due criteri di accesso utente esterno. I criteri globali impediscono agli utenti di comunicare con persone che dispongono di account su provider di messaggistica istantanea pubblica, ad esempio Windows Live. Il criterio per utente, AllowPublicIMCommunication, consente la comunicazione con i provider di messaggistica istantanea pubblici.

Potrebbe essere necessario anche due utenti: Ken e Pilar Ackerman. A Ken è stato assegnato il criterio per utente. A Pilar Ackerman non è stato assegnato un criterio per utente. in altre altre, è gestita dal criterio di accesso esterno globale. Nella tabella seguente viene illustrato l'eventuale utente che può comunicare con i provider di messaggistica istantanea pubblici:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazioni di criteri</th>
<th>Davide Garghentini</th>
<th>Daniela Cazzaniga</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Impostazione dei criteri globali per i provider di messaggistica istantanea pubblici</p></td>
<td><p>No</p></td>
<td><p>No</p></td>
</tr>
<tr class="even">
<td><p>Impostazione dei criteri per utente per i provider di messaggistica istantanea pubblici</p></td>
<td><p>Sì</p></td>
<td><p>No</p></td>
</tr>
<tr class="odd">
<td><p>L'utente può comunicare con i provider di messaggistica istantanea pubblici</p></td>
<td><p>Sì</p></td>
<td><p>No</p></td>
</tr>
</tbody>
</table>


Come si può notare, Ken è autorizzato a comunicare con i provider di messaggistica istantanea pubblici. Ciò è dovuto al fatto che le impostazioni del criterio per utente assegnatogli eseguono l'override delle impostazioni del criterio globale. Pilar Ackerman non è in grado di comunicare con i provider di messaggistica istantanea pubblici. Ciò è dovuto al fatto che è gestita dal criterio globale e che il criterio globale proibisce tali comunicazioni.

I criteri per utente devono essere creati dal supporto tecnico Microsoft. Dopo aver creato i criteri, è possibile assegnarli agli utenti utilizzando il cmdlet **Grant-CS** appropriato (ad esempio, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). I criteri per utente sono facili da identificare perché l'identità dei criteri inizia sempre con il **prefisso**del tag. Ad esempio:

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Il <STRONG>prefisso</STRONG> di tag risale ai giorni di sviluppo precedenti di Lync Server 2010. In quei giorni, i criteri per utente sono stati denominati <EM>criteri di tag</EM> e sono stati identificati dal <STRONG>prefisso</STRONG>del tag. Questi criteri sono ora denominati in modo più accurato come <EM>criteri per utente</EM>e l'ambito dei tag viene definito in modo più accurato come <EM>ambito per utente</EM>. Tuttavia, per motivi tecnici, il <STRONG>prefisso</STRONG> del tag non è mai stato modificato.



</div>

Un altro termine chiave utilizzato quando si lavora con Skype for business online e Windows PowerShell è *tenant*. Quando si configura un account Skype for business online, alla nuova distribuzione viene assegnato un numero di ID tenant, che è un identificatore univoco globale (GUID) simile al seguente:

    bf19b7db-6960-41e5-a139-2aa373474354

Alcuni dei cmdlet di Skype for business online richiedono di immettere l'ID tenant ogni volta che si esegue il cmdlet. È necessario immettere l'ID tenant anche se l'utente ha effettuato l'accesso e dispone di un solo tenant. Fortunatamente, non è necessario memorizzare l'ID tenant. È possibile recuperare l'ID tenant in qualsiasi momento eseguendo il comando di Windows PowerShell seguente:

    Get-CsTenant | Select-Object TenantId

Naturalmente, conoscere elementi quali la differenza tra l'ambito globale e l'ambito per utente (o l'ambito dei tag) è solo la metà della battaglia. È inoltre importante sapere quando (o anche se) è possibile utilizzare questi ambiti. Lo stesso vale per le identità e per il parametro tenant. Negli argomenti seguenti viene descritto il modo in cui i diversi cmdlet Skype for business online utilizzano identità, ambiti e il parametro tenant:

  - [Cmdlet in Skype for business online che utilizzano solo l'ambito globale](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlet in Skype for business online che utilizzano l'ambito globale e l'ambito dei tag](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlet in Skype for business online che utilizzano un'identità utente](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlet in Skype for business online che utilizzano l'identità dell'utente e l'ambito dei tag](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlet in Skype for business online che utilizzano il parametro tenant](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlet in Skype for business online che utilizzano un'identità del provider di servizi di conferenza](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlet in Skype for business online che non utilizzano un ambito o un'identità](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

