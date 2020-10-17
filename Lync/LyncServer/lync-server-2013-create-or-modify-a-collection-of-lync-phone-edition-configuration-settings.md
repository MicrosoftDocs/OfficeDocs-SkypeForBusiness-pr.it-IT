---
title: Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e2d314497223b5a18aa864b0e5333e3762480d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506213"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Quando si installa Lync Server, si ottiene una raccolta globale di impostazioni di Lync Phone Edition. Queste impostazioni si applicano a tutti i dispositivi che eseguono Lync Phone Edition nella distribuzione. È possibile modificare queste impostazioni in qualsiasi momento. È inoltre possibile impostare una nuova raccolta di impostazioni che si applicano ai dispositivi in un sito specifico. Le impostazioni del sito hanno la precedenza sulle impostazioni globali.

Le impostazioni di  configurazione consistono nel nome della raccolta, l'ambito (globale o sito), l'impostazione di sicurezza SIP, il livello di registrazione, il livello della qualità del servizio (QoS) vocale, l'impostazione di blocco del telefono e i dettagli di blocco del telefono, ovvero: a) la lunghezza del PIN e b) la durata dell'inattività del telefono prima del blocco.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Per creare una raccolta di impostazioni di configurazione di Lync Phone Edition o modificare le impostazioni di una raccolta esistente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Client** e quindi sul pulsante di spostamento **Configurazione dispositivo**.

4.  Nella pagina **Configurazione dispositivo** effettuare una delle seguenti operazioni:
    
      - Per creare una nuova raccolta di impostazioni di configurazione di Lync Phone Edition, fare clic su **nuovo**, selezionare un sito, fare clic su **OK**, rivedere le impostazioni predefinite e, se si desidera, apportare le modifiche.
    
      - Per modificare le impostazioni di una raccolta esistente, fare clic sulla raccolta, selezionare il menu **Modifica**, fare clic su **Mostra dettagli** e apportare le modifiche.
        
        <div>
        

        > [!TIP]
        > Per tornare a utilizzare le impostazioni predefinite di una raccolta globale, fare clic sulla stessa, quindi sul menu <STRONG>Modifica</STRONG> e su <STRONG>Elimina</STRONG>, quindi fare clic su <STRONG>OK</STRONG>. La raccolta globale non viene eliminata, ma le impostazioni vengono ripristinate ai valori predefiniti.

        
        </div>

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di nuove impostazioni di configurazione di Lync Phone Edition tramite i cmdlet di Windows PowerShell

È possibile creare le impostazioni di configurazione di Lync Phone Edition (solo nell'ambito del sito) utilizzando Windows PowerShell e il cmdlet **New-CsUCPhoneConfiguration** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Per creare nuove impostazioni di configurazione di Lync Phone Edition che utilizzano i valori predefiniti

  - Con questo comando viene creata una nuova raccolta di impostazioni del telefono UC per il sito Redmond.
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Dal momento che nel comando precedente non sono specificati altri parametri (oltre al parametro Identity, che è obbligatorio), questa nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le proprietà.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Per modificare un singolo valore di proprietà durante la creazione di nuove impostazioni di configurazione di Lync Phone Edition

  - Per creare impostazioni che utilizzano diversi valori di proprietà, è sufficiente includere il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione del telefono UC che, per impostazione predefinita, richiedono il blocco del telefono, utilizzare un comando come il seguente:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Per modificare più valori di proprietà durante la creazione di nuove impostazioni di configurazione di Lync Phone Edition

  - I valori di proprietà multiple possono essere modificati includendo parametri multipli. Ad esempio, questo comando impone il blocco del telefono e imposta la lunghezza minima del PIN su 8 cifre:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Per informazioni dettagliate, vedere [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Applicare il blocco del telefono in Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

