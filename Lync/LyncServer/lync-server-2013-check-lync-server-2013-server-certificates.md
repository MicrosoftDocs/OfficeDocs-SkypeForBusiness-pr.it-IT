---
title: 'Lync Server 2013: verificare i certificati del server Lync Server 2013'
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
ms.openlocfilehash: 11c5e545bc00de48fa5590dc8c4b119a46ffe9e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="check-lync-server-2013-server-certificates"></a>Controllare i certificati del server Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-11-01_


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
<td><p>Strumento di testing</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorizzazioni necessarie</p></td>
<td><p>Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</p>
<p>Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Get-CsCertificate. Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</p>
<p><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Get-CsCertificate&quot;}</code></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descrizione

Il cmdlet Get-CsCertificate consente di recuperare le informazioni su ognuno dei certificati di Lync Server. Questo è particolarmente importante perché i certificati hanno una data di scadenza incorporata. Ad esempio, i certificati rilasciati in privato scadono in genere dopo 12 mesi. Se uno dei certificati di Lync Server scade, si perderà la funzionalità di accompagnamento fino a quando il certificato non verrà rinnovato o sostituito.

</div>

<div>

## <a name="running-the-test"></a>Esecuzione del test

Per restituire informazioni su ognuno dei certificati di Lync Server, eseguire il comando seguente:

`Get-CsCertificate`

In alternativa, è possibile filtrare le informazioni sul certificato restituito in base alla data di scadenza. Ad esempio, questo comando consente di limitare i dati restituiti ai certificati che scadono (non possono essere utilizzati dopo) il 1 ° giugno 2014:

`Get-CsCertificate | Where-Object {$_.NotAfter -lt "6/1/2014"}`

Per ulteriori informazioni, vedere la documentazione della Guida relativa al cmdlet Get-CsCertificate.

Si noti che, anche se il cmdlet Test-CsCertificateConfiguration esiste, non è molto utile per gli amministratori. (Invece, il cmdlet viene utilizzato principalmente dalla configurazione guidata certificati). Anche se il cmdlet funziona, le informazioni restituite sono di valore minimo, come illustrato nell'esempio di output seguente:

Utilizzo di identificazione personale

\---------- ---

A9D51A2911C74FABFF7F2A8A994B20857D399107 predefinito

</div>

<div>

## <a name="reviewing-the-output"></a>Revisione dell'output

Il cmdlet Get-CsCertificate restituisce informazioni simili alle seguenti per ognuno dei certificati di Lync Server:

Autorità emittente: CN = FabrikamCA

NotAfter: 12/28/2015 3:35:41 PM

NotBefore: 1/2/2014 12:49:37 PM

SerialNumber: 611BB01200000000000C

Oggetto: CN = LYNC-SE.fabrikam.com

AlternativeNames: {sip.fabrikam.com, LYNC-SE.fabrikam.com,

meet.fabrikam.com, admin.fabrikam.com...}

Identificazione personale: A9D51A2911C74FABFF7F2A8A994B20857D399107

Utilizzo: impostazione predefinita

Come regola generale, i principali problemi relativi ai certificati di Lync Server coinvolgono date e ore, ad esempio quando i certificati hanno effetto (NotBefore) o quando scadono (NotAfter). Poiché queste date e ore sono importanti, è possibile limitare i dati restituiti a informazioni quali l'utilizzo del certificato, il numero di serie del certificato e la data di scadenza del certificato. sarà quindi possibile esaminare rapidamente tutti i certificati e quando scadranno. Per restituire solo tali informazioni, utilizzare il comando insieme alle opzioni come illustrato di:

`Get-CsCertificate | Select-Object Use, SerialNumber, NotAfter | Sort-Object NotAfter`

Questo comando restituisce i dati simili al seguente, con i certificati ordinati in base alla data di scadenza:

Utilizzo di SerialNumber NotAfter

\--- ------------ --------

Default 611BB01200000000000C 12/28/2015 3:35:41 PM

WebServicesInteral 32980AA20BBB20000191 02/15/2016 2:16:12 PM

WebServicesExternal 0451B012003872651A0C 02/20/2016 7:11:58 AM

Se si verificano problemi relativi ai certificati, è possibile esaminare la AlternativeNames configurata per un certificato. A prima vista, che sembra essere un problema. Per impostazione predefinita, e a seconda delle dimensioni della finestra della console, Get-CsCertificate potrebbe non essere in grado di visualizzare tutti i nomi:

AlternativeNames: {sip.fabrikam.com, LYNC.fabrikam.com,

meet.fabrikam.com, admin. Fabrika...}

Per visualizzare tutti i nomi alternativi assegnati a un certificato, utilizzare un comando simile al seguente:

`Get-CsCertificate | Where-Object {$_.SerialNumber -eq "611BB01200000000000C"} | Select-Object -ExpandProperty AlternativeNames`

Che dovrebbe mostrare tutti i nomi alternativi del certificato:

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

