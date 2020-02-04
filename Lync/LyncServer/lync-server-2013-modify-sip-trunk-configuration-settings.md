---
title: 'Lync Server 2013: modificare le impostazioni di configurazione del trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f7a94a4ab211f1bf21483729519cd53de2a2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756920"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:

  - Se il bypass multimediale deve essere abilitato nei trunk.

  - Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).

  - Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN). Una qualsiasi di queste raccolte può essere modificata in un secondo momento usando il pannello di controllo di Lync Server o Windows PowerShell.

Quando si modificano le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione dell'interfaccia utente</th>
<th>Parametro di PowerShell</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Identity</p></td>
<td><p>Identificatore univoco per la raccolta. Questa proprietà è di sola lettura; non è possibile modificare l'identità di una raccolta di impostazioni di configurazione trunk.</p></td>
</tr>
<tr class="even">
<td><p>Descrizione</p></td>
<td><p>Descrizione</p></td>
<td><p>Consente agli amministratori di archiviare informazioni di aggiunta sulle impostazioni, ad esempio lo scopo della configurazione trunk.</p></td>
</tr>
<tr class="odd">
<td><p>Finestre di dialogo iniziali massime supportate</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Numero massimo di risposte a forcella un gateway PSTN, IP-PBX o SBC presso il provider di servizi può ricevere un invito inviato al Mediation Server.</p></td>
</tr>
<tr class="even">
<td><p>Livello di supporto della crittografia</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indica il livello di supporto per la protezione del traffico multimediale tra il Mediation Server e il gateway PSTN, IP-PBX o SBC presso il provider di servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata usando i cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</p>
<p>I valori consentiti sono:</p>
<ul>
<li><p>Obbligatorio: è necessario usare la crittografia SRTP.</p></li>
<li><p>Facoltativo: SRTP verrà usato se il gateway lo supporta.</p></li>
<li><p>Non supportata: la crittografia SRTP non è supportata e pertanto non verrà usata.</p></li>
</ul>
<p>SRTPMode viene usato solo se il gateway è configurato per l'uso di Transport Layer Security (TLS). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) come trasporto, SRTPMode è impostato internamente su non supportato.</p></td>
</tr>
<tr class="odd">
<td><p>Fare riferimento al supporto</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Se impostato per <strong>abilitare l'invio, fare riferimento al gateway</strong>, indica che il trunk supporta la ricezione di richieste di riferimento dal server Mediation.</p>
<p>Se impostato per <strong>abilitare l'opzione fai riferimento tramite il controllo delle chiamate di terze parti</strong>, indica che il protocollo 3PCC può essere usato per consentire alle chiamate trasferite di ignorare il sito ospitato. 3PCC è anche noto come &quot;controllo di terze&quot; parti e si verifica quando una terza parte viene usata per connettere una coppia di chiamanti (ad esempio, un operatore che effettua una chiamata dalla persona a alla persona B).</p></td>
</tr>
<tr class="even">
<td><p>Abilitare il bypass multimediale</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indica se il bypass multimediale è abilitato per il trunk. Il bypass multimediale può essere abilitato solo se è abilitata anche l' <strong>elaborazione media centralizzata</strong> .</p></td>
</tr>
<tr class="odd">
<td><p>Elaborazione multimediale centralizzata</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indica se è presente un punto di interruzione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione degli elementi multimediali ha lo stesso IP della terminazione dei segnali.</p></td>
</tr>
<tr class="even">
<td><p>Abilitare l'aggancio RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indica se i trunk SIP supportano o meno il latching RTP. Il latching RTP è una tecnologia che consente la connettività RTP/RTCP tramite un dispositivo NAT (Network Address Translator) o un firewall.</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare la cronologia delle chiamate inoltrate</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indica se le informazioni del registro chiamate verranno inoltrate tramite il trunk.</p></td>
</tr>
<tr class="even">
<td><p>Abilitare inoltra P-asserzione-dati identità</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indica se l'intestazione PAI (P-Asserted-Identity) verrà inoltrata insieme alla chiamata. L'intestazione PAI consente di verificare l'identità del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare il timer di failover del routing in uscita</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indica se le chiamate in uscita non risposte dal gateway entro 10 secondi verranno instradate al successivo trunk disponibile. Se non ci sono trunk aggiuntivi, la chiamata verrà eliminata automaticamente. In un'organizzazione con reti lente e risposte del gateway, che potrebbero potenzialmente causare la perdita di chiamate inutilmente.</p></td>
</tr>
<tr class="even">
<td><p>Usi PSTN associati</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Raccolta di utilizzi PSTN assegnati al trunk.</p></td>
</tr>
<tr class="odd">
<td><p>Numero tradotto da testare</p></td>
<td><p>N/D</p></td>
<td><p>Numero di telefono che può essere usato per eseguire un test ad hoc delle impostazioni di configurazione del trunk.</p></td>
</tr>
<tr class="even">
<td><p>Regole di traduzione associate</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Raccolta di regole di traduzione per i numeri di telefono che si applicano alle chiamate gestite dal routing in uscita (chiamate indirizzate a destinazioni PBX o PSTN).</p></td>
</tr>
<tr class="odd">
<td><p>Regole di traduzione del numero chiamate</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Raccolta di regole di conversione dei numeri in uscita assegnate al trunk.</p></td>
</tr>
<tr class="even">
<td><p>Numero di telefono da testare</p></td>
<td><p>N/D</p></td>
<td><p>Numero di telefono che può essere usato per eseguire un test ad hoc sulle regole di traduzione.</p></td>
</tr>
<tr class="odd">
<td><p>Numero chiamante</p></td>
<td><p>N/D</p></td>
<td><p>Indica che il numero di telefono da testare è il numero di telefono del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>Numero chiamato</p></td>
<td><p>N/D</p></td>
<td><p>Indica che il numero di telefono da testare è il numero di telefono della persona che viene chiamata.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server. Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Per modificare le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server fare clic su **routing vocale**e quindi su **configurazione trunk**.

2.  Nella scheda **configurazione trunk** fare doppio clic sulle impostazioni di configurazione trunk da modificare. Tieni presente che puoi modificare solo una raccolta di impostazioni alla volta. Se si desidera apportare le stesse modifiche in più insiemi, utilizzare invece Windows PowerShell.

3.  Nella finestra di dialogo **modifica configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.

4.  La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.

5.  Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.

6.  Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

