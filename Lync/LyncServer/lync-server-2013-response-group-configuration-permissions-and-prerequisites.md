---
title: 'Lync Server 2013: Autorizzazioni e prerequisiti per la configurazione di Response Group'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group configuration permissions and prerequisites
ms:assetid: 4266f16a-b387-452c-a8ca-d771a3c58f0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204840(v=OCS.15)
ms:contentKeyID: 48183972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1360a6dee8dbbf169fa0ceda1ee1b2f215ff09b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-configuration-permissions-and-prerequisites-in-lync-server-2013"></a>Autorizzazioni e prerequisiti per la configurazione di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-05_

Response Group è una caratteristica di gestione delle chiamate vocali aziendali. Questo argomento descrive le informazioni necessarie per configurare Response Group e le credenziali amministrative e le autorizzazioni necessarie per eseguire le attività di configurazione.

Questa sezione presuppone che sia stata letta la documentazione relativa alla pianificazione relativa al gruppo di risposte. Per informazioni dettagliate, vedere [pianificazione delle funzionalità di gestione delle chiamate in Lync Server 2013](lync-server-2013-planning-for-call-management-features.md) nella documentazione relativa alla pianificazione.

<div>

## <a name="configuration-tools-and-administrative-roles"></a>Strumenti di configurazione e ruoli amministrativi

È possibile usare gli strumenti di amministrazione seguenti per configurare Response Group:

  - Pannello di controllo di Lync Server

  - Strumento di configurazione di Response Group

  - Lync Server Management Shell

Per configurare i Response Groups, è necessario essere membri di almeno uno dei ruoli amministrativi seguenti:


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
<td><p><strong>Gruppo di sicurezza di Active Directory (1)</strong></p></td>
<td><p>Creare un flusso di lavoro</p></td>
<td><p>Assegna Manager</p></td>
<td><p>Creare agenti/Assign, code</p></td>
<td><p>Creare/gestire le festività e le ore lavorative</p></td>
<td><p>Attivare/disattivare il flusso di lavoro</p></td>
<td><p>Configurare il flusso di lavoro (IVR o gruppo di caccia)</p></td>
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
> <STRONG>(1)</STRONG> un oggetto utente di servizi di dominio Active Directory deve essere un membro del gruppo di sicurezza Active Directory specificato elencato. Un amministratore o un altro membro del gruppo di Active Directory delegato con le autorizzazioni appropriate per aggiungere utenti a un gruppo di sicurezza, ad esempio Administrator, account Operators, deve aggiungere un oggetto utente al gruppo di sicurezza o al gruppo di protezione elencato per consentire all'utente di eseguire le funzioni elencate. <STRONG>(2)</STRONG> solo per i flussi di lavoro assegnati da CsResponseGroupAdministrator a CsResponseGroupManager. <STRONG>(3)</STRONG> un responsabile del gruppo di risposte può assegnare un altro membro di CsResponseGroupManager a un flusso di lavoro già gestito da gestione corrente. <STRONG>(4)</STRONG> CsViewOnlyAdministrator può eseguire solo il verbo "ottenere" i cmdlet di Lync Server Management Shell.



</div>

</div>

<div>

## <a name="response-group-configuration-prerequisites"></a>Prerequisiti per la configurazione di Response Group

Response Group richiede i componenti seguenti:

  - Servizio applicazione

  - Response Group Application

  - Language Pack

  - Archivio file (per contenere i file audio)

  - Servizi Web (include lo strumento di configurazione di Response Group e la console di accesso e disconnessione degli agenti)

Tutti questi componenti vengono installati per impostazione predefinita quando si distribuisce VoIP aziendale.

Potrebbe essere necessario eseguire le attività seguenti prima di configurare Response Group:

  - Consentire agli utenti di Lync Server 2013 e Enterprise Voice.

  - Modificare un file di configurazione per essere conforme alle norme FIPS (Federal Information Processing Standards).

  - Modificare le regole di confronto del database per supportare i caratteri Yi, Meng e Zang per i nomi delle code e i nomi dei gruppi di agenti.

<div>

## <a name="enabling-users"></a>Abilitazione degli utenti

