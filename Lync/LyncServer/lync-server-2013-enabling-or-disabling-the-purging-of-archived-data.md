---
title: "Lync Server 2013: Abilitazione o disabilitazione dell'eliminazione dei dati archiviati"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Abilitazione o disabilitazione dell'eliminazione dei dati archiviati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013, è possibile utilizzare le configurazioni di archiviazione per abilitare e disabilitare l'eliminazione e configurare la modalità di implementazione dell'eliminazione. Sono incluse le configurazioni di archiviazione seguenti:

  - Una configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e di pool che possono essere create e utilizzate per specificare come deve essere implementata l'archiviazione per siti o pool specifici.

Le configurazioni di archiviazione vengono definite inizialmente al momento della distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione. Per informazioni dettagliate sulla modalità di implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla distribuzione o alla documentazione relativa alle operazioni.

<div>


> [!NOTE]  
> Per utilizzare l'archiviazione per gli utenti ospitati in Lync Server 2013, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi. Per impostazione predefinita, l'archiviazione non è abilitata né per le comunicazioni interne né per quelle esterne. Prima di abilitare Archiviazione nei criteri, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione corrente e, facoltativamente, per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Se si decide dopo la distribuzione dell'archiviazione che si desidera utilizzare l'integrazione di Microsoft Exchange per archiviare i dati di archiviazione e i file nei server Exchange 2013 e tutti gli utenti sono ospitati nei server Exchange 2013, è necessario rimuovere la configurazione del database di SQL Server. dalla topologia. Per eseguire questa operazione, è necessario utilizzare Generatore di topologie. Per ulteriori informazioni, vedere <A href="lync-server-2013-changing-archiving-database-options.md">modifica delle opzioni del database di archiviazione in Lync Server 2013</A> nella documentazione relativa alle operazioni.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Per abilitare o disabilitare l'eliminazione per l'archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.

4.  Fare clic sul nome della configurazione globale, di sito o di pool appropriata nell'elenco delle configurazioni di archiviazione, scegliere **Modifica**, **Mostra dettagli** ed eseguire le operazioni seguenti:
    
      - Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** ed eseguire una delle operazioni seguenti:
        
          - Per eliminare tutti i record, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.
        
          - Per eliminare solo i dati che sono stati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
      - Per disabilitare l'eliminazione, deselezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione**.

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'eliminazione dei dati di archiviazione mediante i cmdlet di Windows PowerShell

L'abilitazione e la disabilitazione dell'eliminazione automatica dei dati di archiviazione possono essere gestite tramite Windows PowerShell e il cmdlet **Set-CsArchivingConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 using Remote PowerShell" at.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Per abilitare l'eliminazione di tutti i dati di archiviazione

  - Per abilitare l'eliminazione di tutti i dati di archiviazione, impostare la proprietà **EnablePurging** su true ($True). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Dopo l'esecuzione di questo comando, tutti i giorni Lync Server eliminerà tutti i record di archiviazione precedenti al valore specificato per la proprietà **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Per abilitare l'eliminazione solo dei dati di archiviazione esportati

  - Per limitare l'eliminazione ai record di archiviazione che sono stati esportati in un file di dati (utilizzando il cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ), è inoltre necessario impostare la proprietà PurgeExportedArchivesOnly su True ($true). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Dopo l'esecuzione di questo comando, Lync Server eliminerà solo i record di archiviazione che soddisfano i due criteri: 1) sono precedenti al valore specificato per la proprietà **KeepArchivingDataForDays** . e 2) sono stati esportati utilizzando il cmdlet **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Per disabilitare l'eliminazione di tutti i dati di archiviazione

  - Per disabilitare l'eliminazione automatica dei record di archiviazione, impostare la proprietà **EnablePurging** su False ($False). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Per ulteriori informazioni, incluse le opzioni aggiuntive per l'eliminazione dei dati di archiviazione, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configurazione e assegnazione dei criteri di archiviazione in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

