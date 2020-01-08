---
title: 'Lync Server 2013: configurazione di Active Directory Federation Services (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a88fb9db7109bdd2a2938f8f9624b4fd0f369fd9
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40982165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="2125d-102">Configurazione di Active Directory Federation Services (AD FS 2,0) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2125d-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2125d-103">_**Argomento Ultima modifica:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="2125d-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="2125d-104">La sezione seguente descrive come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="2125d-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="2125d-105">Per informazioni su come installare ADFS 2,0, vedere istruzioni dettagliate su ADFS 2,0 e su come eseguire le guide [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span><span class="sxs-lookup"><span data-stu-id="2125d-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="2125d-106">Quando si installa ADFS 2,0, non usare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="2125d-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="2125d-107">Scaricare e installare invece il pacchetto-RTW di <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>Active Directory Federation Services 2,0.</span><span class="sxs-lookup"><span data-stu-id="2125d-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="2125d-108">**Per configurare ADFS per l'autenticazione a due fattori**</span><span class="sxs-lookup"><span data-stu-id="2125d-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="2125d-109">Accedere al computer ADFS 2,0 usando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="2125d-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="2125d-110">Avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2125d-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="2125d-111">Nella riga di comando di Windows PowerShell eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="2125d-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="2125d-112">Stabilire una partnership con ogni Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Director, Enterprise pool e Standard Edition server che verranno abilitati per l'autenticazione passiva eseguendo il comando seguente, sostituendo il nome server specifico della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="2125d-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="2125d-113">Nel menu strumenti di amministrazione avviare la console di gestione di ADFS 2,0.</span><span class="sxs-lookup"><span data-stu-id="2125d-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="2125d-114">Espandere i **trust** **tra le relazioni** \> di trust.</span><span class="sxs-lookup"><span data-stu-id="2125d-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="2125d-115">Verificare che sia stato creato un nuovo trust per Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Enterprise pool o Standard Edition Server.</span><span class="sxs-lookup"><span data-stu-id="2125d-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="2125d-116">Creare e assegnare una regola di autorizzazione del rilascio per l'attendibilità del componente tramite Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2125d-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="2125d-117">Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente usando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2125d-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="2125d-118">Nella console di gestione di ADFS 2,0 fare clic con il pulsante destro del mouse sull'attendibilità del componente e scegliere **modifica regole attestazione**.</span><span class="sxs-lookup"><span data-stu-id="2125d-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="2125d-119">Selezionare la scheda **regole di autorizzazione del rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2125d-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="2125d-120">Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="2125d-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

