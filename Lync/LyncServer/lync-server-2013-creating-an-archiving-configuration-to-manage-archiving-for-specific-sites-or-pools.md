---
title: "Lync Server 2013: creazione di una configurazione di archiviazione per la gestione dell'archiviazione per siti o pool specifici"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41c23afb99e20e8e23582664568eba4fb0b7b841
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>Creazione di una configurazione di archiviazione in Lync Server 2013 per la gestione dell'archiviazione per siti o pool specifici

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per controllare la modalità di implementazione dell'archiviazione nella distribuzione. Sono incluse le configurazioni di archiviazione seguenti:

  - Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.

Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione. Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Per utilizzare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi gli utenti ospitati in Lync Server 2013. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne. Prima di abilitare l'archiviazione nei criteri, è consigliabile specificare le configurazioni di archiviazione appropriate per la distribuzione e facoltativamente per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Se si decide dopo la distribuzione dell'archiviazione che si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server Exchange 2013 e tutti gli utenti sono ospitati nei server Exchange 2013, è necessario rimuovere la configurazione del database di SQL Server. dalla topologia. Per eseguire questa operazione, è necessario utilizzare Generatore di topologie. Per ulteriori informazioni, vedere <A href="lync-server-2013-changing-archiving-database-options.md">modifica delle opzioni del database di archiviazione in Lync Server 2013</A> nella documentazione relativa alle operazioni.



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>Per creare una configurazione di archiviazione per un sito o un pool

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.

4.  Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:
    
      - Per creare una configurazione di archiviazione per un sito, fare clic su **Configurazione sito** e quindi in **Seleziona un sito** selezionare un sito da configurare per l'archiviazione.
    
      - Per creare una configurazione di archiviazione per un pool, fare clic su **Configurazione pool** e quindi in **Seleziona pool** selezionare un pool da configurare per l'archiviazione.

5.  Nell'elenco a discesa **Impostazione di archiviazione** in **Nuova impostazione di archiviazione** eseguire una delle operazioni seguenti:
    
      - Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.
    
      - Per abilitare l'archiviazione per le sessioni di messaggistica istantanea e le conferenze Web, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.
    
      - Per disabilitare l'archiviazione dei criteri, fare clic su **Disabilita archiviazione**.

6.  Sempre in **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:
    
      - Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.
    
      - Per utilizzare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .
    
      - Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
        
          - Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
        
          - Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione delle impostazioni di configurazione dell'archiviazione tramite i cmdlet di Windows PowerShell

È possibile creare le impostazioni di configurazione dell'archiviazione utilizzando Windows PowerShell e il cmdlet New-CsArchivingConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>Per creare una nuova raccolta di impostazioni di configurazione di archiviazione per un sito

  - Con il comando seguente viene creata una nuova raccolta di impostazioni di configurazione di archiviazione per il sito Redmond:
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>Per creare una nuova raccolta di impostazioni di configurazione dell'archiviazione che consentono solo l'archiviazione di messaggistica istantanea

  - Poiché nel comando precedente non sono stati specificati parametri, eccetto il parametro obbligatorio Identity, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per le relative proprietà. Per creare impostazioni basate su valori di proprietà diversi, è sufficiente includere il parametro appropriato e il valore corrispondente. Per creare ad esempio una raccolta di impostazioni di configurazione di archiviazione che consentano per impostazione predefinita di archiviare le sessioni di messaggistica istantanea, utilizzare un comando simile al seguente:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>Per specificare più valori di proprietà durante la creazione di impostazioni di configurazione di archiviazione

  - È possibile modificare più valori di proprietà includendo più parametri. Con il comando seguente ad esempio vengono configurate nuove impostazioni per archiviare le sessioni di messaggistica istantanea e per bloccare la messaggistica istantanea del servizio di archiviazione, se non disponibile:
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

