---
title: 'Lync Server 2013: visualizzazione delle informazioni sul profilo del criterio larghezza di banda di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08b8b984b1fd0c468f5ca340880ec294bf870e0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518313"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sul profilo del criterio larghezza di banda di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Microsoft Lync Server 2013, è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. È possibile utilizzare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Ogni profilo di criteri della larghezza di banda può essere associato a uno o più siti di rete. Utilizzare le procedure seguenti per visualizzare un profilo di criteri della larghezza di banda. Per creare o modificare un profilo dei criteri di larghezza di banda, vedere [creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a>Per visualizzare un profilo dei criteri di larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.

4.  Nella pagina **criteri larghezza di banda** fare clic sul profilo dei criteri di larghezza di banda che si desidera visualizzare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul profilo dei criteri di larghezza di banda di rete tramite i cmdlet di Windows PowerShell

I profili di larghezza di banda di rete possono essere visualizzati utilizzando Windows PowerShell e il cmdlet Get-CsNetworkBandwidthPolicyProfile. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a>Per visualizzare le informazioni sul profilo dei criteri di larghezza di banda

  - Per visualizzare informazioni su tutti i profili dei criteri di larghezza di banda di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkBandwidthPolicyProfile
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

Per ulteriori informazioni, vedere l'argomento della Guida per il cmdlet [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

