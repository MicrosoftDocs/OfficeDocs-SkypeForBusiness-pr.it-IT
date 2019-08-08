---
title: Convalidare la distribuzione di Edge in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: ITPro
manager: serdars
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 69837f86-d141-4884-a4ca-c7e7463afaad
description: 'Riepilogo: informazioni su come verificare che la distribuzione di Edge Server o pool di Edge Server funzioni in Skype for Business Server.'
ms.openlocfilehash: 57994e4583a3424fc680c8dfb220aeb11668c6fc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36234078"
---
# <a name="validate-your-edge-deployment-in-skype-for-business-server"></a><span data-ttu-id="2d0dd-103">Convalidare la distribuzione di Edge in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2d0dd-103">Validate your Edge deployment in Skype for Business Server</span></span>
 
<span data-ttu-id="2d0dd-104">**Riepilogo:** Informazioni su come verificare che la distribuzione di Edge Server o pool di Edge Server funzioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-104">**Summary:** Learn how to verify that your deployment of Edge Server or Edge Server pool is working in Skype for Business Server.</span></span>
  
<span data-ttu-id="2d0dd-105">Dopo aver distribuito il pool di Edge Server o Edge Server, è necessario sapere se funziona correttamente.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-105">Once you've deployed your Edge Server or Edge Server pool, you need to know if it's working properly.</span></span> <span data-ttu-id="2d0dd-106">Ecco alcuni aspetti che possono essere utili per confermare che l'ambiente Edge è connesso ai server interni e che gli utenti esterni possono connettersi all'ambiente di Skype for Business Server tramite il proprio Edge.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-106">Here are a couple of things that can help with confirming your Edge environment is connected to your internal servers, and also that your external users can connect to your Skype for Business Server environment through your Edge.</span></span>
  
## <a name="verify-connectivity-between-your-internal-servers-and-your-edge-servers"></a><span data-ttu-id="2d0dd-107">Verificare la connettività tra i server interni e gli Edge Server</span><span class="sxs-lookup"><span data-stu-id="2d0dd-107">Verify connectivity between your internal servers and your Edge servers</span></span>

<span data-ttu-id="2d0dd-108">Mentre la convalida della connettività viene eseguita automaticamente nel pool di Edge Server o Edge Server quando si installano i server perimetrali, è comunque possibile confermarlo con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-108">While validation of connectivity is done automatically in Edge Server or Edge Server pool when the Edge Servers are installed, you can still confirm this for yourself with Windows PowerShell.</span></span> <span data-ttu-id="2d0dd-109">Eseguire il cmdlet Get-CsManagementStoreReplicationStatus nel server interno che include l'Central Management Store o un computer collegato al dominio in cui sono installati i componenti principali di Skype for Business Server (OcsCore. msi).</span><span class="sxs-lookup"><span data-stu-id="2d0dd-109">Run the Get-CsManagementStoreReplicationStatus cmdlet on the internal server which has the Central Management store, or any domain joined computer on which Skype for Business Server Core Components (OcsCore.msi) are installed.</span></span>
  
<span data-ttu-id="2d0dd-110">Il risultato iniziale dell'uso di questo comando potrebbe dare uno stato falso, anziché vero, per la replica.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-110">The initial result of running this command may give a False status, rather than True, for replication.</span></span> <span data-ttu-id="2d0dd-111">Se ciò accade, eseguire il cmdlet Invoke-CsManagementStoreReplication.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-111">If that happens run the Invoke-CsManagementStoreReplication cmdlet.</span></span> <span data-ttu-id="2d0dd-112">Assegnare un po' di tempo per completare la replica e quindi eseguire di nuovo il cmdlet Get-CsManagementStoreReplicationStatus.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-112">Give it some time to complete the replication, and then run the Get-CsManagementStoreReplicationStatus cmdlet again.</span></span>
  
