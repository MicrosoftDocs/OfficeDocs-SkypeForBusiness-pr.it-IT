---
title: 'Lync Server 2013: modificare o configurare URL semplici'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61462b7910375959e002938a91efa27d8d45c988
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533363"
---
# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Modificare o configurare URL semplici in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-04_

Per questa procedura non è necessaria l'appartenenza a un gruppo di amministratori locali o di dominio privilegiato, ma è consigliabile accedere a un computer come utente standard.

Lync Server 2013 utilizza URL semplici per indirizzare le chiamate interne ed esterne ai servizi nel front end server o nel Director, se ne è stata distribuita una. Per ulteriori informazioni sugli URL semplici, vedere [Planning for Simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) nella documentazione relativa alla pianificazione. È possibile selezionare il formato per gli URL semplici da diverse opzioni. Per informazioni dettagliate su queste opzioni, vedere [DNS requirements for Simple URLs in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) nella documentazione relativa alla pianificazione.

Per impostazione predefinita, gli URL semplici verranno configurati nel formato (ad esempio, l'URL semplice in accesso esterno): https://dialin .\<SIP Domain\>

<div>

## <a name="to-configure-simple-urls"></a>Per configurare gli URL semplici

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.

2.  Nel riquadro **URL semplici** selezionare URL di **accesso telefonico:** (chiamata in ingresso) o URL di **riunione:** (Meet) per modificare e quindi fare clic su **modifica URL**.

3.  Aggiornare l'URL in base al valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. Nell'esempio riportato di seguito è stato modificato l'URL di accesso esterno in https://pool01.contoso.net/dialin .

4.  Se necessario, modificare l'URL riunione eseguendo la stessa procedura.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Per definire l'URL semplice facoltativo per l'accesso amministrativo

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.

2.  Nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.
    
    <div>
    

    > [!TIP]  
    > È consigliabile utilizzare l'URL più semplice possibile per l'accesso amministrativo. L'opzione più semplice è <STRONG> https://admin .</STRONG> &lt; dominio &gt; .

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario considerare quali modifiche influiscono sui record DNS (Domain Name System) e sui certificati per gli URL semplici. Se la modifica influisce sulla base di un URL semplice, sarà necessario modificare anche i record DNS e i certificati. Ad esempio, https://lync.contoso.com/Meet se si cambia da per cambiare https://meet.contoso.com l'URL di base da lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati in modo che facciano riferimento a meet.contoso.com. Se l'URL semplice è stato modificato da https://lync.contoso.com/Meet a https://lync.contoso.com/Meetings , l'URL di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche a DNS o certificati. Ogni volta che si modifica un nome URL semplice, è necessario eseguire il cmdlet <STRONG>Enable-CsComputer</STRONG> su ogni Director e front end server per registrare la modifica.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Pianificazione degli URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

