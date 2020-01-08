---
title: "Lync Server 2013: Abilitazione o disabilitazione della modalità critica per bloccare o consentire la messaggistica istantanea e le sessioni di conferenza Web se l'archiviazione non riesce"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling critical mode to block or allow IM and web conferencing sessions if Archiving fails
ms:assetid: fafdcd2e-b778-4ed5-a25f-09208aa3b699
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182609(v=OCS.15)
ms:contentKeyID: 48185927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c690c235a3a753db8cc07cebbc8749a0d27c99f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-critical-mode-in-lync-server-2013-to-block-or-allow-im-and-web-conferencing-sessions-if-archiving-fails"></a>Abilitazione o disabilitazione della modalità critica in Lync Server 2013 per bloccare o consentire la messaggistica istantanea e le sessioni di conferenza Web se l'archiviazione non riesce

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Nel pannello di controllo di Lync Server 2013 si usano le configurazioni di archiviazione per abilitare e disabilitare la modalità critica. Sono incluse le configurazioni di archiviazione seguenti:

  - Configurazione globale creata per impostazione predefinita quando si distribuisce Lync Server 2013.

  - Configurazioni facoltative a livello di sito e a livello di pool che è possibile creare e usare per specificare la modalità di implementazione dell'archiviazione per siti o pool specifici.

È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione. Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere funzionamento dell' [archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md) nella documentazione relativa alla pianificazione, alla documentazione di distribuzione o alla documentazione operativa.

<div>


> [!NOTE]  
> Per usare l'archiviazione, è necessario configurare i criteri di archiviazione per specificare se abilitare l'archiviazione per le comunicazioni interne, per le comunicazioni esterne o per entrambi gli utenti residenti in Lync Server 2013. Per impostazione predefinita, l'archiviazione non è abilitata per le comunicazioni interne o esterne. Prima di abilitare l'archiviazione in qualsiasi criterio, è necessario specificare le configurazioni di archiviazione appropriate per la distribuzione e, facoltativamente, per siti e pool specifici, come descritto in questa sezione. Per informazioni dettagliate sull'abilitazione dell'archiviazione, vedere <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">configurazione e assegnazione di criteri di archiviazione in Lync Server 2013</A> nella documentazione relativa alla distribuzione.<BR>Se si decide dopo la distribuzione dell'archiviazione in cui si vuole usare l'integrazione di Exchange Server per archiviare i dati e i file di archiviazione nei server di Exchange 2013 e tutti gli utenti sono ospitati nei server di Exchange 2013, è necessario rimuovere la configurazione del database di SQL Server da la topologia. Per eseguire questa operazione, è necessario usare generatore di topologie. Per informazioni dettagliate, vedere <A href="lync-server-2013-changing-archiving-database-options.md">modifica delle opzioni di archiviazione del database in Lync Server 2013</A> nella documentazione Operations.



</div>

<div>

## <a name="to-enable-or-disable-blocking-of-im-and-web-conferencing-sessions-if-archiving-fails"></a>Per abilitare o disabilitare il blocco delle sessioni di messaggistica istantanea e di conferenza Web se l'archiviazione non riesce

1.  Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.

4.  Fare clic sul nome della configurazione globale, del sito o del pool appropriata nell'elenco delle configurazioni di archiviazione, fare clic su **modifica**, fare clic su **Mostra dettagli**e quindi eseguire le operazioni seguenti:

5.  Per impostare la modalità di funzionamento dell'archiviazione quando si verifica un errore, selezionare o deselezionare la casella di controllo **Blocca messaggistica istantanea o sessioni di conferenza Web se l'archiviazione non riesce** .

6.  Fare clic su **Commit**.

</div>

<div>

## <a name="enabling-and-disabling-critical-mode-by-using-windows-powershell-cmdlets"></a>Abilitazione e disabilitazione della modalità critica tramite i cmdlet di Windows PowerShell

Puoi abilitare o disabilitare la modalità critica usando il cmdlet **Set-CsArchivingConfiguration** . Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-enable-critical-mode"></a>Per abilitare la modalità critica

  - Per abilitare la modalità critica, imposta il valore della proprietà BlockOnArchiveFailure su true ($True). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $True

</div>

<div>

## <a name="to-disable-critical-mode"></a>Per disabilitare la modalità critica

  - Per disabilitare la modalità critica, imposta il valore della proprietà BlockOnArchiveFailure su false ($False). Ad esempio:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -BlockOnArchiveFailure $False

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Modifica delle opzioni di archiviazione del database in Lync Server 2013](lync-server-2013-changing-archiving-database-options.md)  


[Funzionamento dell'archiviazione in Lync Server 2013](lync-server-2013-how-archiving-works.md)  


[Gestione delle opzioni di configurazione dell'archiviazione in Lync Server 2013 per l'organizzazione, i siti e i pool](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

