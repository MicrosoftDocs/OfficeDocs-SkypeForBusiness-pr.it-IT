---
title: Creare o modificare una raccolta di impostazioni di configurazione della versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d4a3b270ecf35d9fbc33accd8c46909a6e8755b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione della versione client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Le impostazioni di configurazione della versione client vengono utilizzate per abilitare o disabilitare il controllo della versione client. La configurazione globale della versione client viene installata con Lync Server e viene utilizzata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. È inoltre possibile configurare le impostazioni di configurazione della versione client per i singoli siti. È possibile creare o modificare le impostazioni di configurazione della versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>


> [!NOTE]
> Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Per creare o modificare le impostazioni di configurazione della versione client utilizzando il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi fare clic sul pulsante di spostamento **Configurazione versione client** .

4.  Nella pagina **Configurazione versione client** eseguire le operazioni seguenti:
    
      - Per creare una nuova configurazione, fare clic su **nuovo**, selezionare un sito, fare clic su **OK** e aggiornare le impostazioni.
    
      - Per modificare una configurazione, selezionare la configurazione, fare clic su **modifica**, su **Mostra dettagli**e apportare modifiche alle impostazioni.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione o modifica delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell

Per creare le impostazioni di configurazione della versione client, è possibile utilizzare il cmdlet **New-CsClientVersionConfiguration** e modificarle utilizzando il cmdlet **set-CsClientVersionConfiguration** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione della versione client

  - Il comando seguente consente di creare una nuova raccolta di impostazioni di configurazione della versione client applicate al sito Redmond. In questo esempio, il controllo delle versioni client è disabilitato per il sito Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Per abilitare il controllo delle versioni dei client per un sito

  - Questo comando consente di abilitare il controllo delle versioni client per il sito Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Per disabilitare il controllo delle versioni client all'interno dell'organizzazione

  - In questo esempio, il controllo delle versioni client è disabilitato per tutte le impostazioni di configurazione della versione client in uso nell'organizzazione.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo ai cmdlet [New-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

