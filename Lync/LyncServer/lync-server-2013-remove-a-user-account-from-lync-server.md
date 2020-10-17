---
title: 'Lync Server 2013: rimuovere un account utente da Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a user account from Lync Server
ms:assetid: 2f512aba-e358-45ae-af58-74312ee9c514
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688008(v=OCS.15)
ms:contentKeyID: 49733596
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 782077cc532dc751076d3152467de865fe799a29
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536513"
---
# <a name="remove-a-user-account-from-lync-server-2013"></a>Rimuovere un account utente da Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

È possibile utilizzare la procedura seguente per rimuovere un account utente aggiunto in precedenza in Lync Server 2013.

<div>


> [!NOTE]  
> La rimozione di un utente comporterà la perdita delle impostazioni configurate per l'account utente. Se invece si desidera disabilitare temporaneamente un account utente, vedere l'argomento <A href="lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md">disabilitare o riabilitare l'account utente per Lync Server 2013</A>.



</div>

<div>

## <a name="to-remove-a-user-account-by-using-lync-server-management-shell"></a>Per rimuovere un account utente utilizzando Lync Server Management Shell

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Utenti**.

4.  Nella casella **Cerca utenti** digitare anche solo la prima parte del nome visualizzato, nome, cognome, nome dell'account Gestione account di protezione, indirizzo SIP o URI (Uniform Resource Identifier) di linea dell'account utente da disabilitare o riabilitare e quindi fare clic su **Trova**.

5.  Nella tabella fare clic sull'account utente da rimuovere.

6.  Nel menu **Azione** selezionare **Rimuovi da Lync Server**. Verrà visualizzata una finestra di dialogo.

7.  Dalla finestra di dialogo selezionare **OK** per rimuovere l'utente.

</div>

<div>

## <a name="removing-user-accounts-by-using-windows-powershell-cmdlets"></a>Rimozione degli account utente tramite i cmdlet di Windows PowerShell

È possibile rimuovere gli account utente utilizzando il cmdlet Disable-CsUser. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-user-account"></a>Per rimuovere un account utente

  - Per rimuovere un account utente, usare il cmdlet Disable-CsUser. Ad esempio:
    
        Disable-CsUser -Identity "Ken Myer"
    
    Dopo aver eseguito questo comando, non sarà più possibile riabilitare l'account e le relative impostazioni precedenti. Sarà invece necessario usare il cmdlet Enable-CsUser per creare un account completamente nuovo per Davide Garghentini.

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/Disable-CsUser) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Disabilitare o riabilitare l'account utente per Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  


[Abilitazione e disabilitazione degli utenti per Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

