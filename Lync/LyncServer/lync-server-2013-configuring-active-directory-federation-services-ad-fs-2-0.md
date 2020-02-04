---
title: 'Lync Server 2013: configurazione di Active Directory Federation Services (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68864b6e5773bcd1cb9f063b400015697285ba36
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configurazione di Active Directory Federation Services (AD FS 2,0) per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-07-03_

La sezione seguente descrive come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori. Per informazioni su come installare ADFS 2,0, vedere istruzioni dettagliate su ADFS 2,0 e su come eseguire le guide [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> Quando si installa ADFS 2,0, non usare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services. Scaricare e installare invece il pacchetto-RTW di <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory Federation Services 2,0.



</div>

<div>


**Per configurare ADFS per l'autenticazione a due fattori**

1.  Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.

2.  Avviare Windows PowerShell.

3.  Nella riga di comando di Windows PowerShell eseguire il comando seguente:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Stabilire una partnership con ogni Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Director, Enterprise pool e Standard Edition server che verranno abilitati per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome server specifico della distribuzione:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Nel menu strumenti di amministrazione avviare la console di gestione di ADFS 2,0.

6.  Espandere i **trust** **tra le relazioni** \> di trust.

7.  Verificare che sia stato creato un nuovo trust per Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Enterprise pool o Standard Edition Server.

8.  Creare e assegnare una regola di autorizzazione del rilascio per l'attendibilità del componente tramite Windows PowerShell eseguendo i comandi seguenti:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente usando Windows PowerShell eseguendo i comandi seguenti:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Nella console di gestione di ADFS 2,0 fare clic con il pulsante destro del mouse sull'attendibilità del componente e scegliere **modifica regole attestazione**.

11. Selezionare la scheda **regole di autorizzazione del rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.

12. Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

