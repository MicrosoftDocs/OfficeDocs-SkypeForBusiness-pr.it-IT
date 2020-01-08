---
title: "Lync Server 2013: disabilitare o riattivare l'account utente per Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974112"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Disabilitare o riattivare l'account utente per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-04-04_

È possibile usare la procedura seguente per disabilitare un account utente abilitato in precedenza in Lync Server 2013 senza perdere le impostazioni di Lync Server configurate per l'account utente. Poiché non si perdono le impostazioni dell'account utente di Lync Server, è possibile riattivare nuovamente un account utente abilitato in precedenza senza dover riconfigurare l'account utente.

<div>


> [!WARNING]  
> La semplice disabilitazione di un account utente in Active Directory <STRONG>non</STRONG> impedirà a un utente di accedere o usare Lync Server. Questo perché Lync usa l'autenticazione dei certificati che semplifica il processo di autenticazione e questi certificati client sono validi per 180 giorni. Se si vuole interrompere l'accesso a Lync Server per gli account di Active Directory abilitati per Lync, è necessario utilizzare il cmdlet <STRONG>Disable-CsUser</STRONG> oppure usare il <STRONG>Pannello di controllo di Lync Server</STRONG> come disposto in questo articolo. Quando l'utente è disabilitato in Lync e l'archivio di gestione centrale è stato replicato nell'ambiente, gli utenti non potranno più eseguire l'accesso. Inoltre, gli utenti che hanno eseguito l'accesso verranno disconnessi.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Per disabilitare o riattivare un account utente abilitato in precedenza per Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o la prima parte del nome visualizzato, nome, cognome, nome account di Security Accounts Manager (Sam), indirizzo SIP o URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o riabilitare e quindi fare clic su **trova**.

5.  Nella tabella fare clic sull'account utente che si vuole disabilitare o riattivare.

6.  Nel menu **azione** eseguire una delle operazioni seguenti:
    
      - Per disabilitare temporaneamente l'account utente per Lync Server 2013, fare clic su **Disabilita temporaneamente per Lync Server**.
    
      - Per abilitare l'account utente per Lync Server 2013, fare clic su **riattiva per Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Uso di Windows PowerShell per disabilitare o riattivare gli account utente

Gli account utente possono essere temporaneamente disabilitati e quindi riattivati in seguito usando il cmdlet **Set-CsUser** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-disable-a-user-account"></a>Per disabilitare un account utente

  - Per disabilitare temporaneamente un account utente, imposta il valore della proprietà Enabled su false ($False). Ad esempio:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Per riattivare un account utente

  - Per riattivare un account utente disabilitato, imposta il valore della proprietà Enabled su true ($True). Ad esempio:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Aggiungere e abilitare l'account utente per Lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Abilitazione e disabilitazione degli utenti per Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

