---
title: Aggiornare i record SRV DNS
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.
ms.openlocfilehash: ef77f491efd090949ff5dd6b653dd3cd6ea1cde7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812774"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="1eda1-103">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="1eda1-103">Update DNS SRV records</span></span>

<span data-ttu-id="1eda1-104">Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server o al dominio come membro del gruppo Domain Admins o di un membro del gruppo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="1eda1-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
<span data-ttu-id="1eda1-105">Questo argomento descrive come aggiornare i record DNS (Domain Name System) dopo la migrazione a Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1eda1-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Skype for Business Server 2019.</span></span> <span data-ttu-id="1eda1-106">Dopo che tutti gli utenti sono stati spostati in Skype for Business Server 2019, ma prima che il pool o il Director legacy venga disattivati, è necessario aggiornare i record SRV DNS nel DNS interno per ogni dominio SIP.</span><span class="sxs-lookup"><span data-stu-id="1eda1-106">After all users have been moved to Skype for Business Server 2019, but before the legacy pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="1eda1-107">Questa procedura presuppone che il DNS interno disponga di aree per i domini utente SIP.</span><span class="sxs-lookup"><span data-stu-id="1eda1-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>
  
## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="1eda1-108">Per configurare un record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="1eda1-108">To configure a DNS SRV record</span></span>

1. <span data-ttu-id="1eda1-109">Nel server DNS fare clic sul pulsante **Start**, scegliere **strumenti di amministrazione**e quindi fare clic su **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1eda1-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="1eda1-110">Nell'albero della console per il dominio SIP espandere **aree di ricerca in avanti**, espandere il dominio SIP in cui è installato Skype for Business Server 2019 e passare all'impostazione **_tcp** .</span><span class="sxs-lookup"><span data-stu-id="1eda1-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Skype for Business Server 2019 is installed, and navigate to the **_tcp** setting.</span></span> 
    
3. <span data-ttu-id="1eda1-111">Nel riquadro destro fare clic con il pulsante destro del mouse **_sipinternaltls** e scegliere **Proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1eda1-111">In the right pane, right-click **_sipinternaltls** and select **Properties**.</span></span>
    
4. <span data-ttu-id="1eda1-112">In **host che offre questo servizio**, aggiornare il nome di dominio completo dell'host per posizionare il puntatore sul pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="1eda1-112">In **Host offering this service**, update the host FQDN to point to the Skype for Business Server 2019 pool.</span></span>
    
5. <span data-ttu-id="1eda1-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eda1-113">Click **OK**.</span></span>
    
## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="1eda1-114">Per verificare che il nome di dominio completo del pool Front-end o del server Standard Edition possa essere risolto</span><span class="sxs-lookup"><span data-stu-id="1eda1-114">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1. <span data-ttu-id="1eda1-115">Accedere a un computer client nel dominio.</span><span class="sxs-lookup"><span data-stu-id="1eda1-115">Log on to a client computer in the domain.</span></span>
    
2. <span data-ttu-id="1eda1-116">Fare clic sul pulsante **Start**e quindi su **Esegui**.</span><span class="sxs-lookup"><span data-stu-id="1eda1-116">Click **Start**, and then click **Run**.</span></span>
    
3. <span data-ttu-id="1eda1-117">Nella casella **Apri** Digitare cmd e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1eda1-117">In the **Open** box, type cmd, and then click **OK**.</span></span>
    
4. <span data-ttu-id="1eda1-118">Al prompt dei comandi digitare il _ \<nome di dominio completo nslookup del pool\> di front end_ o _ \<il nome di\>dominio completo del server Standard Edition_, quindi premere INVIO.</span><span class="sxs-lookup"><span data-stu-id="1eda1-118">At the command prompt, type nslookup _\<FQDN of the Front End pool\>_ or  _\<FQDN of the Standard Edition server\>_, and then press ENTER.</span></span>
    
5. <span data-ttu-id="1eda1-119">Verificare di ricevere una risposta che venga risolta nell'indirizzo IP appropriato per il nome di dominio completo.</span><span class="sxs-lookup"><span data-stu-id="1eda1-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>
    

