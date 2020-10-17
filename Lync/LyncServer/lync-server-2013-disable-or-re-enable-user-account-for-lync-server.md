---
title: "Lync Server 2013: disabilitare o riabilitare l'account utente per Lync Server"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 646f4ae59ce5058af84c0e5ddd3197f7a9f47fe7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528993"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Disabilitare o riabilitare l'account utente per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-04-04_

È possibile utilizzare la procedura seguente per disabilitare un account utente abilitato in precedenza in Lync Server 2013 senza perdere le impostazioni di Lync Server configurate per l'account utente. Poiché le impostazioni dell'account utente di Lync Server non vengono perse, è possibile riattivare nuovamente un account utente abilitato in precedenza senza dover riconfigurare l'account utente.

<div>


> [!WARNING]  
> La semplice disabilitazione di un account utente in Active Directory <STRONG>non</STRONG> impedirà a un utente di accedere o utilizzare Lync Server. Ciò è dovuto al fatto che Lync utilizza l'autenticazione dei certificati per semplificare il processo di autenticazione e questi certificati client sono validi per 180 giorni. Se si desidera arrestare gli account di Active Directory disabilitati che sono stati abilitati per Lync dall'accesso a Lync Server, è necessario utilizzare il cmdlet <STRONG>Disable-CsUser</STRONG> oppure utilizzare il <STRONG>Pannello di controllo di Lync Server</STRONG> come indicato in questo articolo. Dopo che l'utente è stato disabilitato in Lync e l'archivio di gestione centrale è stato replicato nell'ambiente, gli utenti non saranno più in grado di eseguire l'accesso. Inoltre, gli utenti che hanno effettuato l'accesso verranno disconnessi.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Per disabilitare o riabilitare un account utente abilitato in precedenza per Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare tutto o solo la prima parte del nome visualizzato, del nome, del cognome, del nome di account SAM (Security Accounts Manager), dell'indirizzo SIP o dell'URI (Uniform Resource Identifier) linea dell'account utente che si desidera disabilitare o abilitare di nuovo e quindi fare clic su **Trova**.

5.  Nella tabella fare clic sull'account utente che si desidera disabilitare o abilitare di nuovo.

6.  Dal menu **Azione** scegliere uno dei comandi seguenti:
    
      - Per disabilitare temporaneamente l'account utente per Lync Server 2013, fare clic su **Disabilita temporaneamente per Lync Server**.
    
      - Per abilitare l'account utente per Lync Server 2013, fare clic su **riattiva per Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Utilizzo di Windows PowerShell per disabilitare o riabilitare gli account utente

Gli account utente possono essere temporaneamente disattivati e quindi riattivati in un secondo momento utilizzando il cmdlet **Set-CsUser** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-disable-a-user-account"></a>Per disabilitare un account utente

  - Per disabilitare temporaneamente un account utente, impostare il valore della proprietà Enabled su false ($False). Ad esempio:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Per riattivare un account utente

  - Per riattivare un account utente disabilitato, impostare il valore della proprietà Enabled su true ($True). Ad esempio:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

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

