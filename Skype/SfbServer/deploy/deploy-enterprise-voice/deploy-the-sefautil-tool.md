---
title: Distribuire lo strumento SEFAUtil in Skype for Business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: fb556e50-88dd-4404-a3d5-be36f5ba41e6
description: Distribuzione dello strumento SEFAUtil in Skype for Business Server.
ms.openlocfilehash: 20cda161c182c8dfb426f61b793366b7f60f37d5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812386"
---
# <a name="deploy-the-sefautil-tool-in-skype-for-business"></a><span data-ttu-id="27aa5-103">Distribuire lo strumento SEFAUtil in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="27aa5-103">Deploy the SEFAUtil tool in Skype for Business</span></span>
 
<span data-ttu-id="27aa5-104">Distribuzione dello strumento SEFAUtil in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="27aa5-104">Deploying the SEFAUtil tool in Skype for Business Server.</span></span>
  
<span data-ttu-id="27aa5-105">Per distribuire e gestire la risposta alle chiamate di gruppo, è necessario usare la versione Skype for Business Server dello strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="27aa5-105">To deploy and manage Group Call Pickup, you need to use the Skype for Business Server version of the SEFAUtil tool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="27aa5-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime deve essere installato in qualsiasi computer in cui si prevede di eseguire lo strumento SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="27aa5-106">Microsoft Unified Communications Managed API (UCMA) 5 Runtime must be installed on any computer where you plan to run the SEFAUtil tool.</span></span> <span data-ttu-id="27aa5-107">Scaricalo qui: [Unified Communications Managed API 5.0 Runtime.](https://www.microsoft.com/download/details.aspx?id=47344)</span><span class="sxs-lookup"><span data-stu-id="27aa5-107">Download it here: [Unified Communications Managed API 5.0 Runtime](https://www.microsoft.com/download/details.aspx?id=47344).</span></span> <span data-ttu-id="27aa5-108">Puoi anche scaricare UCMA 5 SDK, che include il runtime, qui: [UCMA 5.0 SDK.](https://www.microsoft.com/download/details.aspx?id=47345)</span><span class="sxs-lookup"><span data-stu-id="27aa5-108">You can also download the UCMA 5 SDK, which includes the runtime, here: [UCMA 5.0 SDK](https://www.microsoft.com/download/details.aspx?id=47345).</span></span>
  
<span data-ttu-id="27aa5-109">È possibile eseguire lo strumento SEFAUtil in qualsiasi pool Front End della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="27aa5-109">You can run the SEFAUtil tool in any Front End pool in your deployment.</span></span> <span data-ttu-id="27aa5-110">Per eseguire lo strumento SEFAUtil, è necessario eseguire i passaggi 1, 2 e 3 dalla Distribuzione guidata di Skype for Business nel computer dell'applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="27aa5-110">To run the SEFAUtil tool you must run Steps 1, 2, and 3 from the Skype for Business Deployment Wizard on the Trusted Application Computer.</span></span> <span data-ttu-id="27aa5-111">SEFAUtil richiede che sia presente l'archivio di configurazione locale, nonché un certificato.</span><span class="sxs-lookup"><span data-stu-id="27aa5-111">SEFAUtil requires the local configuration store to be present, as well as a certificate.</span></span>
  
