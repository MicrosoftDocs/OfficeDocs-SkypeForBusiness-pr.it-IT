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
ms.openlocfilehash: 3b06d21cc0154ea57bc028c87c835e4de9a00f1b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735656"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Abilitazione o disabilitazione dell'eliminazione dei dati archiviati in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013 si usano le configurazioni di archiviazione per abilitare e disabilitare l'eliminazione e la configurazione dell'implementazione. Sono incluse le configurazioni di archiviazione seguenti:

  - Configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e a livello di pool che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o pool specifici.

È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione di distribuzione o alla documentazione operativa.

<div>


> [!NOTE]  
> Per usare l'archiviazione per gli utenti residenti in Lync Server 2013, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne. Prima di abilitare l'archiviazione in qualsiasi criterio, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione e, facoltativamente, per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione di criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Se si decide dopo la distribuzione dell'archiviazione che si vuole usare l'integrazione di Microsoft Exchange per archiviare i dati e i file di archiviazione nei server di Exchange 2013 e tutti gli utenti sono ospitati nei server di Exchange 2013, è necessario rimuovere la configurazione del database di SQL Server. dalla topologia. Per eseguire questa operazione, è necessario usare generatore di topologie. Per informazioni dettagliate, vedere <A href="lync-server-2013-changing-archiving-database-options.md">modifica delle opzioni di archiviazione del database in Lync Server 2013</A> nella documentazione Operations.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>Per abilitare o disabilitare l'eliminazione per l'archiviazione

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

4.  Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:
    
      - Per abilitare l'eliminazione, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:
        
          - Per eliminare tutti i record, fare clic sul pulsante **Elimina dati di archiviazione esportati e archiviare i dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.
        
          - Per eliminare solo i dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.
    
      - Per disabilitare l'eliminazione, deselezionare la casella **di controllo Abilita l'eliminazione dei dati di archiviazione** .

5.  Fare clic su **Commit**.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Abilitazione o disabilitazione dell'eliminazione dei dati di archiviazione tramite i cmdlet di Windows PowerShell

L'attivazione e la disabilitazione dell'eliminazione automatica dei dati di archiviazione possono essere gestite tramite Windows PowerShell e il cmdlet **Set-CsArchivingConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>Per abilitare l'eliminazione di tutti i dati di archiviazione

  - Per abilitare l'eliminazione di tutti i dati di archiviazione, imposta la proprietà **EnablePurging** su true ($true). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    Dopo l'esecuzione del comando, ogni giorno Lync Server eliminerà tutti i record di archiviazione antecedenti al valore specificato per la proprietà **KeepArchivingDataForDays** .

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>Per abilitare l'eliminazione solo dei dati di archiviazione esportati

  - Per limitare l'eliminazione all'archiviazione dei record che sono stati esportati in un file di dati (usando il cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) ) devi anche impostare la proprietà PurgeExportedArchivesOnly su True ($true). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    Dopo l'esecuzione del comando, Lync Server eliminerà solo i record di archiviazione che soddisfano due criteri: 1) che sono antecedenti al valore specificato per la proprietà **KeepArchivingDataForDays** ; e 2) sono stati esportati usando il cmdlet **Export-CsArchivingData** .

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>Per disabilitare l'eliminazione di tutti i dati di archiviazione

  - Per disabilitare l'eliminazione automatica dei record di archiviazione, imposta la proprietà **EnablePurging** su False ($false). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

Per altre informazioni, incluse le opzioni aggiuntive per l'eliminazione dei dati di archiviazione, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Configurazione e assegnazione di criteri di archiviazione in Lync Server 2013](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

