---
title: 'Lync Server 2013: abilitazione del controllo di ammissione alle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling call admission control
ms:assetid: 015f5c8f-2f90-4b9e-8149-b33767e90582
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520942(v=OCS.15)
ms:contentKeyID: 48183228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20cd0f7792f8db2cf1b2d817bfe79ed6d6b16fce
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-call-admission-control-in-lync-server-2013"></a>Abilitazione del controllo di ammissione alle chiamate in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Il servizio Controllo di ammissione di chiamata è una rete di aree, siti e subnet che consentono di applicare restrizioni alle trasmissioni audio e video in base alla larghezza di banda disponibile. Dopo aver configurato la rete CAC, è necessario abilitare CAC per applicare le limitazioni della larghezza di banda. Per eseguire questa operazione, è possibile usare il pannello di controllo di Lync Server.

<div>

## <a name="to-enable-cac-from-lync-server-control-panel"></a>Per abilitare CAC dal pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.

4.  Nella pagina **globale** fare clic sulla configurazione **globale** .
    
    <div>
    

    > [!NOTE]  
    > Solo una rete può essere configurata per qualsiasi distribuzione di Microsoft Lync Server 2013, quindi non ci saranno mai più configurazioni di rete nell'elenco. Non è possibile rinominare la configurazione globale.

    
    </div>

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Nella pagina **Modifica impostazioni globali** selezionare la casella di **controllo Abilita l'ammissione alle chiamate** e quindi fare clic su **conferma**.

Quando si fa clic su **commit**, si esegue un test della configurazione. La finestra di dialogo **Modifica impostazioni globali** viene chiusa, tornando alla pagina **globale** . Verrà visualizzato un messaggio di avviso in caso di errori o incongruenze individuati nella configurazione di rete che ne impediscono il corretto funzionamento, ad esempio se ogni area geografica non è connessa a tutte le altre aree geografiche tramite una route interregion.

Se si apportano modifiche alla configurazione di rete, è possibile eseguire di nuovo il controllo di convalida aprendo la configurazione globale e facendo clic su **commit**. Non è necessario disabilitare prima CAC: tenere selezionata la casella di controllo e fare clic su **conferma**. Puoi eseguire questa operazione in qualsiasi momento senza apportare modifiche alla configurazione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Panoramica del controllo di ammissione alle chiamate in Lync Server 2013](lync-server-2013-overview-of-call-admission-control.md)  


[Pianificazione del servizio Controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md)  
[Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Get-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkConfiguration)  
[Set-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkConfiguration)  
[Remove-CsNetworkConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

