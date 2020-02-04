---
title: Espansione delle impostazioni generali di Mediation Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a460cfcaf696740fa108be451156d53bec96f95d
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697001"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="520ec-102">Espansione delle impostazioni generali di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="520ec-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="520ec-103">Impostazioni generali</span><span class="sxs-lookup"><span data-stu-id="520ec-103">General settings</span></span>

<span data-ttu-id="520ec-104">Nome di dominio completo (FQDN) del pool di Mediation Server o Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="520ec-104">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="520ec-105">Modificare l'FQDN del server per cambiarne il valore.</span><span class="sxs-lookup"><span data-stu-id="520ec-105">Edit the FQDN of the server to change the value.</span></span> <span data-ttu-id="520ec-106">È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="520ec-106">You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="520ec-107">Nella sezione **associazioni** selezionare un server perimetrale o un pool di Edge Server da associare al pool di Mediation Server o Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="520ec-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="520ec-108">Si seleziona il bordo che verrà usato dai componenti multimediali del Mediation Server per l'utente esterno VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="520ec-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="520ec-109">Se non si dispone di un server perimetrale attualmente definito e si deve associare il Mediation Server a un server perimetrale, fare clic su **nuovo** e definire il nuovo pool di Edge Server o Edge Server nella procedura guidata Definisci nuovo pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="520ec-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="520ec-110">Impostazioni dell'hop successivo</span><span class="sxs-lookup"><span data-stu-id="520ec-110">Next hop settings</span></span>

<span data-ttu-id="520ec-111">È possibile specificare il pool di Mediation Server o Mediation Server next hop selezionando il pool di front end Enterprise Edition definito o il server front-end Standard Edition nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="520ec-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="520ec-112">Un pool di Director o Director non è una selezione valida per un pool di Mediation Server o un Mediation Server next hop e non verrà visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="520ec-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="520ec-113">Fare clic su **OK** per accettare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="520ec-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="520ec-114">Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="520ec-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="520ec-115">Impostazioni gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="520ec-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="520ec-116">Puoi definire i gateway PSTN associati al pool di Mediation Server o Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="520ec-116">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="520ec-117">Se sono già stati definiti gateway, saranno disponibili per l'associazione con il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="520ec-117">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> <span data-ttu-id="520ec-118">Se si abilita la collocazione del Mediation Server, definire l'intervallo di porte di attesa nei server del pool per TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="520ec-118">If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS).</span></span> <span data-ttu-id="520ec-119">Per impostazione predefinita, questa porta è la 5067.</span><span class="sxs-lookup"><span data-stu-id="520ec-119">By default, this port is 5067.</span></span> <span data-ttu-id="520ec-120">Se si seleziona **Abilita la porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato.</span><span class="sxs-lookup"><span data-stu-id="520ec-120">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="520ec-121">Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="520ec-121">This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this.</span></span> <span data-ttu-id="520ec-122">Per impostazione predefinita, il valore della porta TCP è 5068.</span><span class="sxs-lookup"><span data-stu-id="520ec-122">By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="520ec-p105">I trunk associati al Mediation Server collocato. Se sono già stati definiti, i trunk potranno essere associati al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="520ec-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="520ec-125">Se si ha più di un trunk associato a un Mediation Server, è possibile specificare un trunk predefinito selezionando il trunk e quindi facendo clic su **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="520ec-125">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**.</span></span> <span data-ttu-id="520ec-126">Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.</span><span class="sxs-lookup"><span data-stu-id="520ec-126">To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

