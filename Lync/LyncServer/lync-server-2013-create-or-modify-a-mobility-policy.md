---
title: 'Lync Server 2013: creare o modificare un criterio per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 469b7789de98cee3d399e09c9cec4396fdb365e9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Creare o modificare un criterio per dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile creare o modificare i criteri di mobilità per consentire agli utenti mobili di utilizzare i dispositivi mobili supportati per le funzionalità di Lync, quali messaggistica istantanea, presenza e contatti. È possibile creare o modificare i criteri per dispositivi mobili dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Per creare un criterio per dispositivi mobili con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri per dispositivi mobili** .

4.  Nella pagina **criteri dispositivi mobili** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:
    
    1.  Per creare un criterio per dispositivi mobili per il sito, fare clic su **criteri sito**, fare clic su un sito, fare clic su **OK**, rivedere le impostazioni predefinite e, se si desidera, apportare eventuali modifiche.
    
    2.  Per creare un criterio per dispositivi mobili per gli utenti, fare clic su **criteri utente**, digitare un nome, esaminare le impostazioni predefinite e, se lo si desidera, apportare eventuali modifiche.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Per modificare un criterio per dispositivi mobili con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri per dispositivi mobili** .

4.  Nella pagina **criteri dispositivi mobili** fare clic su uno dei criteri per dispositivi mobili esistenti.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  Modificare le impostazioni.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Creazione di criteri di accesso esterno tramite i cmdlet di Windows PowerShell

È possibile creare i criteri per dispositivi mobili (nell'ambito del sito o nell'ambito per utente) utilizzando Windows PowerShell e il cmdlet **New-CsMobilityPolicy** . Inoltre, è possibile utilizzare il cmdlet **Set-CsMobilityPolicy** per modificare i criteri esistenti, inclusi i criteri globali. Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Per creare un criterio per dispositivi mobili nell'ambito del sito

  - Questo comando consente di creare un nuovo criterio per dispositivi mobili per il sito Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Poiché nel comando precedente non sono stati specificati parametri (oltre al parametro Identity obbligatorio), i criteri utilizzeranno i valori predefiniti per tutte le proprietà.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Per creare un criterio per dispositivi mobili nell'ambito per utente

  - Per creare un criterio per dispositivi mobili nell'ambito per utente, specificare un'identità univoca per il criterio:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Per modificare un singolo valore di proprietà durante la creazione di un criterio per dispositivi mobili

  - Per creare criteri che utilizzano valori di proprietà diversi, includere il parametro e il valore del parametro corretti. Ad esempio, questo comando consente di creare i criteri per dispositivi mobili che disabilitano la chiamata tramite lavoro:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Per modificare più valori di proprietà durante la creazione di un criterio per dispositivi mobili

  - È possibile modificare più valori di proprietà includendo più parametri. Ad esempio, questo comando consente di creare un criterio che Disabilita sia la mobilità che la chiamata tramite lavoro:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) e [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di criteri per dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

