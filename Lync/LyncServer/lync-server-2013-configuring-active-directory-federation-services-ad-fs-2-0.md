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

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a><span data-ttu-id="0327f-102">Configurazione di Active Directory Federation Services (AD FS 2,0) per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0327f-102">Configuring Active Directory Federation Services (AD FS 2.0) for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0327f-103">_**Ultimo argomento modificato:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="0327f-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="0327f-104">Nella sezione seguente viene descritto come configurare Active Directory Federation Services (AD FS 2,0) per supportare l'autenticazione a più fattori.</span><span class="sxs-lookup"><span data-stu-id="0327f-104">The following section describes how to configure Active Directory Federation Services (AD FS 2.0) to support multi-factor authentication.</span></span> <span data-ttu-id="0327f-105">Per informazioni su come installare ADFS 2,0, vedere AD FS 2,0 Step-by-Step e How to Guide at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span><span class="sxs-lookup"><span data-stu-id="0327f-105">For information on how to install AD FS 2.0, see AD FS 2.0 Step-by-Step and How To Guides at [https://go.microsoft.com/fwlink/p/?LinkId=313374](https://go.microsoft.com/fwlink/p/?linkid=313374).</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="0327f-106">Quando si installa AD FS 2,0, non utilizzare Windows Server Manager per aggiungere il ruolo Active Directory Federation Services.</span><span class="sxs-lookup"><span data-stu-id="0327f-106">When installing AD FS 2.0, do not use the Windows Server Manager to add the Active Directory Federation Services role.</span></span> <span data-ttu-id="0327f-107">Al contrario, scaricare e installare il pacchetto Active Directory Federation Services 2,0 RTW <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="0327f-107">Instead, download and install the Active Directory Federation Services 2.0 RTW package at <A href="https://go.microsoft.com/fwlink/p/?linkid=313375">https://go.microsoft.com/fwlink/p/?LinkId=313375</A>.</span></span>



</div>

<div>


<span data-ttu-id="0327f-108">**Per configurare AD FS per l'autenticazione a due fattori**</span><span class="sxs-lookup"><span data-stu-id="0327f-108">**To configure AD FS for two-factor Authentication**</span></span>

1.  <span data-ttu-id="0327f-109">Accedere al computer AD FS 2,0 utilizzando un account di amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="0327f-109">Log in to the AD FS 2.0 computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="0327f-110">Avviare Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0327f-110">Start Windows PowerShell.</span></span>

3.  <span data-ttu-id="0327f-111">Dalla riga di comando di Windows PowerShell, eseguire il comando riportato di seguito:</span><span class="sxs-lookup"><span data-stu-id="0327f-111">From the Windows PowerShell command-line, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  <span data-ttu-id="0327f-112">Stabilire una partnership con ogni Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Director, Enterprise pool e Standard Edition server che verrà abilitato per l'autenticazione passiva eseguendo il comando riportato di seguito, sostituendo il nome del server specifico della distribuzione:</span><span class="sxs-lookup"><span data-stu-id="0327f-112">Establish a partnership with each Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command, replacing the server name specific to your deployment:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  <span data-ttu-id="0327f-113">Dal menu strumenti di amministrazione, avviare la console di gestione di AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="0327f-113">From the Administrative Tools menu, launch the AD FS 2.0 Management console.</span></span>

6.  <span data-ttu-id="0327f-114">Espandi **relazioni** \> di trust **relying party trust**.</span><span class="sxs-lookup"><span data-stu-id="0327f-114">Expand **Trust Relationships** \> **Relying Party Trusts**.</span></span>

7.  <span data-ttu-id="0327f-115">Verificare che sia stata creata una nuova relazione di trust per Lync Server 2013 con aggiornamenti cumulativi per Lync Server 2013: luglio 2013 Enterprise pool o server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="0327f-115">Verify that a new trust has been created for your Lync Server 2013 with Cumulative Updates for Lync Server 2013: July 2013 Enterprise Pool or Standard Edition server.</span></span>

8.  <span data-ttu-id="0327f-116">Creare e assegnare una regola di autorizzazione di rilascio per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0327f-116">Create and assign an Issuance Authorization Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  <span data-ttu-id="0327f-117">Creare e assegnare una regola di trasformazione dell'emissione per l'attendibilità del componente utilizzando Windows PowerShell eseguendo i comandi seguenti:</span><span class="sxs-lookup"><span data-stu-id="0327f-117">Create and assign an Issuance Transform Rule for your relying party trust using Windows PowerShell by running the following commands:</span></span>
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. <span data-ttu-id="0327f-118">Dalla console di gestione AD FS 2,0, fare clic con il pulsante destro del mouse sul trust relying party e selezionare **modifica regole attestazione**.</span><span class="sxs-lookup"><span data-stu-id="0327f-118">From the AD FS 2.0 Management console, right click on your relying party trust and select **Edit Claim Rules**.</span></span>

11. <span data-ttu-id="0327f-119">Selezionare la scheda **regole di autorizzazione rilascio** e verificare che la nuova regola di autorizzazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0327f-119">Select the **Issuance Authorization Rules** tab and verify that the new authorization rule was created successfully.</span></span>

12. <span data-ttu-id="0327f-120">Selezionare la scheda **regole di trasformazione rilascio** e verificare che la nuova regola di trasformazione sia stata creata correttamente.</span><span class="sxs-lookup"><span data-stu-id="0327f-120">Select the **Issuance Transform Rules** tab and verify that the new transform rule was created successfully.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

