---
title: 'Lync Server 2013: pubblicare le modifiche in sospeso alla configurazione del routing vocale'
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
ms.openlocfilehash: 86444047759c2eab605d8791a6445329651ad43f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-lync-server-2013"></a>Pubblicare le modifiche in sospeso alla configurazione del routing vocale in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-08-07_

Dopo aver apportato modifiche alle impostazioni di configurazione nelle pagine del gruppo **Routing vocale**, eseguire questa procedura per esaminare, pubblicare o annullare le modifiche in sospeso.

<div>


> [!IMPORTANT]  
> Verificare che un solo utente alla volta modifichi le impostazioni di configurazione di Routing vocale.<BR>Tutte le modifiche in sospeso devono essere pubblicate contemporaneamente eseguendo il comando <STRONG>Salva tutto</STRONG>. Non è possibile pubblicare selettivamente le modifiche in sospeso. Prima di pubblicare le modifiche in sospeso, eseguire il comando <STRONG>Rivedi modifiche di cui non è stato eseguito il commit</STRONG> e annullare qualsiasi modifica di configurazione che non si desidera pubblicare.<BR>Se si esce dalle pagine del gruppo <STRONG>Routing vocale</STRONG> prima di eseguire il commit delle modifiche in sospeso, tutte le modifiche in sospeso andranno perse. Tuttavia, è possibile esportare la configurazione corrente (incluse le modifiche in sospeso) in un file di configurazione vocale e quindi importare e pubblicare la configurazione aggiornata. Per ulteriori informazioni, vedere <A href="lync-server-2013-export-a-voice-route-configuration-file.md">esportare un file di configurazione di route vocali in Lync Server 2013</A>.



</div>

<div>

## <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Per rivedere, pubblicare o annullare le modifiche di configurazione del routing vocale

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale**.

4.  Apportare le modifiche della configurazione desiderate alle impostazioni in ogni pagina del gruppo **Routing vocale**.

5.  Per rivedere le modifiche in sospeso senza pubblicarle, scegliere **Rivedi modifiche di cui non è stato eseguito il commit** dal menu **Commit**.

6.  Se si desidera annullare qualsiasi modifica in sospeso, effettuare una delle operazioni seguenti:
    
      - Scegliere **Annulla tutte le modifiche di cui non è stato eseguito il commit** dal menu **Commit**.
    
      - Spostarsi sulla scheda della pagina **Routing vocale** che include le modifiche in sospeso che si desidera annullare, selezionare l'elemento con le modifiche in sospeso, fare clic su **Commit** e quindi su **Annulla modifiche selezionate**.

7.  Dopo aver rivisto tutte le modifiche in sospeso e annullato ogni modifica che non si desidera pubblicare, fare clic su **Commit** e quindi su **Salva tutto**.

8.  Nella finestra di dialogo **Impostazioni di configurazione vocale di cui non è stato eseguito il commit** in cui è visualizzato un elenco delle modifiche in sospeso fare clic su **OK**.
    
    Quando il pannello di controllo di Lync Server ha eseguito il commit delle modifiche, viene visualizzato il messaggio di **configurazione del routing vocale pubblicato correttamente** .

</div>

</div>

<span> </span>

</div>

</div>

</div>

