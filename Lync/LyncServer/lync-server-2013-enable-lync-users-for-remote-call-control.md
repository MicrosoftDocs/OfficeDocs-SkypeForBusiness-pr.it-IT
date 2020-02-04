---
title: 'Lync Server 2013: Abilitare gli utenti di Lync per il controllo delle chiamate remote'
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
ms.openlocfilehash: 260cfc2d3a0b185d58e90f4944162ea23135a0b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736236"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Abilitare gli utenti di Lync per il controllo delle chiamate remote in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Puoi configurare gli utenti di Lync per il controllo delle chiamate remote usando i criteri di provisioning in banda basati su server. È possibile gestire le impostazioni di provisioning in banda tramite il pannello di controllo di Lync Server o l'interfaccia della riga di comando di Lync Server Management Shell. Questi strumenti sostituiscono lo snap-in Strumentazione gestione Windows (WMI) usato per gestire le impostazioni dei criteri di gruppo nelle versioni precedenti.

Se si preferisce consentire agli utenti di configurare le proprie impostazioni di controllo delle chiamate remote in Lync, è possibile configurare le impostazioni del controllo delle chiamate remote per gli utenti nel server senza specificare l' **URI del server di linea** e i valori degli URI di **linea** . Assicurati di comunicare agli utenti l' **URI del server di linea** e i valori **URI** di linea appropriati e fornisci agli utenti le istruzioni per configurare queste impostazioni. Per la procedura per configurare manualmente il controllo delle chiamate remote in Lync Server, vedere "impostare le opzioni e i <http://go.microsoft.com/fwlink/p/?linkid=210132> numeri dei telefoni" nella documentazione del client Lync nel sito Web di Microsoft Office.

Se si dispone di una distribuzione di Communications Server 2007 R2 o Communications Server 2007 esistente, i client Communicator 2007 R2 e Communicator 2007 continueranno a usare criteri di gruppo durante la migrazione affiancata. Tuttavia, se si vuole che le impostazioni dei criteri vengano riportate ai client Lync, è necessario configurare le equivalenti impostazioni di provisioning in banda di Lync Server.

<div>


> [!NOTE]  
> Per abilitare un utente per il controllo delle chiamate remote, è necessario specificare all'utente sia un URI di linea che un URI del server di linea. Come descritto in <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013</A>, è necessario assicurarsi di usare la sintassi richiesta dal gateway per queste impostazioni.<BR>Assicurarsi che il dominio nell'URI del server di linea sia lo stesso del dominio di destinazione specificato nel parametro MatchUri quando è stata configurata la route statica per il gateway.<BR>L'URI di linea specifica il numero di telefono assegnato all'utente nel formato E. 164, con il prefisso "TEL:", ad esempio Tel: + 14255550150. Se si vuole configurare un numero di interno, il formato è Tel: + 14255550150; ext = 111. Se l'URI di linea dell'utente è stato configurato in precedenza e il valore non è stato modificato, non è necessario specificare l'URI di linea quando si Abilita l'utente per il controllo delle chiamate remote.



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>Per abilitare il controllo delle chiamate remote per gli utenti abilitati a Lync tramite Management Shell

1.  Accedere a un computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o come ruolo di controllo di accesso basato sui ruoli a cui è stato assegnato il cmdlet **Set-CsUser** .

2.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

3.  Per usare il cmdlet **Set-CsUser** per configurare il controllo delle chiamate remote per un utente abilitato a Lync esistente, eseguire le operazioni seguenti:
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    Ad esempio:
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Per configurare gli utenti per il controllo delle chiamate remote tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** Digitare All (o la prima parte) del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) line dell'account utente desiderato, quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si vuole modificare.

6.  Nel menu **modifica** fare clic su **modifica**.

7.  In **telefonia**eseguire una delle operazioni seguenti:
    
      - Per abilitare il controllo delle chiamate remote per consentire all'utente di controllare il proprio telefono PBX (Private Branch Exchange) da Lync 2013 per effettuare chiamate audio da PC a PC e chiamate da PC a telefono, fare clic su **controllo delle chiamate remote**. In **URI linea**specificare il numero di telefono dell'utente. In **URI del server di linea**specificare l'URI SIP del gateway SIP/CSTA.
    
      - Per abilitare il controllo delle chiamate remote, ma disabilitare le chiamate audio da PC a PC e per consentire solo all'utente di controllare il proprio telefono PBX da Lync 2013 per effettuare chiamate da PC a telefono, fare clic su **solo controllo chiamata remota**. In **URI linea**specificare il numero di telefono dell'utente. In **URI del server di linea**specificare l'URI SIP del gateway SIP/CSTA.

8.  Al termine, fare clic su **commit**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

