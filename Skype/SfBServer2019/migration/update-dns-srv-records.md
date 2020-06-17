---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.
ms.openlocfilehash: 26bb80618868a2bec03d1de32f6c010869b8cf8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753268"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="0cf04-103">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="0cf04-103">Update DNS SRV records</span></span>

<span data-ttu-id="0cf04-104">Per eseguire correttamente questa procedura, è necessario connettersi al server o al dominio come membro del gruppo Domain Admins o DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="0cf04-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="0cf04-105">In questo argomento viene descritto come aggiornare i record DNS (Domain Name System) dopo la migrazione a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0cf04-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="0cf04-106">Dopo che tutti gli utenti sono stati spostati in Skype for Business Server 2019, ma prima che il pool o il Director legacy venga rimosso, è necessario aggiornare i record DNS SRV nel DNS interno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="0cf04-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="0cf04-107">Per questa procedura si presuppone che nel sistema DNS interno siano disponibili aree per i domini utente SIP.</span><span class="sxs-lookup"><span data-stu-id="0cf04-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="0cf04-108">Per configurare un record DNS SRV</span><span class="sxs-lookup"><span data-stu-id="0cf04-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="0cf04-109">Nel server DNS fare clic sul pulsante **Start**, scegliere **Strumenti di amministrazione** e quindi **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0cf04-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="0cf04-110">Nell'albero della console per il dominio SIP espandere **zone di ricerca diretta**, espandere il dominio SIP in cui è installato Skype for Business Server 2019 e passare all'impostazione **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="0cf04-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="0cf04-111">Nel riquadro destro fare clic con il pulsante destro del mouse su **_sipinternaltls** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="0cf04-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="0cf04-112">In **host che offre questo servizio**aggiornare il nome di dominio completo host in modo che punti al pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0cf04-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="0cf04-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cf04-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="0cf04-114">Per verificare che il nome di domino completo del pool Front End o del server Standard Edition possa essere risolto</span><span class="sxs-lookup"><span data-stu-id="0cf04-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="0cf04-115">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="0cf04-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="0cf04-116">Fare clic sul pulsante **Start** e quindi scegliere **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="0cf04-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="0cf04-117">Nella casella **Apri** Digitare cmd e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="0cf04-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="0cf04-118">Al prompt dei comandi digitare nslookup _\<FQDN of the Front End pool\>_ o _\<FQDN of the Standard Edition server\>_ , quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="0cf04-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="0cf04-119">Verificare di ricevere una risposta che si risolve nell'indirizzo IP appropriato per il nome FQDN.</span><span class="sxs-lookup"><span data-stu-id="0cf04-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

