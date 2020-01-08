---
title: 'Lync Server 2013: creare impostazioni di configurazione della qualità delle esperienze'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977357"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Creare impostazioni di configurazione della qualità delle esperienze in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Le metriche sulla qualità delle esperienze (QoE) tengono traccia della qualità delle chiamate audio e video effettuate nell'organizzazione, tra cui il numero di pacchetti di rete persi, il rumore di fondo e la quantità di "jitter" (differenze nel ritardo del pacchetto). Queste metriche sono archiviate in un database, oltre ad altri dati, ad esempio i record dettagli chiamata, che consentono di abilitare e disabilitare QoE indipendentemente da altre registrazioni di dati.

Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno anche la possibilità di creare impostazioni personalizzate nell'ambito del sito. Ogni volta che vengono usate queste impostazioni con ambito sito, hanno la precedenza sulle impostazioni globali. Ad esempio, se crei impostazioni con ambito sito per il sito Redmond, le impostazioni (invece delle impostazioni globali) verranno usate per gestire i QoE in Redmond.

Le impostazioni di configurazione QoE possono essere create usando il pannello di controllo di Lync Server o il cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Se si usa il pannello di controllo di Lync Server per creare nuove impostazioni, saranno disponibili le opzioni seguenti:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Impostazione dell'interfaccia utente</th>
<th>Parametro di PowerShell</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>Identity</p></td>
<td><p>Identificatore univoco per le impostazioni da creare. Le impostazioni di configurazione QoE possono essere create solo nell'ambito del sito.</p></td>
</tr>
<tr class="even">
<td><p>Abilitare il monitoraggio dei dati QoE</p></td>
<td><p>EnableQoE</p></td>
<td><p>Specifica se i record QoE verranno raccolti e salvati nel database di monitoraggio.</p></td>
</tr>
<tr class="odd">
<td><p>Abilitare l'eliminazione dei dati QoE</p></td>
<td><p>EnablePurging</p></td>
<td><p>Specifica se i record verranno eliminati dopo che è trascorso il periodo definito nella proprietà <strong>Mantieni i dati QoE per una durata massima (giorni)</strong> .</p></td>
</tr>
<tr class="even">
<td><p>Mantieni i dati QoE per la durata massima (giorni)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Numero di giorni i dati QoE verranno archiviati prima di essere eliminati dal database. Questo valore viene ignorato se l'eliminazione è disabilitata.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server. Per altre informazioni, vedere l'argomento della Guida <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Per creare impostazioni di configurazione QoE tramite il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins o come membro del ruolo di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegare le autorizzazioni di configurazione in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **qualità dei dati dell'esperienza**.

4.  Nella pagina **qualità di dati esperienza** fare clic su **nuovo**.

5.  In **Seleziona un sito**fare clic sul sito a cui applicare il criterio e fare clic su **OK**.

6.  Nell' **impostazione nuova qualità dell'esperienza**, eseguire le operazioni seguenti:
    
      - Selezionare **Abilita il monitoraggio dei dati QoE** per attivare il monitoraggio.
    
      - Selezionare **Abilita l'eliminazione dei dati QoE** per attivare l'eliminazione.
    
      - In **Mantieni QoE per la durata massima (giorni)** selezionare il numero massimo di giorni in cui devono essere conservati i record QoE.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di impostazioni di configurazione QoE con i cmdlet di Windows PowerShell

Puoi creare impostazioni di configurazione QoE usando Windows PowerShell e il cmdlet New-CsQoEConfiguration. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE

  - Questo comando crea una nuova raccolta di impostazioni di configurazione QoE applicate al sito Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato

  - Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà. Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati. Ad esempio, per creare una raccolta di impostazioni di configurazione della qualità delle esperienze che, per impostazione predefinita, consentono di disabilitare la registrazione QoE usare un comando simile al seguente:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Per specificare più valori di proprietà quando si crea una nuova raccolta di impostazioni di configurazione QoE

  - Puoi includere più valori di proprietà includendo più parametri. Ad esempio, questo comando Configura le nuove impostazioni per conservare i dati QoE per 30 giorni e per eliminare i vecchi dati in 3:00 AM:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

