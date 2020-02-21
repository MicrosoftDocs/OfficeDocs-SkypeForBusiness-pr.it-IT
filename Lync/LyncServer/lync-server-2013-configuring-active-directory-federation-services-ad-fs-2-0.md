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
ms.openlocfilehash: 9daaec9cbe32f031c7ee99731b1d7c7c9ec10ac1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Configurazione di Active Directory Federation Services (AD FS 2,0) per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-07-03_

Nella sezione seguente viene descritto come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori. Per informazioni su come installare ADFS 2,0, vedere AD FS 2,0 Step-by-Step e How to Guide at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> Quando si installa AD FS 2,0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services. Al contrario, scaricare e installare il pacchetto Active Directory Federation Services 2,0 RTW <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>all'indirizzo.



</div>

<div>


**Per configurare AD FS per l'autenticazione a due fattori**

1.  Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.

2.  Avviare Windows PowerShell.

3.  Dalla riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Stabilire una partnership con ogni Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Director, Enterprise pool e Standard Edition server che verrà abilitato per l'autenticazione passiva eseguendo il comando riportato di seguito, sostituendo il nome del server specifico della distribuzione:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  Dal menu strumenti di amministrazione, avviare la console di gestione di AD FS 2,0.

6.  Espandi **relazioni** \> di trust **relying party trust**.

7.  Verificare che sia stata creata una nuova relazione di trust per Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Enterprise pool o server Standard Edition.

8.  Creare e assegnare una regola di autorizzazione di rilascio per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. Dalla console di gestione AD FS 2,0, fare clic con il pulsante destro del mouse sul trust relying party e selezionare **modifica regole attestazione**.

11. Selezionare la scheda **regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.

12. Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.

</div>

</div>

<span> </span>

</div>

</div>

</div>

