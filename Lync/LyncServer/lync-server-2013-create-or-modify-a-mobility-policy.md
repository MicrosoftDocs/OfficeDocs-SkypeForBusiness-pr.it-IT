---
title: 'Lync Server 2013: creare o modificare un criterio di mobilità'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976501"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Creare o modificare un criterio di mobilità in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

È possibile creare o modificare i criteri di mobilità per consentire agli utenti mobili di usare i dispositivi mobili supportati per le funzionalità di Lync, ad esempio messaggistica istantanea, presenza e contatti. È possibile creare o modificare i criteri di mobilità dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Per creare un criterio di mobilità con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri di mobilità** .

4.  Nella pagina **criteri di mobilità** fare clic su **nuovo**ed eseguire una delle operazioni seguenti:
    
    1.  Per creare un criterio di mobilità del sito, fare clic su **criteri sito**, fare clic su un sito, fare clic su **OK**, rivedere le impostazioni predefinite e, se si vuole, apportare le modifiche desiderate.
    
    2.  Per creare un criterio per la mobilità degli utenti, fare clic su **criteri utente**, digitare un nome, rivedere le impostazioni predefinite e, se si vuole, apportare le modifiche desiderate.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Per modificare un criterio di mobilità con il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento dei **criteri di mobilità** .

4.  Nella pagina **criteri di mobilità** fare clic su uno dei criteri di mobilità esistenti.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  Modificare le impostazioni.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Creazione di criteri di accesso esterno con i cmdlet di Windows PowerShell

È possibile creare criteri di mobilità (nell'ambito del sito o nell'ambito per utente) usando Windows PowerShell e il cmdlet **New-CsMobilityPolicy** . Inoltre, puoi usare il cmdlet **Set-CsMobilityPolicy** per modificare i criteri esistenti, inclusi i criteri globali. Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>Per creare un criterio di mobilità nell'ambito del sito

  - Questo comando crea un nuovo criterio di mobilità per il sito Redmond:
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, i criteri utilizzeranno i valori predefiniti per tutte le relative proprietà.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>Per creare un criterio di mobilità nell'ambito per utente

  - Per creare un criterio di mobilità nell'ambito per utente, specificare un'identità univoca per il criterio:
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>Per modificare un valore di proprietà singola durante la creazione di un criterio di mobilità

  - Per creare criteri che usano valori di proprietà diversi, includere il parametro e il valore del parametro appropriati. Ad esempio, questo comando crea i criteri di mobilità che disabilitano la chiamata tramite lavoro:
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>Per modificare più valori di proprietà durante la creazione di un criterio di mobilità

  - Più valori di proprietà possono essere modificati includendo più parametri. Ad esempio, questo comando crea un criterio che disattiva sia la mobilità che la chiamata tramite lavoro:
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

Per informazioni dettagliate, vedere l'argomento della Guida per i cmdlet [New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) e [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione dei criteri per dispositivi mobili in Lync Server 2013](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

