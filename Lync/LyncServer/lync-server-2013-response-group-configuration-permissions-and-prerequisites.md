---
title: 'Lync Server 2013: autorizzazioni e prerequisiti per la configurazione di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8e27d3495ce2152dee67a5f176c4a0d9f7e7f82
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Autorizzazioni e prerequisiti per la configurazione di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-05_

Response Group è una funzionalità di gestione della chiamate VoIP aziendale. In questo argomento vengono indicati i componenti di cui è necessario disporre prima di poter configurare Response Group e le credenziali e le autorizzazioni amministrative richieste per eseguire le attività di configurazione.

In questa sezione si presuppone la lettura della documentazione relativa alla pianificazione correlata a Response Group. Per informazioni dettagliate, vedere [Planning for Call Management Features in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Strumenti di configurazione e ruoli amministrativi

È possibile utilizzare gli strumenti di amministrazione seguenti per configurare Response Group:

  - Pannello di controllo di Lync Server

  - Strumento di configurazione di Response Group

  - Lync Server Management Shell

Per configurare i Response Group, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Gruppo di sicurezza Active Directory (1)</strong></p></td>
<td><p>Creare flusso di lavoro</p></td>
<td><p>Assegnare responsabile</p></td>
<td><p>Creare/assegnare agenti, code</p></td>
<td><p>Creare/gestire festività e orari di ufficio</p></td>
<td><p>Attivare/disattivare il flusso di lavoro</p></td>
<td><p>Configurare il flusso di lavoro (IVR o gruppo di risposta)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsResponseGroupAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsResponseGroupManager</strong></p></td>
<td> </td>
<td><p>√ (2)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
<td><p>√ (3)</p></td>
</tr>
<tr class="even">
<td><p><strong>CsVoiceAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsServerAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="even">
<td><p><strong>CsAdministrator</strong></p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
<td><p>√</p></td>
</tr>
<tr class="odd">
<td><p><strong>CsViewOnlyAdministrator</strong></p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
<td><p>√ (4)</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <STRONG>(1)</STRONG> un oggetto utente di servizi di dominio Active Directory deve essere membro del gruppo di sicurezza di Active Directory specificato elencato. Un amministratore o un altro membro del gruppo di Active Directory delegato con le autorizzazioni appropriate per aggiungere gli utenti a un gruppo di sicurezza (ad esempio, Administrator, account Operators) deve aggiungere un oggetto utente al gruppo o al gruppo di sicurezza elencato affinché l'utente possa eseguire le funzioni elencate. <STRONG>(2)</STRONG> solo per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager. <STRONG>(3)</STRONG> un responsabile di Response Group può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro che il Manager corrente gestisce già. <STRONG>(4)</STRONG> CsViewOnlyAdministrator è in grado di eseguire solo i cmdlet "Get" di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Prerequisiti di configurazione di Response Group

Per Response Group sono necessari i componenti seguenti:

  - Servizio applicazione

  - Applicazione Response Group

  - Language Pack

  - Archivio file (per gestire i file audio)

  - Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

Prima di configurare Response Group potrebbe essere necessario eseguire le attività seguenti:

  - Abilitare gli utenti per Lync Server 2013 e VoIP aziendale.

  - Modificare un file di configurazione in modo che sia conforme agli standard FIPS (Federal Information Processing Standard).

  - Modificare le regole di confronto del database per supportare caratteri Yi, Meng e Zang per i nomi di code e i nomi dei gruppi di agenti.

<div>

## <a name="enabling-users"></a>Abilitazione degli utenti

Il primo passaggio per la configurazione di Response Group consiste nella creazione di gruppi di agenti. Prima di poter creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti di Response Group per Lync Server 2013 e VoIP aziendale. L'abilitazione degli utenti per Lync Server 2013 è in genere un passaggio del server Enterprise Edition o della distribuzione del server Standard Edition. Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riabilitare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio della distribuzione di VoIP aziendale. Per ulteriori informazioni, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Conformità ai requisiti FIPS

Fare riferimento a questa sezione solo se l'organizzazione deve essere conforme agli standard FIPS (Federal Information Processing Standards).

Per essere conformi a FIPS, è necessario modificare il file Web.config a livello dell'applicazione in modo da usare un algoritmo di crittografia diverso dopo aver installato Servizi Web. È necessario specificare l'uso dell'algoritmo 3DES (Triple Data Encryption Standard) per ASP.NET per l'elaborazione dei dati sugli stati di visualizzazione. Per l'applicazione Response Group, questo requisito si applica allo strumento di configurazione di Response Group e alla console di accesso e disconnessione dell'agente. Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "è possibile che venga visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET che dispongono di ViewState abilitato dopo l'aggiornamento da ASP.NET [https://go.microsoft.com/fwlink/p/?linkId=196183](https://go.microsoft.com/fwlink/p/?linkid=196183)1,1 a ASP.NET 2,0" all'indirizzo.

Per modificare il file Web.config, eseguire le operazioni seguenti:

1.  In un editor di testo come Blocco note aprire il file Web.config a livello dell'applicazione.

2.  Nel file Web. config individuare la `<system.web>` sezione.

3.  Aggiungere la sezione `<machineKey>` seguente alla `<system.web>` sezione:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Salvare il file Web.config.

5.  Riavviare il servizio Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Supporto di caratteri Yi, Meng e Zang

Fare riferimento a questa sezione solo se l'organizzazione richiede il supporto di caratteri Yi, Meng o Zang.

<div>


> [!NOTE]  
> Per informazioni su ciò che sono i caratteri Yi, Meng e Zang e il motivo per cui possono essere importanti per la distribuzione, vedere le informazioni sui set <A href="https://go.microsoft.com/fwlink/p/?linkid=240223">https://go.microsoft.com/fwlink/p/?linkId=240223</A>di caratteri di GB18030.



</div>

Per il supporto di caratteri Yi, Meng o Zang è necessario modificare le regole di confronto del database Rgsconfig. Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti di ogni database Rgsconfig:

  - dbo. AgentGroups

  - dbo. BusinessHours

  - dbo. HolidaySets

  - dbo. Code

  - dbo. Flussi

Per SQL Server 2008 R2 e SQL Server 2012, utilizzare le regole\_di\_confronto per la lingua latina generale 100 (accento sensibile). Se si utilizzano queste regole di confronto, la distinzione tra maiuscole e minuscole non viene applicata ad alcun nome di oggetto.

È possibile modificare le regole di confronto utilizzando Microsoft SQL Server Management Studio. Per informazioni dettagliate sull'utilizzo di questo strumento, vedere "using SQL Server Management Studio [https://go.microsoft.com/fwlink/p/?linkId=196184](https://go.microsoft.com/fwlink/p/?linkid=196184)" all'indirizzo. Per modificare le regole di confronto, eseguire la procedura seguente:

1.  Verificare che SQL Server Management Studio sia configurato per consentire modifiche che richiedono la ricreazione di tabelle. Per informazioni dettagliate, vedere la finestra di dialogo "Salva (non consentita)" all'indirizzo [https://go.microsoft.com/fwlink/p/?linkId=196186](https://go.microsoft.com/fwlink/p/?linkid=196186). Per informazioni dettagliate sull'impostazione di una regola di confronto delle colonne, vedere "procedura: impostare le regole di confronto delle colonne ( [https://go.microsoft.com/fwlink/p/?linkId=196185](https://go.microsoft.com/fwlink/p/?linkid=196185)Visual Database Tools)" all'indirizzo.

2.  Utilizzando Microsoft SQL Server Management Studio connettersi al database Rgsconfig.

3.  Trovare la tabella che si desidera modificare nel database Rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e quindi scegliere **Progetta**.

4.  Modificare le regole di confronto della colonna **Name** e salvare la tabella.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

