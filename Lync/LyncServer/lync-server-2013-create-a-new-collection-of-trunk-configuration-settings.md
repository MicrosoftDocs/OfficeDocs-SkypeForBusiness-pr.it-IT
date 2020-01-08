---
title: 'Lync Server 2013: creare una nuova raccolta di impostazioni di configurazione trunk'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a>Creare una nuova raccolta di impostazioni di configurazione trunk in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Le impostazioni di configurazione trunk SIP definiscono la relazione e le funzionalità tra un Mediation Server e il gateway PSTN (Public Switched Telephone Network), un PBX (IP-Public Branch Exchange) o un SBC (Session Border Controller) presso il provider di servizi. Queste impostazioni eseguono operazioni come specifica:

  - Se il bypass multimediale deve essere abilitato nei trunk.

  - Condizioni in cui vengono inviati i pacchetti RTCP (Real-Time Transport Control Protocol).

  - Indipendentemente dal fatto che sia necessaria o meno la crittografia SRTP (Real-Time Protocol) in ogni trunk.

Quando si installa Microsoft Lync Server 2013, viene creata una raccolta globale di impostazioni di configurazione trunk SIP. Gli amministratori possono inoltre creare raccolte di impostazioni personalizzate nell'ambito del sito o nell'ambito del servizio (solo per il servizio gateway PSTN).

Quando si creano le impostazioni di configurazione del trunk SIP tramite il pannello di controllo di Lync Server, sono disponibili le opzioni seguenti:


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
> I cmdlet di Lync Server CsTrunkConfiguration supportano altre proprietà non visualizzate nel pannello di controllo di Lync Server. Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> .



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a>Per creare nuove impostazioni di configurazione trunk tramite il pannello di controllo di Lync Server

1.  Nel pannello di controllo di Lync Server fare clic su **routing vocale**e quindi su **configurazione trunk**.

2.  Nella scheda **configurazione trunk** fare clic su **nuovo**e quindi su **Trunk sito** per creare le nuove impostazioni nell'ambito del sito o trunk del **pool** per creare le nuove impostazioni nell'ambito del servizio.

3.  Nella finestra di dialogo **Seleziona un sito** o **Seleziona un servizio** (la finestra di dialogo visualizzata dipende dal fatto che si stiano creando impostazioni con ambito del sito o con ambito servizio) selezionare la posizione per le nuove impostazioni di configurazione e quindi fare clic su **OK**. Se la finestra di dialogo è vuota, significa che non è disponibile alcuna posizione per creare le nuove impostazioni. ad esempio, se la finestra di dialogo **Seleziona sito** è vuota, significa che tutti i siti sono già stati assegnati a una raccolta di siti di configurazione trunk e ogni sito (e ogni servizio) può ospitare solo una di queste raccolte. In questo caso, puoi eliminare la raccolta esistente e creare una nuova raccolta oppure semplicemente modificare la raccolta esistente.

4.  Nella finestra di dialogo **nuova configurazione trunk** eseguire le selezioni appropriate e quindi fare clic su **OK**.

5.  La proprietà **state** per la raccolta verrà aggiornata in **UNCOMMITTED**. Per eseguire il commit delle modifiche e per eliminare la raccolta, fare clic su **commit** e quindi su **commit tutti**.

6.  Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** fare clic su **OK**.

7.  Nella finestra di dialogo **Pannello di controllo di Microsoft Lync Server 2013** fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

