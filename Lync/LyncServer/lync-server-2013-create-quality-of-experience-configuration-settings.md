---
title: 'Lync Server 2013: creare impostazioni di configurazione per la qualità delle esperienze'
description: 'Lync Server 2013: creare impostazioni di configurazione per la qualità delle esperienze.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279265f396fc8fcbfba80d195fc587924a2979f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562192"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Creare le impostazioni di configurazione per la qualità delle esperienze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

La metrica QoE registra la qualità delle chiamate audio e video effettuate nell'organizzazione, includendo informazioni quali il numero di pacchetti di rete persi, i rumori di fondo e il livello di "instabilità" (differenze nel ritardo dei pacchetti). Questa metrica viene archiviata in un database separatamente rispetto ad altri dati, ad esempio la registrazione dettagli chiamata, in modo che sia possibile abilitare e disabilitare il servizio QoE in maniera indipendente rispetto ad altre registrazioni di dati.

Quando si installa Microsoft Lync Server 2013, viene creata una singola raccolta globale di impostazioni di configurazione QoE. Gli amministratori hanno inoltre la possibilità di creare impostazioni personalizzato con ambito sito. Ogni volta che vengono utilizzate tali impostazioni con ambito sito, queste avranno la precedenza rispetto alle impostazioni globali. Se si creano impostazioni con ambito sito per il sito Redmond, ad esempio, per gestire i criteri QoE nel sito di Redmond verranno utilizzate tali impostazioni, anziché quelle globali.

È possibile creare le impostazioni di configurazione QoE utilizzando il pannello di controllo di Lync Server o il cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) . Se si utilizza il pannello di controllo di Lync Server per creare nuove impostazioni, saranno disponibili le opzioni seguenti:


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
<td><p>Identità</p></td>
<td><p>Identificatore univoco delle impostazioni da creare. Le impostazioni di configurazione QoE possono essere create solo in ambito di sito.</p></td>
</tr>
<tr class="even">
<td><p>Abilita monitoraggio dei dati QoE</p></td>
<td><p>EnableQoE</p></td>
<td><p>Indica se i record QoE verranno raccolti e salvati nel database di monitoraggio.</p></td>
</tr>
<tr class="odd">
<td><p>Abilita eliminazione dei dati QoE</p></td>
<td><p>EnablePurging</p></td>
<td><p>Indica se i record verranno cancellati dopo la scadenza specificata nella proprietà <strong>Mantieni dati QoE per durata massima (giorni)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Mantieni dati QoE per durata massima (giorni)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>Il numero di giorni in cui i dati QoE verranno archiviati prima di essere eliminati dal database. Questo valore viene ignorato se l'eliminazione è disabilitata.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Il cmdlet New-CsQoEConfiguration include opzioni aggiuntive non disponibili nel pannello di controllo di Lync Server. Per ulteriori informazioni, vedere l'argomento relativo alla guida di <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> .



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Per creare le impostazioni di configurazione QoE utilizzando il pannello di controllo di Lync Server

1.  Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator. Per informazioni dettagliate, vedere [delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Dati QoE**.

4.  Nella pagina **Dati QoE** fare clic su **Nuovo**.

5.  In **Seleziona un sito** fare clic sul sito a cui si desidera applicare i criteri e quindi fare clic su **OK**.

6.  In **Crea nuova impostazione QoE** eseguire le operazioni seguenti:
    
      - Selezionare **Abilita monitoraggio dei dati QoE** per attivare il monitoraggio.
    
      - Selezionare **Abilita eliminazione dei dati QoE** per attivare l'eliminazione.
    
      - In **Mantieni dati QoE per durata massima (giorni)** selezionare il numero massimo di giorni per il mantenimento dei record QoE.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Creazione di impostazioni di configurazione QoE tramite i cmdlet di Windows PowerShell

È possibile creare impostazioni di configurazione QoE utilizzando Windows PowerShell e il cmdlet New-CsQoEConfiguration. È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE

  - Questo comando crea una nuova raccolta di impostazioni di configurazione QoE per il sito Redmond:
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>Per creare una nuova raccolta di impostazioni di configurazione QoE in cui il monitoraggio QoE è disabilitato

  - Dal momento che nel comando precedente non sono stati specificati parametri, oltre al parametro Identity obbligatorio, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per ogni proprietà. Per creare impostazioni che utilizzano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato. Per creare una raccolta di impostazioni di configurazione QoE che consenta la disabilitazione della registrazione QoE per impostazione predefinita, utilizzare un comando come il seguente:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>Per specificare più valori di proprietà durante la creazione di una nuova raccolta di impostazioni di configurazione QoE

  - È possibile specificare più valori di proprietà includendo più parametri. Questo comando, ad esempio, configura le nuove impostazioni per mantenere i dati QoE per 30 giorni ed eliminare i dati obsoleti alle 3.00:
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