## <a name="verify-connectivity-for-your-external-users"></a><span data-ttu-id="2d0dd-113">Verificare la connettività per gli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="2d0dd-113">Verify connectivity for your external users</span></span>

<span data-ttu-id="2d0dd-114">Abbiamo un ottimo strumento per confermare la configurazione di Edge Server e la possibilità di connettersi, inviare e ricevere i messaggi corretti per gli scenari di Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-114">We do have a great tool for confirming your Edge Server configuration, and the ability to connect, send and receive the correct messages for Edge Server scenarios.</span></span> <span data-ttu-id="2d0dd-115">Si tratta del [sito di connettività remota Anaylzer](https://testconnectivity.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="2d0dd-115">It's the [Remote Connectivity Anaylzer site](https://testconnectivity.microsoft.com/).</span></span> <span data-ttu-id="2d0dd-116">Si tratta di un sito gestito e mantenuto dal supporto Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-116">This is a site that's managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="2d0dd-117">Per usare questo strumento, passare al sito Web e seguire le istruzioni per scegliere lo scenario appropriato.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-117">To use this tool, browse to the website and follow the instructions to choose the right scenario for you.</span></span>
  
### <a name="things-to-consider-when-testing-external-user-connectivity"></a><span data-ttu-id="2d0dd-118">Considerazioni da tenere in considerazione durante il test della connettività degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="2d0dd-118">Things to consider when testing external user connectivity</span></span>

<span data-ttu-id="2d0dd-119">Qualsiasi test per l'accesso degli utenti esterni deve includere ogni tipo di utente interno supportato dall'organizzazione, che può includere una o tutte le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d0dd-119">Any test for external user access needs to include each type of internal user your organization supports, which could include any or all of the following:</span></span>
  
- <span data-ttu-id="2d0dd-120">Gli utenti provenienti da almeno un dominio federato (consigliamo di testarli tutti però).</span><span class="sxs-lookup"><span data-stu-id="2d0dd-120">Users from at least one federated domain (we do recommend testing them all though).</span></span>
    
- <span data-ttu-id="2d0dd-121">Utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-121">Anonymous users.</span></span>
    
- <span data-ttu-id="2d0dd-122">Gli utenti dell'organizzazione che si sono connessi a Skype for business in remoto, ma non usano VPN.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-122">Users in your organization who are logged into Skype for Business remotely, but aren't using VPN.</span></span>
    
<span data-ttu-id="2d0dd-123">Questi test determineranno se il server perimetrale è:</span><span class="sxs-lookup"><span data-stu-id="2d0dd-123">These tests will determine whether your Edge Server is:</span></span>
  
- <span data-ttu-id="2d0dd-124">Ascolto sulle porte necessarie usando un client Telnet all'esterno della rete.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-124">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
  - <span data-ttu-id="2d0dd-125">Ad esempio: Telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="2d0dd-125">For example: telnet sip.contoso.com 443</span></span>
    
  - <span data-ttu-id="2d0dd-126">È consigliabile eseguire il test precedente nelle porte in uso nell'Edge Server o nel pool di Edge Server, a seconda della distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-126">You should perform the preceding test on the ports you're using on your Edge Server or Edge Server pool, depending on your deployment.</span></span>
    
- <span data-ttu-id="2d0dd-127">Esecuzione di una risoluzione DNS esterna accurata.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-127">Performing accurate external DNS resolution.</span></span>
    
  - <span data-ttu-id="2d0dd-128">Dall'esterno della rete eseguire il ping di tutti i nomi di dominio completi esterni del pool di Edge Server o Edge Server.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-128">From outside your network, ping each of the external FQDNs of your Edge Server or Edge Server pool.</span></span> <span data-ttu-id="2d0dd-129">Anche se il ping non riesce, verranno visualizzati gli indirizzi IP, che possono essere paragonati agli indirizzi IP assegnati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="2d0dd-129">Even if the ping fails, you'll see the IP addresses, which you can compare the IP addresses you've previously assigned.</span></span>
    

