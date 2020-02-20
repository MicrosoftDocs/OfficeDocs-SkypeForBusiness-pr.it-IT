---
title: 'Lync Server 2013: creare o modificare un nuovo criterio versione client'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a941908c30a338c12f6c0a7731ade2f1e411dc38
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Creare o modificare un nuovo criterio di versione client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile utilizzare i criteri versione client per specificare le versioni dei client supportati nell'ambiente in uso. L'utilizzo del controllo delle versioni client può contribuire a ridurre i costi associati al supporto di più versioni client. È inoltre possibile migliorare l'esperienza complessiva degli utenti, perché quando le versioni precedenti e successive dei client interagiscono, le funzionalità disponibili possono essere limitate dalla versione precedente del client. È possibile creare o modificare i criteri di versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Per creare o modificare i criteri di versione client utilizzando il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**.
    
    <div>
    

    > [!NOTE]  
    > La scheda <STRONG>criteri versione client</STRONG> è selezionata per impostazione predefinita.

    
    </div>

4.  Nella pagina **criteri versione client** eseguire una delle operazioni seguenti:
    
      - Per creare un criterio di versione client, fare clic su **nuovo**, selezionare **criteri sito**, **Criteri pool**o **criteri utente**e quindi fare clic su **OK**.
    
      - Per modificare il criterio globale o un altro criterio di versione client esistente, selezionare il criterio, fare clic su **modifica**e quindi su **Mostra dettagli**.

5.  Nella pagina **modifica criteri versione client** creare o modificare regole come descritto in [creare o modificare una nuova regola di criteri di versione client in Lync Server 2013](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md).

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Creazione o modifica di criteri di versione client tramite i cmdlet di Windows PowerShell

È possibile creare criteri versione client utilizzando il cmdlet **New-CsClientVersionPolicy** e modificarli utilizzando il cmdlet **Set-CsClientVersionPolicy** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>Per creare un nuovo criterio versione client con ambito sito

  - Il comando seguente consente di creare un nuovo criterio di versione client applicato al sito Redmond. Poiché non sono specificati parametri aggiuntivi, il nuovo criterio utilizzerà le impostazioni predefinite della versione client.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>Per creare un nuovo criterio di versione client per utente

  - Per creare un criterio per utente, utilizzare un comando simile al seguente:
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

Per informazioni dettagliate, vedere gli argomenti della Guida per il cmdlet [New-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) e il cmdlet [Set-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