Il primo passaggio della configurazione di Response Group consiste nel creare gruppi di agenti. Prima di poter creare un gruppo di agenti, è necessario abilitare gli utenti che saranno agenti per Response Group per Lync Server 2013 e Enterprise Voice. L'abilitazione degli utenti per Lync Server 2013 è in genere un passaggio nel server Enterprise Edition o nella distribuzione di server Standard Edition. Per informazioni dettagliate sull'abilitazione degli utenti per Lync Server 2013, vedere [disabilitare o riattivare l'account utente per Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). L'abilitazione degli utenti per VoIP aziendale è in genere un passaggio nella distribuzione di VoIP aziendale. Per informazioni dettagliate, vedere [abilitare gli utenti per VoIP aziendale in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).

</div>

<div>

## <a name="complying-with-fips-requirements"></a>Conformità ai requisiti FIPS

Questa sezione si applica solo se l'organizzazione deve essere conforme alle norme FIPS (Federal Information Processing Standards).

Per essere conformi con FIPS, è necessario modificare il file Web. config a livello di applicazione per usare un algoritmo di crittografia diverso dopo l'installazione dei servizi Web. Devi specificare che ASP.NET usa l'algoritmo 3DES (Triple Data Encryption Standard) per elaborare i dati sullo stato di visualizzazione. Per l'applicazione Response Group, questo requisito si applica allo strumento di configurazione dei gruppi di risposta e alla console di accesso e disconnessione dell'agente. Per informazioni dettagliate su questo requisito, vedere l'articolo 911722 della Microsoft Knowledge Base "potrebbe essere visualizzato un messaggio di errore quando si accede alle pagine Web di ASP.NET che hanno ViewState abilitato dopo l'aggiornamento da ASP.NET 1,1 a ASP.NET [http://go.microsoft.com/fwlink/p/?linkId=196183](http://go.microsoft.com/fwlink/p/?linkid=196183)2,0".

Per modificare il file Web. config, eseguire le operazioni seguenti:

1.  In un editor di testo, ad esempio Blocco note, aprire il file Web. config a livello di applicazione.

2.  Nel file Web. config individuare la `<system.web>` sezione.

3.  Aggiungere la sezione `<machineKey>` seguente alla `<system.web>` sezione:
    
        <machineKey validationKey="AutoGenerate,IsolateApps" decryptionKey="AutoGenerate,IsolateApps" validation="3DES" decryption="3DES"/>

4.  Salvare il file Web. config.

5.  Riavviare il servizio Internet Information Services (IIS) eseguendo il comando seguente al prompt dei comandi:
    
        iisreset

</div>

<div>

## <a name="supporting-yi-meng-and-zang-characters"></a>Supporto di caratteri Yi, Meng e Zang

Questa sezione si applica solo se l'organizzazione deve supportare i caratteri Yi, Meng o Zang.

<div>


> [!NOTE]  
> Per informazioni sui caratteri di Yi, Meng e Zang e sul motivo per cui potrebbero essere importanti per la distribuzione, vedere le informazioni sui set <A href="http://go.microsoft.com/fwlink/p/?linkid=240223">http://go.microsoft.com/fwlink/p/?linkId=240223</A>di caratteri GB18030.



</div>

Per supportare i caratteri Yi, Meng o Zang, è necessario modificare le regole di confronto per il database rgsconfig. Modificare le regole di confronto della colonna **Name** nelle tabelle seguenti in ogni database di rgsconfig:

  - dbo. AgentGroups

  - dbo. BusinessHours

  - dbo. HolidaySets

  - dbo. Code

  - dbo. Flussi

Per SQL Server 2008 R2 e SQL Server 2012, usare le regole\_di\_confronto in latino generale 100 (accento sensibile). Se si usano queste regole di confronto, tutti i nomi degli oggetti non saranno distinzione tra maiuscole e minuscole.

È possibile modificare le regole di confronto tramite Microsoft SQL Server Management Studio. Per informazioni dettagliate sull'uso di questo strumento, vedere "utilizzo di SQL Server Management [http://go.microsoft.com/fwlink/p/?linkId=196184](http://go.microsoft.com/fwlink/p/?linkid=196184)studio" all'indirizzo. Seguire questa procedura per modificare le regole di confronto:

1.  Verificare che SQL Server Management Studio sia configurato in modo da consentire la ricreazione delle modifiche che richiedono le tabelle. Per informazioni dettagliate, vedere la finestra di dialogo "Salva (non consentita)" in [http://go.microsoft.com/fwlink/p/?linkId=196186](http://go.microsoft.com/fwlink/p/?linkid=196186). Per informazioni dettagliate sull'impostazione di regole di confronto delle colonne, vedere "procedura: impostare le regole di confronto delle colonne (Visual [http://go.microsoft.com/fwlink/p/?linkId=196185](http://go.microsoft.com/fwlink/p/?linkid=196185)Database Tools)" at.

2.  Con Microsoft SQL Server Management Studio connettersi al database di rgsconfig.

3.  Individuare la tabella che si vuole modificare nel database di rgsconfig, fare clic con il pulsante destro del mouse sulla tabella e scegliere **progettazione**.

4.  Modificare le regole di confronto della colonna **nome** e salvare la tabella.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

