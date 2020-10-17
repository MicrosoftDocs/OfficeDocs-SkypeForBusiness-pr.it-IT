---
title: 'Lync Server 2013: eliminazione dei profili dei criteri di larghezza di banda di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f43f8c6aae2dec5ea55463c1896f327f008980
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525353"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a>Eliminazione dei profili dei criteri di larghezza di banda di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

In Controllo di ammissione di chiamata (CAC) i criteri di larghezza di banda vengono utilizzati per definire le limitazioni della larghezza di banda per alcune modalità. In Microsoft Lync Server 2013, è possibile assegnare limitazioni della larghezza di banda solo alle modalità audio e video. È possibile impostare limitazioni della larghezza di banda globali o per le sessioni. È possibile utilizzare il pannello di controllo di Lync Server per creare, modificare o eliminare un profilo contenitore per questi criteri. Usare le procedure seguenti per eliminare profili di criteri della larghezza di banda di rete. Per informazioni dettagliate sulla creazione o la modifica di un profilo dei criteri di larghezza di banda di rete, vedere [creating or Modifying Bandwidth Policy Profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a>Per eliminare un profilo di criteri della larghezza di banda

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Criteri larghezza di banda**.

4.  Nella pagina **Criteri larghezza di banda** fare clic sul profilo di criteri della larghezza di banda che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più profili contemporaneamente. A tale scopo, tenere premuto CTRL e selezionare i diversi profili. In alternativa, per selezionare tutti i profili, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.

    
    </div>

5.  Scegliere **Elimina** dal menu **Modifica**.
    
    <div>
    

    > [!WARNING]  
    > Non è possibile eliminare un profilo di criteri della larghezza di banda associato a un sito di rete. È necessario rimuovere l'associazione al sito di rete prima di poter eliminare il profilo. Per informazioni dettagliate su come modificare il sito di rete, vedere <A href="lync-server-2013-creating-or-modifying-network-sites.md">creazione o modifica di siti di rete in Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di profili di criteri di larghezza di banda in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[Visualizzazione delle informazioni sul profilo del criterio larghezza di banda di rete in Lync Server 2013](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[Configurare il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

