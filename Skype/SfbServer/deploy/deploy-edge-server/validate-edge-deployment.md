---
title: Convalidare la distribuzione di Edge in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Riepilogo: informazioni su come verificare che la distribuzione di server perimetrali o pool di server perimetrali funzioni in Skype for Business Server.'
ms.openlocfilehash: 1da2bed1bc9df7cb118d47c2b27e190546838e1b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804356"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="1c60c-103">Convalidare la distribuzione di Edge in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1c60c-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="1c60c-104">**Riepilogo:** Informazioni su come verificare che la distribuzione di server perimetrali o pool di server perimetrali funzioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1c60c-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="1c60c-105">Dopo aver distribuito un server perimetrale o un pool di server perimetrali, è necessario sapere se funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="1c60c-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="1c60c-106">Di seguito sono riportate alcune operazioni che possono essere utili per confermare che l'ambiente Edge è connesso ai server interni e che gli utenti esterni possono connettersi all'ambiente Skype for Business Server tramite il proprio Edge.</span><span class="sxs-lookup"><span data-stu-id="1c60c-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="1c60c-107">Verificare la connettività tra i server interni e i server perimetrali</span><span class="sxs-lookup"><span data-stu-id="1c60c-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="1c60c-108">Mentre la convalida della connettività viene eseguita automaticamente nel server perimetrale o nel pool di server perimetrali quando vengono installati i server perimetrali, è comunque possibile confermarla con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1c60c-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="1c60c-109">Eseguire il cmdlet Get-CsManagementStoreReplicationStatus sul server interno con l'archivio di gestione centrale o su un computer aggiunto al dominio in cui sono installati i componenti di base di Skype for Business Server (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="1c60c-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="1c60c-110">Il risultato iniziale dell'esecuzione di questo comando può fornire uno stato false, anziché vero, per la replica.</span><span class="sxs-lookup"><span data-stu-id="1c60c-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="1c60c-111">Se ciò accade, eseguire il cmdlet Invoke-CsManagementStoreReplication.</span><span class="sxs-lookup"><span data-stu-id="1c60c-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="1c60c-112">Fornire un po' di tempo per completare la replica e quindi eseguire di nuovo il cmdlet Get-CsManagementStoreReplicationStatus.</span><span class="sxs-lookup"><span data-stu-id="1c60c-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="1c60c-113">Verificare la connettività per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="1c60c-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="1c60c-114">È presente un ottimo strumento per confermare la configurazione del server perimetrale e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari del server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="1c60c-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="1c60c-115">Si tratta del [sito Anaylzer di connettività remota](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="1c60c-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="1c60c-116">Si tratta di un sito gestito e mantenuto dal supporto tecnico Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1c60c-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="1c60c-117">Per utilizzare questo strumento, passare al sito Web e seguire le istruzioni riportate di seguito per scegliere lo scenario appropriato.</span><span class="sxs-lookup"><span data-stu-id="1c60c-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="1c60c-118">Considerazioni da prendere in considerazione quando si verifica la connettività degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="1c60c-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="1c60c-119">Qualsiasi test per l'accesso degli utenti esterni deve includere ogni tipo di utente interno supportato dall'organizzazione, in modo da includere una o tutte le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1c60c-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="1c60c-120">Utenti provenienti da almeno un dominio federato (si consiglia di testarli tutti anche se).</span><span class="sxs-lookup"><span data-stu-id="1c60c-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="1c60c-121">Utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="1c60c-121">Anonymous users.</span></span>
    
- <span data-ttu-id="1c60c-122">Gli utenti dell'organizzazione che hanno eseguito l'accesso a Skype for business in remoto, ma non utilizzano la VPN.</span><span class="sxs-lookup"><span data-stu-id="1c60c-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="1c60c-123">Questi test determineranno se il server perimetrale è:</span><span class="sxs-lookup"><span data-stu-id="1c60c-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="1c60c-124">È in attesa sulle porte necessarie tramite un client telnet dall'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="1c60c-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="1c60c-125">Ad esempio: Telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="1c60c-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="1c60c-126">È consigliabile eseguire il test precedente nelle porte che si sta utilizzando nel server perimetrale o nel pool di server perimetrali, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="1c60c-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="1c60c-127">Esegue la risoluzione DNS esterna in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="1c60c-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="1c60c-128">Al di fuori della rete, eseguire il ping di ogni FQDN esterno del server perimetrale o del pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="1c60c-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="1c60c-129">Anche se il ping ha esito negativo, verranno visualizzati gli indirizzi IP, che possono essere confrontati con gli indirizzi IP precedentemente assegnati.</span><span class="sxs-lookup"><span data-stu-id="1c60c-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

