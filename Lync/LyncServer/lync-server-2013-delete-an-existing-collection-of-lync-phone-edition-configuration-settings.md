---
title: Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition
description: Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5137590a37b8bbb47f7445d20639157953597ca6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572862"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Se non si desidera più utilizzare una raccolta di impostazioni per i dispositivi che eseguono Lync Phone Edition, eliminarlo. Se si elimina una raccolta per un sito, le impostazioni globali saranno applicabili ai telefoni in quel sito. Non è possibile eliminare la raccolta globale.

<div>


> [!NOTE]
> Invece di eliminare una raccolta, è possibile modificare alcune delle impostazioni. Per informazioni dettagliate su come eseguire questa operazione, vedere <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Per eliminare una raccolta di impostazioni di configurazione di Lync Phone Edition

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Client**, quindi fare clic sul pulsante di navigazione **Configurazione dispositivo**.

4.  Nella pagina **Configurazione dispositivo** fare clic sulla raccolta che si desidera eliminare, quindi scegliere il menu **Modifica** e quindi **Elimina**.
    
    <div>
    

    > [!NOTE]
    > Se si elimina la raccolta globale, vengono ripristinate le impostazioni predefinite. La raccolta viene mantenuta.

    
    </div>

5.  Nella finestra di conferma fare clic su **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione di Lync Phone Edition tramite i cmdlet di Windows PowerShell

È possibile eliminare le impostazioni di configurazione di Lync Phone Edition utilizzando Windows PowerShell e il cmdlet **Remove-CsUCConfiguration** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione di Lync Phone Edition

  - Questo comando elimina le impostazioni di configurazione dei telefoni UC applicate al sito di Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione di Lync Phone Edition applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni di configurazione dei telefoni UC applicate all'ambito del servizio:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Per rimuovere tutte le impostazioni di configurazione di Lync Phone Edition in cui il blocco del telefono è disabilitato

  - Questo comando elimina le raccolte di impostazioni di configurazione dei telefoni UC in cui il blocco del telefono è stato disabilitato:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Per informazioni dettagliate, vedere [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

