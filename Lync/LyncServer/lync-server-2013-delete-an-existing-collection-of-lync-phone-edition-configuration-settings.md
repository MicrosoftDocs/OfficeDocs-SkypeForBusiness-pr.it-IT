---
title: Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition
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
ms.openlocfilehash: dbf7d49a14ce45550777c6c122cd799f6a511f76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737406"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Se non si vuole più usare una raccolta di impostazioni per i dispositivi che usano Lync Phone Edition, eliminarlo. Se si elimina una raccolta per un sito, le impostazioni globali verranno applicate ai telefoni in tale sito. Non è possibile eliminare la raccolta globale.

<div>


> [!NOTE]
> Invece di eliminare una raccolta, potresti voler solo modificare alcune delle impostazioni. Per informazioni dettagliate su come eseguire questa operazione, vedere <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Per eliminare una raccolta di impostazioni di configurazione di Lync Phone Edition

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione del dispositivo** .

4.  Nella pagina **Configurazione dispositivo** fare clic sulla raccolta che si vuole eliminare, fare clic sul menu **modifica** e quindi su **Elimina**.
    
    <div>
    

    > [!NOTE]
    > Se elimini la raccolta globale, le impostazioni vengono ripristinate solo alle impostazioni predefinite. La raccolta non scompare.

    
    </div>

5.  Nella casella di conferma fare clic su **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Rimozione delle impostazioni di configurazione di Lync Phone Edition con i cmdlet di Windows PowerShell

Per eliminare le impostazioni di configurazione di Lync Phone Edition, è possibile usare Windows PowerShell e il cmdlet **Remove-CsUCConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Per rimuovere una raccolta specificata di impostazioni di configurazione di Lync Phone Edition

  - Questo comando Elimina le impostazioni di configurazione del telefono UC applicate al sito Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Per rimuovere tutte le impostazioni di configurazione di Lync Phone Edition applicate all'ambito del sito

  - Questo comando rimuove tutte le impostazioni di configurazione del telefono UC applicate all'ambito del servizio:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Per rimuovere tutte le impostazioni di configurazione di Lync Phone Edition in cui il blocco del telefono è disabilitato

  - Questo comando Elimina qualsiasi raccolta di impostazioni di configurazione del telefono UC in cui è stato disabilitato il blocco del telefono:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Per informazioni dettagliate, vedere [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