> [!NOTE]
> <span data-ttu-id="27aa5-112">Per altri dettagli sull'esecuzione di SEFAUtil, vedi l'articolo del blog "[Come eseguire SEFAutil?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span><span class="sxs-lookup"><span data-stu-id="27aa5-112">For more details about running SEFAUtil, see the  blog article, "[How to get SEFAutil running?](https://go.microsoft.com/fwlink/?LinkId=278940)".</span></span> 
  
### <a name="to-deploy-sefautil"></a><span data-ttu-id="27aa5-113">Per distribuire SEFAUtil</span><span class="sxs-lookup"><span data-stu-id="27aa5-113">To deploy SEFAUtil</span></span>

1. <span data-ttu-id="27aa5-114">Accedere al computer in cui è installato Skype for Business Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in Delegare le autorizzazioni di **installazione.**</span><span class="sxs-lookup"><span data-stu-id="27aa5-114">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="27aa5-115">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="27aa5-115">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="27aa5-116">Lo strumento SEFAUtil può essere eseguito solo in un computer che fa parte di un pool di applicazioni attendibili.</span><span class="sxs-lookup"><span data-stu-id="27aa5-116">The SEFAUtil tool can be run only on a computer that is part of a trusted application pool.</span></span> <span data-ttu-id="27aa5-117">Se necessario, definire un pool di applicazioni attendibili per il pool Front End in cui si prevede di eseguire SEFAUtil.</span><span class="sxs-lookup"><span data-stu-id="27aa5-117">If needed, define a trusted application pool for the Front End pool where you plan to run SEFAUtil.</span></span> <span data-ttu-id="27aa5-118">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="27aa5-118">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplicationPool -id <Pool FQDN> -Registrar <Pool Registrar FQDN> -site Site:<Pool Site>
   ```
    > [!NOTE]
    > <span data-ttu-id="27aa5-119">FQDN pool: FQDN del server o del pool che ospiterà l'applicazione SEFAUtil (in genere un pool o un server Front End Skype for Business).</span><span class="sxs-lookup"><span data-stu-id="27aa5-119">Pool FQDN: The FQDN of the server or pool that will host the SEFAUtil application (usually a Skype for Business Front End server or pool).</span></span>
    > <span data-ttu-id="27aa5-120">FQDN funzione di registrazione pool: FQDN del server Front End Skype for Business o del pool associato a questo pool di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="27aa5-120">Pool Registrar FQDN: The FQDN of the Skype for Business Front End server or pool associated with this application pool.</span></span>
    > <span data-ttu-id="27aa5-121">Sito pool: ID sito del sito in cui si trova il pool.</span><span class="sxs-lookup"><span data-stu-id="27aa5-121">Pool Site: The Site ID of the site on which this pool is homed.</span></span>

4. <span data-ttu-id="27aa5-122">Definire lo strumento SEFAUtil come applicazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="27aa5-122">Define the SEFAUtil tool as a trusted application.</span></span> <span data-ttu-id="27aa5-123">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="27aa5-123">At the command line, run:</span></span>
    
   ```powershell
   New-CsTrustedApplication -ApplicationId sefautil -TrustedApplicationPoolFqdn <Pool FQDN>  -Port 7489
   ```

    > [!NOTE]
    > <span data-ttu-id="27aa5-124">Se necessario, è possibile utilizzare una porta diversa.</span><span class="sxs-lookup"><span data-stu-id="27aa5-124">You can use a different port if needed.</span></span> 
  
5. <span data-ttu-id="27aa5-125">Abilitare la topologia con le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="27aa5-125">Enable the topology with your changes.</span></span> <span data-ttu-id="27aa5-126">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="27aa5-126">At the command line, run:</span></span>
    
   ```powershell
   Enable-CsTopology
   ```

6. <span data-ttu-id="27aa5-127">Se non lo hai già fatto, scarica la versione Skype [](https://www.microsoft.com/download/details.aspx?id=52631)for Business Server dello strumento SEFAUtil da questo percorso e installala nel pool di applicazioni attendibili creato nel passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="27aa5-127">If you haven't already, download the Skype for Business Server version of the SEFAUtil tool from [this location](https://www.microsoft.com/download/details.aspx?id=52631), and install it on the trusted application pool you created in step 3.</span></span>
    
7. <span data-ttu-id="27aa5-128">Verificare che lo strumento SEFAUtil sia in esecuzione correttamente, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="27aa5-128">Verify that the SEFAUtil tool is running correctly, as follows:</span></span> 
    
    <span data-ttu-id="27aa5-129">a.</span><span class="sxs-lookup"><span data-stu-id="27aa5-129">a.</span></span> <span data-ttu-id="27aa5-130">Eseguire lo strumento dal prompt dei comandi di Windows con privilegi di amministratore per visualizzare le impostazioni di inoltro di chiamata di un utente nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="27aa5-130">Run the tool from the Windows command prompt with administrator privileges to display the call forwarding settings of a user in your deployment.</span></span>
    
    <span data-ttu-id="27aa5-131">b.</span><span class="sxs-lookup"><span data-stu-id="27aa5-131">b.</span></span> <span data-ttu-id="27aa5-132">Visualizzare le impostazioni di inoltro di chiamata di un utente.</span><span class="sxs-lookup"><span data-stu-id="27aa5-132">Display the call forwarding settings of a user.</span></span> <span data-ttu-id="27aa5-133">Nella riga di comando digitare il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="27aa5-133">At the command line, run:</span></span>
    
   ```console
   SEFAUtil.exe <user SIP address> /server:<Lync Server/Pool FQDN>
   ```

<span data-ttu-id="27aa5-134">Verranno visualizzate le impostazioni di inoltro di chiamata per l'utente.</span><span class="sxs-lookup"><span data-stu-id="27aa5-134">The call forwarding settings for the user will be displayed.</span></span>
    

