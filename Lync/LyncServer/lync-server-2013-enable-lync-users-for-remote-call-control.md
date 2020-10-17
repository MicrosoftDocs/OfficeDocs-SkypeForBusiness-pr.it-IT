---
title: 'Lync Server 2013: abilitare gli utenti di Lync per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37d5aa0b9f13f17dee91ff48048908cde3dbc2cf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528733"
---
# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

È possibile configurare gli utenti di Lync per il controllo delle chiamate remote utilizzando i criteri di provisioning in-band che sono basati su server. È possibile gestire le impostazioni di provisioning di tipo in-band utilizzando il pannello di controllo di Lync Server o l'interfaccia della riga di comando di Lync Server Management Shell. Questi strumenti sostituiscono lo snap-in Strumentazione gestione Windows (WMI) utilizzato per gestire le impostazioni di criteri di gruppo nelle versioni precedenti.

Se si preferisce consentire agli utenti di configurare le proprie impostazioni di controllo delle chiamate remote in Lync, è possibile configurare le impostazioni del controllo delle chiamate remote per gli utenti nel server senza specificare l' **URI di linea** e i valori **URI di linea** . Assicurarsi di comunicare gli **URI del server di linea** appropriato e gli URI di **linea** ai propri utenti e fornire agli utenti le istruzioni per la configurazione di tali impostazioni. Per la procedura di configurazione manuale del controllo delle chiamate remote in Lync Server, vedere la sezione relativa alla configurazione delle opzioni e dei numeri telefonici nella <https://go.microsoft.com/fwlink/p/?linkid=210132> documentazione relativa al client Lync nel sito Web di Microsoft Office.

Se si dispone di una distribuzione di Communications Server 2007 R2 o Communications Server 2007 esistente, i client Communicator 2007 R2 e Communicator 2007 continueranno a utilizzare criteri di gruppo durante la migrazione affiancata. Tuttavia, se si desidera che le impostazioni dei criteri vengano eseguite nei client Lync, è necessario configurare le impostazioni di provisioning in banda di Lync Server equivalenti.

<div>


> [!NOTE]  
> Per abilitare un utente per il controllo delle chiamate remote, è necessario fornire all'utente sia un URI di linea che un URI del server di linea. Come descritto in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013</A>, è necessario assicurarsi di utilizzare la sintassi necessaria per il gateway per queste impostazioni.<BR>Assicurarsi che il dominio nell'URI del server di linea sia lo stesso del dominio di destinazione specificato nel parametro MatchUri quando è stata configurata la route statica per il gateway.<BR>L'URI di linea specifica il numero di telefono assegnato all'utente nel formato E. 164, con il prefisso "TEL:", ad esempio Tel: + 14255550150. Se si desidera configurare un numero di interno, il formato è Tel: + 14255550150; ext = 111. Se l'URI di linea dell'utente è stato configurato in precedenza e il valore non è stato modificato, non è necessario specificare l'URI di linea quando si Abilita l'utente per il controllo delle chiamate remote.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Per abilitare il controllo delle chiamate remote per utenti con Lync abilitato utilizzando Management Shell

1.  Accedere a un computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o come ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **Set-CsUser** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

3.  Per utilizzare il cmdlet **Set-CsUser** per configurare il controllo delle chiamate remote per un utente esistente con Lync abilitato, effettuare le operazioni seguenti:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Ad esempio:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Per configurare gli utenti per il controllo delle chiamate remote utilizzando il Pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare tutto (o la prima parte) del nome visualizzato, del nome, del cognome, del nome account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente desiderato e quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si desidera modificare.

6.  Scegliere **Modifica** dal menu **Modifica**.

7.  In **Telefonia** effettuare una delle operazioni seguenti:
    
      - Per abilitare il controllo delle chiamate remote per consentire all'utente di controllare il proprio telefono PBX (Private Branch Exchange) da Lync 2013 per effettuare chiamate audio da PC a PC e chiamate da PC a telefono, fare clic su **Remote Call Control**. In **URI linea** specificare il numero di telefono dell'utente. In **URI server linea** specificare l'URI SIP del gateway SIP/CSTA.
    
      - Per abilitare il controllo delle chiamate remote, ma disabilitare le chiamate audio da PC a PC e per abilitare solo l'utente a controllare il proprio telefono PBX da Lync 2013 per effettuare chiamate da PC a telefono, fare clic su **solo controllo**delle chiamate remote. In **URI linea** specificare il numero di telefono dell'utente. In **URI server linea** specificare l'URI SIP del gateway SIP/CSTA.

8.  Al termine, fare clic su **Commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

