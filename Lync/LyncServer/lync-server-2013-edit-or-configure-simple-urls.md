---
title: 'Lync Server 2013: Modificare o configurare URL semplici'
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
ms.openlocfilehash: 0fe6ae7197e2f47c590384547c34dd4b1db50950
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Modificare o configurare URL semplici in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-04_

Questa procedura non richiede l'appartenenza a un amministratore locale o a un gruppo di domini privilegiati. È necessario accedere a un computer come utente standard.

Lync Server 2013 usa URL semplici per indirizzare chiamate interne ed esterne ai servizi nel server front-end o nel Director, se uno è stato distribuito. Per altre informazioni sugli URL semplici, vedere [pianificazione di URL semplici in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) nella documentazione relativa alla pianificazione. Puoi selezionare il formato per i tuoi URL semplici da diverse opzioni. Per informazioni dettagliate su queste opzioni, vedere [requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) nella documentazione relativa alla pianificazione.

Per impostazione predefinita, gli URL semplici verranno configurati in forma di (ad esempio, l'URL semplice in accesso esterno https://dialin.\<SIP ): Domain\>

<div>

## <a name="to-configure-simple-urls"></a>Per configurare gli URL semplici

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.

2.  Nel riquadro **URL semplici** selezionare **URL di accesso telefonico:** (chiamata in ingresso) o URL delle **riunioni: (riunione** ) per modificare e quindi fare clic su **modifica URL**.

3.  Aggiornare l'URL con il valore desiderato e quindi fare clic su **OK** per salvare l'URL modificato. L'esempio illustrato in questo articolo ha modificato l'URL di accesso https://pool01.contoso.net/dialinesterno a.

4.  Modificare l'URL di riunione usando la stessa procedura, se necessario.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Per definire l'URL semplice amministratore facoltativo

1.  In Generatore di topologie fare clic con il pulsante destro del mouse sul nodo **Lync Server** e quindi scegliere **modifica proprietà**.

2.  Nella casella **URL di accesso amministrativo** immettere l'URL semplice desiderato per l'accesso amministrativo al pannello di controllo di Lync Server 2013 e quindi fare clic su **OK**.
    
    <div>
    

    > [!TIP]  
    > È consigliabile usare l'URL più semplice possibile per l'URL di amministratore. L'opzione più semplice è <STRONG> https://admin.</STRONG> &lt;domain&gt;.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Se si modifica un URL semplice dopo la distribuzione iniziale, è necessario essere consapevoli delle modifiche che incidono sui record DNS (Domain Name System) e sui certificati per gli URL semplici. Se la modifica ha un impatto sulla base di un URL semplice, è necessario modificare anche i record DNS e i certificati. Ad esempio, passando da https://lync.contoso.com/Meet per https://meet.contoso.com cambiare l'URL di base da Lync.contoso.com a meet.contoso.com, è necessario modificare i record DNS e i certificati per fare riferimento a meet.contoso.com. Se è stato modificato l'URL https://lync.contoso.com/Meet semplice https://lync.contoso.com/Meetings, l'url di base di Lync.contoso.com rimane invariato, quindi non sono necessarie modifiche DNS o di certificato. Ogni volta che si modifica un nome di URL semplice, è necessario eseguire il cmdlet <STRONG>Enable-CsComputer</STRONG> su ogni Director e front end server per registrare la modifica.

    
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

