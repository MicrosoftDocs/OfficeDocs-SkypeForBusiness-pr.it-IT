---
title: Espansione delle impostazioni generali di Mediation Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/14/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0e0ad9f0-27d5-4975-ae88-0b8ff8a4c514
ms.openlocfilehash: a00573b06c1900718fd670c96a21ffab069b491e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806726"
---
# <a name="mediation-server-general-settings-expander"></a><span data-ttu-id="7cfb3-102">Espansione delle impostazioni generali di Mediation Server</span><span class="sxs-lookup"><span data-stu-id="7cfb3-102">Mediation Server General Settings Expander</span></span>
 


## <a name="general-settings"></a><span data-ttu-id="7cfb3-103">Generale</span><span class="sxs-lookup"><span data-stu-id="7cfb3-103">General settings</span></span>

<span data-ttu-id="7cfb3-p101">Nome di dominio completo (FQDN) del pool Mediation Server o del Mediation Server. Modificare l'FQDN del server per cambiarne il valore. È necessario disporre di un record host (A) DNS (Domain Name System) che coincida con il nuovo valore.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-p101">Fully qualified domain name (FQDN) of the Mediation Server pool or Mediation Server. Edit the FQDN of the server to change the value. You must have a Domain Name System (DNS) host (A) record that coincides with the new value.</span></span>
  
<span data-ttu-id="7cfb3-107">Nella sezione **Associazioni** è possibile selezionare un server perimetrale o un pool di server perimetrali da associare al pool Mediation Server o al Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-107">In the **Associations** section, you select an Edge Server or Edge Server pool to associate with the Mediation Server pool or Mediation Server.</span></span> <span data-ttu-id="7cfb3-108">Selezionare il server perimetrale che verrà utilizzato dai componenti multimediali del Mediation Server per gli utenti VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-108">You select the Edge that the Mediation Server's media components will use for External user Enterprise Voice.</span></span>
  
<span data-ttu-id="7cfb3-109">Se attualmente non è definito un server perimetrale ed è necessario associare il Mediation Server a un server di questo tipo, fare clic su **Nuovo** e definire il nuovo server perimetrale o il nuovo pool di server perimetrali nella procedura guidata Definisci pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-109">If you do not have an Edge Server currently defined and need to associate the Mediation Server with an Edge Server, click **New** and define the new Edge Server or Edge Server pool in the Define the New Edge pool wizard.</span></span>
  
## <a name="next-hop-settings"></a><span data-ttu-id="7cfb3-110">Hop successivo</span><span class="sxs-lookup"><span data-stu-id="7cfb3-110">Next hop settings</span></span>

<span data-ttu-id="7cfb3-111">È possibile specificare l'hop successivo del pool Mediation Server o del Mediation Server selezionando nell'elenco a discesa il pool Enterprise Edition Front End o il server Standard Edition Front End Server definito.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-111">You specify the Mediation Server pool or Mediation Server next hop by selecting the defined Enterprise Edition Front End pool or Standard Edition Front End Server from the drop-down list.</span></span> <span data-ttu-id="7cfb3-112">Un server Director o un pool di server Director non è una selezione valida per l'hop successivo di un pool Mediation Server o di un Mediation Server e non verrà visualizzato nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-112">A Director or Director pool is not a valid selection for a Mediation Server pool or Mediation Server next hop, and will not appear in the list.</span></span> <span data-ttu-id="7cfb3-113">Fare **clic su OK** per accettare e salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-113">Click **OK** to accept and save your changes.</span></span> <span data-ttu-id="7cfb3-114">Fare clic su **Annulla** per rimuovere le modifiche e uscire dalla pagina delle proprietà.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-114">Click **Cancel** to discard your changes and exit the properties page.</span></span>
  
## <a name="pstn-gateway-settings"></a><span data-ttu-id="7cfb3-115">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="7cfb3-115">PSTN gateway settings</span></span>

1. <span data-ttu-id="7cfb3-p104">Definire gateway PSTN associati al pool Mediation Server o al Mediation Server. Se i gateway sono già stati definiti, saranno disponibili per l'associazione al Mediation Server. Se si abilita la collocazione del Mediation Server, definire l'intervallo di porte di attesa nei server del pool per TLS (Transport Layer Security). Per impostazione predefinita, questa porta è la 5067. Se si seleziona **Abilita porta TCP**, sarà necessario definire una porta TCP (Transmission Control Protocol) per il Mediation Server collocato. Questa è un'impostazione facoltativa e, per determinare se sia necessaria, è consigliabile fare riferimento ai requisiti del gateway o della rete PSTN. Per impostazione predefinita, il valore della porta TCP è 5068.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-p104">You define PSTN gateways that are associated with the Mediation Server pool or Mediation Server. If you have already defined gateways, they will be available to associate with the Mediation Server. If you enable the collocation of the Mediation Server, define the listening port range on the pool servers for Transport Layer Security (TLS). By default, this port is 5067. If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server. This is an optional setting, and you should refer to the requirements of your gateway or PSTN requirements to determine if you need this. By default, the TCP port value is 5068.</span></span>
    
2. <span data-ttu-id="7cfb3-p105">Trunk associati al Mediation Server nella stessa posizione. Se i trunk sono già stati definiti, saranno disponibili per l'associazione a Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-p105">Trunks that are associated with the collocated Mediation Server. If you have already defined trunks, they will be available to associate with the Mediation Server.</span></span> 
    
3. <span data-ttu-id="7cfb3-p106">Se a Mediation Server sono associati più trunk, sarà possibile specificare un trunk predefinito, selezionando il trunk e quindi facendo clic su **Rendi predefinito**. Per annullare la selezione di un gateway come predefinito, fare clic su **Annulla predefinito**.</span><span class="sxs-lookup"><span data-stu-id="7cfb3-p106">If you have more than one trunk associated with a Mediation Server, you can specify a default trunk by selecting the trunk and then clicking **Make Default**. To unselect a gateway as the default, click **Unmake Default**.</span></span> 
    

