---
title: 'Lync Server 2013: verificare i certificati server di Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Check server certificates
ms:assetid: 7b0474e8-0efe-47f0-84eb-a1ba575dabfd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn725210(v=OCS.15)
ms:contentKeyID: 63969620
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af0a80df18a4fc6e27200d1ac04476fcea798b9b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Verificare i certificati server di Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-11-01_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pianificazione della verifica</p></td>
<td><p>Mensile</p></td>
</tr>
<tr class="even">
<td><p>Strumento di test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Get-CsCertificate. Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Get-CsCertificate consente di recuperare informazioni su ognuno dei certificati di Lync Server. Questo è particolarmente importante perché i certificati hanno una data di scadenza predefinita. Ad esempio, i certificati emessi in privato scadono in genere dopo 12 mesi. Se uno dei certificati di Lync Server scade, si perderà la funzionalità associata finché il certificato non viene rinnovato o sostituito.

</div>

<div>

## <a name="running-the-test"></a>Eseguire il test

Per restituire informazioni su ognuno dei certificati di Lync Server è sufficiente eseguire il comando seguente:

`Get-CsCertificate`

In alternativa, è possibile filtrare le informazioni sul certificato restituito in base alla data di scadenza. Ad esempio, questo comando limita i dati restituiti ai certificati che scadono (non può essere usato dopo) il 1 giugno 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Per altre informazioni, vedere la documentazione della Guida relativa al cmdlet Get-CsCertificate.

Tieni presente che, anche se il cmdlet Test-CsCertificateConfiguration esiste, non è molto utile per gli amministratori. Il cmdlet viene invece usato principalmente dalla creazione guidata certificato. Anche se il cmdlet funziona, le informazioni restituite sono di valore minimo, come illustrato nell'esempio di output seguente:

Uso di identificazione personale

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 predefinito

</div>

<div>

## <a name="reviewing-the-output"></a>Revisione dell'output

Il cmdlet Get-CsCertificate restituisce informazioni simili a quelle seguenti per ogni certificato di Lync Server:

Emittente: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 PM

NotBefore: 1/2/2014 12:49:37 PM

NumeroSerie: 611BB01200000000000C

Oggetto: CN = LYNC-SE.fabrikam.com

AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Identificazione personale: A9D51A2911C74FABFF7F2A8A994B20857D399107

USA: impostazione predefinita

Di norma, i principali problemi che coinvolgono i certificati di Lync Server coinvolgono date e ore, ad esempio quando i certificati hanno effetto (NotBefore) o quando scadono (NotAfter). Poiché queste date e ore sono così importanti, è consigliabile limitare i dati restituiti alle informazioni, ad esempio l'uso del certificato, il numero di serie del certificato e la data di scadenza del certificato. è quindi possibile rivedere rapidamente tutti i certificati e quando scadono. Per restituire solo queste informazioni, usare il comando insieme alle opzioni come illustrato:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Questo comando restituisce i dati simili a quelli seguenti, con i certificati ordinati in ordine alla data di scadenza:

Usare NumeroSerie NotAfter

\--- ------------ --------

Impostazione predefinita 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58

Se si hanno problemi di certificato, è consigliabile rivedere il AlternativeNames configurato per un certificato. A prima vista, questo sembra essere un problema. Per impostazione predefinita, a seconda delle dimensioni della finestra della console, Get-CsCertificate potrebbe non essere in grado di visualizzare tutti i nomi:

AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, amministratore. Fabrika...}

Per visualizzare tutti i nomi alternativi assegnati a un certificato, usare un comando simile al seguente:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Che dovrebbe mostrare tutti i nomi alternativi nel certificato:

sip.fabrikam.com

LYNC.fabrikam.com

meet.fabrikam.com

admin.fabrikam.com

LYNC-SE.fabrikam.com

Dialin.fabrikam.com

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Get-CsCertificate](https://docs.microsoft.com/powershell/module/skype/Get-CsCertificate)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

