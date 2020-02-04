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
ms.openlocfilehash: b2551c8bbc40429d7e5bc4af45cae862991381a8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756680"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Visualizzare i record di utilizzo PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

Un record di utilizzo PSTN (Public Switched Telephone Network) specifica una classe di chiamata, ad esempio Internal, local o Long Distance, che può essere eseguita da vari utenti o gruppi di utenti di un'organizzazione. Per informazioni dettagliate, vedere [record sull'utilizzo PSTN in Lync Server 2013](lync-server-2013-pstn-usage-records.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Per visualizzare un record di utilizzo PSTN tramite il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **routing vocale** e quindi su **utilizzo PSTN**.

4.  Nella pagina **uso PSTN** evidenziare il record di utilizzo PSTN che si vuole visualizzare, fare clic su **modifica** e quindi su **Mostra dettagli**.
    
    <div>
    

    > [!NOTE]  
    > Una pagina di sola lettura del record di utilizzo PSTN selezionato Mostra le route associate e i criteri vocali associati.

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell

È anche possibile visualizzare gli usi PSTN tramite Windows PowerShell e il cmdlet **Get-CsPstnUsage** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Per visualizzare le informazioni sull'utilizzo PSTN tramite i cmdlet di Windows PowerShell

  - Per visualizzare informazioni su tutti gli usi PSTN, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsPstnUsage
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
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

