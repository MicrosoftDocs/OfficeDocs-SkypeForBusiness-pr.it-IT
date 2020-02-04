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
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Creare o modificare una raccolta di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Quando si installa Lync Server, si ottiene una raccolta globale delle impostazioni di Lync Phone Edition. Queste impostazioni si applicano a tutti i dispositivi in cui è in uso Lync Phone Edition nella distribuzione. È possibile modificare queste impostazioni in qualsiasi momento. È anche possibile configurare una nuova raccolta di impostazioni che si applicano ai dispositivi di un sito specifico. Le impostazioni del sito hanno la precedenza sulle impostazioni globali.

Le impostazioni di configurazione includono il nome della raccolta, l'ambito (globale o il sito), l'impostazione di sicurezza SIP, il livello di registrazione, il livello di qualità vocale del servizio (QoS), l'impostazione di blocco telefonico e i dettagli del blocco telefonico, ovvero la durata della a) per sbloccare il numero di identificazione personale ( PIN) deve essere e b) il telefono rimane inattivo prima di bloccarsi.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Per creare una raccolta di impostazioni di configurazione di Lync Phone Edition o modificare le impostazioni per una raccolta esistente

1.  Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **client**e quindi sul pulsante di spostamento della **configurazione del dispositivo** .

4.  Nella pagina **Configurazione dispositivo** eseguire una delle operazioni seguenti:
    
      - Per creare una nuova raccolta di impostazioni di configurazione di Lync Phone Edition, fare clic su **nuovo**, selezionare un sito, fare clic su **OK**, rivedere le impostazioni predefinite e, se si vuole, apportare le modifiche desiderate.
    
      - Per modificare le impostazioni di una raccolta esistente, fare clic sulla raccolta, fare clic sul menu **modifica** , fare clic su **Mostra dettagli**e quindi apportare le modifiche desiderate.
        
        <div>
        

        > [!TIP]
        > Per tornare all'uso delle impostazioni predefinite per la raccolta globale, fare clic sulla raccolta globale, fare clic sul menu <STRONG>modifica</STRONG> , scegliere <STRONG>Elimina</STRONG>e quindi fare clic su <STRONG>OK</STRONG>. In questo modo non verrà eliminata la raccolta globale; Ripristina solo le impostazioni predefinite.

        
        </div>

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di nuove impostazioni di configurazione di Lync Phone Edition con i cmdlet di Windows PowerShell

È possibile creare le impostazioni di configurazione di Lync Phone Edition (solo nell'ambito del sito) tramite Windows PowerShell e il cmdlet **New-CsUCPhoneConfiguration** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Per creare nuove impostazioni di configurazione di Lync Phone Edition che usano i valori predefiniti

  - Questo comando crea un nuovo set di impostazioni di configurazione del telefono UC per il sito Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Per modificare un valore di proprietà Single durante la creazione di nuove impostazioni di configurazione di Lync Phone Edition

  - Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione del telefono UC che, per impostazione predefinita, richiedono il blocco del telefono, usa un comando simile al seguente:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Per modificare più valori di proprietà quando si creano nuove impostazioni di configurazione di Lync Phone Edition

  - Più valori di proprietà possono essere modificati includendo più parametri. Ad esempio, questo comando impone il blocco del telefono e imposta anche la lunghezza minima del PIN su 8 cifre:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Per informazioni dettagliate, vedere [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminare una raccolta esistente di impostazioni di configurazione di Lync Phone Edition in Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurare le impostazioni di sicurezza per Lync Phone Edition in Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Applicare il blocco telefonico in Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

