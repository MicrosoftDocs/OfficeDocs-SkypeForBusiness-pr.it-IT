---
title: Espansione delle impostazioni del trunk
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
ROBOTS: NOINDEX, NOFOLLOW
description: 'Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:'
ms.openlocfilehash: 97c1578418fdf46ad39256312d7aa15abd44ff84
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797407"
---
# <a name="trunk-settings-expander"></a><span data-ttu-id="04c61-103">Espansione delle impostazioni del trunk</span><span class="sxs-lookup"><span data-stu-id="04c61-103">Trunk Settings Expander</span></span>

<span data-ttu-id="04c61-104">Per modificare le impostazioni di un trunk SIP, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="04c61-104">To edit or modify the settings for a SIP trunk, you do the following:</span></span>

 <span data-ttu-id="04c61-105">**Nome trunk** è un campo obbligatorio che identifica in modo univoco il trunk SIP nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="04c61-105">**Trunk name** is a required entry and uniquely identifies the SIP trunk in the deployment.</span></span>

 <span data-ttu-id="04c61-106">**Gateway PSTN associato**: selezionare un gateway PSTN precedentemente definito nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="04c61-106">**Associated PSTN gateway**: Select an existing PSTN gateway that has been defined in the deployment.</span></span>

 <span data-ttu-id="04c61-p101">**Porta di attesa per gateway IP/PSTN**: indica la porta TCP/IP sulla quale il gateway attenderà le richieste. Il valore è obbligatorio e può variare a seconda del fornitore del gateway, ma l'impostazione predefinita corrisponde alla porta 5067.</span><span class="sxs-lookup"><span data-stu-id="04c61-p101">**Listening port for IP/PSTN gateway**: Indicates what TCP/IP port the gateway will be listening for requests on. The required value may differ, based on the vendor of the gateway, but the default is port 5067.</span></span>

 <span data-ttu-id="04c61-p102">**Protocollo trasporto SIP**: il protocollo usato è TCP o TLS. TLS corrisponde all'impostazione predefinita. Per determinare il protocollo supportato dal gateway in uso, vedere la documentazione del fornitore del gateway. L'impostazione predefinita TLS deve essere considerata la scelta più sicura, se il gateway supporta tale protocollo.</span><span class="sxs-lookup"><span data-stu-id="04c61-p102">**SIP Transport Protocol**: The protocol used is either TCP or TLS. TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>

 <span data-ttu-id="04c61-113">**Mediation Server associato**: selezionare un Mediation Server esistente dalla distribuzione da associare al trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="04c61-113">**Associated Mediation Server**: Select an existing Mediation Server from the deployment to associate with the SIP trunk.</span></span>

> [!NOTE]
> <span data-ttu-id="04c61-114">Solo il trunk radice può essere associato a un Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="04c61-114">Only the root trunk can be associated with a Mediation Server.</span></span>

 <span data-ttu-id="04c61-115">**Porta Mediation Server associata**: valore obbligatorio, impostato sul valore configurato per l'ascolto del server Mediation.</span><span class="sxs-lookup"><span data-stu-id="04c61-115">**Associated Mediation Server port**: A required value, this is set to the value that the Mediation Server is configured to listen on.</span></span>

![Espansione delle impostazioni del trunk](../../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="04c61-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="04c61-117">See also</span></span>

[<span data-ttu-id="04c61-118">Elenco di controllo della distribuzione SIP trunking</span><span class="sxs-lookup"><span data-stu-id="04c61-118">SIP Trunking Deployment Checklist</span></span>](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[<span data-ttu-id="04c61-119">Componenti e topologie per il trunking SIP</span><span class="sxs-lookup"><span data-stu-id="04c61-119">Components and Topologies for SIP Trunking</span></span>](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
