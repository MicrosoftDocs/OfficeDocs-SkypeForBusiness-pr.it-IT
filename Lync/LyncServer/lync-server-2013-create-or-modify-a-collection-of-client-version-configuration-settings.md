---
title: Creare o modificare una raccolta di impostazioni di configurazione della versione client
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 84df13c7abbc98cbb90c5b59a6b0717deb855e28
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione della versione client in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le impostazioni di configurazione della versione client vengono utilizzate per attivare o disattivare il controllo della versione client. La configurazione della versione client globale viene installata con Lync Server e viene usata per abilitare o disabilitare il controllo della versione client per l'intera distribuzione del server. È anche possibile configurare le impostazioni di configurazione della versione client per singoli siti. È possibile creare o modificare le impostazioni di configurazione della versione client dal pannello di controllo di Lync Server 2013 o Lync Server 2013 Management Shell.

<div>


> [!NOTE]
> Poiché gli utenti anonimi non sono associati ad alcun utente, sito o servizio, sono interessati solo dai criteri a livello globale.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Per creare o modificare le impostazioni di configurazione della versione client tramite il pannello di controllo di Lync Server

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione della versione client** .

4.  Nella pagina **Configurazione versione client** eseguire le operazioni seguenti:
    
      - Per creare una nuova configurazione, fare clic su **nuovo**, selezionare un sito, fare clic su nome **OK** e aggiornare le impostazioni.
    
      - Per modificare una configurazione, selezionare la configurazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e apportare modifiche alle impostazioni.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione o modifica delle impostazioni di configurazione della versione client tramite i cmdlet di Windows PowerShell

Puoi creare le impostazioni di configurazione della versione client usando il cmdlet **New-CsClientVersionConfiguration** e modificarle usando il cmdlet **set-CsClientVersionConfiguration** . Questi cmdlet possono essere eseguiti da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione della versione client

  - Il comando seguente crea una nuova raccolta di impostazioni di configurazione della versione client applicata al sito Redmond. In questo esempio, il controllo delle versioni dei client è disabilitato per il sito Redmond.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>Per abilitare il controllo delle versioni del client per un sito

  - Questo comando consente di abilitare il controllo delle versioni del client per il sito Redmond.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>Per disabilitare il controllo delle versioni del client in tutta l'organizzazione

  - In questo esempio, il controllo delle versioni dei client è disabilitato per tutte le impostazioni di configurazione della versione client in uso nell'organizzazione.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

Per informazioni dettagliate, vedere l'argomento della Guida per i cmdlet [New-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg399029(v=OCS.15)) e [set-CsClientVersionConfiguration](https://technet.microsoft.com/en-us/library/Gg398623(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

