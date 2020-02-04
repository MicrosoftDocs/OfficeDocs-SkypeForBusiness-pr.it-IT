---
title: 'Lync Server 2013: pubblicare le modifiche in sospeso nella configurazione del routing vocale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish pending changes to the voice routing configuration
ms:assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413088(v=OCS.15)
ms:contentKeyID: 48185974
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aac5c30cb73ef428d0571a1a0fe6853dbf70db4c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724616"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Pubblicare le modifiche in sospeso nella configurazione di routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-08-07_

Dopo aver apportato le modifiche alle impostazioni di configurazione nelle pagine del gruppo **routing vocale** , eseguire questa procedura per rivedere, pubblicare o annullare le modifiche in sospeso.

<div>


> [!IMPORTANT]  
> Assicurarsi che solo un utente alla volta modifichi le impostazioni di configurazione del routing vocale.<BR>Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando <STRONG>commit tutti</STRONG> . Non è possibile pubblicare in modo selettivo le modifiche in sospeso. Prima di pubblicare le modifiche in sospeso, eseguire il comando <STRONG>revisione delle modifiche non salvate</STRONG> e annullare le modifiche di configurazione che non si desidera pubblicare.<BR>Se si esce dalle pagine del gruppo <STRONG>routing vocale</STRONG> prima di confermare le modifiche in sospeso, tutte le modifiche in sospeso andranno perse. È tuttavia possibile esportare la configurazione corrente (incluse le eventuali modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata. Per informazioni dettagliate, vedere <A href="lync-server-2013-export-a-voice-route-configuration-file.md">esportare un file di configurazione della route vocale in Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Per rivedere, pubblicare o annullare le modifiche alla configurazione del routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale**.

4.  Apportare le modifiche di configurazione desiderate alle impostazioni in ogni pagina del gruppo di **routing vocale** .

5.  Per rivedere le modifiche in sospeso senza pubblicarle, selezionare **rivedere le modifiche non salvate** dal menu **conferma** .

6.  Se si vuole annullare una delle modifiche in sospeso, eseguire una delle operazioni seguenti:
    
      - Selezionare **Annulla tutte le modifiche non salvate** dal menu **conferma** .
    
      - Passare alla scheda della pagina di **routing vocale** contenente le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **commit**e quindi su **Annulla modifiche selezionate**.

7.  Dopo aver esaminato tutte le modifiche in sospeso e annullato qualsiasi che non si vuole pubblicare, fare clic su **commit**e quindi su **commit tutti**.

8.  Nella finestra di dialogo **impostazioni di configurazione vocale non impegnata** , in cui viene visualizzato un elenco di tutte le modifiche in sospeso, fare clic su **OK**.
    
    Quando il pannello di controllo di Lync Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio di **configurazione del routing vocale pubblicato correttamente** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

