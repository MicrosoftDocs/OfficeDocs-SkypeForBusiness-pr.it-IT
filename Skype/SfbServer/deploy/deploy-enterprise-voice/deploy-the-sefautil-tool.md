---
title: Distribuire lo strumento SEFAUtil in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Distribuzione dello strumento SEFAUtil in Skype for Business Server.
ms.openlocfilehash: 1721f4d611a08a3054366e36b0ec9a3ebccf6c78
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245781"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="184d9-103">Distribuire lo strumento SEFAUtil in Skype for business</span><span class="sxs-lookup"><span data-stu-id="184d9-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="184d9-104">Distribuzione dello strumento SEFAUtil in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="184d9-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="184d9-105">Per distribuire e gestire il ritiro delle chiamate di gruppo, è necessario usare la versione di Skype for Business Server dello strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="184d9-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="184d9-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="184d9-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="184d9-107">Scaricalo qui: [Unified Communications Managed API 5,0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span><span class="sxs-lookup"><span data-stu-id="184d9-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=47344).</span></span> <span data-ttu-id="184d9-108">È anche possibile scaricare il UCMA 5 SDK, che include il runtime, qui: [UCMA 5,0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span><span class="sxs-lookup"><span data-stu-id="184d9-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/en-us/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="184d9-109">È possibile eseguire lo strumento SEFAUtil in qualsiasi pool Front-end della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="184d9-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="184d9-110">Per eseguire lo strumento SEFAUtil, è necessario eseguire i passaggi 1, 2 e 3 della distribuzione guidata di Skype for business nel computer dell'applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="184d9-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="184d9-111">SEFAUtil richiede che l'archivio di configurazione locale sia presente, oltre a un certificato.</span><span class="sxs-lookup"><span data-stu-id="184d9-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="184d9-112">Per altre informazioni sull'uso di SEFAUtil, vedere l'articolo su Blog "[come ottenere SEFAUtil in uso?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="184d9-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="184d9-113">Per distribuire SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="184d9-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="184d9-114">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di **configurazione**Delegate.</span><span class="sxs-lookup"><span data-stu-id="184d9-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="184d9-115">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="184d9-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="184d9-116">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibile.</span><span class="sxs-lookup"><span data-stu-id="184d9-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="184d9-117">Se necessario, definire un pool di applicazioni attendibili per il pool Front-end in cui si prevede di eseguire SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="184d9-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="184d9-118">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="184d9-118">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="184d9-119">FQDN del pool: il nome di dominio completo del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un server front-end o un pool di Skype for business).</span><span class="sxs-lookup"><span data-stu-id="184d9-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="184d9-120">FQDN del registrar del pool: il nome di dominio completo del server front end o del pool di Skype for business associato al pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="184d9-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="184d9-121">Sito del pool: ID sito del sito in cui è ospitato questo pool.</span><span class="sxs-lookup"><span data-stu-id="184d9-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="184d9-122">Definire lo strumento SEFAUtil come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="184d9-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="184d9-123">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="184d9-123">At the command line, run:</span></span>
    
   ```
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="184d9-124">Se necessario, è possibile usare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="184d9-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="184d9-125">Abilitare la topologia con le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="184d9-125">Enable the topology with your changes.</span></span> <span data-ttu-id="184d9-126">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="184d9-126">At the command line, run:</span></span>
    
   ```
   Enable-CsTopology
   ```

6. <span data-ttu-id="184d9-127">Se non è già stato fatto, scaricare la versione di Skype for Business Server dello strumento SEFAUtil da [questo percorso](https://www.microsoft.com/en-us/download/details.aspx?id=52631)e installarlo nel pool di applicazioni attendibile creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="184d9-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/en-us/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="184d9-128">Verificare che lo strumento SEFAUtil sia in uso correttamente, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="184d9-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="184d9-129">un.</span><span class="sxs-lookup"><span data-stu-id="184d9-129">a.</span></span> <span data-ttu-id="184d9-130">Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="184d9-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="184d9-131">b.</span><span class="sxs-lookup"><span data-stu-id="184d9-131">b.</span></span> <span data-ttu-id="184d9-132">Visualizzare le impostazioni di inoltro di chiamata di un utente.</span><span class="sxs-lookup"><span data-stu-id="184d9-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="184d9-133">Nella riga di comando eseguire:</span><span class="sxs-lookup"><span data-stu-id="184d9-133">At the command line, run:</span></span>
    
   ```
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="184d9-134">Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="184d9-134">The call forwarding settings for the user will be displayed.</span></span>
    

