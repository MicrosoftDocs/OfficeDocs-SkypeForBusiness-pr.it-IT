---
title: Configurare un'applicazione SNMP in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Configurare un'applicazione SNMP per l'uso con E9-1-1 in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195490"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="07e5f-103">Configurare un'applicazione SNMP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="07e5f-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="07e5f-104">Configurare un'applicazione SNMP per l'uso con E9-1-1 in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="07e5f-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="07e5f-105">Skype for Business Server include un'interfaccia di servizio Web standard che puoi usare per connettere il servizio informazioni sulla posizione alle applicazioni SNMP (Simple Network Management Protocol) che corrispondono agli indirizzi MAC con le informazioni sulla porta e sullo switch.</span><span class="sxs-lookup"><span data-stu-id="07e5f-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="07e5f-106">Se è installata un'applicazione SNMP e il servizio informazioni sulla posizione non riesce a trovare una corrispondenza nel database della posizione, il servizio informazioni sulla posizione esegue automaticamente una query nell'applicazione usando l'indirizzo MAC fornito dal client.</span><span class="sxs-lookup"><span data-stu-id="07e5f-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="07e5f-107">Il servizio informazioni sulla posizione usa quindi la porta e cambia le informazioni restituite dall'applicazione SNMP per interrogare di nuovo il database della posizione.</span><span class="sxs-lookup"><span data-stu-id="07e5f-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="07e5f-108">Gli indirizzi MAC non sono disponibili nei computer che eseguono Windows 8.</span><span class="sxs-lookup"><span data-stu-id="07e5f-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="07e5f-109">Per configurare l'URL dell'applicazione SNMP</span><span class="sxs-lookup"><span data-stu-id="07e5f-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="07e5f-110">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="07e5f-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="07e5f-111">Eseguire il cmdlet seguente per configurare l'URL per l'applicazione SNMP.</span><span class="sxs-lookup"><span data-stu-id="07e5f-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="07e5f-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07e5f-112">See also</span></span>

[<span data-ttu-id="07e5f-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="07e5f-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

