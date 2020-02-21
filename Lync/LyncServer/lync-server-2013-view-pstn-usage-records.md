---
title: 'Lync Server 2013: visualizzare i record di utilizzo PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6c6ca5761959b8b98cb4eb6a8f17e87c543e788
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211692"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Visualizzare i record di utilizzo PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-22_

Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata (ad esempio, interna, locale o interurbana) che può essere effettuata da diversi utenti o gruppi di utenti di un'organizzazione. Per informazioni dettagliate, vedere [PSTN Usage Records in Lync Server 2013](lync-server-2013-pstn-usage-records.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Routing vocale** e quindi su **Utilizzo PSTN**.

4.  Nella pagina **Utilizzo PSTN** evidenziare i record di utilizzo PSTN che si desidera visualizzare, fare clic su **Modifica** e quindi su **Mostra dettagli**.
    
    <div>
    

    > [!NOTE]  
    > In una pagina di sola lettura per il record di utilizzo PSTN selezionato vengono visualizzati le route e i criteri vocali associati.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell

È inoltre possibile visualizzare gli utilizzi PSTN utilizzando Windows PowerShell e il cmdlet **Get-CsPstnUsage** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Per visualizzare le informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell

  - Per visualizzare informazioni su tutti gli utilizzi PSTN, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsPstnUsage
    
    Il comando restituisce informazioni simili a quelle riportate di seguito:
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

Per informazioni dettagliate, vedere [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

