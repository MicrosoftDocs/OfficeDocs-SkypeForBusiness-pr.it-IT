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
ms.openlocfilehash: 356c418c620cbbf38a97da2df652b5767f9fced9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515323"
---
# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a>Modificare le impostazioni di configurazione del trunk SIP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Le impostazioni di configurazione dei trunk SIP consentono di definire le funzionalità e la relazione tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un sistema IP-PBX o un servizio Session Border Controller (SBC) nel provider di servizi. Queste impostazioni consentono di specificare quanto segue:

  - Se abilitare il bypass multimediale nei trunk.

  - Le condizioni in base alle quali vengono inviati pacchetti RTCP (Real-Time Control Protocol).

  - Se in ogni trunk è richiesta la crittografia SRTP (Secure Real-Time Protocol).

Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione del trunk SIP. Gli amministratori inoltre possono creare raccolte di impostazioni personalizzate nell'ambito del sito o del servizio (solo per il servizio gateway PSTN). Uno di questi insiemi può essere modificato in un secondo momento utilizzando il pannello di controllo di Lync Server o Windows PowerShell.

Quando si modificano le impostazioni di configurazione del trunk SIP utilizzando il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:


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
<td><p>Identità</p></td>
<td><p>Identificatore univoco della raccolta. È una proprietà di sola lettura; non è possibile modificare l'identitià di una raccolta di impostazioni di configurazione per il trunk.</p></td>
</tr>
<tr class="even">
<td><p>Descrizione</p></td>
<td><p>Descrizione</p></td>
<td><p>Consente agli amministratori di archiviare informazioni aggiuntive sulle impostazioni (ad esempio, le finalità della configurazione del trunk).</p></td>
</tr>
<tr class="odd">
<td><p>Dialoghi anticipati massimi supportati</p></td>
<td><p>MaxEarlyDialogs</p></td>
<td><p>Il numero massimo di risposte instradate che un gateway PSTN, IP-PBX o SBC nel provider di servizi può ricevere per un invito inviato a Mediation Server.</p></td>
</tr>
<tr class="even">
<td><p>Livello di supporto della crittografia</p></td>
<td><p>SRTPMode</p></td>
<td><p>Indica il livello di supporto per la protezione del traffico multimediale tra Mediation Server e il gateway PSTN, il sistema IP-PBX o il servizio SBC nel provider dei servizi. Nel caso del bypass multimediale, questo valore deve essere compatibile con l'impostazione di EncryptionLevel nella configurazione degli elementi multimediali. La configurazione multimediale viene impostata utilizzando i cmdlet <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> .</p>
<p>I valori consentiti sono:</p>
<ul>
<li><p>Obbligatorio: è necessario utilizzare la crittografia SRTP.</p></li>
<li><p>Facoltativo: SRTP verrà utilizzato se supportato dal gateway.</p></li>
<li><p>Non supportato: la crittografia SRTP non è supportata, pertanto non verrà utilizzata.</p></li>
</ul>
<p>SRTPMode viene utilizzato solo se il gateway è configurato per l'uso di TLS (Transport Layer Security). Se il gateway è configurato con il protocollo TCP (Transmission Control Protocol) per il trasporto, SRTPMode viene impostato internamente su NotSupported.</p></td>
</tr>
<tr class="odd">
<td><p>Supporto riferimento</p></td>
<td><p>Enable3pccRefer</p>
<p>EnableReferSupport</p></td>
<td><p>Se impostato su <strong>Abilita l'invio del riferimento al gateway</strong>, indica che il trunk supporta ricezione di richieste Refer da Mediation Server.</p>
<p>Se impostato su <strong>Abilita il riferimento usando il controllo delle chiamate di terze parti</strong>, indica che il protocollo 3pcc può essere utilizzato per consentire alle chiamate trasferite di eseguire il bypass del sito ospitato. 3PCC è noto anche come controllo di terze &quot; parti &quot; e si verifica quando viene utilizzata una terza parte per connettere una coppia di chiamanti, ad esempio un operatore che effettua una chiamata dalla persona a alla persona B.</p></td>
</tr>
<tr class="even">
<td><p>Abilita bypass multimediale</p></td>
<td><p>EnableBypass</p></td>
<td><p>Indica se il bypass multimediale è abilitato per questo trunk. È possibile abilitare il bypass multimediale solo se è abilitato anche <strong>Elaborazione multimediale centralizzata</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Elaborazione multimediale centralizzata</p></td>
<td><p>ConcentratedTopology</p></td>
<td><p>Indica se esiste un punto di terminazione multimediale noto. Un esempio di punto di terminazione multimediale noto può essere costituito da un gateway PSTN in cui la terminazione dei supporti ha lo stesso IP della terminazione dei segnali.</p></td>
</tr>
<tr class="even">
<td><p>Abilita scatto RTP</p></td>
<td><p>EnableRTPLatching</p></td>
<td><p>Indica se i trunk SIP supportano lo scatto RTP, una tecnologia che abilita la connettività RTP/RTCP attraverso un dispositivo NAT o firewall.</p></td>
</tr>
<tr class="odd">
<td><p>Abilita inoltro cronologia chiamate</p></td>
<td><p>ForwardCallHistory</p></td>
<td><p>Indica se le informazioni relative alla cronologia delle chiamate saranno inoltrate attraverso il trunk.</p></td>
</tr>
<tr class="even">
<td><p>Abilita inoltro dati PAI</p></td>
<td><p>ForwardPAI</p></td>
<td><p>Indica se l'intestazione PAI sarà inoltrata con la chiamata. L'intestazione PAI consente di identificare l'identità del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>Abilita timer di failover del routing in uscita</p></td>
<td><p>EnableFastFailoverTimer</p></td>
<td><p>Indica se le chiamate non risposte dal entro 10 secondi saranno instradate al primo trunk disponibile; se non esistono altri trunk, la chiamata sarà ignorata. In un'organizzazione con reti e risposte del gateway lente, ciò potrebbe portare a ignorare chiamate non volutamente.</p></td>
</tr>
<tr class="even">
<td><p>Utilizzo PSTN associato</p></td>
<td><p>PSTNUsages</p></td>
<td><p>Raccolta di utilizzi PSTN assegnati al trunk.</p></td>
</tr>
<tr class="odd">
<td><p>Numero convertito da testare</p></td>
<td><p>N/D</p></td>
<td><p>Numero di telefono che può essere utilizzato per un test ad hoc delle impostazioni di configurazione del trunk.</p></td>
</tr>
<tr class="even">
<td><p>Regole di conversione associate</p></td>
<td><p>OutboundTranslationRulesList</p></td>
<td><p>Raccolta di regole di conversione dei numeri di telefono che si applicano alle chiamate gestite mediante il routing in uscita (chiamate instradate a destinazioni PBX o PSTN).</p></td>
</tr>
<tr class="odd">
<td><p>Regole di conversione del numero chiamato</p></td>
<td><p>OutboundCallingNumberTranslationRulesList</p></td>
<td><p>Raccolta di regole di conversione del numero chiamato in uscita, assegnate al trunk.</p></td>
</tr>
<tr class="even">
<td><p>Numero di telefono da testare.</p></td>
<td><p>N/D</p></td>
<td><p>Numero di telefono che può essere utilizzato per un test ad hoc delle regole di conversione.</p></td>
</tr>
<tr class="odd">
<td><p>Numero di chiamata</p></td>
<td><p>N/D</p></td>
<td><p>Indica che il numero di telefono da testare è il numero di telefono del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>Numero chiamato</p></td>
<td><p>N/D</p></td>
<td><p>Indica che il numero di telefono da testare è il numero di telefono della persona che riceve la chiamata.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server. Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Per modificare le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server, fare clic su **routing vocale**e quindi su **configurazione trunk**.

2.  Nella scheda **Configurazione trunk** fare doppio clic sulle impostazioni di configurazione del trunk che si desidera modificare. È possibile modificare una sola raccolta di impostazioni per volta. Per apportare le stesse modifiche a più raccolte, utilizzare Windows PowerShell.

3.  Nella finestra di dialogo **modifica configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.

4.  La proprietà **Stato** per la raccolta verrà aggiornata a **Commit non eseguito**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **Commit**, quindi su **Salva tutto**.

5.  Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** fare clic su **OK**.

6.  Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** scegliere **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

