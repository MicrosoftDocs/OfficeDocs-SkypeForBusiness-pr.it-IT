---
title: 'Lync Server 2013: Configurare componenti aggiuntivi per le chat room'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure add-ins for rooms
ms:assetid: 4eeaf19e-8369-4f6f-af65-a283cf7daa1c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204878(v=OCS.15)
ms:contentKeyID: 48184090
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8389f72394be26057eb12560c054bd5292b528f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-add-ins-for-rooms-in-lync-server-2013"></a>Configurare componenti aggiuntivi per le chat room in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-21_

Nel pannello di controllo di Lync Server 2013 è possibile usare la sezione **componente aggiuntivo** della pagina della **chat persistente** per associare gli URL alle chat room permanenti. Questi URL vengono visualizzati nel client Lync 2013 nella chat room nel riquadro Extensibility delle conversazioni. Un amministratore deve aggiungere componenti aggiuntivi all'elenco di componenti aggiuntivi registrati e i responsabili/creatori della chat room devono associare le camere a uno dei componenti aggiuntivi registrati prima che gli utenti possano vedere questo aggiornamento nel client Lync 2013.

I componenti aggiuntivi sono usati per ampliare l'esperienza all'interno della chat. Un componente aggiuntivo tipico può includere un URL che punta a un'applicazione Silverlight che intercetta quando un ticker del titolo viene inserito in una chat room e Mostra la cronologia del titolo nel riquadro estensibilità. Altri esempi sono l'incorporamento di un URL di OneNote 2013 nella chat room come componente aggiuntivo per includere contenuto condiviso, ad esempio "In primo piano" o "Argomento del giorno".

<div>

## <a name="to-configure-add-ins-for-chat-rooms"></a>Per configurare componenti aggiuntivi per le chat room

1.  Da un account utente assegnato al ruolo CsPersistentChatAdministrator o CsAdministrator, accedere a un qualsiasi computer nella distribuzione interna.

2.  Nel menu **Start** selezionare il pannello di controllo di Lync Server o aprire una finestra del browser e quindi immettere l'URL dell'amministratore. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).
    
    <div>
    

    > [!IMPORTANT]  
    > È anche possibile usare i cmdlet di Windows PowerShell. Per informazioni dettagliate, vedere <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">configurazione del server di chat persistente tramite i cmdlet di Windows PowerShell</A> nella documentazione relativa alla distribuzione.

    
    </div>

3.  Sulla barra di spostamento sinistra fare clic su **Chat persistente** e quindi su **Componente aggiuntivo**.
    
    Per più distribuzioni di pool di server di chat persistenti, selezionare il pool appropriato nell'elenco a discesa.

4.  Nella pagina **Componente aggiuntivo** fare clic su **Nuovo**.

5.  In **Seleziona un servizio**selezionare il servizio corrispondente al pool del server di chat persistente in cui è necessario creare il componente aggiuntivo. I componenti aggiuntivi non possono essere spostati da un pool a un altro o condivisi da pool diversi.

6.  In **Nuovo componente aggiuntivo** eseguire le operazioni seguenti:
    
      - In **Nome** specificare un nome per il nuovo componente aggiuntivo.
    
      - In **URL** specificare l'URL da associare al componente aggiuntivo. Gli URL devono limitarsi ai protocolli http e https.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Aprire gli strumenti di amministrazione di Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md)  


[Configurazione del server Chat persistente tramite i cmdlet di Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

